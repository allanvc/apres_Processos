---
title       : Movimento Browniano e Mercado Financeiro
subtitle    : A Equação de Black-Scholes
author      : Caio Balena / Allan Vieira
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : prettify  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax, bootstrap, quiz]            # {mathjax, quiz, bootstrap}
ext_widgets : #{rCharts: libraries/nvd3}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
assets      : {js: 'test.js'}
logo        : est_logo.png
biglogo     : unb_big_logo.png
--- dt:10

<!-- widgets bootstrap e quiz sao importantes para as tabs funcionarem -->



<style>
body {
  background-color: #000;
}
.quiz-option label{
  display: inline;
  font-size: 1em;
}
ul.nav li::before { content: ""; }  
ul.nav li{ font-size: 18px; line-height: 24px;}
</style>

<!-- para alterar cor de fundo dos slides -->
<style>
.title-slide {
  background-color: #FFFFFF; /* #EDE0CF; #CA9F9D*/
}
</style>

<!-- Limit image width and height -->
<style type="text/css">
img {     
  max-height: 400px;     
  max-width: 450px; 
}
</style>

<!-- criando um estilo css que divide os slides em 3 colunas - bem util! -->
<!-- depois chamar com <div class ="col3"> (...) </div> -->
<!-- https://stackoverflow.com/questions/31753897/2-column-section-in-r-markdown -->
<style>
  .col2 {
    columns: 2 200px;         /* number of columns and width in pixels*/
    -webkit-columns: 2 200px; /* chrome, safari */
    -moz-columns: 2 200px;    /* firefox */
  }
  .col3 {
    columns: 3 100px;
    -webkit-columns: 3 100px;
    -moz-columns: 3 100px;
  }
</style>

## Movimento Browniano



Movimento Browniano como conhecemos:

<p><center><img src="./assets/img/brown_animation.gif" align="middle">
</center></p>

--- &twocol  

## Movimento Browniano - Mercado Financeiro

*** =left

<p><center><img src="./assets/img/wallstreet_bull(3).jpg" align="middle">
</center></p>

*** =right

<p><center><img src="./assets/img/bear_vs_bull.jpg" align="middle">
</center></p>

--- {class: class, tpl: tabs}
## Exemplo Mov. Br. - Mercado Financeiro

*** {class: active, id: day}

