# Blender-Fake-Caustics-for-eyes
Quick, mostly realtime, fake caustics for Genesis 8.1 models originally but can be used in theory on any cornea shader. It's not accurate but can be modified. Unfinished as of writing this. It needs accessibility.

To use this, download the "EyeCaustics" Blend file and append the material in your scene. 

For Genesis 8.1/8 characters:
The original blend file contains a material for Genesis 8/8.1. You need to merge the cornea and eye moisture material in 1, then separate them with a mask input in "EyeCausticsShader". It needs to be a black and white texture, can be 512x512 probably even lower. It needs to have blurry edges. The cornea needs to be white. The white area on the texture will cast caustics, the black area will have the shader from the " Original Moisture Texture" area and they will blend nicely. At least as nicely as you make your mask. The black area will cast no shadows.

For any other characters:
If you don't use a Genesis 8.1 model and you have a properly modeled eye, just add the "EyeCaustics" node group after your cornea's Principled BSDF.


If you have any ideas for improvement let me know by committing an issue or something. If you are unsure and wanna discuss it beforehand add me on Discord, my username should be "calibrator". I dunno how it works anymore.

NOTE: I forgot to mention that Refraction caustics should be disabled in render properties unless they are absolutely required for something else. For this shader they are not needed and can only introduce noise.