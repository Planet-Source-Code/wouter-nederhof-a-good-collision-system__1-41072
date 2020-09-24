<div align="center">

## A good collision system


</div>

### Description

My article learns you how to make a good collision engine (d3drm). I hope this will help you to make a good game.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Wouter Nederhof](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/wouter-nederhof.md)
**Level**          |Advanced
**User Rating**    |4.0 (12 globes from 3 users)
**Compatibility**  |VB 5\.0, VB 6\.0
**Category**       |[DirectX](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/directx__1-44.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/wouter-nederhof-a-good-collision-system__1-41072/archive/master.zip)





### Source Code

<B>D3DRM Colission engine in VB 5+<br>'Written by: Wouter Nederhof.<br>'Please note: This article is for advanced users. I am verrry sorry for my poor english :(</b><br><br>'How does a colission system works? That is a question many programmers want to know. Well I hope the answer is here.<br>'I found out how it works, because I was playing on my N64 and felt down some grass. A colission that searches for his collision in a .x file system is very handy, because all you have to do is what you always have to do. Export a .3ds to a .x. A collision engine is very handy, because you don't have to make a special map editor to make a map for your games, no now you can do it in every 3D editor that can export .x or .3ds!!!<br>'<br>'How it works.<br>'So as you can see below, these 3 things are vertexes.<br>' .<br>' / \<br>' / \<br>'.-----.<br>'A vertex is a point to point way to create object.<br>' <br>'(at least) 3 vertexes mean 1 polygon. A vertex is 3D too, because it has a X, an Y and a Z.<br>'You know what a wireframe is? If you look at the lines that go like this for example:<br>'---.<br>' \<br>' \.--------<br>'Then the dots are the vertexes.<br>'Now, about my engine. It works with vertexes too.<br>'It's a DirectX 7 D3D engine.<br>'You see the picture above? it's kinda a very bad example. But that's because I don't know how to add a picture. Well for a better example, try downloading a 3D editor and load a model into it. Then check in wireframe to the points I mean or to the corners. Whatever editor you've got... (WHATEVER!!)<br>'Now, my engine tests if a object hits a vertex of another object.<br>'It tests all vertexes of 1 object, the most impornantest object, for example: if you've got a camera and a enviroment, the enviroment will be tested. Testing both, make your program go slow.<br>'But, to test a eviroment, there must be at least 1 vertex in a meter, if you set the distance.x to 1 or the distance.y to 1 or the distance.z (if you know what I mean). Because if it doesn't hit a vertex, the position won't be restored, so if you make a engine, you'll fall automaticly down until you hit a vertex, you'll fall down till you end your engine. That's why we make 1 mesh for the graphics, it doesn't matter how much vertexes we use, and we make a second, the collision mesh. All you have to do with the normal mesh is add more vertexes and give it another name. You now think, why not use 1 mesh for GFX and collision. Well, you could but you could make secret area's if you make a game by removing a piece of a wall in the collision one. And with 2 of those many poly's meshes, it'll drasticly bring down your speed. The collision mesh won't be painted. It doesn't even need an object to add a mesh to. Only the one for the GFX, yes he needs both. A object (Direct3DRMFrame3) and a mesh (Direct3DRMMeshBuilder3).<br>'So I mean something like this:<br>'Dim meshGFX As Direct3DRMMeshBuilder3<br>'Dim meshCollision As Direct3DRMMeshBuilder3<br>'Dim objGFX As Direct3DRMFrame3<br>'So first DIM the 2 meshes, and one object.<br>'The code for testing if a object hits a vertex of another object, looks like this.<br>'Private sub coltest(oldpos as D3DVECTOR)		'Dim the oldpos for restoring the object's position.<br>' Dim coltest As Single				'Number of vertex<br>' Dim mapcol As D3DVECTOR			'The variable for getting the coordinates of the vertex<br>' For coltest = 0 To {MESH1}(1).GetVertexCount - 1 'Make a loop to test all vertexes.<br>' {MESH1}(1).GetVertex coltest, mapcol		'Get the coordinates of the vertex(coltest)<br>' If mapcol.x + 1 > campos.x Then			'Check if in sight, (x+1 etc is the max distance between a vertex and the object)<br>' If mapcol.x - 1 < campos.x Then<br>' If mapcol.y + 0.4 > campos.y Then<br>' If mapcol.y - 0.4 < campos.y Then<br>' If mapcol.z + 1 > campos.z Then<br>' If mapcol.z - 1 < campos.z Then<br>' {OBJ1}.SetPosition scene, oldpos.x, oldpos.y, oldpos.z 'If insight, restore position<br>' End If						'Yeah, yeah endif already<br>' End If<br>' End If<br>' End If<br>' End If<br>' End If<br>'End sub						'That's all :)<br>'I guess you can put this code in every VB-D3DRM engine you want, if only you change the {} names.<br>'If you think: this sux, this rulez, I don't get it, thank you for making this or whatever, email me or add me to my msn: woutezz@hotmail.com.<br>'Sorry, my english sux.<br>'Thx and Copyright(C)Wouter Nederhof.<br>'<B>Remember:</B> To copy the source code of the collision engine, remove the '-s first, I did this because PlanetSourceCode.com removed my spaces. :(

