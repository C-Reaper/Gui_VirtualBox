## Overview

This project is a simple C application designed to run on various platforms including Linux, Windows, and through WebAssembly. The primary file of interest is `src/Main.c`, which serves as the entry point for the program.

## Features

- The program is built using Makefiles tailored for different environments: Linux (`Makefile.linux`), Windows (`Makefile.windows`), Wine (`Makefile.wine`), and WebAssembly (`Makefile.web`).
- The source code includes `Main.c` and associated header files (`*.h`) located in the `src/` directory.
- Different build configurations are provided to facilitate development on various platforms.

## Project Structure

```
Gui_VirtualBox/
├── Makefile.linux
├── Makefile.windows
├── Makefile.wine
├── Makefile.web
├── README.md
└── src/
    ├── Main.c
    └── *.h
```

### Prerequisites

- **C/C++ Compiler and Debugger**: GCC or Clang for Linux, MSVC for Windows.
- **Make utility**: Required to run the build scripts.
- **Standard development tools**: Commonly installed on most Linux distributions; MSYS2/MinGW for Windows.
- **Libraries**:
  - For Linux: X11 (`libX11-dev`), PNG and JPEG libraries (`libpng-dev`, `libjpeg-dev`).
  - For Windows: User32, GDI32, Winmm libraries (part of the Windows SDK).
  - For Wine: Wine development tools.
  - For WebAssembly: Emscripten (`emcc`).

## Build & Run

### Building on Linux

To build and run the project on a Linux system:

1. Navigate to the project directory:
   ```bash
   cd Gui_VirtualBox/
   ```

2. Build the project using the provided Makefile for Linux:
   ```bash
   make -f Makefile.linux all
   ```

3. To run the executable, use:
   ```bash
   make -f Makefile.linux exe
   ```

### Building on Windows

To build and run the project on a Windows system:

1. Navigate to the project directory:
   ```bash
   cd Gui_VirtualBox/
   ```

2. Build the project using the provided Makefile for Windows:
   ```bash
   make -f Makefile.windows all
   ```

3. To run the executable, use:
   ```bash
   make -f Makefile.windows exe
   ```

### Building on Wine

To build and run the project cross-compiling to Windows using Wine:

1. Navigate to the project directory:
   ```bash
   cd Gui_VirtualBox/
   ```

2. Build the project using the provided Makefile for Wine:
   ```bash
   make -f Makefile.wine all
   ```

3. To run the executable in a Wine environment, use:
   ```bash
   make -f Makefile.wine exe
   ```

### Building WebAssembly

To build and run the project as WebAssembly:

1. Navigate to the project directory:
   ```bash
   cd Gui_VirtualBox/
   ```

2. Build the project using the provided Makefile for WebAssembly:
   ```bash
   make -f Makefile.web all
   ```

3. To serve the generated HTML file and run it in a browser, use:
   ```bash
   make -f Makefile.web exe
   ```

4. Open your web browser and navigate to `http://localhost:8080` to view the application.

### Cleaning

To clean up build artifacts:

```bash
make -f Makefile.(os) clean
```

Replace `(os)` with `linux`, `windows`, `wine`, or `web` depending on the target platform.