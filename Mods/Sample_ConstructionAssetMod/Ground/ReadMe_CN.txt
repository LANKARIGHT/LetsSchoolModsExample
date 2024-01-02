如何创建地面模组
在创建了模组之后，你可以在学园构想家中加入自定义的地面样式，步骤如下：
0.在模组目录下创建文件夹 命名为 Ground，注意所有和地面有关的资源都需要在该文件夹下。

1.在Ground文件夹中建立一个描述墙面信息的Json文件（建议你从官方模板复制文件）

2.json文件中需要包含一个头文件MetaData
  "metaData": {
    "assetName": "填写该资源的名称",
    "assetType": "ground",
    "assetIcon": "该资源的图标"
  },

3.需要提供一张宽高为32或32的倍数的png图片作为自定义地面贴图和光滑度贴图，并且需要把文件名（不包含后缀名）填写进json中

  "baseTexture": "地面贴图的颜色贴图",
  "smoothTexture": "地面贴图的光滑度贴图（选填）",
地面贴图可以包含多个地面格32x32每格，读取地面文件时，程序会切分每一个格子按照从左到右、从下到上的顺序一次读取。

4.构建贴图队列
读取贴图需要从编号0开始形成一个队列，例如64x32的地面格子有两个地块，因此需要配置为如下格式
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
其中x指的是贴图坐标，Y指的是动画偏移（通常填写1），更多以此类推。

5.构建贴图规律
生成规则会使用队列中的地面数据生成地面格
规则有如下几种：
        Default 默认（使用0作为地面展示）
        checkerboard 棋盘格（使用0，1按照棋盘格交替展示）
        intervalX （横向间隔0和1进行展示）
        intervalY （纵向间隔0和1进行展示）
        PointRandom （0和1按照20：1的比例点状随机展示）
        surround （一圈1包围一个0进行展示）
        Tatami（榻榻米，0-4进行展示）
        FourTypeRandom = 7,（在0、1、2、3中随机展示）
        Berlin8 = 9,（在0~7中随机展示）
    
需要将rule填入json文件
"Rule": "Default"

5.季节性地面
如果你需要每个季节使用不同的图像队列，那么你需要标记
    "useSeason": true,

然后使用
    "Season1": [],
    "Season2": [],
    "Season3": [],
    "Season4": [],
替代
    "sprite": []
配置数据。


6.设置地面边缘融合
地面边缘融合度越高，融合效果越强，
  "Blend": 0.0 硬边缘
  "Blend": 3.0 软边缘




7.如果你需要可以在建造面板中看到该资源，需要标注
  "CanbuildOnGroundBuilder": true

8.你可以使用BuyPrice定出售价（注意在不同难度中这个数值会被修正）
 "BuyPrice": 10,
9.你可以配置地面是否耐脏0是不会脏，1是容易脏
    "CleanlinessRate": 0.0,



这样就大功告成了，可以进游戏看看。
案例代码

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
