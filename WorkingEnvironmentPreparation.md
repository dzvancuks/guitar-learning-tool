# Drivers #
## Windows specific drivers ##
  * ASIO4ALL

# Development tools #
  * QT version >= 4.8
  * IDE (i.e. NetBeans)
  * Portaudio SDK
  * Protocol Buffer (by Google)
## Windows specific tools ##
  * ASIO SDK (you can get free copy from http://www.steinberg.net/en/company/developer.html; "extended development account" must be created)
  * msys 1.0

# Tool preparation #
## QT ##
  1. Add "QT += multimedia" to .pro file. For NetBeans add it via project properties -> build -> QT -> user definitions, for both Debug and Release projects.
## Portaudio ##
  1. Get SDK from http://www.portaudio.com/download.html.
  1. Unpack && ./configure && make && make install

## ASIO ##
To use Windows ASIO, you need to configure Portaudio with driver support
  1. `./configure --with-host_os=mingw --with-winapi=asio --with-asiodir=/usr/local/asiosdk2`
  1. Copy portaudio.h into QT framework's _include_ directory
  1. Add library support: -lportaudio -L"/path/to/lib" OR libportaudiodll.a in project configuration


## Protocol Buffers ##
Windows: if by any means you have problems with protobuf (included into project code crashes runtime), read this article about proper compilation: http://stackoverflow.com/questions/13000290/generated-protobuf-code-crashes-application