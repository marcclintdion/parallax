early parallax shader work.  These shaders are a mix of PowerVR, DHPOware and Irrlicht parallax shaders.  The ones that turned out the best are a mix of all three.  

The powerVR(iOS 5 SDK) shader sets the tone with it's efficency.   The other two shaders provided alternative components to boost the illusion of depth. 

Some of the example modules are broken for non-nVidia platforms.  nVidia drivers tend to automatically correct casting errors which other manufacturers do not always do.  It's likely only a small correction is neccessary.(The errors may also be FBO related.)

Everything in these GLSL shaders should work for every type of GPU going back several years for mobile devices and Intel. 
These algorithms should also work fine for all ATI/nVidia cards that were made over the past decade.  

The supporting OpenGL code should be fine for all platforms as well.



