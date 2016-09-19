# Radius and Temperature of Main Sequence Stars

![Radius and Temperature of Main Sequence Stars](http://demonstrations.wolfram.com/RadiusAndTemperatureOfMainSequenceStars/HTMLImages/index.en/popup_2.jpg)

Stars constantly struggle to balance gravity and pressure throughout their lives. Main sequence stars fuse hydrogen in their cores in order to maintain this balance. For a main sequence star with a chemical composition similar to the Sun, the relationship between radius and effective surface temperature (in Kelvin) can be modeled fairly easily.

This Demonstration presents this simple case by imagining that the various spectral classes of stars, OBAFGKM, are laid out on a shiny table next to each other for comparison. If you change the temperature of a star, its color and radius (measured in terms of the Sun's radius, ![R](http://demonstrations.wolfram.com/RadiusAndTemperatureOfMainSequenceStars/HTMLImages/index.en/1.gif)) also change. The hottest stars, the O and B stars, are always blue. At the other end of the spectral class range, the color changes become more evident.

---
Contributed by: [Jeff Bryant](http://demonstrations.wolfram.com/author.html?author=Jeff%20Bryant)

#### WOLFRAM LANGUAGE CODE
```Mathematica
Manipulate[
Module[{
r1=ClassVRadius[t1],
r2=ClassVRadius[t2],
r3=ClassVRadius[t3],
r4=ClassVRadius[t4],
r5=ClassVRadius[t5],
r6=ClassVRadius[t6],
r7=ClassVRadius[t7]},
Graphics3D[{
{ColorData["BlackBodySpectrum"][t1],Sphere[{0,0,r1},r1],Sphere[{0,0,-r1},r1]},{ColorData["BlackBodySpectrum"][t2],Sphere[{-r1-r2,0,r2},r2],Sphere[{-r1-r2,0,-r2},r2]},{ColorData["BlackBodySpectrum"][t3],Sphere[{-r1-2r2-r3,0,r3},r3],Sphere[{-r1-2r2-r3,0,-r3},r3]},{ColorData["BlackBodySpectrum"][t4],Sphere[{-r1-2r2-2r3-r4,0,r4},r4],Sphere[{-r1-2r2-2r3-r4,0,-r4},r4]},{ColorData["BlackBodySpectrum"][t5],Sphere[{-r1-2r2-2r3-2r4-r5,0,r5},r5],Sphere[{-r1-2r2-2r3-2r4-r5,0,-r5},r5]},{ColorData["BlackBodySpectrum"][t6],Sphere[{-r1-2r2-2r3-2r4-2r5-r6,0,r6},r6],Sphere[{-r1-2r2-2r3-2r4-2r5-r6,0,-r6},r6]},{ColorData["BlackBodySpectrum"][t7],Sphere[{-r1-2r2-2r3-2r4-2r5-2r6-r7,0,r7},r7],Sphere[{-r1-2r2-2r3-2r4-2r5-2r6-r7,0,-r7},r7]},Black,Specularity[White,128],Opacity[.5],EdgeForm[GrayLevel[.2]],
Polygon[{{-100,-100,0},{-100,100,0},{100,100,0},{100,-100,0}}],
Opacity[1],
Polygon[{{-100,-100,-r1-.1},{-100,100,-r1-.1},{100,100,-r1-.1},{100,-100,-r1-.1}}],
Polygon[{{-r1-2r2-2r3-2r4-2r5-2r6-2r7,-r1,-r1-.1},{-r1-2r2-2r3-2r4-2r5-2r6-2r7,r1,-r1-.1},{r1,r1,-r1-.1},{r1,-r1,-r1-.1}}],
Polygon[{{-r1-2r2-2r3-2r4-2r5-2r6-2r7,r1,0},{r1,r1,0},{r1,r1,-r1-.1},{-r1-2r2-2r3-2r4-2r5-2r6-2r7,r1,-r1-.1}}],
Polygon[{{-r1-2r2-2r3-2r4-2r5-2r6-2r7,-r1,0},{r1,-r1,0},{r1,-r1,-r1-.1},{-r1-2r2-2r3-2r4-2r5-2r6-2r7,-r1,-r1-.1}}],
Polygon[{{-r1-2r2-2r3-2r4-2r5-2r6-2r7,-r1,0},{-r1-2r2-2r3-2r4-2r5-2r6-2r7,-r1,-r1-.1},{-r1-2r2-2r3-2r4-2r5-2r6-2r7,r1,-r1-.1},{-r1-2r2-2r3-2r4-2r5-2r6-2r7,r1,0}}],
Polygon[{{r1,-r1,0},{r1,-r1,-r1-.1},{r1,r1,-r1-.1},{r1,r1,0}}]},
Epilog->{White,
Text[
Column[{
Row[{"Star radii in ",Subscript["R","\[CircleDot]"]}],
Row[{"O  ",ToString[NumberForm[r1,{4,2}]]}],
Row[{"B  ",ToString[NumberForm[r2,{4,2}]]}],
Row[{"A  ",ToString[NumberForm[r3,{4,2}]]}],
Row[{"F  ",ToString[NumberForm[r4,{4,2}]]}],
Row[{"G  ",ToString[NumberForm[r5,{4,2}]]}],
Row[{"K  ",ToString[NumberForm[r6,{4,2}]]}],
Row[{"M  ",ToString[NumberForm[r7,{4,2}]]}]
},Center],ImageScaled[{.8,.8}],{-1,0}]},
PlotRange->{{-r1-2r2-2r3-2r4-2r5-2r6-2r7,r1},{-r1,r1},{-r1-.1,2r1}},ViewPoint->{0,2,1},ViewAngle->\[Pi]/(7+30zoom),ViewCenter->{.5(1-zoom),.9 zoom,.5},Lighting->{{"Ambient",GrayLevel[.4]},{"Directional",White,ImageScaled[{0,0,1}]}},Background->Black,ImageSize->{400,375},Boxed->False,Method->{"SpherePoints"->ControlActive[10,Automatic]}]],
Style["temperature for star type:",Bold],
"",
{{t1,40000,"O"},30000,42000,1,Appearance->"Labeled",ImageSize->Tiny},
{{t2,20000,"B"},10000,30000,1,Appearance->"Labeled",ImageSize->Tiny},
{{t3,9000,"A"},7500,10000,1,Appearance->"Labeled",ImageSize->Tiny},
{{t4,6500,"F"},6000,7500,1,Appearance->"Labeled",ImageSize->Tiny},
{{t5,5500,"G"},5000,6000,1,Appearance->"Labeled",ImageSize->Tiny},
{{t6,4000,"K"},3500,5000,1,Appearance->"Labeled",ImageSize->Tiny},
{{t7,3170,"M"},3170,3500,1,Appearance->"Labeled",ImageSize->Tiny},
Delimiter,
{{zoom,0,"pan and zoom"},0,.9,ImageSize->Tiny},
AutorunSequencing->{1,3,{8,15}},
Initialization:>(
temperatureV={42000,30000,15200,11400,9790,8180,7300,6650,5940,5560,5150,4410,3840,3520,3170};radiusV={12,7.4,3.9,3.0,2.4,1.7,1.5,1.3,1.1,.92,.85,.72,.6,.5,.27};
classVint=Interpolation[Transpose[N@{temperatureV,radiusV}]];
ClassVRadius[temp_]:=If[temp>42000||temp<3170,0,classVint[temp]]
),
PreserveImageOptions->Automatic]
```
#### DETAILS
The relationship shown in this Demonstration is based on data from A. N. Cox, ed., Allen's Astrophysical Quantities, 4th ed., New York: AIP Press (Springer), 2000.

#### RELATED LINKS
[Blackbody (ScienceWorld)](http://mathworld.wolfram.com/Blackbody.html)

[Main Sequence (ScienceWorld)](http://mathworld.wolfram.com/MainSequence.html)

[Star (ScienceWorld)](http://mathworld.wolfram.com/Star.html)

#### PERMANENT CITATION
[Jeff Bryant](http://demonstrations.wolfram.com/author.html?author=Jeff%20Bryant)
"Radius and Temperature of Main Sequence Stars"
http://demonstrations.wolfram.com/RadiusAndTemperatureOfMainSequenceStars/
Wolfram Demonstrations Project
Published: January 24, 2008
