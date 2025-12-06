---
## Front matter
title: "Отчёт по лабораторной работе 7"
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

Изучить способы создания презентации и постеров в LaTex.

# Задание

Изучить все возможные способы создания презентации и постеров, а также их функции.

# Выполнение лабораторной работы

## Презентация в beamer

Начать данную работу хотелось бы с того, как именно можно создать презентацию в LaTex. Для этого мы должны в качестве аргумента documentclass написать beamer.

Также можно задавать тему для презентации и её цвет, если он у неё есть. Для этого используется в начале документа usetheme и usecolortheme.

Он включает в себя множество разных функций, но начнем с основы.

Без слайдов не будет презентации и чтобы их создать мы каждый слайд прописываем как begin и end с надписью frame.

Первое что мы видим в презентации это титульный лист. Для того чтобы его сделать, нужно прописать данные которые на нём будут, а потом на слайде написать комманду titlepage. Пример продемонстрирован на рисунке ниже.

![pres titlepage](CSlab7photo/1.jpg)

Далее нужно создавать обычные слайды, для того чтобы было понятно о чем этот слайд в фигурных скобках рядом с frame мы можем написать его описание, которое будет сверху, это можно увидеть на изображениях ниже.

Офрмлять их уже можно по разному, можно просто написать текст внутри как продемонстрировано на изобраении ниже

![pres text on page](CSlab7photo/2.jpg)

Можно записать текст разными блоками, для этого мы пишем begin и end с block, результат этих действий виден на иллюстрации ниже

![pres block on page](CSlab7photo/3.jpg)

При этом мы можем не выводит на презентацию сразу два блока, а сделать так, чтобы они появлялись поочереди, для этого можно использовать функцию pause. При отображении в pdf , это будет выведено как два разных слайда, а в презентации это будет выглядеть, так как будто на уже на существующем слайде добавилась новая запись, ниже на рисунке представлен вид в pdf

![pres block with pause](CSlab7photo/4.jpg)

Также не обязательно оформлять все именно блоками, мы можем записывать это части в виде списка используя item, как на илюстрации ниже. Он в свою очередь тоже работает с функцией pause.

![pres item on page](CSlab7photo/5.jpg)

Однако такая запись через pause не всегда может быть удобно и есть другой аналог uncover, при его использовании в скобках необходимо указывать его номер для появления. Важно:

- 1- (надпись будет с 1-ого слайда и до последнего, если смотреть по версии pdf)
- 1-3 (надпись будет на слайде до 4-ого uncover, а после пропадет)

На изображении ниже виден код программы, а на итоговой иллюстрации взят последний итоговый слайд и выделены части вывода, которые выводятся на него друг за другом.

![uncover](CSlab7photo/6.jpg)

При этом такие же индексы мы можен использовать для item, но если мы назчем с 3, то два слайда которые создадуться до этого будут пустыми, в отличии от uncover, использовать item же для создания слайдов нам позволяет itemize, как это делать продеманстрировано на изображении ниже.

![item and uncover](CSlab7photo/7.jpg)

## Создание постеров.

Существует 3 разных способа и в зависимости от выбраного типа, отличается вид постера соответственно.

Начнем с того, что чтобы задать постер на нужно изменить documentclass.

1. тип a0poster, на изображении ниже показан пример, на нём видно как именно записывать класс, отражена возможно записи текста разного размера, добавление изображений, деление на колонки, а также изменение цвета текста (для того, чтобы изменить цвет текста необходимо добавить отдельно специальный пакет).

![poster](CSlab7photo/poster.jpg)

2. тип beamerposter, он преобразует beamer с которым мы работали и делали презентацию в постер, ниже на иллюстрации показано как делить строницу на несколько колонок, разного размера, важно, что в данном случае мы вначале документа прописываем возможность изменения цвета текста, поэтому внутри нам уже никакие строки для этого дописывать ненужно в отличии от предыдущего метода.

![beamerposter](CSlab7photo/beamerposter.jpg)

3. тип tikzposter, по-моему мнению один из самых интересных с точки зрения внешнего вида, важное отличие от других, что тут для того, чтобы что-то написать необходимо задавать блок с этой информацией и текст, изображение и прочее писать уже внутри блоков. Есть кастомный блок с заголовком. А также из очень удобных и интересных функций, внутри блока можно выделить поле для заметки, так чтобы оно при это не перекрывало текст внутри. Все это видно на изображении ниже

![tikzposter](CSlab7photo/tikzposter.jpg)

# Выводы

В процессе выполнения данной лабораторной работы я научилась создавать презентацию и постеры разного типа в среде LaTex. 

# Список литературы{.unnumbered}

::: Пособие по лабораторным работам [posobie]
