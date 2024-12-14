# CudaTemplate
A no-nonsense template on getting started quickly with a CUDA project with a CMake build system.

## So, how do I build?
Sadly, I only have access to a Linux machine, but i reckon the steps would be same on all platforms if you have CUDA Toolkit setup.

```
# 1. Make a build directory
mkdir build

# 2. Change your current working directory into it
cd build

# 3. Run CMake to configure your project
cmake .. -DCMAKE_BUILD_TYPE=Release # For release build
cmake .. -DCMAKE_BUILD_TYPE=Debug   # For debug build

# 4. Run your build!
cmake --build .
```