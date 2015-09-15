early parallax shader work.  These shaders are a mix of PowerVR, DHPOware and Irrlicht parallax shaders.  The ones that turned out the best are a mix of all three.  

The powerVR(iOS 5 SDK) shader sets the tone with it's efficency.   The other two shaders provided alternative components to boost the illusion of depth. 

NOTE TO SELF: design a frequency spectrum plotting method for the efficacy of shaders like this at various levels of detail.  This class of shader has low visual impact and low processing overhead and works best at smaller details.  (Approximately 1cm of pixel screenspace or less when viewed on a 22.5 inch mid-2011 HD screen.)
ie:Cone-Step Mapping tends to be more effective for super low frequency detail. 

as an analogy, if cone-step mapping were compared to infrared wavelengths and normal maps were closer to the upper  frequencies of blue-light then these parallax shaders would be most effective in the early blue spectrum as a depth illusion; 
towards the higher blues, these parallax shaders are more useful for correcting the apparent stretching of normal-maps as they approach the silhouette of the model.

Some of the example modules are broken for non-nVidia platforms.  nVidia drivers tend to automatically correct casting errors which other manufacturers do not always do.  It's likely only a small correction is neccessary.(The errors may also be FBO related.)

Everything in these GLSL shaders should work for every type of GPU going back several years for mobile devices and Intel. 
These algorithms should also work fine for all ATI/nVidia cards that were made over the past decade.  

The supporting OpenGL code should be fine for all platforms as well.



