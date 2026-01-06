<img width="1394" height="997" alt="Screenshot 2026-01-02 182311" src="https://github.com/user-attachments/assets/5de4e3d7-b660-4ea4-a513-aca077b695cf" />

<br>

# Prerequisites

### Install

- **CMake** 3.15 or later - (https://cmake.org/download/)
- **C++ Compiler** with C++17 support - [MinGW-w64](https://www.mingw-w64.org/downloads/)
- **SFML 2.5** or later - [Download](https://www.sfml-dev.org/download.php)
  - Extract to a location (e.g., `C:/SFML`)
- **OpenGL** support (usually included with graphics drivers)

### Build

1. Configure and build:
   ```bash
   mkdir build
   cd build
   cmake .. -DSFML_ROOT=C:/SFML
   cmake --build . --config Release
   ```

2. Copy SFML DLLs:
   ```powershell
   Copy-Item C:\SFML\bin\sfml-*.dll .\Release\
   ```

### Run

```bash
.\Release\RubikGame.exe
```

### Edit

```bash
cmake --build . --config Release
.\Release\RubikGame.exe
```

<br>

# Victory

Rotating faces until all 6 sides have same color.

<br>

# History

### Invention (1974)
- **Ernő Rubik**: Hungarian sculptor & professor of architecture invented the cube in 1974.
- **Original Purpose**: Created as a teaching tool to help students understand 3D spatial relationships.
- **First Name**: Originally called the "Magic Cube" (Bűvös kocka in Hungarian).
- **Patent**: Rubik applied for a Hungarian patent in 1975.

### Modern (1980s-Present)
- **International Release**: Licensed to Ideal Toy Corp. in 1980, renamed "Rubik's Cube".
- **Worldwide Phenomenon**: Over 100 million cubes sold in the first two years.
- **Algorithms**: Development of advanced solving methods (CFOP, Roux, ZZ, Petrus).
- **Digital Versions**: Transition to computer simulations and virtual reality implementations.

### Logos

- **Permutations**: The cube has 43,252,003,274,489,856,000 (43 quintillion) possible configurations.
- **God's Number**: Proven in 2010 that any scrambled cube can be solved in 20 moves or fewer.

<br>

# Arch

```
.
├── CMakeLists.txt # Build configuration
├── main.cpp # Main application and SFML GUI
├── rubik_cube.h # Rubik's cube logic header
├── rubik_cube.cpp # Rubik's cube logic and rotation mechanics
├── renderer.h # 3D OpenGL rendering system header
├── renderer.cpp # 3D OpenGL rendering system implementation
├── copy_dlls.ps1 # PowerShell script to copy SFML DLLs
├── .gitignore # Git ignore file
└── README.md # This file
```

# Files Needed for Build and Run

## Source Files (Required for Build)
- `CMakeLists.txt` - Build configuration
- `main.cpp` - Main application entry point
- `rubik_cube.cpp` / `rubik_cube.h` - Rubik's cube logic and rotation mechanics
- `renderer.cpp` / `renderer.h` - 3D OpenGL rendering system

## External Dependencies (Required for Build)
- **SFML 2.5+** installed at `C:/SFML` (or path specified via `-DSFML_ROOT`)
  - Headers: `C:/SFML/include/`
  - Libraries: `C:/SFML/lib/` (e.g., `sfml-graphics.lib`, `sfml-window.lib`, `sfml-system.lib`)
- **CMake** 3.15 or later
- **C++17 compiler** (e.g., MinGW-w64)
- **OpenGL** support (usually included with graphics drivers)

## Runtime Files (Required to Run)
- `build/Release/RubikGame.exe` - Built executable
- **SFML DLLs** in `build/Release/` directory:
  - `sfml-graphics-2.dll` (or `sfml-graphics-d-2.dll` for Debug)
  - `sfml-window-2.dll` (or `sfml-window-d-2.dll` for Debug)
  - `sfml-system-2.dll` (or `sfml-system-d-2.dll` for Debug)
  - `sfml-audio-2.dll` (if audio features are used)
  - `sfml-network-2.dll` (if networking features are used)
