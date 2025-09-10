![Private / Proprietary](https://img.shields.io/badge/License-Proprietary-red)

## 🎥 Subscribe to My YouTube Channel
# ⚠️ zage engine – Private Game Engine

**Copyright (c) 2025 SitizenFX (Elijah Siita / VidllQ Authority)**  

**NOTICE:** Unauthorized use, modification, distribution, or sharing of this engine, its source code, assets, or branding is strictly prohibited and may result in legal action under Zambian copyright law.

---

## Overview

Nage Engine is a **fully proprietary custom game engine** developed and maintained by DJsiita Studios.  
It is intended **exclusively for internal use** by our development team. This engine combines advanced systems, custom tools, and gameplay mechanics tailored for our projects.  

This engine is **not open-source**. Any use, redistribution, modification, or reverse engineering without explicit written permission from DJsiita Studios is strictly forbidden.

---

## Features

- **Core Engine Systems** – Fully customized rendering, physics, and scripting pipelines.  
- **Gameplay Mechanics** – Proprietary AI, animation, and game logic systems.  
- **Development Tools** – Build pipelines, configuration systems, and deployment tools for internal use only.  
- **Branding & Assets** – All logos, UI/UX elements, and engine identifiers are **protected intellectual property** of DJsiita Studios.  

---

## License

This engine is governed by the **Nage Engine – Private Game Engine License, Version 1.0 (August 24, 2025)**.  
All modifications, enhancements, and new systems created by DJsiita Studios are **proprietary and restricted**.  

- **Full license details:** See `LICENSE.txt` file  
- **Governing law:** Zambia  

---

## Disclaimer

- This engine is intended for **internal studio use only**.  
- **No individual or third party** is authorized to access, distribute, or modify this engine in any form.  
- Unauthorized use, sharing, or redistribution will be treated as a **copyright infringement**.  

---

## Contact

For inquiries regarding licensing, internal use, or collaborations, contact:

**DJsiita Studios / Elijah Siita (VidllQ Authority)**  
Email: legalvidllq@gmail.com  
Website: [your website here]

Check out my YouTube channel for videos, tutorials, and updates related to game development and Nage Engine:

[**Subscribe to VidllQ on YouTube**](https://www.youtube.com/@Mrsiita)
For the latest details and system requirements, refer to [System Requirements](https://o3de.org/docs/welcome-guide/requirements/) in the documentation.

#### Windows

*   Visual Studio 2019 16.9.2 minimum (All editions supported, including Community): [https://visualstudio.microsoft.com/downloads/](https://visualstudio.microsoft.com/downloads/)
    *   Check [System Requirements](https://o3de.org/docs/welcome-guide/requirements/) for other supported versions.
    *   Install the following workloads:
        *   Game Development with C++
        *   MSVC v142 - VS 2019 C++ x64/x86
        *   C++ 2019 redistributable update
*   CMake 3.22.0 minimum: [https://cmake.org/download/#latest](https://cmake.org/download/#latest) (Release Candidate versions are not supported)

#### Optional

*   Wwise audio SDK
    *   For the latest version requirements and setup instructions, refer to the [Wwise Audio Engine Gem](https://o3de.org/docs/user-guide/gems/reference/audio/wwise/audio-engine-wwise/) reference in the documentation.

### Quick start engine setup

To set up a project-centric source engine, complete the following steps. For other build options, refer to [Setting up O3DE from GitHub](https://o3de.org/docs/welcome-guide/setup/setup-from-github/) in the documentation.

1.  Create a writable folder to cache downloadable third-party packages. You can also use this to store other redistributable SDKs.
    
1.  Install the following redistributables:
    - Visual Studio and VC++ redistributable can be installed to any location.
    - CMake can be installed to any location, as long as it's available in the system path.

1.  Configure the engine source into a solution using this command line, replacing `<your build path>`, `<your source path>`, and `<3rdParty package path>` with the paths you've created:
    ```
    cmake -B <your build path> -S <your source path> -G "Visual Studio 16" -DLY_3RDPARTY_PATH=<3rdParty package path>
    ```
    
    Example:
    ```
    cmake -B C:\o3de\build\windows -S C:\o3de -G "Visual Studio 16" -DLY_3RDPARTY_PATH=C:\o3de-packages
    ```
    
    > Note:  Do not use trailing slashes for the <3rdParty package path>.

1.  Alternatively, you can do this through the CMake GUI:
    
    1.  Start `cmake-gui.exe`.
    1.  Select the local path of the repo under "Where is the source code".
    1.  Select a path where to build binaries under "Where to build the binaries".
    1.  Click **Add Entry** and add a cache entry for the <3rdParty package path> folder you created, using the following values:
        1.  **Name:** LY_3RDPARTY_PATH
        1.  **Type:** STRING
        1.  **Value:** `<3rdParty package path>`
    1.  Click **Configure**.
    1.  Wait for the key values to populate. Update or add any additional fields that are needed for your project.
    1.  Click **Generate**.
    
1.  Register the engine with this command:
    ```
    scripts\o3de.bat register --this-engine
    ```

1.  The configuration of the solution is complete. You are now ready to create a project and build the engine.

For more details on the steps above, refer to [Setting up O3DE from GitHub](https://o3de.org/docs/welcome-guide/setup/setup-from-github/) in the documentation.

### Setting up new projects and building the engine

1. From the O3DE repo folder, set up a new project using the `o3de create-project` command.
    ```
    scripts\o3de.bat create-project --project-path <your new project path>
    ```

1. Configure a solution for your project.
    ```
    cmake -B <your project build path> -S <your new project source path> -G "Visual Studio 16"
    ```

    Example:
    ```
    cmake -B C:\my-project\build\windows -S C:\my-project -G "Visual Studio 16"
    ```
    
    > Note:  Do not use trailing slashes for the <3rdParty cache path>.

1. Build the project, Asset Processor, and Editor to binaries by running this command inside your project:
    ```
    cmake --build <your project build path> --target <New Project Name>.GameLauncher Editor --config profile -- /m
    ```
    
    > Note: Your project name used in the build target is the same as the directory name of your project.

This will compile after some time and binaries will be available in the project build path you've specified, under `bin/profile`.

For a complete tutorial on project configuration, see [Creating Projects Using the Command Line Interface](https://o3de.org/docs/welcome-guide/create/creating-projects-using-cli/) in the documentation.

## Code Contributors

This project exists thanks to all the people who contribute. [[Contribute](CONTRIBUTING.md)].

<a href="https://github.com/o3de/o3de/graphs/contributors"><img src="https://contrib.rocks/image?repo=o3de/o3de&max=200&columns=24" width=850px /></a>

## License

For terms please see the LICENSE*.TXT files at the root of this distribution.
