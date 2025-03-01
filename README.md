## Prerequisites

Before installing the project dependencies, you may need to install SWIG. This
is often required for building Box2D from source, particularly on Windows.

**Installation Instructions:**

*   **Windows:** Download the latest SWIG release from [http://www.swig.org/download.html](http://www.swig.org/download.html).  Extract the `swigwin` zip file to a directory (e.g., `C:\swigwin-4.x.x`), and add that directory to your system's `PATH` environment variable.
*   **macOS (using Homebrew):**
    ```bash
    brew install swig
    ```
*   **Linux (Debian/Ubuntu):**
    ```bash
    sudo apt-get update
    sudo apt-get install swig
    ```
*   **Linux (Fedora/CentOS/RHEL):**
    ```bash
    sudo yum install swig
    ```
*  **Using Conda**:
    ```bash
    conda install swig
    ```
Once SWIG is installed, you can proceed with installing the Python dependencies