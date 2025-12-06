---
## Front matter
title: "Отчёт по лабораторной работе №2"
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

# Цель работы

Изучить процесс создания и компиляции учебных LaTeX-документов, отработать навыки работы с разделами, оглавлением, формулами, пробелами и специальными символами, а также освоить механизм перекрёстных ссылок и многоэтапной компиляции. Дополнительно — проверить корректность генерации PDF-файлов и освоить принципы автоматической верстки текста в LaTeX.

# Ход выполнения

## Компиляция первого учебного документа

Работа началась с открытия файла `exercise-2.1.4.tex` и его компиляции в среде LaTeX.  
На скриншоте видно, как запускается компиляция, загружаются стандартные классы и шрифты, а также формируется PDF-файл `exercise-2.1.4.pdf`.

![Компиляция файла exercise-2.1.4.tex](ima1.png){ #fig:001 width=80% }

Полученный документ содержит пример формулы в режиме display math, нумерованные разделы, а также перекрёстные ссылки, демонстрирующие основы структурирования математического текста.

![Документ с разделами, формулой и ссылкой на рисунок](ima1_1.png){ #fig:002 width=80% }

## Компиляция нескольких документов и работа с оглавлением

Затем были собраны документы `exercise-2.1.4.tex` и `space-comparison.tex`.  
После компиляции была проверена корректность генерации PDF-файлов.

![Компиляция нескольких файлов и проверка наличия PDF](ima2.png){ #fig:003 width=80% }

Один из документов иллюстрирует работу автоматически созданного оглавления. Команда `\tableofcontents` формирует структуру содержания на основе разделов и подразделов.

![Документ с автоматически сгенерированным оглавлением](ima2_1.png){ #fig:004 width=80% }

Файл `exercise-2.1.4.pdf` демонстрирует обработку абзацев, различие в использовании пробелов, особенности переноса строк и логику форматирования LaTeX по умолчанию.

![Страницы упражнения 2.1.4](ima2_2.png){ #fig:005 width=80% }

## Итоговый документ и перекрёстные ссылки

Далее был создан итоговый документ `final-summary.tex`.  
Первый проход компиляции вызвал предупреждения о неразрешённых ссылках — нормальная ситуация для LaTeX.  
На втором проходе ссылки корректно обновились.

![Два прохода компиляции и предупреждения о ссылках](ima3.png){ #fig:006 width=80% }

## Документ сравнения пробелов

Документ `space-comparison.pdf` изучает различия между обычными и «жёсткими» пробелами, а также демонстрирует перенос длинных строк.

![Документ Space Comparison](ima3_1.png){ #fig:007 width=80% }

## Проверка владения материалом

Создан документ `mastery-test.tex`, включающий:

- вывод специальных символов LaTeX,
- разделение абзацев пустой строкой,
- использование неразрывных пробелов,
- демонстрацию переноса длинных предложений.

![Документ Mastery Test](ima4_1.png){ #fig:008 width=80% }

## Финальная проверка PDF-файлов

На заключительном этапе были открыты все сгенерированные PDF-файлы и проверено их наличие в рабочем каталоге.  
Все документы успешно сформированы:  
`exercise-2.1.4.pdf`, `space-comparison.pdf`, `mastery-test.pdf`.

![Проверка всех итоговых PDF-файлов](ima4.png){ #fig:009 width=80% }

# Вывод

В ходе выполнения работы:

* изучены принципы компиляции и структура LaTeX-документов;
* освоена работа с оглавлением, разделами и перекрёстными ссылками;
* протестированы механизмы обычных и неразрывных пробелов;
* проверено использование специальных символов и оформление длинных абзацев;
* успешно созданы и собраны несколько учебных PDF-документов;
* подтверждена корректная работа установленной системы LaTeX и компилятора `pdflatex`.

Все задания выполнены в полном объёме, LaTeX функционирует стабильно и корректно.
