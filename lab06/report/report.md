---
## Front matter
title: "Отчёт по лабораторной работе №6"
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

Освоение использования систем управления библиографией **natbib** и **biblatex**, изучение порядка компиляции для каждого варианта, создание собственных записей в библиографической базе и исследование поведения системы при отсутствии записи в базе данных.

# Ход выполнения

## Работа с natbib и BibTeX

Для начала была выполнена компиляция документа с использованием пакета **natbib**. Запуск `pdflatex` показал, что в первом проходе отсутствуют некоторые записи в базе данных, о чём LaTeX сообщил соответствующими предупреждениями:

![Предупреждения natbib о неопределённых ссылках](im1.png){ #fig:001 width=80% }

В результате компиляции был сформирован PDF-файл, но ссылки `Graham1995` и `Thomas2008` остались неопределёнными до выполнения BibTeX.

Следующим шагом была запущена команда: `bibtex exercise-6-bibliography`

BibTeX корректно обработал файл `exercise-6-bibliography.aux` и нашёл базу данных `references.bib`:

![Запуск BibTeX и подключение базы данных](im2.png){ #fig:002 width=80% }

После выполнения BibTeX документ снова был собран двумя проходами `pdflatex`.  
В первом проходе LaTeX всё ещё предупреждал о неразрешённых ссылках — это ожидаемо, так как ссылки обновляются только на финальном этапе:

![Повторная компиляция и предупреждения natbib](im3.png){ #fig:003 width=80% }

На следующем проходе ссылки были разрешены, и финальный PDF сформировался без ошибок:

![Финальное предупреждение и завершение компиляции](im4.png){ #fig:004 width=80% }

После этого был выполнен ещё один запуск `pdflatex`:

![Последний проход pdflatex без предупреждений](im5.png){ #fig:005 width=80% }

В результате сформировался корректный документ, содержащий цитаты и список литературы, сгенерированный через BibTeX и natbib:

![Готовый PDF с оформленной библиографией через natbib](im6.png){ #fig:006 width=80% }

## Установка и использование biblatex + Biber

Для выполнения второй части задания была произведена установка необходимых компонентов:
`tlmgr update --self`
`tlmgr install biblatex biber`


Это позволило подключить пакет **biblatex** и использовать **Biber** как backend.

![Установка biblatex и biber через tlmgr](im7.png){ #fig:007 width=80% }

После установки был открыт документ `exercise-6-complete.tex`, а затем выполнены последовательные шаги компиляции:

1. `pdflatex exercise-6-complete.tex`
2. `biber exercise-6-complete`
3. `pdflatex exercise-6-complete.tex`

Запуск Biber успешно обработал файл `references.bib`:

![Запуск Biber и сбор библиографии](im8.png){ #fig:008 width=80% }

Файл `.bbl` был сгенерирован, и на финальном проходе LaTeX корректно построил всю библиографию.

## Дополнительная компиляция с biblatex

После установки необходимых пакетов был выполнен первый проход `pdflatex` для документа `exercise-6-complete.tex`.  
LaTeX корректно загрузил пакет `biblatex` и подготовил структуру документа:

![Первый проход pdflatex с biblatex](im9.png){ #fig:009 width=80% }

Затем был открыт PDF-файл, в котором отображаются сравнения методов и примеры цитирования:

![Сформированный документ с примерами работы biblatex](im10.png){ #fig:010 width=80% }

Финальный список литературы был создан автоматически:

![Библиография, созданная biblatex + biber](im10_1.png){ #fig:011 width=80% }

## Работа с файлом exercise-6-both-methods.tex

Далее был открыт документ, демонстрирующий использование **обоих методов** — BibTeX/natbib и BibLaTeX.

Команда: `bibtex exercise-6-both-methods` 
подготовила `.bbl` файл для части, использующей natbib.  
Затем два прохода `pdflatex` попытались собрать документ:

![Компиляция exercise-6-both-methods.tex](im11.png){ #fig:012 width=80% }

В первом проходе LaTeX сообщил о неопределённых ссылках, что ожидаемо до выполнения BibTeX:

![Предупреждения natbib при сборке обеих систем](im11_1.png){ #fig:013 width=80% }

После генерации `.bbl` файл был успешно подключён:

Полученный PDF вывел корректные текстовые, скобочные и множественные цитирования:

`Textual: Graham et al. [1995]`
`Parenthetical: [Thomas et al., 2008]`
`Multiple: [Graham et al., 1995, Thomas et al., 2008]`

Ниже — итоговый вид документа, сформированного с использованием обоих методов библиографии:

![Итоговый PDF для обоих методов](im11_2.png){ #fig:015 width=80% }

# Вывод

Оба подхода к формированию библиографии — **BibTeX/natbib** и **BibLaTeX/Biber** — были успешно применены. Опробованы различные типы цитирования, добавлены новые записи в базу данных и протестировано поведение при отсутствии ключей. Продемонстрированы числовые стили и автоматическая генерация списка литературы. Каждый метод корректно формирует ссылки после выполнения необходимой последовательности компиляции.
