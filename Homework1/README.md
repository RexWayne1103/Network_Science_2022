# Network-Science-COM530500-Homework1
## igraph
https://igraph.org/python/versions/latest/api/index.html \\
igraph                    0.10.1
```powershell
conda install -c conda-forge python-igraph
```
## pandas
pandas                    1.5.0  
```
conda install -c anaconda pandas
```
## Coding 
Python                    3.8
```py
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
