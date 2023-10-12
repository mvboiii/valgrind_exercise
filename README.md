# valgrind_exercise
 valgrind excersise for enpm808x Manav Nagda

## Standard install via command-line
```bash
# Configure the project and generate a native build system:
  # Must re-run this command whenever any CMakeLists.txt file has been changed.
  cmake -S ./ -B build/
# Compile and build the project:
  # rebuild only files that are modified since the last build
  cmake --build build/
  # or rebuild everything from scracth
  cmake --build build/ --clean-first
  # to see verbose output, do:
  cmake --build build/ --verbose
# Run program:
  ./build/app/shell-app
# Clean
  cmake --build build/ --target clean
# Clean and start over:
  rm -rf build/
```

## Extra credit

What happens when the executable is linked statically?  Does Valgrind still detect those same bugs?
Why or why not.?

Answer - 1. if the executable is linked statically, all the dependancies and the libraries required in the program are present 
            in the executable itself, no external libraries or dependancies are used here. Due to this there is no connection 
            of the code with external library or any dependancy.

        2.  yes valgrind will still detect these bugs as both the bugs are only memory leaks and valgrind can detect memory leaks 
            in both static and dynamic cases, however it won't be able to pinpoint the issue and only detect the presence of bug 
            in the file.