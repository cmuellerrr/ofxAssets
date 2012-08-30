# ofxAssets

## Introduction

ofxAssets is an openFrameworks addon for simple access to assets inside your data folder. 

## Usage

### Include source and headers
Setup the addon with your project (e.g. drag the ofxAssets src files into your XCode project).

### Put assets into an  assets folder

Assets go inside `data/assets`

```
appFolder/
appFolder/data/assets/images - places images here (png, jpg, jpeg)
appFolder/data/assets/shaders - place any shaders here (vert, frag, geom)
appFolder/data/assets/fonts - place any font files here (ttf)
```

### Use ofxAssets in your code

`header`
```c++
#include “ofxAssets.h”
using namespace ofxAssets; // this is optional
```

`source`
```c++
//example
void testApp::draw() {

    // quick access to assets
	image("imageName").draw(10,10);	
	font("fontName", 30).drawString("...", 10, 10); 
	shader("shaderName").begin();
    
    // if you don’t put ‘using namespace ofxAssets’ at the top of your source or header, then use:	
	ofxAssets::image("imageName").draw(10,10);
}
```

You can also reload the asset register (e.g. you edit an image externally and what to see it updated in your app) using

```c++
AssetRegister::refresh()
```

## Notes
If your asset filename is `background.png`, then you access this asset without the extension, e.g. `image("background").draw(10,10)`.