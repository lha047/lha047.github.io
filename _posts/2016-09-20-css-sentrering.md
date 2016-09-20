---
layout: post
title:  "Css sentrering"
date:   2016-09-20
categories: code post
---
Css sentrering
===========
Det finnes mange måter å sentrer elementer med CSS. Her er liten kjapp 
oppsummering av metoder jeg plukket opp fra [DevTips - Centering CSS](https://www.youtube.com/watch?v=hIG-fZ2042k#t=81.17199)

text-align
----------
```scss
.container 
    text-align: center;
.child-element
    display: inline-block;
```
Man setter `text-align: center;` på elementet som er foreldre til elementet som skal senteres. 
Dersom elementet som skal sentreres har `display: inline-block;` vil det bli sentrert vertikalt.
Dette kan brukes om man har flere elementer som skal sentreres. 

margin-auto
-----------
```scss
.element
    //display: block;
    margin: 0 auto;
    //margin-left: auto; //(bare margin-left: auto; vil flytte elementet til høyre side, slik som float: right;)
    //margin-right: auto;
```
Elementet som skal sentreres må ha `display: block;`. Da kan det sentreres ved å bruke margin attributtet med auto. 
auto justerer margin automatisk, slik at om auto brukes både på `margin-left` og `margin-right` blir elementet sentrert.
Margin presser elementet fra begge sider.

absolute-positioning
--------------------
```scss
.container
    position: relative;
.element
    position: absolute;
    left: 50%; //den venstre kanten på elementer er på 50% av plassen
    top: 50%;
    margin-left: -200px; //man må vite bredden på elemente som skal sentreres.
    margin-top: -200px;
```
Med `position: absolute` og `left: 50%` blir venstre kan av elementet plassert på 50% av bredden. Selve elementet
blir vist fra halve bredden. For å plassere elementet på midten må man vite hvor bredt elementet er slik at man kan bruke
`margin-left: -200px` til å juster elementet hvis bredden av er 400px.

translate
---------
```scss
.container
    position: relative;
.element
    position: absolute;
    left: 50%; //den venstre kanten på elementer er på 50% av plassen
    top: 50%;
    +tranform(translate(-50%, -50%))
```
Foreldre elementet er `position: relativ;` og elementer er alignet med venstre kanten 50% fra venstre og øverste kant 50% fra toppen.
Elementet er plassert med den hjørnet øverst til venstre i sentrum av siden. Med bruk av `transform` og `translate` flyttes elementet
slik at midten av elementet er sentrert i midten av foreldreelementet.


