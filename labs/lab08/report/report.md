---
## Front matter
title: "Шаблон отчёта по лабораторной работе"
subtitle: "Простейший вариант"
author: "Лупупа Чилеще"

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
	- babelshorthands=true
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

Приобретение навыков написания программ с использованием циклов и обработкой
аргументов командной строки.

# Задание

1. Создайте каталог для программам лабораторной работы № 8, перейдите в него и создайте
файл lab8-1.asm:

![lab8-1.asm](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab08/report/image/Screenshot from 2023-11-30 13-52-54.png)

   __комментарий:__ Создал каталог для lab 8 и в нем создал файл lab8-1asm.
   

2. Введите в файл lab8-1.asm текст программы из листинга 8.1. Создайте исполняемый файл
и проверьте его работу.

![листинг 8.1](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab08/report/image/Screenshot from 2023-11-30 13-52-14.png)


![исполняемый файл](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab08/report/image/Screenshot from 2023-11-30 13-52-38.png)
   
   __комментарий:__ Я внимательно изучил текст в листинге 8.1, вложил его в созданный файл и сделал исполняемый файл.
   
 
3. Измените текст программы добавив изменение
значение регистра ecx в цикле:

label:
 sub ecx,1 ; `ecx=ecx-1`
 mov [N],ecx
 mov eax,[N]
 call iprintLF
 loop label

![ecx=ecx-1`](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab08/report/image/Screenshot from 2023-11-30 14-03-44.png)


4. Создайте исполняемый файл и проверьте его работу

![ecx=ecx-1`](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab08/report/image/Screenshot from 2023-11-30 14-02-12.png)

   __комментарий:__ Я изменил текст программы, изменив в цикле значение регистра ecx
   
   
5. Внесите изменения в текст программы добавив команды push
и pop (добавления в стек и извлечения из стека) для сохранения значения счетчика цикла
loop:

label:
push ecx          ; добавление значения ecx в стек
sub ecx,1
mov [N],ecx
mov eax,[N]
call iprintLF
pop ecx           ; извлечение значения ecx из стека
loop label

![](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab08/report/image/Screenshot from 2023-11-30 14-04-27.png)

  __комментарий:__ Я внес изменения в текст, включив команды push и pop для сохранения значения счетчика цикла.
  
  
6. Создайте исполняемый файл и проверьте его работу

![исполняемый файл](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab08/report/image/Screenshot from 2023-11-30 14-08-56.png)

   __комментарий:__ создал исполняемый файл для файла после изменения текста
    

7. Создайте файл lab8-2.asm в каталоге ~/work/arch-pc/lab08 и введите в него текст программы из листинга 8.2.
Создайте исполняемый файл и запустите его, указав аргументы:

user@dk4n31:~$ ./lab8-2 аргумент1 аргумент 2 'аргумент 3'

![листинг 8.2](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab08/report/image/Screenshot from 2023-11-30 14-19-19.png)

   __комментарий:__ Создал файл с именем lab8-2.asm. Я внимательно изучил содержимое листинга 8.2 и поместил его в созданный файл. Далее я создал исполняемый файл
   

8. Создайте файл lab8-3.asm в каталоге ~/work/archpc/lab08 и введите в него текст программы из листинга 8.3.

Создайте исполняемый файл и запустите его, указав аргументы. Пример результата работы
программы:

user@dk4n31:~$ ./main 12 13 7 10 5
Результат: 47
user@dk4n31:~$

![lab8-3.asm ](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab08/report/image/Screenshot from 2023-11-30 14-34-22.png)

   __комментарий:__ Я создал файл lab8-3.asm и поместил в него содержимое листинга 8.3. Далее я создал для созданного файла исполняемый файл
   
##  Задание для самостоятельной работы

Вариант 15: 6𝑥 + 13

![Самостоятельная работа](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab08/report/image/Screenshot from 2023-12-02 18-36-00.png)

![Самостоятельная работа](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab08/report/image/Screenshot from 2023-11-30 14-44-40.png)

   __комментарий:__ Я создал файл для самостоятельной работы. В нем я написал текст для ответа на 15 вопрос.
   
   


# Выводы

Я научился писать программы с использованием циклов и обработки.
аргументы командной строки.

