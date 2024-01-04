V1:

NOTE: If you don't need Caustics enabled for anything else, you should disable them. It will reduce render times and noise but the fake eye caustics are using alpha/transparency instead.

NOTE 2: Forgot to mention it only works with Cycles. If anyone knows how to make it work with Eevee let me know.

Fake Eye caustics shader. The example file shows how to add it to a material. I am separating a mesh over the sclera and the cornea with a texture, but you can directly add the "FakeEyeCaustics" node group on the cornea. 

The ray control is there to remove noise (if disabled) but it hides the light from reflecting with diffuse and glossy rays. Keep it enabled unless you want it hidden.

Unfortunately I used a map range node so control from a node group is hard to achieve, but I managed to add a slider for enabling/disabling the light, which can be used to dim it and I also added a slider to multiply it's strength. If you want even more control you will need to edit the map range node inside the node group.

If you want to use a normal map for whatever reason you can add a new group input and plug it into the Layer Weight node.

In my testing I needed to increase the max values of the map range quite a lot to make it properly noticeable. That said, I am happy with this and unless someone suggests some changes or reports a solvable issue I will not be updating this further.

V1 is pretty much completely different from the old beta version I uploaded 2 months ago so the change log is "everything"

You're free to use this however you want. Credit is appreciated and if you wanna support me there's a Patreon link in my profile.

---------------------------------------
Old beta version (can be downloaded from the "beta-old" branch):

# Blender-Fake-Caustics-for-eyes
Quick, mostly realtime, fake caustics for Genesis 8.1 models originally but can be used in theory on any cornea shader. It's not accurate but can be modified. Unfinished as of writing this. It needs accessibility.

How to use:
For custom characters:
Download "EyeCaustics.blend"
If you don't use a Genesis 8.1 model and you have a properly modeled eye, just add the "EyeCaustics" node group after your cornea's Principled BSDF.

For Genesis 8.1/8 characters:
Download "EyeCausticsGenesis8.blend"
The blend file contains a material for Genesis 8/8.1. You need to merge the cornea and eye moisture material in 1, then separate them with a mask input in "EyeCausticsShader". It needs to be a black and white texture, can be 512x512 probably even lower. It needs to have blurry edges. The cornea needs to be white. The white area on the texture will cast caustics, the black area will have the shader from the " Original Moisture Texture" area and they will blend nicely. At least as nicely as you make your mask. The black area will cast no shadows.


If you have any ideas for improvement let me know by committing an issue or something. If you are unsure and wanna discuss it beforehand add me on Discord, my username should be "calibrator". I dunno how it works anymore.

NOTE: I forgot to mention that Refraction caustics should be disabled in render properties unless they are absolutely required for something else. For this shader they are not needed and can only introduce noise.
