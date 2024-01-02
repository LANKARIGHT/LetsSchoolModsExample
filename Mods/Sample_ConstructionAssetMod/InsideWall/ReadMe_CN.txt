如何创建墙面模组
在创建了模组之后，你可以在学园构想家中加入自定义的设施内墙样式，步骤如下：
0.在模组目录下创建文件夹 命名为 InsideWall，注意所有和设施内墙有关的资源都需要在该文件夹下。

1.在InsideWall文件夹中建立一个描述墙面信息的Json文件

2.json文件中需要包含一个头文件MetaData
  "metaData": {
    "assetName": "填写该资源的名称",
    "assetType": "wall",
    "assetIcon": "该资源的图标"
  },

3.需要提供32X64的png图片作为自定义墙面贴图和光滑度贴图，并且需要把文件名（不包含后缀名）填写进json中

  "baseTexture": "墙面贴图的颜色贴图",
  "smoothTexture": "墙面贴图的光滑度贴图（选填）",

4.如果你需要可以在建造面板中看到该资源，需要标注
  "CanbuildOnWallBuilder": true

这样就大功告成了，可以进游戏看看。
案例代码
测试墙面.json
{
  "metaData": {
    "assetName": "测试墙面",
    "assetType": "wall",
    "assetIcon": "测试墙面_B"
  },
  "baseTexture": "测试墙面_B",
  "smoothTexture": "测试墙面_S",
  "CanbuildOnWallBuilder": true
}