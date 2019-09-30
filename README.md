Xilinx MALI repo for EGL / OpenGLES binaries and headers
=======
By downloading this repository you are agreeing upon the EULA agreement 
(please refer EULA).This repository provides OpenGLES implementation for ARM
Mali400 platform.

Directory structure
=======
The directory structure is organized as below:
```
|-- top
    |-- release_c (ex, r9p0-01rel0)
        |-- glesHeaders (ex, EGL/GLES2... headers)
        |-- aarch_a     (ex, aarch64)
        |-- aarch_b     (ex, arm32)
            |-- common     
            |-- platform_a (ex, fbdev)
            |-- platform_b (ex, x11)
            |-- platform_c (ex, wayland)
            |-- platform_d (ex, headless)
                |-- libraries
```

Mali userspace support for EGL/GLES2 are shipped as a monolithic library,
the libraries in common directory are dummy which should be linked to the
right backend/platform. For example, run "ln -sf fbdev/libMali.so.9.0
common/libMali.so.9.0", this should create symbolic links to desired backend.

Whenever there's a new release, a new release directory is created with directories
for available platforms.
