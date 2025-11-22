---
## Front matter
title: "Отчёт по лабораторной работе 6"
author: "Супонина Анастасия Павловна"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
  - spelling=modern
  - babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Изучить способы добавления списка литературы в LaTex.

# Задание

Изучить для возможных метода для добления списка литературы.

# Выполнение лабораторной работы

## Файл bib

Для того, чтобы добавлять список литературы и ссылки на неё внутри документа необходимо создать файл с расширением bib, в котором оа будет записана для добавления

![Список источнико](CSlab6photo/Bib.jpg)

Зеленым цыетом выделен формат записи для ссылок, где в первых двух используется формат обозначения Автор + год, таким образом они будут в дальнейшем именоваться при ссылке.

Для того, чтобы их использовать существует два различных способа, мы их рассмотрим ниже.

## natbib

Пакет natbib работает с BibTex, является достаточно удобным в использовании. Пакет natbib предлагает как текстовые, так и скобочные стили цитирования, \citet и \citep соответственно. Указания стиля записи и название файла, откуда берется информация о литературе, записывается в конце, при помощи bibliographystyle и bibliography соответвественно. В bibliography файл можно записать не дописывая расширение.

Если нужно добавить дополнительную информацию она добавляется в квадратных скобках перед названием источника. В natbib необходимо указывать записи p. и pp., biblatex же добавляет их самостоятельно, что будет видно позже.

При первой компиляции через LuaLaTex в документе будут вопросительные знаки, чтобы прочитать файл bib и скомпилировать необходимо запустить этот документ через BibTex, а потом снова ещё 2 раза через LuaLaTex и именно тогда вы увидите конечный результат, который представлен на изображении ниже.

![natbib](Cslab6photo/natbib.JPG)

## biblatex

Пакет biblatex, также предназначен для работы с литературой, но имеет ряд отличий. Первое и очень важное это что стиль и исходный документ записываются в самом начале и распространяются на весь документ. Также файл со списком источников необходимо указывать в полной записи(с расширением). 

Стиль задается в квадратных скобках перед названием пакета, а документ обозначается при помощи addbibresource. 

Как уже упоминалось ранее станицы в данном пакете указываются только цифрами, в отличии от natbib. 

Также имеет большее количество вариантов записи ссылки внутри текста **parencite**, **textcite** или **citetitle**, наглядная разница между которыми видна на изображении ниже.

А в конце для отдельной записи всего списка литературы, необходимо прописывать **printbibliography**.

![biblatex](Cslab6photo/biblatex.JPG)

# Выводы

В процессе выполнения данной лабораторной работы я научилась добавлять и редактировать список литературы в среде LaTex. 

# Список литературы{.unnumbered}

::: Пособие по лабораторным работам [posobie]
