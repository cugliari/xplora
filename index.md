---
title       : Analyse Exploratoire de Données
subtitle    : M2 ECD | SISE
author      : Jairo Cugliari
job         : Université Lumière Lyon 2
license     : by-nc-sa
github      : {user: cugliari, repo: xplora}
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # {solarized_light}
widgets     : [mathjax, bootstrap] # {quiz}
mode        : selfcontained # {standalone, draft}
--- 

<style>
iframe{
  height:450px;
  width:900px;
  margin:auto auto;
}

iframe {height: 300px; width: 900px}
</style>




Ex 1. Le quartet d'Anscombe
---------------------


```r
quartet <- read.table('quartet.txt', header = TRUE)            
quartet
```

```
##    x1    y1 x2   y2 x3    y3 x4    y4
## 1  10  8.04 10 9.14 10  7.46  8  6.58
## 2   8  6.95  8 8.14  8  6.77  8  5.76
## 3  13  7.58 13 8.74 13 12.74  8  7.71
## 4   9  8.81  9 8.77  9  7.11  8  8.84
## 5  11  8.33 11 9.26 11  7.81  8  8.47
## 6  14  9.96 14 8.10 14  8.84  8  7.04
## 7   6  7.24  6 6.13  6  6.08  8  5.25
## 8   4  4.26  4 3.10  4  5.39 19 12.50
## 9  12 10.84 12 9.13 12  8.15  8  5.56
## 10  7  4.82  7 7.26  7  6.42  8  7.91
## 11  5  5.68  5 4.74  5  5.73  8  6.89
```


---

Le quartet d'Anscombe
---------------------

``` 
Moyenne  des x : 9.0  ~~   [mean(x)]  
Variance des x : 11   ~~     [var(x)]
Moyenne  des y : 7.50
Variance des y : 4.12
Correlation entre x e y : 0.816  ~~ [ cor(x, y) ou cor(data) ]
Regression linéaire : y = 3 + 0.5 x  ~~ [ lm(y~x, data) ]
```
Les mêmes valeurs de résumé ==> les mêmes données 

---


```r
par(mfcol = c(2, 2), mai = c(.3, .3, .3, .3))
plot(quartet$x1, quartet$y1, pch = 19,
     panel.last = abline(lm(y1 ~ x1, data = quartet)) )
plot(quartet$x2, quartet$y2, pch = 19,
     panel.last = abline(lm(y2 ~ x2, data = quartet)) )
plot(quartet$x3, quartet$y3, pch = 19,
     panel.last = abline(lm(y3 ~ x3, data = quartet)) )
plot(quartet$x4, quartet$y4, pch = 19,
     panel.last = abline(lm(y4 ~ x4, data = quartet)) )
```

<img src="figure/unnamed-chunk-3.png" title="plot of chunk unnamed-chunk-3" alt="plot of chunk unnamed-chunk-3" style="display: block; margin: auto;" />


---

Ex 2. Les données barley
---------------------

<img src="figure/unnamed-chunk-4.png" title="plot of chunk unnamed-chunk-4" alt="plot of chunk unnamed-chunk-4" style="display: block; margin: auto;" />



---
## Plan

1. Données univariées
2. Données bivariées
3. Données trivariées 
4. Données hypervariées

--- .class #id 

## Diagrammes à tiges et à feuilles

![alt text](figure/72.png)

---

## 1. Données univariées 


```r
dim(singer)
```

```
## [1] 235   2
```

```r
head(singer)
```

```
##   height voice.part
## 1     64  Soprano 1
## 2     62  Soprano 1
## 3     66  Soprano 1
## 4     65  Soprano 1
## 5     60  Soprano 1
## 6     61  Soprano 1
```


---


```r
boxplot(2.54 * singer$height, horizontal=TRUE)
```

![plot of chunk unnamed-chunk-6](figure/unnamed-chunk-6.png) 


---

```r
stem(2.54 * singer$height, scale=.8)
```

```
## 
##   The decimal point is 1 digit(s) to the right of the |
## 
##   15 | 22222
##   15 | 5555555577777777777777
##   16 | 0000000000000333333333333333
##   16 | 55555555555555555555555555555588888888888888888888888888888
##   17 | 00000000000000333333333333333333
##   17 | 5555555555555588888888888888888888888
##   18 | 0000000000000003333333333333333
##   18 | 55555888888
##   19 | 1111111133
```


--- 

## 1. Données univariées : q-plot

$ q(f) : f $

---

<img src="figure/unnamed-chunk-8.png" title="plot of chunk unnamed-chunk-8" alt="plot of chunk unnamed-chunk-8" style="display: block; margin: auto;" />


---

<img src="figure/unnamed-chunk-9.png" title="plot of chunk unnamed-chunk-9" alt="plot of chunk unnamed-chunk-9" style="display: block; margin: auto;" />


---

## 1. Données univariées : qq-plot 

<img src="figure/unnamed-chunk-10.png" title="plot of chunk unnamed-chunk-10" alt="plot of chunk unnamed-chunk-10" style="display: block; margin: auto;" />




---

## 1. Données univariées :  m-d plot

<img src="figure/unnamed-chunk-11.png" title="plot of chunk unnamed-chunk-11" alt="plot of chunk unnamed-chunk-11" style="display: block; margin: auto;" />


---

## 1. Données univariées :  qq plots

<img src="figure/unnamed-chunk-12.png" title="plot of chunk unnamed-chunk-12" alt="plot of chunk unnamed-chunk-12" style="display: block; margin: auto;" />


---


<img src="figure/unnamed-chunk-13.png" title="plot of chunk unnamed-chunk-13" alt="plot of chunk unnamed-chunk-13" style="display: block; margin: auto;" />


---

<img src="figure/unnamed-chunk-14.png" title="plot of chunk unnamed-chunk-14" alt="plot of chunk unnamed-chunk-14" style="display: block; margin: auto;" />


---

<img src="figure/unnamed-chunk-15.png" title="plot of chunk unnamed-chunk-15" alt="plot of chunk unnamed-chunk-15" style="display: block; margin: auto;" />
