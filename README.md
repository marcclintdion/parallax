# parallax
various mix of simple parallax shaders, the most effective ones are a mix of three open source algorithm components.

Alphabetically, the first half dozen are really quite nice and efficient so far as the shaders go.  
I'm avoiding this for models with curvature since the method uses tangents and crossTangents 
to calculate the texture coodinate offset.  This exceeds the 32bit stride for the model's vertex array.  
Once we exceed 32bit's of data per vertex, we cause a bandwidth jump to the next power of two, in this case the model
would become 64bit but it wouldn't become more precise, just more bulky with information.
This creates GPU memory cache misses since model data now takes up twice as much memory space.(memory becomes less effective.)

For shaders like this, models with curvature tend to have the most vertices and are inefficient.  There is also
little benefit if the high-poly model is also relatively small in regards to pixel screen space.  

This type of parallax effect creates the most noticable displacement effect when used with height maps 
that have detail that is approximately 1cm squared.  (That number is subject to screen size andscreen pixel density).  

NOTE TO SELF: Look for a spectrum to identify the impact of a particular algorithm as a function of detail frequency.
ie: tiles stones in a scene where each individual rock appears to take up about 1cm of screen 
real-estate should work fine for these algoritms.  
The illusion of height that is created is noticable for such a compact algorithm.  

The foundation of these shaders was the PowerVR SDK example from the 4th generation iPodTouch/iPhones.  
The parallax effect was barely noticable, howver the shader was very compact and easy to read and modify.

Algorithm components were integrated into the PowerVR shader as replacements for some of the weaker math.

The DHPOware website has a parallax example and there is some shader code posted somewhere on an Irllicht game engine 
documentation forums/docs.

The resulting shaders(the ones that turned out to be most effective) are a blend of all three source code examples

At higher frequencies, these shaders give little apparent depth correction, 
however, they do tend to give a nice correction for normal maps around the curvature of the model.  The normal
show less lighting distortion towards lower dot-product values(towards the model's silouette)

For effects that give a much more low-frequency and deep illusion of depth, see the cone-step mapping example folder.
Those are all mostly based on Jonathan Dummer's work that he published in 2006.  His work was the basis for a 
chapter in GPU Gems which expands upon the techniques published by Jonathan.



