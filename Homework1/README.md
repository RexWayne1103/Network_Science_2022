# Network-Science-COM530500-Homework1
[RexWayne1103/Network_Science_2022](https://github.com/RexWayne1103/Network_Science_2022)
## Requirements
* python 3.8.13
* igraph 0.10.1
* pandas 1.5.0
### igraph
```powershell
$ conda install -c conda-forge python-igraph
```
### pandas
```powershell
$ conda install -c anaconda pandas
```
## Coding
### Problem 5.(15%) 
Read the tutorial from [Ping-En Lu’s GitHub repository](https://github.com/PingEnLu/Network-Science-COM530500/tree/master/Network_Science_Python_iGraph_Tutorial) to install Python3 and python-igraph (if you need).

Paste your screenshots of “Hello, World!” of both Python 3 (5%) and python-igraph (5%),and write a brief report (5%). (For example, you can write down some problems you encountered,and how you solved them.)

```python
from igraph import *

g = Graph()
print(g)
print("Hello, World!")

exit()
```
### Problem 6.(35%) 
Please download the tvshow dataset from [Ping-En Lu’s GitHub repository](https://github.com/PingEnLu/Network-Science-COM530500/tree/master/Network_Science_Python_iGraph_Tutorial),and find the following information from this dataset.
  • Number of nodes. (5%)
  • Number of edges. (5%)
  • Mean degree. (5%)
  • Maximum degree. (5%)
  • Diameter. (5%)
  You need to upload your python source code to eLearn, and write a brief report (10%)
including screenshots, README file, and descriptions of your code below the solution
area. There
```python
import igraph as ig                         #圖形分析資料庫
import pandas as pd                         #資料分析函式庫

csvfile = pd.read_csv('.//tvshow_edges.csv')        #讀取csv檔
g = ig.Graph.DataFrame(csvfile, directed=False)             #創建成igraph，已無向圖方式創建
ig.summary(g)                               #Summary representation of a graph.

md=(2*g.ecount()/g.vcount())                #calculate mean degree
print("Number of nodes:%d"%g.vcount())      #Number of nodes. 
print("Number of edges:%d"%g.ecount())      #item Number of edges
print("Mean degree:%s"%md)	                #item Mean degree
print("Maximum degree:%d"%g.maxdegree())	#item Maximum degree
print("Diameter:%d"%g.diameter())           #item Diameter
#print(g.farthest_points())                 #degree的路徑頭尾兩個點，加度數
#print(g.get_diameter())                    #diameter路徑
```