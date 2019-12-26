# Call Of Duty Emblem Specs
Formats and specifications of Call Of Duty Emblems and other User Generated Content
I'm currently working on a universal emblem editor but until it is clean enough for release I will leave this repo up.
I currently only have access to Black Ops II, III and IIII for PC so if someone would like to help me w/ other CODS that would be a huge help.

# Black Ops II
**EmblemID**(UInt16), **Red**(float32), **Green**(float32), **Blue**(float32), **Alpha**(float32), **PosX**(float32), **PosY**(float32), **ScaleX**(float32), **ScaleY**(float32), **Rotation**(float32)[Degrees], **Outlined**(byte)[Bool], **Flipped**(byte)[Bool], **Padding**(2 Bytes)
* True Scale is equal to 2^ScaleVal and to convert back (e.g. you have the value 50% or 0.5) use log2(S)
* Position is equal to the % of the screen away from the center 
  - e.g. if the center of the emblem was placed on the right edge of the viewing window PosX is 1.0 and on the left edge -1.0
  - Values can be more than +-100%
* There can be 32 layers. One layer has 44 bytes and an entire emblem has 1408 bytes.
  
 # Black Ops III
 **Material**(UInt16), **Red_1**(float32), **Green_1**(float32), **Blue_1**(float32), **Alpha_1**(float32), **Red_2**(float32), **Green_2**(float32), **Blue_2**(float32), **Alpha_2**(float32), **Radial_Gradient**(UInt16)[Bool], **Gradient_Rotation**(float32)[Degrees], **Gradient_Pos**(float32), **PosX**(float32), **PosY**(float32), **ScaleX**(float32), **ScaleY**(float32), **Rotation**(float32), **UNKNOWN**(UInt16), **UNKNOWN**(UInt16), **Material_ScaleX**(float32), **Material_ScaleY**(float32), **Material_Rotation**(float32)[Degrees], **Outlined**(byte)[Bool], **Flipped**(byte)[Bool], **UNKNOWN**(byte), **UNKNOWN**(byte), **EmblemID**(UInt8), **END_LAYER**(UInt8)
 * I just started working on BO3 the same day as I am writing this so I haven't figured out the pos and scale algorithms as well as a few unknown values which seem to me like padding
 * There are two colors in BO3 so that you can do gradients. Having 2 different colors automatically enables the gradient mode
 * The boolean value for Radial Gradient Mode takes up 4 entire bytes for some reason
 * Every layer ends with FF00
 * There can be 64 layers. One layer has 96 bytes and an entire emblem has 6144 bytes.
