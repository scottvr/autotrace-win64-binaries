# autotrace-win64-binaries
pre-compiled, statically linked autotrace binaries for 64-bit Windows

I wanted to use inkscape-centerline-trace, which uses autotrace, but had nothing but fail wth 
64-bit Inkscape under Windows 7. Strangely, if I started the autotrace-w32 binary under SysWow64\cmd.exe, 
would run without visibly crashing about every third time, and create a non-zero-byte output file on about one 
out of three of those non-crashing executions. *shrug* 

I built this under MSYS2/MinGW64-6.1 against libpng v1.2.56 rather than update the autotrace code to use the 
getters and setters that modern versions of libpng implement. For your convenience, I statically linked this 
version of libpng into the autotrace binary. I haven't bothered linking against ImageMagick or Ming because I 
only needed to read a PNG, but if this binary is useful to someone other than me who wants the other formats
supported, I can make another build. 
