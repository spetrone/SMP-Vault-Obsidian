Windows GPU: NVIDIA GeForce RTX 2080 SUPER
Windows Driver: NVIDIA CUDA 12.6.65

https://docs.nvidia.com/cuda/wsl-user-guide/index.html

he CUDA driver installed on Windows host will be stubbed inside the WSL 2 as `libcuda.so`, therefore **users must not install any NVIDIA GPU Linux driver within WSL 2**. One has to be very careful here as the default CUDA Toolkit comes packaged with a driver, and it is easy to overwrite the WSL 2 NVIDIA driver with the default installation. We recommend developers to use a separate CUDA Toolkit for WSL 2 (Ubuntu) available from the [CUDA Toolkit Downloads](https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=WSL-Ubuntu&target_version=2.0) page to avoid this overwriting.