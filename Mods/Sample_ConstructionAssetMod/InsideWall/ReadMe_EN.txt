How to Create Facility Wall Mod

Create a Json file describing the wall surface information.

The Json file must include a MetaData header:
"metaData": {
"assetName": "Specify the name of the resource",
"assetType": "wall",
"assetIcon": "Icon for the resource"
},

Provide 32X64 PNG images as custom wall Basetexture and smoothnessTexture. Include the file names (excluding the file extension) in the Json:
"baseTexture": "Color texture for the wall",
"smoothTexture": "Smoothness texture for the wall (optional)",

If you want the resource to be visible in the construction panel, indicate:
"CanbuildOnWallBuilder": true

If you have completed the above steps, you have accomplished a great deal. Now you can enter the game and take a look.

ExsampleCode：
test_wall.json
{
"metaData": {
"assetName": "Test Wall",
"assetType": "wall",
"assetIcon": "Test Wall_B"
},
"baseTexture": "Test Wall_B",
"smoothTexture": "Test Wall_S",
"CanbuildOnWallBuilder": true
}