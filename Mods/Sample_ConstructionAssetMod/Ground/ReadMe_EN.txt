Title: How to Create Ground Modules

After creating a module, you can add custom ground styles to the Academy Architect. Follow these steps:

1. Create a Ground Folder in the Module Directory

   Create a folder named "Ground" under the module directory. Note that all resources related to the ground should be placed in this folder.

2. Create a Json File Describing Wall Information in the Ground Folder

   Create a Json file in the Ground folder to describe wall information (it is recommended to copy the file from the official template).

3. Include a MetaData Header in the Json File
   "metaData": {
     "assetName": "Fill in the resource name",
     "assetType": "ground",
     "assetIcon": "Icon for the resource"
   },

4. Provide a PNG Image for Custom Ground Texture and Smoothness

   Provide an image with a width and height of 32 or multiples of 32 as a custom ground texture and smoothness texture. Include the file names (without extensions) in the Json file.
   "baseTexture": "Color texture for ground",
   "smoothTexture": "Smoothness texture for ground (optional)",

5. Build the Texture Queue

   Create a queue starting from index 0. For example, for a 64x32 ground grid with two tiles, configure it as follows:
   "sprite": [
     {
       "x": 0,
       "y": 1
     },
     {
       "x": 1,
       "y": 1
     }
   ],


6. Establish Texture Patterns

   Use the queue data to generate ground grid patterns. The available rules include Default, Checkerboard, IntervalX, IntervalY, PointRandom, Surround, Tatami, FourTypeRandom, and Berlin8.


   "Rule": "Default"


7. Seasonal Ground

   If you want different image queues for each season, mark:


   "useSeason": true,


   Then replace the "sprite" configuration with:


   "Season1": [],
   "Season2": [],
   "Season3": [],
   "Season4": [],


8. Set Ground Edge Blending

   Adjust the blending for stronger or softer edge effects:


   "Blend": 0.0  // Hard edge
   "Blend": 3.0  // Soft edge


9. Display in Construction Panel

   If you want the resource to appear in the construction panel, specify:

   "CanbuildOnGroundBuilder": true


10. Set Buy Price
	
	Use BuyPrice to set the selling price:
    "BuyPrice": 10


11. Configure Ground Cleanliness

    Set CleanlinessRate to 0 for no dirt, and 1 for easy dirt:


    "CleanlinessRate": 0.0


This completes the setup. You can now explore the results in the game.

Example Code:


{
  "metaData": {
    "assetName": "GroundSample1",
    "assetType": "ground",
    "assetIcon": "GroundSample1_B"
  },
  "baseTexture": "GroundSample1_B",
  "smoothTexture": "GroundSample1_S",
  "CanbuildOnGroundBuilder": true,
  "Rule": "Default",
  "data": {
    "GroundNameI18n": {
      "Key": "testGroundNameKey",
      "Value": "GroundSample1"
    },
    "GroundCommentsI18n": {
      "Key": "",
      "Value": ""
    },
    "Blend": 3.0,
    "rule": 0,
    "useSeason": false,
    "sprite": [
      {
        "x": 0,
        "y": 1
      }
    ],
    "Season1": [],
    "Season2": [],
    "Season3": [],
    "Season4": [],
    "CanWalk": true,
    "BuyPrice": 10,
    "CleanlinessRate": 0.0,
    "MovementFactor": 0.0,
    "RootTable": {
      "instanceID": 36630
    },
    "tempPreview": {
      "instanceID": -6430608
    }
  }
}