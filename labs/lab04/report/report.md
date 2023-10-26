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

Освоение процедуры компиляции и сборки программ, написанных на ассемблере NASM.

# Задание

## Программа Hello world!

1. Рассмотрим пример простой программы на языке ассемблера NASM. Традиционно первая
программа выводит приветственное сообщение Hello world! на экран.
Создайте каталог для работы с программами на языке ассемблера NASM:

mkdir -p ~/work/arch-pc/lab04

![mkdir -p ~/work/arch-pc/lab04](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab04/report/image/Screenshot from 2023-10-26 13-17-49.png)

__комментарий:__ Создан каталог для работы с программой на языке ассемблера NASM.

2. Перейдите в созданный каталог:

     cd ~/work/arch-pc/lab04

![cd ~/work/arch-pc/lab04](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab04/report/image/Screenshot from 2023-10-26 13-18-18.png)

__комментарий:__изменил каталог на созданный каталог


3. Создайте текстовый файл с именем hello.asm

![hello.asm](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab04/report/image/Screenshot from 2023-10-26 13-19-45.png) 

__комментарий:__Создал текстовый файл под названием hello.asm.


4. откройте этот файл с помощью любого текстового редактора, например, gedit

![gedit](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab04/report/image/Screenshot from 2023-10-26 20-35-22.png)

__комментарий:__открыл файл с помощью текстового редактора gedit


## Транслятор NASM

5. NASM превращает текст программы в объектный код. Например, для компиляции приведённого выше текста программы «Hello World» необходимо написать:

      nasm -f elf hello.asm
      
![nasm -f elf hello.asm](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab04/report/image/Screenshot from 2023-10-26 13-28-07.png)

__комментарий:__скомпилировал текст программы hello world


## Расширенный синтаксис командной строки NASM

6. Выполните следующую команду:
    
    nasm -o obj.o -f elf -g -l list.lst hello.asm 

![ obj.o](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab04/report/image/Screenshot from 2023-10-26 13-28-47.png)

 __комментарий__:скомпилировал файл в obj.o И использовал команду ls, чтобы проверить, был ли создан файл.



##  Компоновщик LD  

7. Как видно из схемы на рис. 4.3, чтобы получить исполняемую программу, объектный файл
необходимо передать на обработку компоновщику:

     ld -m elf_i386 hello.o -o hello
     
![ ld](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab04/report/image/Screenshot from 2023-10-26 21-01-57.png)


__комментарий__:Передал целевой файл компоновщику для обработки.

![ls](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab04/report/image/Screenshot from 2023-10-26 13-29-54.png)


8. Ключ -o с последующим значением задаёт в данном случае имя создаваемого исполняемого файла.
Выполните следующую команду:

     ld -m elf_i386 obj.o -o main

![ ключа -o ](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab04/report/image/Screenshot from 2023-10-26 13-30-45.png)

__комментарий:__с помощью ключа -o я указал имя создаваемого исполняемого файла


9. Запустить на выполнение созданный исполняемый файл, находящийся в текущем каталоге,
можно, набрав в командной строке:

     ./hello

![hello](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab04/report/image/Screenshot from 2023-10-26 13-31-19.png)

__комментарий:__Созданный исполняемый файл, расположенный в текущем каталоге, я запускаю с помощью команды ./hello



## Задание для самостоятельной работы


1.  В каталоге ~/work/arch-pc/lab04 с помощью команды cp создайте копию файла
hello.asm с именем lab4.asm          
      
![cp ](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab04/report/image/Screenshot from 2023-10-26 13-37-52.png)

![cp.2](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab04/report/image/Screenshot from 2023-10-27 00-41-17.png)

__комментарий:__ скопировал и изменил имя файла hello.asm на lab4.asm

2. С помощью любого текстового редактора внесите изменения в текст программы в
файле lab4.asm так, чтобы вместо Hello world! на экран выводилась строка с вашими
фамилией и именем.


![Лупупа Чилеше](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab04/report/image/Screenshot from 2023-10-27 00-34-03.png)

__комментарий:__ изменил hello world на свое имя

3. Оттранслируйте полученный текст программы lab4.asm в объектный файл. Выполните
компоновку объектного файла и запустите получившийся исполняемый файл.

![объектный файл.](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab04/report/image/Screenshot from 2023-10-26 13-47-26.png)

__комментарий:__ Перевел полученный текст программы lab4.asm в объектный файл.

4. Скопируйте файлы hello.asm и lab4.asm в Ваш локальный репозиторий в каталог ~/work/study/2023-2024/"Архитектура компьютера"/arch-pc/labs/lab04/.
Загрузите файлы на Github.

![github](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab04/report/image/Screenshot from 2023-10-27 00-59-09.png)

__комментарий:__ скопируйте файлы hello.asm и lab4.asm в мой репозиторий на github.

# Выводы

Освоил навык компиляции и ассемблирования программ, написанных на ассемблере NASM.


