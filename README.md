# vscode-cpp-template
Template for making C++ apps from scratch

# Overview

The directory structure is the following:
<ul>
  <li><em><b>.vscode</b></em> (contains instructions for Visual Studio Code to compile your code and give you real time suggestions when coding)</li>
  <li><em><b>build</b></em> (will contain the built executable file .exe)</li>
  <li><em><b>dependencies</b></em> (will contain dependencies which are header files and libraries)</li>
    <ul>
      <li><em><b>include</b></em> (contains the header files)</li>
      <li><em><b>lib</b></em> (contains libraries)</lib>
    </ul>
  <li><em><b>source</b></em> (contains your source code, in this example the main.cpp file is provided)</li>
</ul>

## The <em>tasks.json</em> file

The <em>tasks.json</em> file contains a series of command line instructions that Visual Studio Code will automatically run when using the default build task.
If you need to add libraries to your project you need to define them as arguments at the end of your arguments list. 
For example if you want to include a static library (.lib or .a) you need to first add the library file in your <em>lib</em> folder, then add the argument at the end of
the <em>tasks.json</em> file like so:<br>
```
...
"args": [
    "-o",
    "./build/app.exe",
    "-I./dependencies/include",
    "-L./dependencies/lib",
    "./source/main.cpp",
    "-lglfw3",
],
...
```

## The <em>c_cpp_properties.json</em> file

This file is used by Visual Studio Code to assist you while writing the code. <b>Make sure to set the right compiler path.</b>
```
...
"compilerPath": "C:\\Program Files\\mingw-w64\\x86_64-8.1.0-posix-seh-rt_v6-rev0\\mingw64\\bin\\gcc.exe",
...
```
