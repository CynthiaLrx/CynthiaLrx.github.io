# CynthiaLrx.github.io
### This is my personal page for code-presentation
### 注意：第二次作业在页面后

# 计算机科学与编程入门课程第一次作业
## 1900017866 骆汝茜

## 1.作业1
#### 作业1选取了曹雪芹《红楼梦》作为分析文本。作为一部以家族为切入点，反映社会兴衰的长篇小说，红楼梦中出现的人物角色数不胜数，难以通过人力统计。在文本分析的传统方式之外，量化描述能够提供另外的角度，科学地分析文本。同时，对于以讲述人在家族/社会中的活动，以人物为主体的小说，人物的言行活动与主旨息息相关。通过统计人物名称出现的次数，能够初步确定《红楼梦》文本中各个人物的重要程度，即小说人物的重要程度可以对等其出现的次数。然而，这一论断是粗糙的，出现次数只能反映出大致倾向，人物的重要性还通过角色与其他人物的关系、视角的选择等一方面因素有关。因此，这次作业只是一个初步的结果。
#### 利用同样的方式，可以将《红楼梦》文本中一些词进行词频分析，从而根据其聚集程度将文本分为不同的几部分，以发现和验证《红楼梦》中描述的不同时期，从而更加客观地说明《红楼梦》家族与社会兴衰的主题。同时，根据自然语言学的一些言论，写作者使用介词的频率是相对稳定的，也可以用词频统计来研究1-80章和81-120章是否为一个作者所写等问题，如[李贤平先生的研究](https://max.book118.com/html/2017/0426/102469126.shtm)。
#### 选择这一文本是基于作者的兴趣。
#### 本作业对词频分析的结果进行了初步的可视化实现。
### 使用的技术与其他想说的：
- 使用了jiaba库进行分词，并根据posseg函数筛选了人物名称这一词性，缩小了筛选范围
- 使用了pyecharts库中的WordCloud()、Bar()和Pie()函数，从三个角度对词频统计进行了可视化，其一非常直观地体现出出现次数的大小区别，其二相比于其一蕴含的数据量更大，也能看出具体的数据差别，其三侧重于人物出现次数的比例，注重对比。
- 因为统计了前100名人物的出现频次，数据量较大，条形图使用了滑块帮助阅读者更加清晰地浏览各人物的次数。同时，添加了工具栏，让阅读者能够方便地选择自己更适应的形式看数据分布。
- 从条形图/折线图猜测，小说人物的出现似乎服从泊松分布或其他一些有迹可循的分布形式，后续可以通过数据分析，并加大样本量进行确定。

