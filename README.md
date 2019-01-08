UPDATE: jnweiger has updated autotrace to build windows packages now. You can get them from https://github.com/autotrace/autotrace/releases

The binary there does not support png and is dynamically linked to several other DLLs, where this build is statically  linked with PNG support. That, coupled with the fact that much existing documentation points people here, I've gone ahead and built a binary from the latest 0.40.0 source. You should probably go for the official build so that he can have more Windows testers and thus stronger support, but here this is so that until new documentation around the official build displaces the old stuff pointing here, those instructions still work. 

# autotrace-win64-binaries
pre-compiled, statically linked autotrace (0.40.0) binaries for 64-bit Windows

I wanted to use inkscape-centerline-trace, which uses autotrace, but had nothing but fail wth 
64-bit Inkscape under Windows 7. Strangely, if I started the autotrace-w32 binary under SysWow64\cmd.exe, 
would run without visibly crashing about every third time, and create a non-zero-byte output file on about one 
out of three of those non-crashing executions. *shrug* 

I built this under MSYS2/MinGW64-6.1 against libpng v1.2.56 rather than update the autotrace code to use the 
getters and setters that modern versions of libpng implement. For your convenience, I statically linked this 
version of libpng into the autotrace binary. I haven't bothered linking against ImageMagick or Ming because I 
only needed to read a PNG, but if this binary is useful to someone other than me who wants the other formats
supported, I can make another build. 

USAGE:Copy the .exe into the extensions folder where the python extension resides. That's it.. The ceterline autotrace function should start working.
