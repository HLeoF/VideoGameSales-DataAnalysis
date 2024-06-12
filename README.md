# 游戏销售量数据分析

![](https://user-images.githubusercontent.com/74038190/212745723-c7c386dc-108c-4a50-9c76-0f90afb2c0fa.gif)

本次数据项目使用python进行数据的清洗工作和简单的数据探索(EDA);其中使用的python库包括`pandas`, `seaborn`, `plotly` 和 `matplotlib`。在数据进行清洗过后，将使用`Power BI` 制作关于游戏销售量的数据分析仪表盘根据清洗过后的数据集。

## 数据源
数据源来源于 [Kaggle](https://www.kaggle.com/datasets/gregorut/videogamesales) 平台；数据从[vgchartz.com](vgchartz.com)网站收集而来. 该数据包含超过`100,000`个游戏销售数据。

作者：[GregorySmith](https://www.kaggle.com/gregorut)

原始数据集中含有`11`列，它们分别时：

`Rank` $\to$ 总销售量排名

`Name` $\to$ 游戏名称

`Platfrom` $\to$ 游戏平台

`Year` $\to$ 游戏发行年份

`Genre` $\to$ 游戏类型

`Publisher` $\to$ 游戏发行商

`NA_Sales` $\to$ 北美地区销售量

`EU_Sales` $\to$ 欧洲地区销售量

`JP_Sales` $\to$ 日本地区销售量

`Other_Sales` $\to$ 其他地区销售量

`Global_Sales` $\to$ 全球销售量

## 清理数据

![](https://github.com/HLeoF/VideoGameSales-DataAnalysis/blob/main/img/1.jpg)|![](https://github.com/HLeoF/VideoGameSales-DataAnalysis/blob/main/img/2.jpg)
---|---


Year这一栏共有271个缺失值，经过计算：

$$\frac{\text{Messing Values in Column of Year}}{\text{Total Rows}} = \frac{271}{16598} \approx 0.00163$$

这缺失值占约占全部数据的0.0016. 所以将这些缺失值，这些缺失值对本次数据的分析影响很小。再删除这些缺失值之后，还有36个Publisher列的缺失值，再进一步对这些 missing value 进行一步研究，发现这些游戏Publisher发行的游戏平台并不是主流平台，所有我将这些missing value 也进行删除。最后得到一个干净的数据，放便我们进行下一步的使用。

![](https://github.com/HLeoF/VideoGameSales-DataAnalysis/blob/main/img/3.jpg)

## Exploratory Data Analysis (EDA) 探索性数据分析

#### 探究游戏平台全球销售量占比份额 Top 10 (1980-2020)

![](https://github.com/HLeoF/VideoGameSales-DataAnalysis/blob/main/img/4.png)

前五名的游戏平台分别是PS2、X360、PS3、Wii和DS。PS2以微弱的优势排名第一，显示出其在销售量上的显著地位。除了这五大平台外，PS、GBA、PSP、PS4和PC也在全球销量中占有重要份额。这些结果揭示了这些平台在过去数十年中对全球游戏市场的重要性。 进一步分析显示，游戏行业在北美、欧洲和日本尤其盛行。在北美，Xbox系列平台表现尤为突出，而在欧洲和亚洲，索尼的PlayStation系列和任天堂的设备则占据了主导地位。日本作为游戏机的发源地，依然是任天堂和索尼的重要市场，同时北美和欧洲的市场份额也在不断增长。

#### 探究 Top 10 最受欢迎的游戏发行商 （1980 - 2020）

![](https://github.com/HLeoF/VideoGameSales-DataAnalysis/blob/main/img/5.png)

 前十的分别是`Nintendo`、`EA`、`Activision`、`Sony Computer Entertainment`、`Ubisoft`、`Take-Two Interactive`、`THQ`、`Konami`、`Sega`和`Namco Bandai Games`。任天堂以其广泛的游戏阵容和长期的市场影响力稳居首位，而`EA`和`Activision`则凭借多样化的游戏类型和高质量的发行紧随其后。这些发行商在全球各地均有显著影响力，但不同地区的偏好有所不同。例如，北美市场对`EA`和`Activision`的游戏反应热烈，而在亚洲市场，`Nintendo`和`Sony Computer Entertainment`的游戏更受欢迎。欧洲市场则表现出对`Ubisoft`和`Konami`的青睐。这些发行商通过不断创新和适应市场需求，成功吸引了全球范围内的大量玩家，推动了游戏行业的持续发展。

 #### Top 10 全球销售量最好的游戏

![](https://github.com/HLeoF/VideoGameSales-DataAnalysis/blob/main/img/6.png)

 在探究过去四十年间最受欢迎的游戏时，我发现排名前十的分别是`Wii Sports`、`Grand Theft Auto V`、`Super Mario Bros`、`Tetris`、`Mario Kart Wii`、`Wii Sports Resort`、`Pokemon Red/Pokemon Blue`、`Call of Duty: Modern Warfare 3`、`New Super Mario Bros`和`Call of Duty: Black Ops II`。`Wii Sports`凭借其创新的体感操作和家庭娱乐性质稳居首位，而`Grand Theft Auto V`则因其开放世界和丰富的游戏内容紧随其后。这些游戏的受欢迎程度反映了不同地区的游戏偏好。任天堂的作品，如`Wii Sports`、`Super Mario Bros`和`Pokemon`系列，在全球范围内都拥有庞大的粉丝基础，特别是在日本和北美市场。而像`Grand Theft Auto V`和`Call of Duty`系列这样的游戏则在欧美市场表现尤为突出，吸引了大量喜欢动作和射击类游戏的玩家。`Tetris`这种经典益智游戏则凭借其简单却上瘾的玩法，在全球范围内长盛不衰。通过这些游戏的成功，我们可以看到游戏行业在不同类型和玩法上的多样化发展，以及各大市场对不同游戏类型的喜好。

 #### 日本地区销量最好的游戏 Top 10
 
![](https://github.com/HLeoF/VideoGameSales-DataAnalysis/blob/main/img/7.png)

 在探究日本地区最受欢迎的游戏时，我发现排名前十的分别是`Pokemon Red/Pokemon Blue`、`Pokemon Gold/Pokemon Silver`、`Super Mario Bros`、`New Super Mario Bros`、`Pokemon Diamond/Pokemon Pearl`、`Tetris、Pokemon Black/Pokemon White`、`Dragon Quest VII: Warriors of Eden`、`Pokemon Ruby/Pokemon Sapphire`和`Animal Crossing: Wild World`。显然，宝可梦系列在日本市场占据了主导地位，其中多款宝可梦游戏位居前列。 任天堂的经典游戏，如`Super Mario Bros`和`New Super Mario Bros`，也在日本市场表现出色，显示了马里奥系列持久的吸引力。Tetris这款经典益智游戏凭借其简单易上手的玩法，在日本依然备受欢迎。`Dragon Quest VII`和`Animal Crossing: Wild World`的入选则表明日本玩家对角色扮演游戏和模拟生活类游戏的偏爱。这些游戏的成功反映了日本市场对游戏趣味性、创新性和持续性的高要求。

#### 北美地区销量最好的游戏 Top 10

![](https://github.com/HLeoF/VideoGameSales-DataAnalysis/blob/main/img/8.png)

排名前十的分别是`Wii Sports`、`Super Mario Bros`、`Duck Hunt`、`Tetris`、`Grand Theft Auto V`、`Call of Duty: Black Ops`、`Super Mario World`、`Mario Kart Wii`、`Wii Sports Resort`和`Call of Duty: Modern Warfare 3`。`Wii Sports`以其创新的体感操作和家庭娱乐性质稳居首位，展示了其在北美市场的巨大影响力。经典的任天堂游戏，如`Super Mario Bros`、`Duck Hunt`和`Super Mario World`，也深受北美玩家喜爱，显示了马里奥系列长久以来的吸引力。`Tetris`这款简单却上瘾的益智游戏在北美同样广受欢迎。动作和射击类游戏，如`Grand Theft Auto V`和`Call of Duty`系列，在北美市场表现尤为突出，吸引了大量喜欢激烈游戏体验的玩家。

#### 欧洲地区销售最好的游戏 Top 10

![](https://github.com/HLeoF/VideoGameSales-DataAnalysis/blob/main/img/9.png)

排名前十的分别是`Wii Sports`、`Grand Theft Auto V`、`Mario Kart Wii`、`FIFA 15`、`Call of Duty: Modern Warfare 3`、`FIFA 16`、`FIFA 14`、`Call of Duty: Black Ops II`、`Wii Sports Resort`和`Nintendogs`。`Wii Sports`凭借其创新的体感操作和家庭娱乐性质稳居首位，而`Grand Theft Auto V`则因其开放世界和丰富的游戏内容紧随其后。FIFA系列游戏在欧洲市场表现尤为突出，`FIFA 15`、`FIFA 16`和`FIFA 14`都位列前十，显示出欧洲玩家对足球游戏的热爱。任天堂的`Mario Kart Wii`和`Wii Sports Resort`也深受欢迎，显示了其在家庭娱乐方面的强大吸引力。`Call of Duty`系列中的`Modern Warfare 3`和`Black Ops II`在欧洲市场也取得了显著的成功，吸引了大量喜欢动作和射击类游戏的玩家。







