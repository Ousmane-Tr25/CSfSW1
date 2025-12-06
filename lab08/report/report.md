---
## Front matter
title: "Отчёт по лабораторной работе №8"
subtitle: "Computer Skills for Scientific Writing"
author: "Усман Траоре"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true
toc-depth: 2
lof: true
lot: true
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
  - \usepackage{float}
  - \floatplacement{figure}{H}
---

# Отчёт по выполнению упражнений TikZ (8.1–8.4)

## Цель работы

Освоение базовых возможностей пакета **TikZ** в среде LaTeX: построение простых линий, использование стилей, применение узлов (nodes) и создание элементарных графов.  
Также целью является проверка корректной компиляции `.tex`-файлов с TikZ-кодом и анализ сообщений, возникающих в процессе сборки.

# Ход выполнения

## Компиляция файла *tikz-1.tex* (Exercise 8.1 — Basic Drawing)

Файл был открыт и скомпилирован с помощью стандартных средств.  
При компиляции подключились необходимые пакеты (`tikz`, `pgf`), ошибок не возникло.

**Скриншот процесса компиляции:**

![Компиляция tikz-1.tex](im1.png){ #fig:001 width=90% }

**Результат работы:**

![Exercise 8.1 — рисунок](im2_1.png){ #fig:002 width=90% }

Вывод: линии и базовые формы отображаются корректно.

## 2. Компиляция *tikz-2.tex* (Exercise 8.2 — Styles and Arrows)

При запуске компиляции все зависимости были загружены автоматически.

**Скриншот компиляции:**

![Компиляция tikz-2.tex](im2.png){ #fig:003 width=90% }

**Полученный рисунок:**

![Exercise 8.2 — рисунок](im3_1.png){ #fig:004 width=90% }

Вывод: стрелки, цветные линии и геометрические фигуры отображаются корректно.

## Компиляция *tikz-3.tex* (Exercise 8.3 — Nodes and Text)

Компиляция прошла успешно: были подключены системы шрифтов и внутренние модули TikZ.

**Скриншот компиляции:**

![Компиляция tikz-3.tex](im3.png){ #fig:005 width=90% }

**Результат:**

![Exercise 8.3 — рисунок](im4_1.png){ #fig:006 width=90% }

Вывод: текстовые узлы, узлы с формами и математическими выражениями отображаются корректно.

## Компиляция *tikz-4.tex* (Exercise 8.4 — Simple Graph)

Все модули TikZ были корректно загружены, PDF успешно создан.

**Скриншот компиляции:**

![Компиляция tikz-4.tex](im5.png){ #fig:007 width=90% }

**Граф, полученный в результате:**

![Exercise 8.4 — рисунок](im5_1.png){ #fig:008 width=90% }

Вывод: граф с вершинами и пронумерованными рёбрами отображается корректно; стили рёбер применены успешно.

# Вывод

В ходе работы успешно выполнены упражнения 8.1–8.4 по TikZ.  
Удалось:

- освоить основы построения графики в TikZ,
- разобраться со стилями линий и стрелок,
- использовать узлы (nodes) для текста и форм,
- построить простой граф,
- убедиться в корректности компиляции всех `.tex`-файлов.

TikZ функционирует корректно, система TeX Live настроена правильно, ошибки компиляции отсутствуют.