<!-- MotionChart generated in R 3.4.2 by googleVis 0.6.2 package -->
<!-- Wed Nov 15 11:34:24 2017 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataMotionChartIDcd74d1e3f3d () {
var data = new google.visualization.DataTable();
var datajson =
[
 [
"PETR4.SA",
new Date(2017,10,10),
16.72
],
[
"PETR4.SA",
new Date(2017,10,9),
16.72
],
[
"PETR4.SA",
new Date(2017,10,8),
16.95
],
[
"PETR4.SA",
new Date(2017,10,7),
16.5
],
[
"PETR4.SA",
new Date(2017,10,6),
17.43
],
[
"PETR4.SA",
new Date(2017,10,3),
16.94
],
[
"PETR4.SA",
new Date(2017,10,1),
16.9
],
[
"PETR4.SA",
new Date(2017,9,31),
16.77
],
[
"PETR4.SA",
new Date(2017,9,30),
16.78
],
[
"PETR4.SA",
new Date(2017,9,27),
17.03
],
[
"PETR4.SA",
new Date(2017,9,26),
16.73
],
[
"PETR4.SA",
new Date(2017,9,25),
16.72
],
[
"PETR4.SA",
new Date(2017,9,24),
16.51
],
[
"PETR4.SA",
new Date(2017,9,23),
16.2
],
[
"PETR4.SA",
new Date(2017,9,20),
16.22
],
[
"PETR4.SA",
new Date(2017,9,19),
16.15
],
[
"PETR4.SA",
new Date(2017,9,18),
16.16
],
[
"PETR4.SA",
new Date(2017,9,17),
16.13
],
[
"PETR4.SA",
new Date(2017,9,16),
16.12
],
[
"PETR4.SA",
new Date(2017,9,13),
16.08
],
[
"PETR4.SA",
new Date(2017,9,11),
16.08
],
[
"PETR4.SA",
new Date(2017,9,10),
16.19
],
[
"PETR4.SA",
new Date(2017,9,9),
15.89
],
[
"PETR4.SA",
new Date(2017,9,6),
15.69
],
[
"PETR4.SA",
new Date(2017,9,5),
15.9
],
[
"PETR4.SA",
new Date(2017,9,4),
15.66
],
[
"PETR4.SA",
new Date(2017,9,3),
15.98
],
[
"PETR4.SA",
new Date(2017,9,2),
15.4
],
[
"PETR4.SA",
new Date(2017,8,29),
15.3
],
[
"PETR4.SA",
new Date(2017,8,28),
15.34
],
[
"PETR4.SA",
new Date(2017,8,27),
15.31
],
[
"PETR4.SA",
new Date(2017,8,26),
15.56
],
[
"PETR4.SA",
new Date(2017,8,25),
15.84
],
[
"PETR4.SA",
new Date(2017,8,22),
15.69
],
[
"PETR4.SA",
new Date(2017,8,21),
15.67
],
[
"PETR4.SA",
new Date(2017,8,20),
15.87
],
[
"PETR4.SA",
new Date(2017,8,19),
15.14
],
[
"PETR4.SA",
new Date(2017,8,18),
15.04
],
[
"PETR4.SA",
new Date(2017,8,15),
15.04
],
[
"PETR4.SA",
new Date(2017,8,14),
15.04
],
[
"PETR4.SA",
new Date(2017,8,13),
15.03
],
[
"PETR4.SA",
new Date(2017,8,12),
14.87
],
[
"PETR4.SA",
new Date(2017,8,11),
14.99
],
[
"PETR4.SA",
new Date(2017,8,8),
14.71
],
[
"PETR4.SA",
new Date(2017,8,6),
15.02
],
[
"PETR4.SA",
new Date(2017,8,5),
14.41
],
[
"PETR4.SA",
new Date(2017,8,4),
14.17
],
[
"PETR4.SA",
new Date(2017,8,1),
14.02
],
[
"PETR4.SA",
new Date(2017,7,31),
13.65
],
[
"PETR4.SA",
new Date(2017,7,30),
13.45
],
[
"PETR4.SA",
new Date(2017,7,29),
13.85
],
[
"PETR4.SA",
new Date(2017,7,28),
13.87
],
[
"PETR4.SA",
new Date(2017,7,25),
13.88
],
[
"PETR4.SA",
new Date(2017,7,24),
13.8
],
[
"PETR4.SA",
new Date(2017,7,23),
13.76
],
[
"PETR4.SA",
new Date(2017,7,22),
13.79
],
[
"PETR4.SA",
new Date(2017,7,21),
13.34
],
[
"PETR4.SA",
new Date(2017,7,18),
13.6
],
[
"PETR4.SA",
new Date(2017,7,17),
13.05
],
[
"PETR4.SA",
new Date(2017,7,16),
13.13
],
[
"PETR4.SA",
new Date(2017,7,15),
13.15
],
[
"PETR4.SA",
new Date(2017,7,14),
13.08
],
[
"PETR4.SA",
new Date(2017,7,11),
12.95
],
[
"PETR4.SA",
new Date(2017,7,10),
13.19
],
[
"PETR4.SA",
new Date(2017,7,9),
13.52
],
[
"PETR4.SA",
new Date(2017,7,8),
13.49
],
[
"PETR4.SA",
new Date(2017,7,7),
13.55
],
[
"PETR4.SA",
new Date(2017,7,4),
13.4
],
[
"PETR4.SA",
new Date(2017,7,3),
13.31
],
[
"PETR4.SA",
new Date(2017,7,2),
13.51
],
[
"PETR4.SA",
new Date(2017,7,1),
13.12
],
[
"PETR4.SA",
new Date(2017,6,31),
13.29
],
[
"PETR4.SA",
new Date(2017,6,28),
13.13
],
[
"PETR4.SA",
new Date(2017,6,27),
13
],
[
"PETR4.SA",
new Date(2017,6,26),
12.98
],
[
"PETR4.SA",
new Date(2017,6,25),
13.22
],
[
"PETR4.SA",
new Date(2017,6,24),
12.88
],
[
"PETR4.SA",
new Date(2017,6,21),
12.69
],
[
"PETR4.SA",
new Date(2017,6,20),
13.1
],
[
"PETR4.SA",
new Date(2017,6,19),
13.23
],
[
"PETR4.SA",
new Date(2017,6,18),
12.94
],
[
"PETR4.SA",
new Date(2017,6,17),
12.89
],
[
"PETR4.SA",
new Date(2017,6,14),
13.05
],
[
"PETR4.SA",
new Date(2017,6,13),
12.87
],
[
"PETR4.SA",
new Date(2017,6,12),
12.94
],
[
"PETR4.SA",
new Date(2017,6,11),
12.33
],
[
"PETR4.SA",
new Date(2017,6,10),
11.98
],
[
"PETR4.SA",
new Date(2017,6,7),
11.93
],
[
"PETR4.SA",
new Date(2017,6,6),
12.17
],
[
"PETR4.SA",
new Date(2017,6,5),
12.21
],
[
"PETR4.SA",
new Date(2017,6,4),
12.43
],
[
"PETR4.SA",
new Date(2017,6,3),
12.36
],
[
"PETR4.SA",
new Date(2017,5,30),
12.37
],
[
"PETR4.SA",
new Date(2017,5,29),
12.18
],
[
"PETR4.SA",
new Date(2017,5,28),
12.08
],
[
"PETR4.SA",
new Date(2017,5,27),
12.21
],
[
"PETR4.SA",
new Date(2017,5,26),
12.27
],
[
"PETR4.SA",
new Date(2017,5,23),
11.93
],
[
"PETR4.SA",
new Date(2017,5,22),
12.04
],
[
"PETR4.SA",
new Date(2017,5,21),
11.64
],
[
"PETR4.SA",
new Date(2017,5,20),
11.86
],
[
"PETR4.SA",
new Date(2017,5,19),
12.29
],
[
"PETR4.SA",
new Date(2017,5,16),
12.28
],
[
"PETR4.SA",
new Date(2017,5,14),
12.62
],
[
"PETR4.SA",
new Date(2017,5,13),
12.94
],
[
"PETR4.SA",
new Date(2017,5,12),
12.9
],
[
"PETR4.SA",
new Date(2017,5,9),
12.85
],
[
"PETR4.SA",
new Date(2017,5,8),
12.84
],
[
"PETR4.SA",
new Date(2017,5,7),
12.87
],
[
"PETR4.SA",
new Date(2017,5,6),
13.18
],
[
"PETR4.SA",
new Date(2017,5,5),
13.18
],
[
"PETR4.SA",
new Date(2017,5,2),
13.05
],
[
"PETR4.SA",
new Date(2017,5,1),
12.82
],
[
"PETR4.SA",
new Date(2017,4,31),
12.96
],
[
"PETR4.SA",
new Date(2017,4,30),
13.36
],
[
"PETR4.SA",
new Date(2017,4,29),
13.57
],
[
"PETR4.SA",
new Date(2017,4,26),
13.68
],
[
"PETR4.SA",
new Date(2017,4,25),
13.74
],
[
"PETR4.SA",
new Date(2017,4,24),
13.94
],
[
"PETR4.SA",
new Date(2017,4,23),
13.49
],
[
"PETR4.SA",
new Date(2017,4,22),
13.4
],
[
"PETR4.SA",
new Date(2017,4,19),
13.62
],
[
"PETR4.SA",
new Date(2017,4,18),
13.15
],
[
"PETR4.SA",
new Date(2017,4,17),
15.61
],
[
"PETR4.SA",
new Date(2017,4,16),
15.7
],
[
"PETR4.SA",
new Date(2017,4,15),
15.68
],
[
"PETR4.SA",
new Date(2017,4,12),
15.45
],
[
"PETR4.SA",
new Date(2017,4,11),
14.82
],
[
"PETR4.SA",
new Date(2017,4,10),
14.73
],
[
"PETR4.SA",
new Date(2017,4,9),
14.14
],
[
"PETR4.SA",
new Date(2017,4,8),
14.08
],
[
"PETR4.SA",
new Date(2017,4,5),
14.21
],
[
"PETR4.SA",
new Date(2017,4,4),
13.6
],
[
"PETR4.SA",
new Date(2017,4,3),
14.16
],
[
"PETR4.SA",
new Date(2017,4,2),
13.99
],
[
"PETR4.SA",
new Date(2017,3,28),
13.97
],
[
"PETR4.SA",
new Date(2017,3,27),
13.73
],
[
"PETR4.SA",
new Date(2017,3,26),
14
],
[
"PETR4.SA",
new Date(2017,3,25),
14.34
],
[
"PETR4.SA",
new Date(2017,3,24),
14.03
],
[
"PETR4.SA",
new Date(2017,3,20),
13.88
],
[
"PETR4.SA",
new Date(2017,3,19),
13.6
],
[
"PETR4.SA",
new Date(2017,3,18),
14.1
],
[
"PETR4.SA",
new Date(2017,3,17),
14.28
],
[
"PETR4.SA",
new Date(2017,3,13),
14.08
],
[
"PETR4.SA",
new Date(2017,3,12),
14.65
],
[
"PETR4.SA",
new Date(2017,3,11),
14.68
],
[
"PETR4.SA",
new Date(2017,3,10),
14.94
],
[
"PETR4.SA",
new Date(2017,3,7),
14.7
],
[
"PETR4.SA",
new Date(2017,3,6),
14.53
],
[
"PETR4.SA",
new Date(2017,3,5),
14.57
],
[
"PETR4.SA",
new Date(2017,3,4),
14.85
],
[
"PETR4.SA",
new Date(2017,3,3),
14.67
],
[
"PETR4.SA",
new Date(2017,2,31),
14.49
],
[
"PETR4.SA",
new Date(2017,2,30),
14.45
],
[
"PETR4.SA",
new Date(2017,2,29),
14.45
],
[
"PETR4.SA",
new Date(2017,2,28),
13.95
],
[
"PETR4.SA",
new Date(2017,2,27),
13.77
],
[
"PETR4.SA",
new Date(2017,2,24),
13.48
],
[
"PETR4.SA",
new Date(2017,2,23),
13.57
],
[
"PETR4.SA",
new Date(2017,2,22),
13.66
],
[
"PETR4.SA",
new Date(2017,2,21),
13
],
[
"PETR4.SA",
new Date(2017,2,20),
13.6
],
[
"PETR4.SA",
new Date(2017,2,17),
13.16
],
[
"PETR4.SA",
new Date(2017,2,16),
13.71
],
[
"PETR4.SA",
new Date(2017,2,15),
14.2
],
[
"PETR4.SA",
new Date(2017,2,14),
13.59
],
[
"PETR4.SA",
new Date(2017,2,13),
14.37
],
[
"PETR4.SA",
new Date(2017,2,10),
14.31
],
[
"PETR4.SA",
new Date(2017,2,9),
14.5
],
[
"PETR4.SA",
new Date(2017,2,8),
14.55
],
[
"PETR4.SA",
new Date(2017,2,7),
15.18
],
[
"PETR4.SA",
new Date(2017,2,6),
15.1
],
[
"PETR4.SA",
new Date(2017,2,3),
15.32
],
[
"PETR4.SA",
new Date(2017,2,2),
15.11
],
[
"PETR4.SA",
new Date(2017,2,1),
15.52
],
[
"PETR4.SA",
new Date(2017,1,24),
15.18
],
[
"PETR4.SA",
new Date(2017,1,23),
15.56
],
[
"PETR4.SA",
new Date(2017,1,22),
15.7
],
[
"PETR4.SA",
new Date(2017,1,21),
16.09
],
[
"PETR4.SA",
new Date(2017,1,20),
15.92
],
[
"PETR4.SA",
new Date(2017,1,17),
15.61
],
[
"PETR4.SA",
new Date(2017,1,16),
15.86
],
[
"PETR4.SA",
new Date(2017,1,15),
15.84
],
[
"PETR4.SA",
new Date(2017,1,14),
15.82
],
[
"PETR4.SA",
new Date(2017,1,13),
15.62
],
[
"PETR4.SA",
new Date(2017,1,10),
15.58
],
[
"PETR4.SA",
new Date(2017,1,9),
15.05
],
[
"PETR4.SA",
new Date(2017,1,8),
15.1
],
[
"PETR4.SA",
new Date(2017,1,7),
14.7
],
[
"PETR4.SA",
new Date(2017,1,6),
14.96
],
[
"PETR4.SA",
new Date(2017,1,3),
15.34
],
[
"PETR4.SA",
new Date(2017,1,2),
14.89
],
[
"PETR4.SA",
new Date(2017,1,1),
15.02
],
[
"PETR4.SA",
new Date(2017,0,31),
15.02
],
[
"PETR4.SA",
new Date(2017,0,30),
14.84
],
[
"PETR4.SA",
new Date(2017,0,27),
15.62
],
[
"PETR4.SA",
new Date(2017,0,26),
15.8
],
[
"LAME4.SA",
new Date(2017,10,10),
15.31
],
[
"LAME4.SA",
new Date(2017,10,9),
15.44
],
[
"LAME4.SA",
new Date(2017,10,8),
15.83
],
[
"LAME4.SA",
new Date(2017,10,7),
15.35
],
[
"LAME4.SA",
new Date(2017,10,6),
15.76
],
[
"LAME4.SA",
new Date(2017,10,3),
15.85
],
[
"LAME4.SA",
new Date(2017,10,1),
17.08
],
[
"LAME4.SA",
new Date(2017,9,31),
17.58
],
[
"LAME4.SA",
new Date(2017,9,30),
17.25
],
[
"LAME4.SA",
new Date(2017,9,27),
17.77
],
[
"LAME4.SA",
new Date(2017,9,26),
17.66
],
[
"LAME4.SA",
new Date(2017,9,25),
18.03
],
[
"LAME4.SA",
new Date(2017,9,24),
18
],
[
"LAME4.SA",
new Date(2017,9,23),
18.01
],
[
"LAME4.SA",
new Date(2017,9,20),
18.58
],
[
"LAME4.SA",
new Date(2017,9,19),
18.39
],
[
"LAME4.SA",
new Date(2017,9,18),
18.39
],
[
"LAME4.SA",
new Date(2017,9,17),
17.99
],
[
"LAME4.SA",
new Date(2017,9,16),
18.6
],
[
"LAME4.SA",
new Date(2017,9,13),
19.22
],
[
"LAME4.SA",
new Date(2017,9,11),
19.86
],
[
"LAME4.SA",
new Date(2017,9,10),
19.94
],
[
"LAME4.SA",
new Date(2017,9,9),
19.72
],
[
"LAME4.SA",
new Date(2017,9,6),
20.01
],
[
"LAME4.SA",
new Date(2017,9,5),
20.35
],
[
"LAME4.SA",
new Date(2017,9,4),
20.2
],
[
"LAME4.SA",
new Date(2017,9,3),
19.64
],
[
"LAME4.SA",
new Date(2017,9,2),
19.12
],
[
"LAME4.SA",
new Date(2017,8,29),
19.25
],
[
"LAME4.SA",
new Date(2017,8,28),
18.73
],
[
"LAME4.SA",
new Date(2017,8,27),
18.6
],
[
"LAME4.SA",
new Date(2017,8,26),
19.02
],
[
"LAME4.SA",
new Date(2017,8,25),
19.02
],
[
"LAME4.SA",
new Date(2017,8,22),
19.53
],
[
"LAME4.SA",
new Date(2017,8,21),
19.36
],
[
"LAME4.SA",
new Date(2017,8,20),
19.67
],
[
"LAME4.SA",
new Date(2017,8,19),
20.12
],
[
"LAME4.SA",
new Date(2017,8,18),
20.14
],
[
"LAME4.SA",
new Date(2017,8,15),
19.91
],
[
"LAME4.SA",
new Date(2017,8,14),
19.51
],
[
"LAME4.SA",
new Date(2017,8,13),
19.08
],
[
"LAME4.SA",
new Date(2017,8,12),
18.9
],
[
"LAME4.SA",
new Date(2017,8,11),
19.06
],
[
"LAME4.SA",
new Date(2017,8,8),
18.8
],
[
"LAME4.SA",
new Date(2017,8,6),
18.7
],
[
"LAME4.SA",
new Date(2017,8,5),
18.13
],
[
"LAME4.SA",
new Date(2017,8,4),
18.11
],
[
"LAME4.SA",
new Date(2017,8,1),
17.86
],
[
"LAME4.SA",
new Date(2017,7,31),
17.77
],
[
"LAME4.SA",
new Date(2017,7,30),
17.94
],
[
"LAME4.SA",
new Date(2017,7,29),
17.89
],
[
"LAME4.SA",
new Date(2017,7,28),
17.68
],
[
"LAME4.SA",
new Date(2017,7,25),
17.79
],
[
"LAME4.SA",
new Date(2017,7,24),
17.63
],
[
"LAME4.SA",
new Date(2017,7,23),
17.2
],
[
"LAME4.SA",
new Date(2017,7,22),
17.13
],
[
"LAME4.SA",
new Date(2017,7,21),
17.04
],
[
"LAME4.SA",
new Date(2017,7,18),
16.93
],
[
"LAME4.SA",
new Date(2017,7,17),
16.81
],
[
"LAME4.SA",
new Date(2017,7,16),
16.52
],
[
"LAME4.SA",
new Date(2017,7,15),
16.49
],
[
"LAME4.SA",
new Date(2017,7,14),
16.38
],
[
"LAME4.SA",
new Date(2017,7,11),
15.82
],
[
"LAME4.SA",
new Date(2017,7,10),
15.25
],
[
"LAME4.SA",
new Date(2017,7,9),
15.56
],
[
"LAME4.SA",
new Date(2017,7,8),
15.7
],
[
"LAME4.SA",
new Date(2017,7,7),
15.95
],
[
"LAME4.SA",
new Date(2017,7,4),
16.07
],
[
"LAME4.SA",
new Date(2017,7,3),
16.09
],
[
"LAME4.SA",
new Date(2017,7,2),
16.15
],
[
"LAME4.SA",
new Date(2017,7,1),
15.9
],
[
"LAME4.SA",
new Date(2017,6,31),
15.67
],
[
"LAME4.SA",
new Date(2017,6,28),
15.55
],
[
"LAME4.SA",
new Date(2017,6,27),
15.5
],
[
"LAME4.SA",
new Date(2017,6,26),
15.18
],
[
"LAME4.SA",
new Date(2017,6,25),
15.22
],
[
"LAME4.SA",
new Date(2017,6,24),
15.02
],
[
"LAME4.SA",
new Date(2017,6,21),
14.76
],
[
"LAME4.SA",
new Date(2017,6,20),
14.85
],
[
"LAME4.SA",
new Date(2017,6,19),
14.65
],
[
"LAME4.SA",
new Date(2017,6,18),
14.94
],
[
"LAME4.SA",
new Date(2017,6,17),
14.98
],
[
"LAME4.SA",
new Date(2017,6,14),
15.14
],
[
"LAME4.SA",
new Date(2017,6,13),
15.2
],
[
"LAME4.SA",
new Date(2017,6,12),
15.27
],
[
"LAME4.SA",
new Date(2017,6,11),
14.88
],
[
"LAME4.SA",
new Date(2017,6,10),
14.59
],
[
"LAME4.SA",
new Date(2017,6,7),
14.35
],
[
"LAME4.SA",
new Date(2017,6,6),
13.75
],
[
"LAME4.SA",
new Date(2017,6,5),
13.97
],
[
"LAME4.SA",
new Date(2017,6,4),
13.85
],
[
"LAME4.SA",
new Date(2017,6,3),
13.88
],
[
"LAME4.SA",
new Date(2017,5,30),
14
],
[
"LAME4.SA",
new Date(2017,5,29),
13.73
],
[
"LAME4.SA",
new Date(2017,5,28),
13.75
],
[
"LAME4.SA",
new Date(2017,5,27),
13.69
],
[
"LAME4.SA",
new Date(2017,5,26),
13.9
],
[
"LAME4.SA",
new Date(2017,5,23),
13.5
],
[
"LAME4.SA",
new Date(2017,5,22),
13.25
],
[
"LAME4.SA",
new Date(2017,5,21),
13.42
],
[
"LAME4.SA",
new Date(2017,5,20),
13.6
],
[
"LAME4.SA",
new Date(2017,5,19),
13.88
],
[
"LAME4.SA",
new Date(2017,5,16),
13.9
],
[
"LAME4.SA",
new Date(2017,5,14),
14.27
],
[
"LAME4.SA",
new Date(2017,5,13),
14.25
],
[
"LAME4.SA",
new Date(2017,5,12),
14.2
],
[
"LAME4.SA",
new Date(2017,5,9),
14.4
],
[
"LAME4.SA",
new Date(2017,5,8),
14.45
],
[
"LAME4.SA",
new Date(2017,5,7),
14.65
],
[
"LAME4.SA",
new Date(2017,5,6),
14.65
],
[
"LAME4.SA",
new Date(2017,5,5),
14.43
],
[
"LAME4.SA",
new Date(2017,5,2),
14.48
],
[
"LAME4.SA",
new Date(2017,5,1),
14.33
],
[
"LAME4.SA",
new Date(2017,4,31),
14.6
],
[
"LAME4.SA",
new Date(2017,4,30),
14.89
],
[
"LAME4.SA",
new Date(2017,4,29),
15.04
],
[
"LAME4.SA",
new Date(2017,4,26),
14.93
],
[
"LAME4.SA",
new Date(2017,4,25),
14.48
],
[
"LAME4.SA",
new Date(2017,4,24),
14.56
],
[
"LAME4.SA",
new Date(2017,4,23),
14.44
],
[
"LAME4.SA",
new Date(2017,4,22),
14.01
],
[
"LAME4.SA",
new Date(2017,4,19),
14.45
],
[
"LAME4.SA",
new Date(2017,4,18),
14.4
],
[
"LAME4.SA",
new Date(2017,4,17),
17.01
],
[
"LAME4.SA",
new Date(2017,4,16),
17.08
],
[
"LAME4.SA",
new Date(2017,4,15),
17.1
],
[
"LAME4.SA",
new Date(2017,4,12),
17.15
],
[
"LAME4.SA",
new Date(2017,4,11),
17.73
],
[
"LAME4.SA",
new Date(2017,4,10),
18
],
[
"LAME4.SA",
new Date(2017,4,9),
17.34
],
[
"LAME4.SA",
new Date(2017,4,8),
17.35
],
[
"LAME4.SA",
new Date(2017,4,5),
17.5
],
[
"LAME4.SA",
new Date(2017,4,4),
17.6
],
[
"LAME4.SA",
new Date(2017,4,3),
18.03
],
[
"LAME4.SA",
new Date(2017,4,2),
18.08
],
[
"LAME4.SA",
new Date(2017,3,28),
16.84
],
[
"LAME4.SA",
new Date(2017,3,27),
16.59
],
[
"LAME4.SA",
new Date(2017,3,26),
16.75
],
[
"LAME4.SA",
new Date(2017,3,25),
16.7
],
[
"LAME4.SA",
new Date(2017,3,24),
16.66
],
[
"LAME4.SA",
new Date(2017,3,20),
16.4
],
[
"LAME4.SA",
new Date(2017,3,19),
16.01
],
[
"LAME4.SA",
new Date(2017,3,18),
16.21
],
[
"LAME4.SA",
new Date(2017,3,17),
16.05
],
[
"LAME4.SA",
new Date(2017,3,13),
15.64
],
[
"LAME4.SA",
new Date(2017,3,12),
15.9
],
[
"LAME4.SA",
new Date(2017,3,11),
16.13
],
[
"LAME4.SA",
new Date(2017,3,10),
16.15
],
[
"LAME4.SA",
new Date(2017,3,7),
16.15
],
[
"LAME4.SA",
new Date(2017,3,6),
15.9
],
[
"LAME4.SA",
new Date(2017,3,5),
15.99
],
[
"LAME4.SA",
new Date(2017,3,4),
16.11
],
[
"LAME4.SA",
new Date(2017,3,3),
16.25
],
[
"LAME4.SA",
new Date(2017,2,31),
16.36
],
[
"LAME4.SA",
new Date(2017,2,30),
16.42
],
[
"LAME4.SA",
new Date(2017,2,29),
16.45
],
[
"LAME4.SA",
new Date(2017,2,28),
16.44
],
[
"LAME4.SA",
new Date(2017,2,27),
16.06
],
[
"LAME4.SA",
new Date(2017,2,24),
16.1
],
[
"LAME4.SA",
new Date(2017,2,23),
15.9
],
[
"LAME4.SA",
new Date(2017,2,22),
15.58
],
[
"LAME4.SA",
new Date(2017,2,21),
15.48
],
[
"LAME4.SA",
new Date(2017,2,20),
15.9
],
[
"LAME4.SA",
new Date(2017,2,17),
15.65
],
[
"LAME4.SA",
new Date(2017,2,16),
16.08
],
[
"LAME4.SA",
new Date(2017,2,15),
15.91
],
[
"LAME4.SA",
new Date(2017,2,14),
15.6
],
[
"LAME4.SA",
new Date(2017,2,13),
15.86
],
[
"LAME4.SA",
new Date(2017,2,10),
15.5
],
[
"LAME4.SA",
new Date(2017,2,9),
15.8
],
[
"LAME4.SA",
new Date(2017,2,8),
16.1
],
[
"LAME4.SA",
new Date(2017,2,7),
16.94
],
[
"LAME4.SA",
new Date(2017,2,6),
17.15
],
[
"LAME4.SA",
new Date(2017,2,3),
16.62
],
[
"LAME4.SA",
new Date(2017,2,2),
16.6
],
[
"LAME4.SA",
new Date(2017,2,1),
16.65
],
[
"LAME4.SA",
new Date(2017,1,24),
16.4
],
[
"LAME4.SA",
new Date(2017,1,23),
16.92
],
[
"LAME4.SA",
new Date(2017,1,22),
16.92
],
[
"LAME4.SA",
new Date(2017,1,21),
16.9
],
[
"LAME4.SA",
new Date(2017,1,20),
17.2
],
[
"LAME4.SA",
new Date(2017,1,17),
16.76
],
[
"LAME4.SA",
new Date(2017,1,16),
16.3
],
[
"LAME4.SA",
new Date(2017,1,15),
16.2
],
[
"LAME4.SA",
new Date(2017,1,14),
16.8
],
[
"LAME4.SA",
new Date(2017,1,13),
17
],
[
"LAME4.SA",
new Date(2017,1,10),
17
],
[
"LAME4.SA",
new Date(2017,1,9),
16.96
],
[
"LAME4.SA",
new Date(2017,1,8),
16.93
],
[
"LAME4.SA",
new Date(2017,1,7),
16.94
],
[
"LAME4.SA",
new Date(2017,1,6),
16.91
],
[
"LAME4.SA",
new Date(2017,1,3),
17
],
[
"LAME4.SA",
new Date(2017,1,2),
16.5
],
[
"LAME4.SA",
new Date(2017,1,1),
16.75
],
[
"LAME4.SA",
new Date(2017,0,31),
16.73
],
[
"LAME4.SA",
new Date(2017,0,30),
16.92
],
[
"LAME4.SA",
new Date(2017,0,27),
17.45
],
[
"LAME4.SA",
new Date(2017,0,26),
17.57
],
[
"ABEV3.SA",
new Date(2017,10,10),
20.21
],
[
"ABEV3.SA",
new Date(2017,10,9),
20.22
],
[
"ABEV3.SA",
new Date(2017,10,8),
20.27
],
[
"ABEV3.SA",
new Date(2017,10,7),
20.2
],
[
"ABEV3.SA",
new Date(2017,10,6),
20.54
],
[
"ABEV3.SA",
new Date(2017,10,3),
20.6
],
[
"ABEV3.SA",
new Date(2017,10,1),
20.74
],
[
"ABEV3.SA",
new Date(2017,9,31),
20.9
],
[
"ABEV3.SA",
new Date(2017,9,30),
20.96
],
[
"ABEV3.SA",
new Date(2017,9,27),
20.91
],
[
"ABEV3.SA",
new Date(2017,9,26),
21.04
],
[
"ABEV3.SA",
new Date(2017,9,25),
21.19
],
[
"ABEV3.SA",
new Date(2017,9,24),
21.32
],
[
"ABEV3.SA",
new Date(2017,9,23),
21.3
],
[
"ABEV3.SA",
new Date(2017,9,20),
21.53
],
[
"ABEV3.SA",
new Date(2017,9,19),
21.83
],
[
"ABEV3.SA",
new Date(2017,9,18),
21.78
],
[
"ABEV3.SA",
new Date(2017,9,17),
21.75
],
[
"ABEV3.SA",
new Date(2017,9,16),
21.92
],
[
"ABEV3.SA",
new Date(2017,9,13),
22.13
],
[
"ABEV3.SA",
new Date(2017,9,11),
21.63
],
[
"ABEV3.SA",
new Date(2017,9,10),
21.56
],
[
"ABEV3.SA",
new Date(2017,9,9),
21.07
],
[
"ABEV3.SA",
new Date(2017,9,6),
21.07
],
[
"ABEV3.SA",
new Date(2017,9,5),
21.23
],
[
"ABEV3.SA",
new Date(2017,9,4),
21.2
],
[
"ABEV3.SA",
new Date(2017,9,3),
21.42
],
[
"ABEV3.SA",
new Date(2017,9,2),
20.7
],
[
"ABEV3.SA",
new Date(2017,8,29),
21.04
],
[
"ABEV3.SA",
new Date(2017,8,28),
21.06
],
[
"ABEV3.SA",
new Date(2017,8,27),
21.1
],
[
"ABEV3.SA",
new Date(2017,8,26),
21.18
],
[
"ABEV3.SA",
new Date(2017,8,25),
21.5
],
[
"ABEV3.SA",
new Date(2017,8,22),
21.52
],
[
"ABEV3.SA",
new Date(2017,8,21),
21.36
],
[
"ABEV3.SA",
new Date(2017,8,20),
21.48
],
[
"ABEV3.SA",
new Date(2017,8,19),
21.4
],
[
"ABEV3.SA",
new Date(2017,8,18),
21.2
],
[
"ABEV3.SA",
new Date(2017,8,15),
21.46
],
[
"ABEV3.SA",
new Date(2017,8,14),
21.19
],
[
"ABEV3.SA",
new Date(2017,8,13),
21.18
],
[
"ABEV3.SA",
new Date(2017,8,12),
21.01
],
[
"ABEV3.SA",
new Date(2017,8,11),
20.26
],
[
"ABEV3.SA",
new Date(2017,8,8),
20.1
],
[
"ABEV3.SA",
new Date(2017,8,6),
20.13
],
[
"ABEV3.SA",
new Date(2017,8,5),
19.82
],
[
"ABEV3.SA",
new Date(2017,8,4),
19.73
],
[
"ABEV3.SA",
new Date(2017,8,1),
19.76
],
[
"ABEV3.SA",
new Date(2017,7,31),
19.86
],
[
"ABEV3.SA",
new Date(2017,7,30),
19.88
],
[
"ABEV3.SA",
new Date(2017,7,29),
19.9
],
[
"ABEV3.SA",
new Date(2017,7,28),
19.85
],
[
"ABEV3.SA",
new Date(2017,7,25),
19.85
],
[
"ABEV3.SA",
new Date(2017,7,24),
19.8
],
[
"ABEV3.SA",
new Date(2017,7,23),
19.84
],
[
"ABEV3.SA",
new Date(2017,7,22),
19.75
],
[
"ABEV3.SA",
new Date(2017,7,21),
19.74
],
[
"ABEV3.SA",
new Date(2017,7,18),
19.76
],
[
"ABEV3.SA",
new Date(2017,7,17),
19.79
],
[
"ABEV3.SA",
new Date(2017,7,16),
19.81
],
[
"ABEV3.SA",
new Date(2017,7,15),
19.78
],
[
"ABEV3.SA",
new Date(2017,7,14),
19.71
],
[
"ABEV3.SA",
new Date(2017,7,11),
19.52
],
[
"ABEV3.SA",
new Date(2017,7,10),
19.4
],
[
"ABEV3.SA",
new Date(2017,7,9),
19.42
],
[
"ABEV3.SA",
new Date(2017,7,8),
19.39
],
[
"ABEV3.SA",
new Date(2017,7,7),
19.35
],
[
"ABEV3.SA",
new Date(2017,7,4),
19.26
],
[
"ABEV3.SA",
new Date(2017,7,3),
19.26
],
[
"ABEV3.SA",
new Date(2017,7,2),
19.4
],
[
"ABEV3.SA",
new Date(2017,7,1),
19.24
],
[
"ABEV3.SA",
new Date(2017,6,31),
19.15
],
[
"ABEV3.SA",
new Date(2017,6,28),
19.1
],
[
"ABEV3.SA",
new Date(2017,6,27),
19.11
],
[
"ABEV3.SA",
new Date(2017,6,26),
18.83
],
[
"ABEV3.SA",
new Date(2017,6,25),
18.88
],
[
"ABEV3.SA",
new Date(2017,6,24),
18.82
],
[
"ABEV3.SA",
new Date(2017,6,21),
18.81
],
[
"ABEV3.SA",
new Date(2017,6,20),
18.78
],
[
"ABEV3.SA",
new Date(2017,6,19),
18.82
],
[
"ABEV3.SA",
new Date(2017,6,18),
18.75
],
[
"ABEV3.SA",
new Date(2017,6,17),
18.84
],
[
"ABEV3.SA",
new Date(2017,6,14),
18.75
],
[
"ABEV3.SA",
new Date(2017,6,13),
18.68
],
[
"ABEV3.SA",
new Date(2017,6,12),
18.65
],
[
"ABEV3.SA",
new Date(2017,6,11),
18.52
],
[
"ABEV3.SA",
new Date(2017,6,10),
18.31
],
[
"ABEV3.SA",
new Date(2017,6,7),
18.02
],
[
"ABEV3.SA",
new Date(2017,6,6),
17.78
],
[
"ABEV3.SA",
new Date(2017,6,5),
18.22
],
[
"ABEV3.SA",
new Date(2017,6,4),
18.24
],
[
"ABEV3.SA",
new Date(2017,6,3),
18.28
],
[
"ABEV3.SA",
new Date(2017,5,30),
18.31
],
[
"ABEV3.SA",
new Date(2017,5,29),
18.25
],
[
"ABEV3.SA",
new Date(2017,5,28),
18.3
],
[
"ABEV3.SA",
new Date(2017,5,27),
18.29
],
[
"ABEV3.SA",
new Date(2017,5,26),
18.27
],
[
"ABEV3.SA",
new Date(2017,5,23),
18.24
],
[
"ABEV3.SA",
new Date(2017,5,22),
18.2
],
[
"ABEV3.SA",
new Date(2017,5,21),
18.13
],
[
"ABEV3.SA",
new Date(2017,5,20),
18.07
],
[
"ABEV3.SA",
new Date(2017,5,19),
17.87
],
[
"ABEV3.SA",
new Date(2017,5,16),
17.78
],
[
"ABEV3.SA",
new Date(2017,5,14),
18.18
],
[
"ABEV3.SA",
new Date(2017,5,13),
18.39
],
[
"ABEV3.SA",
new Date(2017,5,12),
18.08
],
[
"ABEV3.SA",
new Date(2017,5,9),
18.11
],
[
"ABEV3.SA",
new Date(2017,5,8),
18.53
],
[
"ABEV3.SA",
new Date(2017,5,7),
18.84
],
[
"ABEV3.SA",
new Date(2017,5,6),
19.07
],
[
"ABEV3.SA",
new Date(2017,5,5),
18.91
],
[
"ABEV3.SA",
new Date(2017,5,2),
18.57
],
[
"ABEV3.SA",
new Date(2017,5,1),
18.55
],
[
"ABEV3.SA",
new Date(2017,4,31),
18.71
],
[
"ABEV3.SA",
new Date(2017,4,30),
18.79
],
[
"ABEV3.SA",
new Date(2017,4,29),
18.88
],
[
"ABEV3.SA",
new Date(2017,4,26),
19.03
],
[
"ABEV3.SA",
new Date(2017,4,25),
18.92
],
[
"ABEV3.SA",
new Date(2017,4,24),
18.86
],
[
"ABEV3.SA",
new Date(2017,4,23),
18.89
],
[
"ABEV3.SA",
new Date(2017,4,22),
18.57
],
[
"ABEV3.SA",
new Date(2017,4,19),
18.62
],
[
"ABEV3.SA",
new Date(2017,4,18),
18.8
],
[
"ABEV3.SA",
new Date(2017,4,17),
19.64
],
[
"ABEV3.SA",
new Date(2017,4,16),
19.82
],
[
"ABEV3.SA",
new Date(2017,4,15),
19.74
],
[
"ABEV3.SA",
new Date(2017,4,12),
19.69
],
[
"ABEV3.SA",
new Date(2017,4,11),
19.53
],
[
"ABEV3.SA",
new Date(2017,4,10),
19.19
],
[
"ABEV3.SA",
new Date(2017,4,9),
18.95
],
[
"ABEV3.SA",
new Date(2017,4,8),
18.89
],
[
"ABEV3.SA",
new Date(2017,4,5),
18.9
],
[
"ABEV3.SA",
new Date(2017,4,4),
19.03
],
[
"ABEV3.SA",
new Date(2017,4,3),
18.56
],
[
"ABEV3.SA",
new Date(2017,4,2),
18.57
],
[
"ABEV3.SA",
new Date(2017,3,28),
18.26
],
[
"ABEV3.SA",
new Date(2017,3,27),
18.2
],
[
"ABEV3.SA",
new Date(2017,3,26),
18.21
],
[
"ABEV3.SA",
new Date(2017,3,25),
18.32
],
[
"ABEV3.SA",
new Date(2017,3,24),
18.03
],
[
"ABEV3.SA",
new Date(2017,3,20),
17.98
],
[
"ABEV3.SA",
new Date(2017,3,19),
18.1
],
[
"ABEV3.SA",
new Date(2017,3,18),
18.16
],
[
"ABEV3.SA",
new Date(2017,3,17),
18.06
],
[
"ABEV3.SA",
new Date(2017,3,13),
17.76
],
[
"ABEV3.SA",
new Date(2017,3,12),
17.67
],
[
"ABEV3.SA",
new Date(2017,3,11),
17.62
],
[
"ABEV3.SA",
new Date(2017,3,10),
18
],
[
"ABEV3.SA",
new Date(2017,3,7),
18.05
],
[
"ABEV3.SA",
new Date(2017,3,6),
17.98
],
[
"ABEV3.SA",
new Date(2017,3,5),
17.88
],
[
"ABEV3.SA",
new Date(2017,3,4),
18.11
],
[
"ABEV3.SA",
new Date(2017,3,3),
18
],
[
"ABEV3.SA",
new Date(2017,2,31),
18.24
],
[
"ABEV3.SA",
new Date(2017,2,30),
18.27
],
[
"ABEV3.SA",
new Date(2017,2,29),
18.18
],
[
"ABEV3.SA",
new Date(2017,2,28),
17.94
],
[
"ABEV3.SA",
new Date(2017,2,27),
17.79
],
[
"ABEV3.SA",
new Date(2017,2,24),
17.63
],
[
"ABEV3.SA",
new Date(2017,2,23),
17.44
],
[
"ABEV3.SA",
new Date(2017,2,22),
17.31
],
[
"ABEV3.SA",
new Date(2017,2,21),
17.42
],
[
"ABEV3.SA",
new Date(2017,2,20),
17.64
],
[
"ABEV3.SA",
new Date(2017,2,17),
17.21
],
[
"ABEV3.SA",
new Date(2017,2,16),
17.28
],
[
"ABEV3.SA",
new Date(2017,2,15),
17.3
],
[
"ABEV3.SA",
new Date(2017,2,14),
17.1
],
[
"ABEV3.SA",
new Date(2017,2,13),
17.36
],
[
"ABEV3.SA",
new Date(2017,2,10),
17.3
],
[
"ABEV3.SA",
new Date(2017,2,9),
17.3
],
[
"ABEV3.SA",
new Date(2017,2,8),
17.12
],
[
"ABEV3.SA",
new Date(2017,2,7),
16.82
],
[
"ABEV3.SA",
new Date(2017,2,6),
17.25
],
[
"ABEV3.SA",
new Date(2017,2,3),
17.39
],
[
"ABEV3.SA",
new Date(2017,2,2),
17.21
],
[
"ABEV3.SA",
new Date(2017,2,1),
17.91
],
[
"ABEV3.SA",
new Date(2017,1,24),
17.84
],
[
"ABEV3.SA",
new Date(2017,1,23),
18.13
],
[
"ABEV3.SA",
new Date(2017,1,22),
18.28
],
[
"ABEV3.SA",
new Date(2017,1,21),
18.07
],
[
"ABEV3.SA",
new Date(2017,1,20),
17.84
],
[
"ABEV3.SA",
new Date(2017,1,17),
17.9
],
[
"ABEV3.SA",
new Date(2017,1,16),
17.97
],
[
"ABEV3.SA",
new Date(2017,1,15),
18.02
],
[
"ABEV3.SA",
new Date(2017,1,14),
17.38
],
[
"ABEV3.SA",
new Date(2017,1,13),
17.25
],
[
"ABEV3.SA",
new Date(2017,1,10),
17.14
],
[
"ABEV3.SA",
new Date(2017,1,9),
16.89
],
[
"ABEV3.SA",
new Date(2017,1,8),
16.96
],
[
"ABEV3.SA",
new Date(2017,1,7),
17.02
],
[
"ABEV3.SA",
new Date(2017,1,6),
17.07
],
[
"ABEV3.SA",
new Date(2017,1,3),
17.35
],
[
"ABEV3.SA",
new Date(2017,1,2),
17.16
],
[
"ABEV3.SA",
new Date(2017,1,1),
17.32
],
[
"ABEV3.SA",
new Date(2017,0,31),
17.2
],
[
"ABEV3.SA",
new Date(2017,0,30),
16.97
],
[
"ABEV3.SA",
new Date(2017,0,27),
17.32
],
[
"ABEV3.SA",
new Date(2017,0,26),
17.31
] 
];
data.addColumn('string','bond');
data.addColumn('date','data');
data.addColumn('number','cot');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartMotionChartIDcd74d1e3f3d() {
var data = gvisDataMotionChartIDcd74d1e3f3d();
var options = {};
options["width"] = 900;
options["height"] = 450;
options["state"] = "";

    var chart = new google.visualization.MotionChart(
    document.getElementById('MotionChartIDcd74d1e3f3d')
    );
    chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
var pkgs = window.__gvisPackages = window.__gvisPackages || [];
var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
var chartid = "motionchart";
  
// Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
var i, newPackage = true;
for (i = 0; newPackage && i < pkgs.length; i++) {
if (pkgs[i] === chartid)
newPackage = false;
}
if (newPackage)
  pkgs.push(chartid);
  
// Add the drawChart function to the global list of callbacks
callbacks.push(drawChartMotionChartIDcd74d1e3f3d);
})();
function displayChartMotionChartIDcd74d1e3f3d() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  window.clearTimeout(window.__gvisLoad);
  // The timeout is set to 100 because otherwise the container div we are
  // targeting might not be part of the document yet
  window.__gvisLoad = setTimeout(function() {
  var pkgCount = pkgs.length;
  google.load("visualization", "1", { packages:pkgs, callback: function() {
  if (pkgCount != pkgs.length) {
  // Race condition where another setTimeout call snuck in after us; if
  // that call added a package, we must not shift its callback
  return;
}
while (callbacks.length > 0)
callbacks.shift()();
} });
}, 100);
}
 
