# Bildertisch

Bildertisch (drawCanvas.exe) is a tool written out of the need for a simple tool, that yet did not exist on the net

When working with photo images I often work with combinations of 3,4 or many pictures. Look up the gallery hangings of Wolfgang Tillmanns, Anders Petersen or Michael Schmid to get an impression, how the combination of image can be used in an artistic way.

Instead of using GIMP or any image manipulation programm I wrote my own app... since I did not find any app on the net that was able to fullfil my needs for a simple, intuitive tool.

So, without any documentation, Bildertisch is a bit unfinished, though the code is in productive use since 2017. It's win32 only, as some of the packages are precompiled binaries and rely on win only dlls. Sorry, but it runs fine under WINE!

## Minimal Documentation:
###  Installation
drawCanvas.exe is a standalone win32 application, so make a suitable subdirectory anywhere you like and drop drawCanvas.exe into. 

###  Technical specs
drawCanvas.exe depends on jpeg62.dll (or it cousin jpegturbo), but thats within the file and gets extracted to ./ when you start drawCanavas.exe the first time.
drawCanvas.exe is a TCL-Starkit, the app is written mostly in TCL (http://www.tcl.tk and http://wiki.tcl.tk for more info), but as it is working with images it has to rely on some binary extensions, namely the Img extension, blt/rpc for resize operations and so on.
I added some compiled c-code to leverage jpegs ability to partly decode images, speeding up the loading process.
Source code, kit-file and precompiled exe are all downloadable from https://github.com/MichaelMiR01/bildertisch

###  Introduction
Introduction: what Bildertisch (Image-table) is (and what it is not)
Bildertisch was written solely to build image combinations (tableau). Therefore it has no fancy image editing whatsoever. No brightness, contrast, anything! You have to finalize your images beforehand, select them down and reexport from your favorite image editing/image organisation app. Btw, I myself use good old Picasa for that...
It's analog origin is a real table (every house should have one), where we are moving images to form combinations.

###  Preface: Organizing images in your filesystem
To my experience, I work with lots of images (1000-3000) as source to combine and produce lots of combinations as output.
Keeping them all in one directory quickly turned out as a mess, so I split directories. 
I personally have one subdir called ProjectDesktop, there go all my active image projects I'm working at. There I open up a subdir with my source images for a project (lets call this 2022_Samples), there I put reduced size copies of my images (2000px long side). why? Well, it speeds up image handling and intuition is all about speed.
In this project dir I will makedir a subdir called tableaus. Bildertisch will automatically recognize the name and use it for saving/loading tableaus from.

Bildertisch has an extremly simplified interface, but some keyboard shortcuts to help out. Therefor, it is actually not useful to use it on a tablet... sigh!
When you first start you have to set the image directory. This can be done via Menu (Configure - Set Image Directory) or with the Dir symbol top left.
This will also try setting the Project Directory (the home of your tableaus) to {imagedir}/tableaus or if this does not exist it will be set to {imagedir}.

###  How-To combine
You should now see your images to the left and a working area (the tisch/table) to the right.
Just double click images (or drga and drop) them into the workspace, rearrange them and combine.
Images can be rotated (Ctrl-r), Resized (click near the border), Moved, Snapped (hold Ctrl Key while moving). That's it, basically. 

Save (Ctrl-S) will save two files into the tableau directory: A text file, default name will be tableau_YYYY-MM-DD_HH-MM-SS.tbl, that holds the abstracted data of your combination (layout, position, size, imagenames etc.)
The second file is a plain Jpeg and will be used as thumbnail, so it size is relatively small. 

To get large sized rendering of your combination use the RenderImage button at the bottom. Warning, final size is limited to win32-memory , so somewhere above 10000px this will yield an error.

The working area can be zoomed from 0.5 to 2.0 (Ctrl-Mousewheel or the buttons zoom+/- at the bottom). It's initial size is 3000x5000px, but it will automatically extend, when you place images beyond.

### Key Shortcuts
```
        <Control-t> 			New Tab
        <Control-s> 			Save
        <Control-w> 			Close Tab

        <Control-r> 			Rotate image
        <Control-c> 			Copy Image
        <Control-v> 			Paste Image

        <Home>    				Find Image in Palette
        
        <Control-z> 			Undo
        <Control-y> 			Redo

        <F1> 					Open Console
        <F11> 					Fullscreen

        <Control-Prior> 		Zoom+
        <Control-Next> 			Zoom-
        <Control-MouseWheel> 	Zoom

```


I'll maybe writeup some more dok in the future if and when I find the time...