[作业1链接](http://CynthiaLrx.github.io/红楼梦人物频次.html)

## 2.作业2
#### 生育问题与生育矛盾在近年更加凸显和激化，是一个备受争议的热点社会问题。在很多对于生育问题的研究中，都有提到生育率与许多因素有着相关关系：如经济水平、文化习俗、男女比例、受教育水平（尤其是女性受教育水平）等。考虑到生育率很难在实验室环境下进行控制变量地研究（当然，也许我们可以通过计算机建模模拟这一问题），造成两个社群之间生育率差异往往是上述所说因素的综合效应。朴素地看，地区差异就是一个各因素的整合——根据我国国情，不同省份的人因流动有限，天然的地理隔离形成了不同的文化习俗；同时，省份之间的经济水平也是有显著差异的；等等。
#### 要分析每一个因素对于生育率的影响，首先可以对地区差异进行初步的探索，一来是数据相较于其他因素差异的样本更好收集，一方面也因为可以通过不同省份各因素之间的对比，与生育率差异进行关联，从而确定在中国国情下，各影响因素对于生育率的贡献率。
#### 数据来自国家统计局。国家统计局的数据也统计了不同年龄段妇女的生育率，年龄数据可能不能直观地反映出一些事情，但能够辅助地说明各地区生育观念差异等，因此也将生育率根据年龄分类进行了可视化操作。
#### 选择这一主题也是基于作者的个人兴趣。
#### 使用的技术和其他想说的：
- 使用了pyecharts库中的Map()，用不同颜色直观地反映出各省份之间总的生育率差异。尝试了分立的颜色，帮助阅读者更简单地区分地区差异。可以看出，云贵新等经济较落后的地方生育率最高，而东北三省（男女平等）和北京（经济发达）的地区生育率最低。
- 使用了timline()函数，以反映出不同年龄段的省份差异，将多张图动态地融成一张图。此处作者尝试了直接将不同年龄通过legend进行区分，但由于pyecharts库函数的特性，可以将不同label数据叠加，由于各年龄段的数据差异过大，叠加反而会损失部分数据的差异，叠加后很难看出有什么区别，所以使用了“可能没那么贴切”的timeline函数。
- 第二张图也尝试了颜色不离散的连续模式，体现出更加细微的差异。
- 考虑到与作业1相同的问题，仅通过最直观的图画形式，不能准确看出数据的差异，作者还增设了一个叠加bar的条形图，从条形图中可以看出各省的生育率总体差异和每个省各年龄段对生育率的贡献程度。可以对legend进行选择和取消来看部分年龄段的生育率差异。也添加了工具栏让阅读者自由选择图表模式。将纵坐标的字体进行了旋转，让每一个省份的名称都能在图表上显示（初始状态下只能显示部分省份的名称）
- 作业还尝试使用了漏斗图，来反映全国范围内各年龄段妇女对生育率贡献的大小比较，这是一种粗糙但直观的数据呈现模式。并对图的颜色搭配（主题）进行了探索。

[作业2链接](http://CynthiaLrx.github.io/中国育龄妇女生育率.html)

## 3.作业3
#### 该作业的要求是在世界地图上做一些可视化操作。基于好奇和对过去生活的留念，作者借用这个作业的机会回顾了自己曾经旅游到过的国家，不禁感叹原来我的足迹已经遍布了这么多的地方。当箭头指出的动画效果呈现，确实能感受到一些生活上的小确幸。
#### 使用的技术和其他想说的：
- 使用了geo（）函数，使用国家：年份这一格式对世界地图进行了描点，并画了剪头指向旅游的行进方向。
- 调整了图片大小，使网页点进去时整个页面都是大地图，并使用了较暗的颜色主题，符合个人审美
- 根据旅游时期进行了区分，可以看出因为学业增重，旅游的轨迹逐渐集中于东南亚。
  
[作业3链接](http://CynthiaLrx.github.io/我的旅行轨迹——世界地图.html)

## 4.作业4
#### 这一作业的主题是组合图表，作者对自己未曾尝试过的图表形式都进行了尝试，画了雷达图、条形-折线多y轴图、水球图、仪表盘、环状图等，使用的是从气象局网站和其他天气软件上的北京天气数据。并使用了两种形式对这些图表进行了整合（如下两个链接）：page和tab。
#### 借用这次机会，了解了很多pyecharts参数的使用方法，调整颜色、增设副标题、调整y轴位置、形状选择等。
#### 使用的技术和其他想说的：
- 空气质量指数-仪表盘图的颜色是与空气质量指数对应的不同等级相对应的
- 昼夜比例图的颜色与白天-黑夜颜色一致
- 使用了Bar, Grid, Line, Liquid, Page, Pie, Gauge, Radar, Tab(均来自pyecharts）库并学会了怎样精确到所想要的几位小数的方式。

[作业3链接1](http://CynthiaLrx.github.io/北京20220327天气指数.html)
  
[作业3链接2](http://CynthiaLrx.github.io/北京20220327天气指数-tab.html)


  
    
      
        
        
# 计算机科学与编程入门课程第二次作业
## 1900017866 骆汝茜

## 1.作业 1 
#### 这一作业是设计一个html网页，页面包含输入框、按钮和一些介绍文字，实现某个搜索引擎的搜索功能。我选择的搜索引擎是谷歌。（因此需要挂梯子才能上！！）
#### 网页设计使用了：
- 标题设置为居中
- 简易的Google介绍
- 配上了Google引擎的标志图片
- 使用了输入-查询框将浏览者索引至google搜索
#### 考虑到搜索引擎要简洁更好，没有使用其他的美化。

[作业1链接](http://CynthiaLrx.github.io/google搜索.html)

## 2. 作业 2
#### 这一作业是使用文本编辑器，设计一个网页并用CSS美化。我热爱喝椰树牌椰奶！而且它的文案、图片设计都十分醒目且魔性，所以我用html网页复刻了它的图片文案。
#### 学习了用CSS美化的基础技术：文字大小设置、文字排列设置、颜色（文本背景颜色）设置、行间距设计，并附加了椰树牌椰奶的实拍图（最后发现并不是特别像）。

[作业2链接](http://CynthiaLrx.github.io/椰树牌椰奶.html)

## 3.作业 3
#### 这一作业包含两部分，第一部分是共现分析可视化呈现，第二部分是将其制作成网页。
#### 我选择的文本与上一次一致，为红楼梦，这是基于个人兴趣。对红楼梦进行共现分析也是非常合适的，一方面，人物个数多，文本长。行文即从人物之间的关系反应主旨，因而人物关系密切且有足够数据量支撑。也更容易从人物共现次数的差异来反应人物关系的密切程度，从而帮助我们认识到主线、主旨。
#### 我选择的文本与上一次一致，为红楼梦，这是基于个人兴趣。对红楼梦进行共现分析也是非常合适的，一方面，人物个数多，文本长。行文即从人物之间的关系反应主旨，因而人物关系密切且有足够数据量支撑。也更容易从人物共现次数的差异来反应人物关系的密切程度，从而帮助我们认识到主线、主旨。
#### 网页设计方面的一些考虑
- 使用了暗色、纯色背景，简约且护眼
- 标题与各文本的颜色、大小选取清晰、有侧重
- 附加了对红楼梦人物频次分析的第一次作业链接，使信息更加完全
- 文本大部分使用居中排列，使页面重心平衡，满足浏览体验
- 附加了《红楼梦》的百度百科链接，并隐藏在图片中，既反应出《红楼梦》主题，使超链接没有那么生硬，在功能上也满足普通浏览者的需求——帮助浏览者更好的了解红楼梦。
- 考虑到页面主要是对红楼梦人物的分析，出现了100个人物，可能浏览者不了解关系图中出现的某些人物，所以在最后附加了一个查询接口，索引至百度搜索，更加便捷。

[作业3链接](http://CynthiaLrx.github.io/红楼梦人人物关系分析.html)