// jsFooter
</script>
 
<!-- jsChart -->  
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartMotionChartIDcd74d1e3f3d"></script>
 
<!-- divChart -->
  
<div id="MotionChartIDcd74d1e3f3d" 
  style="width: 900; height: 450;">
</div>

*** {id: intraday}

<!-- MotionChart generated in R 3.4.2 by googleVis 0.6.2 package -->
<!-- Wed Nov 15 12:34:00 2017 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataMotionChartIDcd71b36fce0 () {
var data = new google.visualization.DataTable();
var datajson =
[
 [
"PETR4.SA",
new Date(2200,0,1),
15.35
],
[
"PETR4.SA",
new Date(2199,0,1),
15.41
],
[
"PETR4.SA",
new Date(2198,0,1),
15.42
],
[
"PETR4.SA",
new Date(2197,0,1),
15.4
],
[
"PETR4.SA",
new Date(2196,0,1),
15.41
],
[
"PETR4.SA",
new Date(2195,0,1),
15.4
],
[
"PETR4.SA",
new Date(2194,0,1),
15.4
],
[
"PETR4.SA",
new Date(2193,0,1),
15.41
],
[
"PETR4.SA",
new Date(2192,0,1),
15.4
],
[
"PETR4.SA",
new Date(2191,0,1),
15.38
],
[
"PETR4.SA",
new Date(2190,0,1),
15.39
],
[
"PETR4.SA",
new Date(2189,0,1),
15.43
],
[
"PETR4.SA",
new Date(2188,0,1),
15.41
],
[
"PETR4.SA",
new Date(2187,0,1),
15.4
],
[
"PETR4.SA",
new Date(2186,0,1),
15.38
],
[
"PETR4.SA",
new Date(2185,0,1),
15.39
],
[
"PETR4.SA",
new Date(2184,0,1),
15.37
],
[
"PETR4.SA",
new Date(2183,0,1),
15.35
],
[
"PETR4.SA",
new Date(2182,0,1),
15.38
],
[
"PETR4.SA",
new Date(2181,0,1),
15.35
],
[
"PETR4.SA",
new Date(2180,0,1),
15.37
],
[
"PETR4.SA",
new Date(2179,0,1),
15.35
],
[
"PETR4.SA",
new Date(2178,0,1),
15.33
],
[
"PETR4.SA",
new Date(2177,0,1),
15.32
],
[
"PETR4.SA",
new Date(2176,0,1),
15.34
],
[
"PETR4.SA",
new Date(2175,0,1),
15.38
],
[
"PETR4.SA",
new Date(2174,0,1),
15.39
],
[
"PETR4.SA",
new Date(2173,0,1),
15.42
],
[
"PETR4.SA",
new Date(2172,0,1),
15.42
],
[
"PETR4.SA",
new Date(2171,0,1),
15.44
],
[
"PETR4.SA",
new Date(2170,0,1),
15.45
],
[
"PETR4.SA",
new Date(2169,0,1),
15.45
],
[
"PETR4.SA",
new Date(2168,0,1),
15.47
],
[
"PETR4.SA",
new Date(2167,0,1),
15.48
],
[
"PETR4.SA",
new Date(2166,0,1),
15.49
],
[
"PETR4.SA",
new Date(2165,0,1),
15.49
],
[
"PETR4.SA",
new Date(2164,0,1),
15.49
],
[
"PETR4.SA",
new Date(2163,0,1),
15.5
],
[
"PETR4.SA",
new Date(2162,0,1),
15.5
],
[
"PETR4.SA",
new Date(2161,0,1),
15.5
],
[
"PETR4.SA",
new Date(2160,0,1),
15.51
],
[
"PETR4.SA",
new Date(2159,0,1),
15.52
],
[
"PETR4.SA",
new Date(2158,0,1),
15.52
],
[
"PETR4.SA",
new Date(2157,0,1),
15.51
],
[
"PETR4.SA",
new Date(2156,0,1),
15.52
],
[
"PETR4.SA",
new Date(2155,0,1),
15.53
],
[
"PETR4.SA",
new Date(2154,0,1),
15.53
],
[
"PETR4.SA",
new Date(2153,0,1),
15.54
],
[
"PETR4.SA",
new Date(2152,0,1),
15.54
],
[
"PETR4.SA",
new Date(2151,0,1),
15.55
],
[
"PETR4.SA",
new Date(2150,0,1),
15.55
],
[
"PETR4.SA",
new Date(2149,0,1),
15.56
],
[
"PETR4.SA",
new Date(2148,0,1),
15.56
],
[
"PETR4.SA",
new Date(2147,0,1),
15.58
],
[
"PETR4.SA",
new Date(2146,0,1),
15.58
],
[
"PETR4.SA",
new Date(2145,0,1),
15.56
],
[
"PETR4.SA",
new Date(2144,0,1),
15.55
],
[
"PETR4.SA",
new Date(2143,0,1),
15.55
],
[
"PETR4.SA",
new Date(2142,0,1),
15.56
],
[
"PETR4.SA",
new Date(2141,0,1),
15.57
],
[
"PETR4.SA",
new Date(2140,0,1),
15.55
],
[
"PETR4.SA",
new Date(2139,0,1),
15.55
],
[
"PETR4.SA",
new Date(2138,0,1),
15.55
],
[
"PETR4.SA",
new Date(2137,0,1),
15.57
],
[
"PETR4.SA",
new Date(2136,0,1),
15.57
],
[
"PETR4.SA",
new Date(2135,0,1),
15.58
],
[
"PETR4.SA",
new Date(2134,0,1),
15.58
],
[
"PETR4.SA",
new Date(2133,0,1),
15.58
],
[
"PETR4.SA",
new Date(2132,0,1),
15.58
],
[
"PETR4.SA",
new Date(2131,0,1),
15.58
],
[
"PETR4.SA",
new Date(2130,0,1),
15.57
],
[
"PETR4.SA",
new Date(2129,0,1),
15.55
],
[
"PETR4.SA",
new Date(2128,0,1),
15.57
],
[
"PETR4.SA",
new Date(2127,0,1),
15.58
],
[
"PETR4.SA",
new Date(2126,0,1),
15.57
],
[
"PETR4.SA",
new Date(2125,0,1),
15.57
],
[
"PETR4.SA",
new Date(2124,0,1),
15.56
],
[
"PETR4.SA",
new Date(2123,0,1),
15.59
],
[
"PETR4.SA",
new Date(2122,0,1),
15.6
],
[
"PETR4.SA",
new Date(2121,0,1),
15.6
],
[
"PETR4.SA",
new Date(2120,0,1),
15.6
],
[
"PETR4.SA",
new Date(2119,0,1),
15.6
],
[
"PETR4.SA",
new Date(2118,0,1),
15.6
],
[
"PETR4.SA",
new Date(2117,0,1),
15.62
],
[
"PETR4.SA",
new Date(2116,0,1),
15.62
],
[
"PETR4.SA",
new Date(2115,0,1),
15.62
],
[
"PETR4.SA",
new Date(2114,0,1),
15.64
],
[
"PETR4.SA",
new Date(2113,0,1),
15.66
],
[
"PETR4.SA",
new Date(2112,0,1),
15.69
],
[
"PETR4.SA",
new Date(2111,0,1),
15.67
],
[
"PETR4.SA",
new Date(2110,0,1),
15.66
],
[
"PETR4.SA",
new Date(2109,0,1),
15.65
],
[
"PETR4.SA",
new Date(2108,0,1),
15.65
],
[
"PETR4.SA",
new Date(2107,0,1),
15.66
],
[
"PETR4.SA",
new Date(2106,0,1),
15.66
],
[
"PETR4.SA",
new Date(2105,0,1),
15.66
],
[
"PETR4.SA",
new Date(2104,0,1),
15.66
],
[
"PETR4.SA",
new Date(2103,0,1),
15.68
],
[
"PETR4.SA",
new Date(2102,0,1),
15.68
],
[
"PETR4.SA",
new Date(2101,0,1),
15.67
],
[
"PETR4.SA",
new Date(2100,0,1),
15.67
],
[
"PETR4.SA",
new Date(2099,0,1),
15.65
],
[
"PETR4.SA",
new Date(2098,0,1),
15.65
],
[
"PETR4.SA",
new Date(2097,0,1),
15.63
],
[
"PETR4.SA",
new Date(2096,0,1),
15.63
],
[
"PETR4.SA",
new Date(2095,0,1),
15.61
],
[
"PETR4.SA",
new Date(2094,0,1),
15.63
],
[
"PETR4.SA",
new Date(2093,0,1),
15.63
],
[
"PETR4.SA",
new Date(2092,0,1),
15.64
],
[
"PETR4.SA",
new Date(2091,0,1),
15.66
],
[
"PETR4.SA",
new Date(2090,0,1),
15.65
],
[
"PETR4.SA",
new Date(2089,0,1),
15.66
],
[
"PETR4.SA",
new Date(2088,0,1),
15.67
],
[
"PETR4.SA",
new Date(2087,0,1),
15.67
],
[
"PETR4.SA",
new Date(2086,0,1),
15.67
],
[
"PETR4.SA",
new Date(2085,0,1),
15.67
],
[
"PETR4.SA",
new Date(2084,0,1),
15.68
],
[
"PETR4.SA",
new Date(2083,0,1),
15.68
],
[
"PETR4.SA",
new Date(2082,0,1),
15.67
],
[
"PETR4.SA",
new Date(2081,0,1),
15.67
],
[
"PETR4.SA",
new Date(2080,0,1),
15.68
],
[
"PETR4.SA",
new Date(2079,0,1),
15.69
],
[
"PETR4.SA",
new Date(2078,0,1),
15.69
],
[
"PETR4.SA",
new Date(2077,0,1),
15.72
],
[
"PETR4.SA",
new Date(2076,0,1),
15.72
],
[
"PETR4.SA",
new Date(2075,0,1),
15.7
],
[
"PETR4.SA",
new Date(2074,0,1),
15.69
],
[
"PETR4.SA",
new Date(2073,0,1),
15.7
],
[
"PETR4.SA",
new Date(2072,0,1),
15.72
],
[
"PETR4.SA",
new Date(2071,0,1),
15.71
],
[
"PETR4.SA",
new Date(2070,0,1),
15.73
],
[
"PETR4.SA",
new Date(2069,0,1),
15.73
],
[
"PETR4.SA",
new Date(2068,0,1),
15.76
],
[
"PETR4.SA",
new Date(2067,0,1),
15.75
],
[
"PETR4.SA",
new Date(2066,0,1),
15.73
],
[
"PETR4.SA",
new Date(2065,0,1),
15.76
],
[
"PETR4.SA",
new Date(2064,0,1),
15.75
],
[
"PETR4.SA",
new Date(2063,0,1),
15.76
],
[
"PETR4.SA",
new Date(2062,0,1),
15.77
],
[
"PETR4.SA",
new Date(2061,0,1),
15.77
],
[
"PETR4.SA",
new Date(2060,0,1),
15.75
],
[
"PETR4.SA",
new Date(2059,0,1),
15.74
],
[
"PETR4.SA",
new Date(2058,0,1),
15.75
],
[
"PETR4.SA",
new Date(2057,0,1),
15.75
],
[
"PETR4.SA",
new Date(2056,0,1),
15.73
],
[
"PETR4.SA",
new Date(2055,0,1),
15.73
],
[
"PETR4.SA",
new Date(2054,0,1),
15.7
],
[
"PETR4.SA",
new Date(2053,0,1),
15.73
],
[
"PETR4.SA",
new Date(2052,0,1),
15.74
],
[
"PETR4.SA",
new Date(2051,0,1),
15.74
],
[
"PETR4.SA",
new Date(2050,0,1),
15.74
],
[
"PETR4.SA",
new Date(2049,0,1),
15.74
],
[
"PETR4.SA",
new Date(2048,0,1),
15.76
],
[
"PETR4.SA",
new Date(2047,0,1),
15.74
],
[
"PETR4.SA",
new Date(2046,0,1),
15.72
],
[
"PETR4.SA",
new Date(2045,0,1),
15.72
],
[
"PETR4.SA",
new Date(2044,0,1),
15.72
],
[
"PETR4.SA",
new Date(2043,0,1),
15.7
],
[
"PETR4.SA",
new Date(2042,0,1),
15.68
],
[
"PETR4.SA",
new Date(2041,0,1),
15.67
],
[
"PETR4.SA",
new Date(2040,0,1),
15.66
],
[
"PETR4.SA",
new Date(2039,0,1),
15.66
],
[
"PETR4.SA",
new Date(2038,0,1),
15.64
],
[
"PETR4.SA",
new Date(2037,0,1),
15.64
],
[
"PETR4.SA",
new Date(2036,0,1),
15.62
],
[
"PETR4.SA",
new Date(2035,0,1),
15.63
],
[
"PETR4.SA",
new Date(2034,0,1),
15.64
],
[
"PETR4.SA",
new Date(2033,0,1),
15.62
],
[
"PETR4.SA",
new Date(2032,0,1),
15.6
],
[
"PETR4.SA",
new Date(2031,0,1),
15.61
],
[
"PETR4.SA",
new Date(2030,0,1),
15.64
],
[
"PETR4.SA",
new Date(2029,0,1),
15.64
],
[
"PETR4.SA",
new Date(2028,0,1),
15.66
],
[
"PETR4.SA",
new Date(2027,0,1),
15.68
],
[
"PETR4.SA",
new Date(2026,0,1),
15.65
],
[
"PETR4.SA",
new Date(2025,0,1),
15.66
],
[
"PETR4.SA",
new Date(2024,0,1),
15.66
],
[
"PETR4.SA",
new Date(2023,0,1),
15.67
],
[
"PETR4.SA",
new Date(2022,0,1),
15.67
],
[
"PETR4.SA",
new Date(2021,0,1),
15.67
],
[
"PETR4.SA",
new Date(2020,0,1),
15.66
],
[
"PETR4.SA",
new Date(2019,0,1),
15.66
],
[
"PETR4.SA",
new Date(2018,0,1),
15.67
],
[
"PETR4.SA",
new Date(2017,0,1),
15.69
],
[
"PETR4.SA",
new Date(2016,0,1),
15.69
],
[
"PETR4.SA",
new Date(2015,0,1),
15.66
],
[
"PETR4.SA",
new Date(2014,0,1),
15.63
],
[
"PETR4.SA",
new Date(2013,0,1),
15.64
],
[
"PETR4.SA",
new Date(2012,0,1),
15.65
],
[
"PETR4.SA",
new Date(2011,0,1),
15.64
],
[
"PETR4.SA",
new Date(2010,0,1),
15.64
],
[
"PETR4.SA",
new Date(2009,0,1),
15.66
],
[
"PETR4.SA",
new Date(2008,0,1),
15.66
],
[
"PETR4.SA",
new Date(2007,0,1),
15.66
],
[
"PETR4.SA",
new Date(2006,0,1),
15.68
],
[
"PETR4.SA",
new Date(2005,0,1),
15.67
],
[
"PETR4.SA",
new Date(2004,0,1),
15.65
],
[
"PETR4.SA",
new Date(2003,0,1),
15.69
],
[
"PETR4.SA",
new Date(2002,0,1),
15.68
],
[
"PETR4.SA",
new Date(2001,0,1),
15.69
] 
];
data.addColumn('string','bond');
data.addColumn('date','tempo');
data.addColumn('number','cot');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartMotionChartIDcd71b36fce0() {
var data = gvisDataMotionChartIDcd71b36fce0();
var options = {};
options["width"] = 900;
options["height"] = 450;
options["state"] = "";

    var chart = new google.visualization.MotionChart(
    document.getElementById('MotionChartIDcd71b36fce0')
    );
    chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
var pkgs = window.__gvisPackages = window.__gvisPackages || [];
var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
var chartid = "motionchart";
  
// Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
var i, newPackage = true;
for (i = 0; newPackage && i < pkgs.length; i++) {
if (pkgs[i] === chartid)
newPackage = false;
}
if (newPackage)
  pkgs.push(chartid);
  
// Add the drawChart function to the global list of callbacks
callbacks.push(drawChartMotionChartIDcd71b36fce0);
})();
function displayChartMotionChartIDcd71b36fce0() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  window.clearTimeout(window.__gvisLoad);
  // The timeout is set to 100 because otherwise the container div we are
  // targeting might not be part of the document yet
  window.__gvisLoad = setTimeout(function() {
  var pkgCount = pkgs.length;
  google.load("visualization", "1", { packages:pkgs, callback: function() {
  if (pkgCount != pkgs.length) {
  // Race condition where another setTimeout call snuck in after us; if
  // that call added a package, we must not shift its callback
  return;
}
while (callbacks.length > 0)
callbacks.shift()();
} });
}, 100);
}
 
