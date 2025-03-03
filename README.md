## Prerequisites

Before installing the project dependencies, you may need to install SWIG, `ffmpeg`, and some additional system-level packages. These are often required for building Box2D, handling video encoding, and other dependencies correctly, particularly on Windows and when working with rendering.

**Installation Instructions:**

*   **Windows:**
    1.  **SWIG:** Download the latest SWIG release from [http://www.swig.org/download.html](http://www.swig.org/download.html). Extract the `swigwin` zip file to a directory (e.g., `C:\swigwin-4.x.x`), and add that directory to your system's `PATH` environment variable.
    2.  **Visual C++ Build Tools:**  Ensure you have the Microsoft C++ Build Tools installed.  You can get these through the Visual Studio installer (select the "Desktop development with C++" workload) or by installing the "Build Tools for Visual Studio" separately.  This is essential for compiling some of the Python packages.
    3.  **ffmpeg:** Download a pre-built `ffmpeg` executable from a reputable source (e.g., [https://www.gyan.dev/ffmpeg/builds/](https://www.gyan.dev/ffmpeg/builds/) - choose a "full" or "essentials" build). Extract the `ffmpeg.exe` file (usually in a `bin` subdirectory) to a directory on your system (e.g., `C:\ffmpeg\bin`) and add this directory to your system's `PATH` environment variable.  *Alternatively*, you can use a package manager like Chocolatey: `choco install ffmpeg`.
    4. **Other dependencies**: You may need to install `cmake`.

*   **macOS (using Homebrew):**
    ```bash
    brew install swig cmake ffmpeg
    ```

*   **Linux (Debian/Ubuntu):**
    ```bash
    sudo apt-get update
    sudo apt-get install swig cmake ffmpeg libopenmpi-dev zlib1g-dev libglfw3 libglfw3-dev -y
    ```

*   **Linux (Fedora/CentOS/RHEL):**
    ```bash
    sudo yum install swig cmake ffmpeg openmpi-devel zlib-devel glfw-devel -y
    ```
*  **Using Conda**:
    ```bash
    conda install swig cmake ffmpeg -c conda-forge
    ```

Once SWIG, ffmpeg, and the necessary system dependencies are installed, you can proceed with installing the Python dependencies (described in the next section, presumably).

**Important Notes:**

*   **Rendering Dependencies:**  The `CarRacing-v3` environment uses OpenGL for rendering. The `glfw` packages provide a cross-platform way to handle OpenGL contexts.  If you encounter errors related to rendering (e.g., "failed to create GLFW window"), ensure these packages are installed. The `-y` flag automatically answers "yes" to any prompts during installation.
* **OpenMPI:** `libopenmpi-dev` (or `openmpi-devel`) is often a dependency for some scientific computing libraries.  It's included here as a precaution.
*   **CMake:** `cmake` is a build tool and also a requirement.
* **ffmpeg:** `ffmpeg` is required by `imageio` to create the MP4 videos. Make sure it's installed and accessible in your system's `PATH`.
*   **Windows Build Tools:**  The Visual C++ Build Tools are *critical* on Windows.  Without them, many Python packages with C/C++ extensions will fail to install.
* **Conda:** If you use Conda, consider creating a dedicated environment for this project: `conda create -n car-racing python=3.12 swig cmake ffmpeg -c conda-forge -y`. Then activate the environment `conda activate car-racing`. The `-c conda-forge` is added, which is often required.
