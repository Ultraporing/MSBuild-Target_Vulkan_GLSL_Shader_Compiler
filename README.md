# MSBuild-Target for Vulkan GLSL Shaders
Thanks to this (http://reedbeta.com/blog/custom-toolchain-with-msbuild/#example-project) article I was able to put a simple buildtarget for Visual Studio and MSBuild together. 
You can just drop *.frag and *.vert files into a shader directory, you'll need to create it your self in the root of your project where the *.vcxproj is located. 
And set your projects Build Dependency to use VulkanGLSLShaderCompiler.targets, now *.frag and *.vert files are automatically recognized by Visual Studio as VulkanGLSLShader Files and will use the new target.
All compiled shader get the .spv extension and are placed in the same shader dir.
