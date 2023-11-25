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

Изучение команд условного и безусловного переходов. Приобретение навыков написания
программ с использованием переходов. Знакомство с назначением и структурой файла
листинга

# Задание

1. Создайте каталог для программам лабораторной работы № 7, перейдите в него и создайте файл lab7-1.asm:

mkdir ~/work/arch-pc/lab07
cd ~/work/arch-pc/lab07
touch lab7-1.asm

![lab7-1.asm](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab07/report/image/Screenshot from 2023-11-23 09-44-17.png)

   __Комментарий:__ Создал каталог под названием lab07. В нем создал файл с названием lab7-1.asm.
   
   
2. Инструкция jmp в NASM используется для реализации безусловных переходов. Рассмотрим пример программы с использованием инструкции jmp. Введите в файл lab7-1.asm
текст программы из листинга 7.1.

![листинг 7.1](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab07/report/image/Screenshot from 2023-11-23 14-13-57.png)  

   __Комментарий:__ Текст из листинга 7.1 я поместил в файл lab7-1.asm.
   
Создайте исполняемый файл и запустите его. Результат работы данной программы будет
следующим:

user@dk4n31:~$ ./lab7-1
Сообщение № 2
Сообщение № 3
user@dk4n31:~$


![./lab7-1](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab07/report/image/Screenshot from 2023-11-23 09-54-53.png)

   __Комментарий:__ Создал исполняемый файл и запустил его.


Таким образом, использование инструкции jmp _label2 меняет порядок исполнения
инструкций и позволяет выполнить инструкции начиная с метки _label2, пропустив вывод
первого сообщения.
Инструкция jmp позволяет осуществлять переходы не только вперед но и назад. Изменим
программу таким образом, чтобы она выводила сначала ‘Сообщение № 2’, потом ‘Сообщение
№ 1’ и завершала работу. Для этого в текст программы после вывода сообщения № 2 добавим
инструкцию jmp с меткой _label1 (т.е. переход к инструкциям вывода сообщения № 1)
и после вывода сообщения № 1 добавим инструкцию jmp с меткой _end (т.е. переход к
инструкции call quit). Измените текст программы в соответствии с листингом 7.2.

![листинг 7.2](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab07/report/image/Screenshot from 2023-11-23 14-27-22.png)

   __Комментарий:__ Я изменил текст в lab7-1.asm в соответствии с листингом 7.2.
   
Создайте исполняемый файл и проверьте его работу.
Измените текст программы добавив или изменив инструкции jmp, чтобы вывод программы был следующим:

user@dk4n31:~$ ./lab7-1
Сообщение № 3
Сообщение № 2
Сообщение № 1
user@dk4n31:~$   
     
![./lab7-1](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab07/report/image/Screenshot from 2023-11-23 10-02-58.png)      

   __Комментарий:__ Создал исполняемый файл для lab7-1.asm и запустил его.
   

3. Использование инструкции jmp приводит к переходу в любом случае. Однако, часто при
написании программ необходимо использовать условные переходы, т.е. переход должен происходить если выполнено какое-либо условие. В качестве примера рассмотрим
программу, которая определяет и выводит на экран наибольшую из 3 целочисленных
переменных: A,B и C. Значения для A и C задаются в программе, значение B вводиться с
клавиатуры.

Создайте файл lab7-2.asm в каталоге ~/work/arch-pc/lab07. Внимательно изучите текст
программы из листинга 7.3 и введите в lab7-2.asm.

![листинг 7.3](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab07/report/image/Screenshot from 2023-11-23 10-16-10.png)

   __Комментарий:__ Я создал файл lab7-2.asm в каталоге ~/work/arch-pc/lab07. Далее в созданный файл я ввел текст из листинга 7.3.
   
   
Создайте исполняемый файл и проверьте его работу для разных значений B.

![исполняемый файл](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab07/report/image/Screenshot from 2023-11-23 10-15-47.png)

   __Комментарий:__ Я создал исполняемый файл и убедился, что он работает.
   
   
4. Обычно nasm создаёт в результате ассемблирования только объектный файл. Получить
файл листинга можно, указав ключ -l и задав имя файла листинга в командной строке.
Создайте файл листинга для программы из файла lab7-2.asm

nasm -f elf -l lab7-2.lst lab7-2.asm

Откройте файл листинга lab7-2.lst с помощью любого текстового редактора, например
mcedit:

mcedit lab7-2.lst

![mcedit lab7-2.lst](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab07/report/image/Screenshot from 2023-11-23 10-19-12.png)

   __Комментарий:__ Я создал файл листинга программы в lab7-2.asm и открыл его с помощью текстового редактора mcedit.
   
   
   
Внимательно ознакомиться с его форматом и содержимым. Подробно объяснить содержимое трёх строк файла листинга по выбору.
Откройте файл с программой lab7-2.asm и в любой инструкции с двумя операндами
удалить один операнд. 

![lab7-2.asm](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab07/report/image/Screenshot from 2023-11-23 12-32-53.png) 


Выполните трансляцию с получением файла листинга:

   nasm -f elf -l lab7-2.lst lab7-2.asm  

![ nasm -f elf -l lab7-2.lst lab7-2.asm  ](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab07/report/image/Screenshot from 2023-11-23 12-33-59.png)
    
   
   
#  Задание для самостоятельной работы

1. Напишите программу нахождения наименьшей из 3 целочисленных переменных 𝑎,𝑏 и .
Значения переменных выбрать из табл. 7.5 в соответствии с вариантом, полученным
при выполнении лабораторной работы № 7. Создайте исполняемый файл и проверьте
его работу.

![sr7](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab07/report/image/Screenshot from 2023-11-24 01-38-42.png)

![sr7](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab07/report/image/Screenshot from 2023-11-23 13-39-57.png)

2. Напишите программу, которая для введенных с клавиатуры значений 𝑥 и 𝑎 вычисляет
значение заданной функции 𝑓(𝑥) и выводит результат вычислений. Вид функции 𝑓(𝑥)
выбрать из таблицы 7.6 вариантов заданий в соответствии с вариантом, полученным
при выполнении лабораторной работы № 7. Создайте исполняемый файл и проверьте
его работу для значений 𝑥 и 𝑎 из 7.6.

# Выводы

Я научился использовать команду безусловного и условного перехода. Дальше я научился писать программы с использованием переходов. Я также хорошо понял назначение и структуру файла листинга.


