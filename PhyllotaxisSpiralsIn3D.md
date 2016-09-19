# Phyllotaxis Spirals in 3D

![Phyllotaxis Spirals in 3D](http://demonstrations.wolfram.com/PhyllotaxisSpiralsIn3D/HTMLImages/index.en/popup_3.jpg)

In almost all above-ground growth in plants, new sprouts come out at angles of about 137.5° relative to the previous one. But between each sprout, the main stem or trunk has grown different amounts. See the effect this has on the overall form.

---
Contributed by: [Stephen Wolfram](http://demonstrations.wolfram.com/author.html?author=Stephen%20Wolfram)

#### WOLFRAM LANGUAGE CODE
```Mathematica
Manipulate[Graphics3D[{Pink,Table[Sphere[Sqrt[i]{Sin[i (a Degree)],Cos[i (a Degree)],-pN[i+1^-10]^e},size],{i,0,n}]}, ImageSize->{450, 300},Boxed->False,PlotRange->{{-Sqrt[n]-size,Sqrt[n]+size},{-Sqrt[n]-size,Sqrt[n]+size},All}],
{{n,100,"number of elements"},1,250,Appearance->"Labeled"},{{size,1.5,"radius of each element"},0.1,3},{{a,137.5,"angle"},0,180,Appearance->"Labeled"},
{{p,0.3,"pointiness"},0,2,Appearance->"Labeled"},
{{e,0,"pointiness exponent"},0,0.65,Appearance->"Labeled"}]
```

#### RELATED LINKS
[Growth of Plants and Animals](http://www.wolframscience.com/nksonline/page-409)[(NKS|Online)](http://www.wolframscience.com/nksonline/)

#### PERMANENT CITATION

"Phyllotaxis Spirals in 3D" from the Wolfram Demonstrations Project
http://demonstrations.wolfram.com/PhyllotaxisSpiralsIn3D/
Contributed by: [Stephen Wolfram](http://demonstrations.wolfram.com/author.html?author=Stephen%20Wolfram)
