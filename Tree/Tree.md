[TOC]

# Tree













![1535879408293](C:\Users\Spring\AppData\Local\Temp\1535879408293.png)

信息熵计算实现

```python
#计算结果集中的香农熵
def calcShannonEnt(dataSet):
        numEntries = len(dataSet)
        labelCounts = {}
        for featVec in dataSet:
                #获取数据集的标签,作为key
                currentLabel = featVec[-1]
                #遍历数据集,将标签作为key,计算出现的次数value
                if currentLabel not in labelCounts.keys():
                        labelCounts[currentLabel] = 0
                labelCounts[currentLabel] += 1
        shannonEnt = 0.0
        for key in labelCounts:
                #计算出现的概率
                prob = float(labelCounts[key])/numEntries
                #计算香农熵
                shannonEnt -= prob*log(prob,2)
        return shannonEnt
```

