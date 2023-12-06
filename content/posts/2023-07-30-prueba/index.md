---
title: Estadística Descriptiva
author: Joel Burbano
date: '2023-07-30'
slug: []
categories: []
tags: []
authors: []
description: ''
externalLink: ''
series: []
---
<script src="{{< blogdown/postref >}}index_files/clipboard/clipboard.min.js"></script>
<link href="{{< blogdown/postref >}}index_files/xaringanExtra-clipboard/xaringanExtra-clipboard.css" rel="stylesheet" />
<script src="{{< blogdown/postref >}}index_files/xaringanExtra-clipboard/xaringanExtra-clipboard.js"></script>
<script>window.xaringanExtraClipboard(null, {"button":"Copy Code","success":"Copied!","error":"Press Ctrl+C to Copy"})</script>



La estadística descriptiva nos permite realizar el análisis exploratorio de la información y el pre-procesamiento de la información antes de tener un modelo de machine learning.



```python
import pandas as pd
```


```python
df = pd.read_csv("cars.csv")
df.head()
```

```
   speed  dist
0      4     2
1      4    10
2      7     4
3      7    22
4      8    16
```



