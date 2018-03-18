# subwayMap
首先，像其他的jQuery插件一样添加jQuery库和插件的Js库。

<script src="res/newjs/jquery-1.2.6.js" type="text/javascript"></script>
<script src="res/newjs/index_new.js?v=20101208"  type="text/javascript"></script>

然后定义我们的画布DIV

<div id = “subway_canvas”></div>

使用jquery选择器让我们的铁路图生效~

$(“#subway_canvas”) .subwayMap({ debug: true });

参数说明：debug：[true|false] 调试模式  打开时可以在JS控制台显示调试信息
下面看看线路节点是怎么设置的：

通过Demo可以知道，这是典型的导航型插件，通过UL和LI标签定义节点。而<canvas>则可以设置背景等信 息,<canvas>是使用网格布局；而不同的地图可以在一个网格上重叠，只要使用不同的UL标签标识就OK。看一看都有哪些信息可以设置：

Canvas参数说明：

(DIV)data-columns：<canvas>的网格列数；

(DIV)data-rows：<canvas>的网格行数；

(DIV)data-cellSize:每个网格的大小，大小为像素;整个<canvas>的大小=data_colums*data-cellSize-data_rows*data-cellSize；

(DIV)data-legendId:地图的图例位置，输入的是一个<div>的id；

(DIV)data-textClass:地图节点的文字样式；

(DIV)data-gridNumbers：是否显示网格的行列数；

(DIV)data-grid:是否显示网格;

(DIV)data-lineWidth:地图路线的宽度,像素值;
(UL)data-color:表示该线路的颜色；

(UL)data-label:该线路唯一的ID标识，也是图例显示的名称；

(LI)data-coords:该点的坐标，可以为浮点数；

(LI)data-labelPos:该点名称的显示位置,可以为N, E, S, W, NE, NW, SE, SW，默认为S；
(UL)data-shiftCoords:地图路线偏离原来的位置的大小，是一个x,y值对，可以为负数，正数代表向右向下移动；

(li)data-marker:地图上的地点表示，可以为”station” 和” interchange”，如果表示的地点不在连续的线路上，可以使用”@station”或者”@interchange”表示；

(li)data-dir:为了实现地图的圆滑的效果，可以使用拐角效果，该属性值可以为N,S,W,W表示拐角的方向；

(li)data-markerInfo:地图标志信息，表示地图的上的连接点，可以是两个不同的路线，也可以是同一条路线，属性值为[v|h]+数值，v表示垂直方向，h表示水平方向,数值为像素，表示延伸的长度；
