# Stained-Glass Filter from a Voronoi Mesh

![Stained-Glass Filter from a Voronoi Mesh](http://demonstrations.wolfram.com/StainedGlassFilterFromAVoronoiMesh/HTMLImages/index.en/popup_2.jpg)

This Demonstration creates a stained glass filter for photographic images. The filter is based on the polygons of a Voronoi mesh started from seeds that are points along the lines of equal density in the image.

The polygons can be further "refined" by repeatedly creating a new Voronoi mesh from the center of the polygons generated previously.

---
Contributed by: [Erik Mahieu](http://demonstrations.wolfram.com/author.html?author=Erik%20Mahieu)

#### WOLFRAM LANGUAGE CODE
```Mathematica
Manipulate[
Module[{img,colors,nearestColor,bounds,edges,seeds,vrnMesh,polygons},
SeedRandom[123456];
img=images[[i]];
colors=If[palt=="from image",Nothing,ColorData[palt,"ColorList"]];nearestColor=If[palt=="from image",Identity,Nearest[colors]];
bounds={{0,150},{0,150}};
edges=EdgeDetect[img];
seeds=RandomSample[ImageValuePositions[edges,White],m];
vrnMesh=VoronoiMesh[dither[seeds,.01],bounds];
polygons=Table[{EdgeForm[{AbsoluteThickness[athn],Black}],FaceForm[Switch[palt,"from image",RGBColor[PixelValue[img,Mean@@pol]],_,nearestColor@RGBColor[ImageValue[img,Mean@@pol]]]],pol},{pol,MeshPrimitives[Nest[VoronoiMesh[Mean@@@MeshPrimitives[#,2],bounds]&,vrnMesh,n],2]}];
Graphics[polygons,ImageSize->475]],
Style["Image",11,Bold],
{{i,3,""},Dynamic[MapIndexed[First[#2]->#&,thumbs]],PopupMenu},
"",
"color palette",
{{palt,"from image",""},Flatten[{"from image",ColorData["Named"]}]},Delimiter,
"",
Style["Voronoi polygons",11,Bold],
"",
"number of seeds",
{{m,1000,""},Range[250,2000,250],PopupMenu},
"",
"refinements",
{{n,2,""},Range[5]},
"",
"mesh thickness",
{{athn,.25,""},{0.001->"none",.125->"finest",.25->"fine",.5->"thick",1->"thickest"},PopupMenu},
SynchronousUpdating->False,
SynchronousInitialization->False,
AutorunSequencing->{3,4,5,2},
TrackedSymbols:>{i,palt,m,n,athn},
Initialization:>{(*dither a 2D array of point{x,y}coordinates*)
dither[pts_,dith_]:=pts+.25 dith RandomReal[{-1,1},{Length@pts,2}];
images=Join[ExampleData /@ {{"TestImage", "Peppers"}, {"TestImage", "Mandrill"}, {"TestImage", "Lena"},{"TestImage", "Tiffany"}}, {ImageCrop[Entity["Artwork", "MonaLisa::LeonardoDaVinci"]["Image"], {96, 96}, Bottom]}];
thumbs = ImageResize[#, 80] & /@ images}]
```
#### RELATED LINKS
[Voronoi Diagram (Wolfram MathWorld)](http://mathworld.wolfram.com/VoronoiDiagram.html)

[Voronoi Polygon (Wolfram MathWorld)](http://mathworld.wolfram.com/VoronoiPolygon.html)

#### PERMANENT CITATION
[Erik Mahieu](http://demonstrations.wolfram.com/author.html?author=Erik%20Mahieu)
"Stained-Glass Filter from a Voronoi Mesh"
http://demonstrations.wolfram.com/StainedGlassFilterFromAVoronoiMesh/
Wolfram Demonstrations Project
Published: June 6, 2016
