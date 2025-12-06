---
## Front matter
title: "Отчёт по лабораторной работе №1"
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

Изучить базовую структуру документа LaTeX, освоить процесс компиляции с использованием `pdflatex`, разобраться с устройством преамбулы, окружений и специальных символов, а также протестировать работу минимального документа и команд для вывода специальных символов.

# Ход выполнения

## Установка TeX Live через Chocolatey

Работа началась с установки дистрибутива **TeX Live 2025** через Chocolatey. На первом этапе была проверена доступность установленного менеджера пакетов, после чего выполнена команда установки. В процессе были загружены и распакованы десятки пакетов, формирующих основу дистрибутива.

![Процесс установки TeX Live](im1.png){ #fig:001 width=80% }

По завершении установки система уведомила о необходимости обновить переменные окружения. Команда `refreshenv` в PowerShell не выполнилась, что является нормальным явлением — переменные обновляются после открытия нового окна терминала.

![Завершение установки и сообщение об обновлении окружения](im1_2.png){ #fig:002 width=80% }

## Проверка работоспособности LaTeX

После установки была выполнена серия тестов по компиляции учебных файлов из каталога `C:\LaTeX-Projet`.  

На скриншоте виден вывод компиляции одного из тестовых документов, включающий генерацию шрифтов и вспомогательных файлов.

![Компиляция тестовых документов LaTeX](im2.png){ #fig:003 width=80% }

Затем был просмотрен список созданных файлов — рядом с каждым `.tex` появился соответствующий `.pdf`, что подтверждает корректность работы TeX Live.

## Создание первого документа LaTeX

Создан минимальный документ `first.tex` со следующим содержанием:

```tex
\documentclass{article}
\usepackage[T1]{fontenc}

\begin{document}
Hey world!
This is a first document.
\end{document}
```

После запуска `pdflatex first.tex` был получен корректный PDF:

![Результат компиляции первого документа](im2_1.png){ #fig:005 width=80% }

Документ содержит две строки текста и автоматически сформированный номер страницы.

## Тестирование специальных символов

Далее был создан документ для проверки вывода специальных символов, таких как `{`, `}`, `%`, `$`, `#`, `\`, `_`, `^`, `~`.
Результат компиляции представлен ниже:

![Документ с таблицей специальных символов](im3.png){ #fig:006 width=80% }

PDF корректно отобразил таблицу коротких и длинных команд, а также пример использования жёсткого пробела (`~`).

# Вывод

В ходе работы:

* установлена и успешно протестирована система **TeX Live 2025**;
* выполнена компиляция тестовых файлов, подтверждающая корректную работу LaTeX;
* создан и собран первый минимальный LaTeX-документ;
* исследована структура документа и механизм работы со специальными символами;
* освоены базовые операции LaTeX: компиляция, анализ логов, структура документа.

Все этапы работы выполнены успешно, система LaTeX функционирует корректно.
