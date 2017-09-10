# CMake Diaries

## More Verbose NMake

On Windows using NMake even if you set the CMAKE_VERBOSE_MAKEFILE option to ON you will still see lines like:

```
C:\PROGRA~1\MICROS~1.0\VC\bin\cl.exe  @C:\Users\...\AppData\Local\Temp\nm1362.tmp
```

The reason is NMake have limitation on the length of command strings to 8,191 bytes. So that CMake tackles this problem by writing the arguments to a file and then passes this file to NMake with @filepath syntax.

But if you still want to be able to see the actual commands, you can deactivate this feature by uncommenting the lines on "Windows.cmake" file that sets CMAKE_START_TEMP_FILE and CMAKE_END_TEMP_FILE to empty strings. This file is located in "CMake/share/Modules/Platform" folder.

References: 
- https://cmake.org/Wiki/CMake_FAQ#Is_there_an_option_to_produce_more_.27verbose.27_compiling.3F
- https://stackoverflow.com/questions/23560590/verbose-nmake-makefiles-using-cmake