// jsFooter
</script>
 
<!-- jsChart -->  
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartMotionChartIDcd71b36fce0"></script>
 
<!-- divChart -->
  
<div id="MotionChartIDcd71b36fce0" 
  style="width: 900; height: 450;">
</div>



--- .class #id 

## O que são Opções ?


> - Opções vs. Ações

> - Call vs. Put


--- .class #id  

## Black, Scholes (e Merton!!)

<div class="col3">

<p><center><img src="./assets/img/black.jpg" align="middle">
</center></p>

<p><center><img src="./assets/img/scholes.png" align="middle">
</center></p>

<p><center><img src="./assets/img/merton.jpg" align="middle">
</center></p>

</div>


--- .class #id 

## Teoria - Movimento Browniano
<br/>

Um processo estocástico $\{ X(t), t \geq 0 \}$ com espaço de estados $S=R$ é Movimento Browniano se satisfaz:

<br>

> 1. $X(0) = 0$
> 2. $X(t)$ tem incrementos independentes e estacionários
> 3. $X(t+s) - X(s) \sim  N(0,t)$


--- .class #id  

## Teoria - Equação de Black-Scholes


<p style="font-size:40px">

$$
C_{o} = S_{o}N(d_{1}) - Xe^{-rT}N(d_{2})
$$
</p>

