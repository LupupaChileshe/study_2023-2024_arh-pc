---
## Front matter
title: "Шаблон отчёта по лабораторной работе"
subtitle: "Простейший вариант"
author: "Лупупа Чилеше"
## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
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
	- babelshorthands=
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
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

Целью работы является освоение процедуры оформления отчетов с помощью легковесного
языка разметки Markdown.

# Задание

#  Порядок выполнения лабораторной работы

1. Откройте терминал 

![терминал](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab03/report/image/Screenshot from 2023-10-14 16-03-45.png)

  __комментарий__:Открыть терминал


2. Перейдите в каталог курса сформированный при выполнении лабораторной работы №2 

![каталог курс](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab03/report/image/Screenshot from 2023-10-14 16-09-39.png)

 Обновите локальный репозиторий, скачав изменения из удаленного репозитория с помо-
щью команды git pull. 


 ![git pull](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab03/report/image/Screenshot from 2023-10-14 16-12-14.png)
 
  __комментарий__:Обновил свой рабочий репозиторий с помощью команды git pull.
 
 
 
 3. Перейдите в каталог с шаблоном отчета по лабораторной работе № 3 

 
 ![каталог с шаблоном отчета по лабораторной работе № 3](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab03/report/image/Screenshot from 2023-10-14 16-16-59.png)
 
  __комментарий__:Перешёл в каталог с шаблоном отчета по лабораторной работе № 3
 
 
 
 4. Проведите компиляцию шаблона с использованием Makefile. Для этого введите ко-
манду(рис.
make

![make](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab03/report/image/Screenshot from 2023-10-14 16-22-48.png)

При успешной компиляции должны сгенерироваться файлы report.pdf и report.docx.
Откройте и проверьте корректность полученных файлов

  __комментарий__:Скомпилировал шаблон командой *make*
               Я убедился, что компиляция прошла успешно, используя команду ls



5. Удалите полученный файлы с использованием Makefile. Для этого введите команду
make clean

![make clean](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab03/report/image/Screenshot from 2023-10-14 16-26-09.png)

Проверьте, что после этой команды файлы report.pdf и report.docx были удалены.
  
  __комментарий__:Удалил все полученные файлы с помощью Makefile.



6. Откройте файл report.md c помощью любого текстового редактора, например gedit
gedit report.md

![gedit report.md](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab03/report/image/Screenshot from 2023-10-14 16-39-26.png)

  __комментарий__: Открыл файл report.md


# Выводы

Научились работать с легким языком разметки Markdown.



