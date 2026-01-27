<img width="1394" height="997" alt="Screenshot 2026-01-02 182311" src="https://github.com/user-attachments/assets/5de4e3d7-b660-4ea4-a513-aca077b695cf" />

<br>

# C++

### Install

- **CMake** 3.15 or later - (https://cmake.org/download/)
- **C++ Compiler** with C++17 support - [MinGW-w64](https://www.mingw-w64.org/downloads/)
- **SFML 2.5** or later - [Download](https://www.sfml-dev.org/download.php)
  - Extract to a location (e.g. , `C:/SFML`)
- **OpenGL** support (usually included with graphics driver)

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
- **Phenomenon**: Over 1000,000 cubes sold in the 1st 2 years.

<br>

# Structure

```
.
├── CMakeLists.txt          # Build configuration                 (Backend)  (Config)
├── .gitignore              # Git ignore file                     (Config)
├── rubik_cube.h            # Rubik's cube logic header           (Backend)  (Source /  Header)
├── rubik_cube.cpp          # Rubik's cube logic and rotation     (Backend)  (Source /  Library)
├── renderer.h              # 3D OpenGL rendering system header   (Frontend) (Source /  Header)
├── renderer.cpp            # 3D OpenGL rendering implementation  (Frontend) (Source /  Library)
├── main.cpp                # Main application and SFML GUI       (Frontend) (Source /  Script)
├── copy_dlls.ps1           # PowerShell script to copy SFML DLLs (Config)
└── README.md               # This file
```
