# MSBuild-Target for Vulkan GLSL Shaders
Thanks to this (http://reedbeta.com/blog/custom-toolchain-with-msbuild/#example-project) article I was able to put a simple buildtarget for Visual Studio and MSBuild together. 

You can just add *.frag and *.vert files to your project. 
And set your projects Build Dependency to use VulkanGLSLShaderCompiler.targets, now *.frag and *.vert files are automatically recognized by Visual Studio as VulkanGLSLShader Files and will use the new target.

All compiled shader get the .spv extension and are placed in the same output directory as your binary files in the "shader" directory. The output directory can be changed in the .target file, look for the "BinShaderOutPath" parameter.