<p style="font-size:15px">
<div class="col2">
onde,
$$
d_{1} = \frac{\ln(\frac{S_{o}}{X}) + (r + \frac{\sigma^{2}}{2})T}{\sigma\sqrt{T}}
$$

$$
d_{2} = \frac{\ln(\frac{S_{o}}{X}) + (r - \frac{\sigma^{2}}{2})T}{\sigma\sqrt{T}}
$$
ou,
$$ 
d_{2} = d_{1} - \sigma\sqrt{T}
$$

\(S_{o} = \) preço da ação; <br/>

\(X = \) preço de exercício (strike); <br/>

\(r = \) taxa de juros "risk-free"; <br/>

\(T = \) tempo até expirar; <br/>

\(\sigma = \) desvio padrão dos retornos em escala log (volatilidade)

</div>
</p>


--- &twocol 

## Exemplo - Cálculo do preço de uma Opção Call (1)
<br>

*** =left
* Preço da ação \(S_{o}\): \($62,00\)
* Preço de exercício \(X\): \($62,00\)
* Tempo até expirar \(T\): $40$ dias $\rightarrow$ \(40/365\)
* Volatilidade \(\sigma\): \(32\% \rightarrow .32\)
* Taxa de juros "risk-free": \(4\% \rightarrow .4\)

*** =right

$$
d_{1} = \frac{\ln(\frac{62}{60}) + (0.4 +\frac{(.32)^{2}}{2})\frac{40}{365}} {.32\sqrt{\frac{40}{365}}} \approx 0.4
$$

$$
d_{2} = 0.404 - 0.32\sqrt{\frac{40}{365}} \approx 0.3
$$
$$ N(d_{1}) \approx 0.6554$$
$$ N(d_{2}) \approx 0.6179$$


--- .class #id 

## Exemplo - Cálculo do preço de uma Opção Call (2)
<br>

<p style="font-size:40px">

$$
C_{o} = S_{o}N(d_{1}) - Xe^{-rT}N(d_{2})
$$
</p>

<p style="font-size:20px">

$$
C_{o} = (62)(0.6554) - [(60)e^{-0.04(\frac{40}{365})}(0.6179)]
$$

$$
C_{o} = 40.63 - (59.74)(0.6179)
$$

$$
C_{o} = \$40.63 - \$36.91 = \$3.72
$$
</p>



--- .class #id 

## Obrigado!!!


