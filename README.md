# CMAKE Getting

1. Sources
2. https://cmake.org/cmake/help/latest/manual/cmake-language.7.html#organization
3. https://cmake.org/cmake/help/latest/manual/cmake-buildsystem.7.html#introduction
4. https://gitlab.kitware.com/cmake/cmake



 Section I: Getting Set Up with CMake
This first section sets up your environment so you can follow the course smoothly. It covers multiple ways to install CMake (official installers, OS package managers, pip), how to confirm your version, and the basic invocation model using -S (source), -B (build), and -G (generator).

You’ll understand that CMake generates a build system (Ninja, VS/MSBuild, Xcode), which then compiles your code. The section clarifies the difference between single-config and multi-config generators and how that impacts build commands and where binaries are written. Special attention is given to Windows setup using the Developer Prompt/PowerShell so compilers are discoverable.

Finally, it points you to the official docs, cmake --help, Discourse for questions, and the Step 0 written tutorial with exercises.



How To Get CMake

Download installers/binaries or source from cmake.org.
Use package managers: winget, apt, dnf, pacman, brew.
Python option: pip install cmake.
Verify install with cmake --version.


Running CMake

Course uses command line primarily; IDEs offer rich CMake integrations too.
Important CLI flags:
-S <src>: source tree (where CMakeLists.txt lives).
-B <build>: out-of-source build directory.
-G <generator>: choose build system (Ninja, Visual Studio, Xcode, etc.).
cmake --build <build-dir> to compile using the generated build system.


CMake is a Meta Build System

It generates a build system (e.g., Ninja files, MSBuild/VS solutions, Xcode projects).
You then invoke that build system (often via cmake --build).


Single vs Multi-config Generators

Single-config (e.g., Ninja): one configuration per build tree.
Multi-config (Visual Studio, Xcode, Ninja Multi-Config): multiple configs (Debug/Release/etc.) in the same build tree.
With multi-config, specify --config <Config> on build/test/install commands and expect outputs under subfolders like build/Release/.


Windows Dev Note

Use Developer Command Prompt/PowerShell for Visual Studio so compilers and env vars are set; otherwise CMake may fail to find a C++ compiler.


Help & Docs

cmake --help is excellent.
Full reference at cmake.org; community Q&A at discourse.cmake.org.
A matching text version with exercises exists as Step 0 of the CMake tutorial.
