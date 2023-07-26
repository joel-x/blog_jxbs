---
title: Estadística Descriptiva
author: Joel Burbano
date: '2023-07-26'
slug: []
categories: ["R"]
tags: ["R","Estadistica"]
---

# Estadística 

**Consideremos el siguiente problema:**

En un proceso de inyección de plástico una característica
de calidad del producto (disco) es su grosor, que debe ser
de `\(1.20\)` mm con una tolerancia de `\(\pm0.10\)` mm. Así, para
considerar que el proceso de inyección fue satisfactorio,
el grosor del disco debe estar entre la especificación inferior,
`\(EI = 1.10\)` y la superior, `\(ES = 1.30\)`. En un estudio de
capacidad para este proceso es necesario contestar las
siguientes interrogantes: ¿qué tipo de discos en cuanto a
grosor se están produciendo? ¿El grosor medio es adecuado?
¿La variabilidad del grosor es mucha o poca?

Para contestar estas preguntas, durante una semana
se obtuvieron de una línea de producción los `\(125\)` datos
de la tabla siguiente El muestreo fue sistemático: cada determinado
tiempo se tomaban cinco productos y se medían
y al final de la semana se tuvieron los datos referidos. A
continuación se analizarán estos datos por medio de diferentes estadísticos


```
##   [1] 1.15 1.20 1.17 1.16 1.16 1.15 1.17 1.20 1.16 1.19 1.17 1.13 1.15 1.20 1.18
##  [16] 1.17 1.16 1.20 1.17 1.17 1.20 1.14 1.19 1.13 1.19 1.16 1.18 1.16 1.17 1.15
##  [31] 1.21 1.15 1.20 1.18 1.17 1.17 1.13 1.16 1.16 1.17 1.20 1.18 1.15 1.13 1.20
##  [46] 1.17 1.19 1.23 1.20 1.24 1.17 1.17 1.17 1.17 1.18 1.24 1.16 1.18 1.16 1.22
##  [61] 1.23 1.22 1.19 1.13 1.15 1.15 1.22 1.19 1.18 1.19 1.17 1.16 1.17 1.18 1.19
##  [76] 1.23 1.19 1.16 1.19 1.20 1.17 1.13 1.22 1.19 1.21 1.20 1.19 1.17 1.19 1.22
##  [91] 1.19 1.18 1.11 1.19 1.19 1.17 1.19 1.17 1.20 1.16 1.19 1.20 1.20 1.17 1.25
## [106] 1.16 1.16 1.20 1.20 1.16 1.18 1.21 1.20 1.22 1.19 1.14 1.19 1.17 1.20 1.16
## [121] 1.15 1.20 1.12 1.11 1.18
```

