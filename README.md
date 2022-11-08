# MSBuild-Target for Vulkan GLSL&HLSL Shaders
Thanks to this (http://reedbeta.com/blog/custom-toolchain-with-msbuild/#example-project) article I was able to put a simple buildtarget for Visual Studio and MSBuild together. 

# USAGE GLSL & HLSL
Automatic extension recognized for GLSL like shown, for HLSL add .hlsl at the end and need to go to properties and select the Vulkan HLSL Compiler.
And make sure to set a shader_stage via ```#pragma shader_stage(<stage>)``` replace <stage> with a shader stage.
More infos on what stages to select and extensions: https://github.com/google/shaderc/tree/main/glslc#311-shader-stage-specification

You can just add shader files with the corrisponding extensions and set it up like described above. 
And set your projects Build Dependency to use VulkanGLSLShaderCompiler.targets, now GLSL files are automatically recognized by Visual Studio as Vulkan GLSL Shader Files, for HLSL please change from the autoselected ```HLSL shader``` Item Type to the ```Vulkan HLSL Shader``` type and it will use the new target.

All compiled shader get the .spv extension and are placed in the same output directory as your binary files in the "shader" directory. The output directory can be changed in the .target file, look for the "BinShaderOutPath" parameter.
