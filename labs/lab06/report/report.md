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

Освоение арифметических инструкций языка ассемблера NASM.

# Задание

1. Создайте каталог для программам лабораторной работы № 6, перейдите в него и
создайте файл lab6-1.asm:

mkdir ~/work/arch-pc/lab06
cd ~/work/arch-pc/lab06
touch lab6-1.asm

![lab6-1.asm](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab06/report/image/Screenshot from 2023-11-16 01-13-14.png)

   __КОММЕНТАРИЙ:__ Создал новый файл с именем lab6-1.asm. 


2. Рассмотрим примеры программ вывода символьных и численных значений. Программы будут выводить значения записанные в регистр eax.
Введите в файл lab6-1.asm текст программы из листинга 6.1.

![листинга 6.1.](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab06/report/image/Screenshot from 2023-11-16 01-24-38.png)

  
![листинга 6.1](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab06/report/image/Screenshot from 2023-11-16 01-38-52.png)

    __КОММЕНТАРИЙ:__ В файл, который я сделал, я вставил текст из листинга 6.1.Мне нужно было убедиться, что файл in_out.asm также находится в созданном мной каталоге.
 
 
  Создайте исполняемый файл и запустите его.
  
![исполняемый файл](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab06/report/image/Screenshot from 2023-11-16 01-41-31.png) 


3. Далее изменим текст программы и вместо символов, запишем в регистры числа. Исправьте текст программы (Листинг 6.1) следующим образом: замените строки 

     mov eax,'6'
     mov ebx,'4'

     на строки
 
     mov eax,6
     mov ebx,4

![](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab06/report/image/Screenshot from 2023-11-16 01-44-26.png)


Создайте исполняемый файл и запустите его.

![исполняемый файл Листинг 6.1 ](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab06/report/image/Screenshot from 2023-11-16 01-48-29.png)

 __КОММЕНТАРИЙ:__ Изменил текст в программе на mov eax,6  mov ebx,4.И создал исполняемый файл


4. Как отмечалось выше, для работы с числами в файле in_out.asm реализованы подпрограммы для преобразования ASCII символов в числа и обратно. Преобразуем текст
программы из Листинга 6.1 с использованием этих функций.


Создайте файл lab6-2.asm в каталоге ~/work/arch-pc/lab06 и введите в него текст программы из листинга 6.2.


![lab6-2.asm ](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab06/report/image/Screenshot from 2023-11-16 02-07-03.png)

![листинга 6.2](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab06/report/image/Screenshot from 2023-11-16 02-08-37.png)
   
Создайте исполняемый файл и запустите его

![исполняемый файл листинга 6.2 ](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab06/report/image/Screenshot from 2023-11-16 02-11-08.png)


  __КОММЕНТАРИЙ:__ я создал файл под названием lab6-2 в каталоге lab06 и в него вставил текст из листинга 6.2.

5. Аналогично предыдущему примеру изменим символы на числа. Замените строки
  
   mov eax,'6'
   mov ebx,'4'

   на строки
   
   mov eax,6
   mov ebx,4


![](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab06/report/image/Screenshot from 2023-11-16 02-12-27.png)


Замените функцию iprintLF на iprint. Создайте исполняемый файл и запустите его. Чем
отличается вывод функций iprintLF и iprint?

![iprint](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab06/report/image/Screenshot from 2023-11-16 09-30-48.png)

 
    __КОММЕНТАРИЙ:__ Я поменял цифры на символы, сменил iprintLF на iprint. Далее я создал исполняемый файл
    
    
## Выполнение арифметических операций в NASM

6. В качестве примера выполнения арифметических операций в NASM приведем программу вычисления арифметического выражения 𝑓(𝑥) = (5 ∗ 2 + 3)/3.

Создайте файл lab6-3.asm в каталоге ~/work/arch-pc/lab06:

touch ~/work/arch-pc/lab06/lab6-3.asm

![lab6-3.asm](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab06/report/image/Screenshot from 2023-11-16 09-33-05.png)

Внимательно изучите текст программы из листинга 6.3 и введите в lab6-3.asm.
 
![листинга 6.3](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab06/report/image/Screenshot from 2023-11-18 15-24-55.png)

Создайте исполняемый файл и запустите его. Результат работы программы должен быть
следующим:

   user@dk4n31:~$ ./lab6-3
   Результат: 4
   Остаток от деления: 1
   user@dk4n31:~$
 
 
 ![исполняемый файл листинга 6.3](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab06/report/image/Screenshot from 2023-11-16 09-47-05.png)

   __КОММЕНТАРИЙ:__ Я создал файл под названием lab6-3.asm и вставил в него текст из листинга 6.3. ДАЛЬШЕ мне пришлось создать исполняемый файл, чтобы увидеть результаты
  
  
 Измените текст программы для вычисления выражения 𝑓(𝑥) = (4 ∗ 6 + 2)/5. Создайте
исполняемый файл и проверьте его работу.


![исполняемый файл 2](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab06/report/image/Screenshot from 2023-11-16 09-51-58.png)

  __КОММЕНТАРИЙ:__ Я изменил текст программы для решения выражения
 
7. В качестве другого примера рассмотрим программу вычисления варианта задания по
номеру студенческого билета, работающую по следующему алгоритму:
   
   • вывести запрос на введение № студенческого билета
   • вычислить номер варианта по формуле: (𝑆𝑛 mod 20) + 1, где 𝑆𝑛 – номер студенческого билета (В данном случае 𝑎 mod 𝑏 – это остаток от деления 𝑎 на 𝑏).
   • вывести на экран номер варианта. 
 
 
 Создайте файл variant.asm в каталоге ~/work/arch-pc/lab06:

    touch ~/work/arch-pc/lab06/variant.asm
 
![variant.asm](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab06/report/image/Screenshot from 2023-11-16 09-56-04.png)


Внимательно изучите текст программы из листинга 6.4 и введите в файл variant.asm

![листинга 6.4](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab06/report/image/Screenshot from 2023-11-18 15-40-03.png)

Создайте исполняемый файл и запустите его. Проверьте результат работы программы вычислив номер варианта аналитически.

![исполняемый файл листинга 6.4](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab06/report/image/Screenshot from 2023-11-16 10-06-06.png)
 
  __КОММЕНТАРИЙ:__ Я создал файл variant.asm. В этот файл я вставил текст из листинга 6.4. Далее я создал исполняемый файл
  
     1. Какие строки листинга 6.4 отвечают за вывод на экран сообщения ‘Ваш вариант:’?
     
     mov eax,rem
     call sprint
     mov eax,edx
     call iprintLF
     
     2. Для чего используется следующие инструкции?

    mov ecx, x
    mov edx, 80
    call sread 
 
 
        mov ecx, x: Эта команда перемещает значение x в регистр ECX. Здесь x может быть либо константой, либо адресом памяти, в котором хранится значение x 2.
     
        mov edx, 80: Эта команда перемещает значение 80 в регистр EDX 2.
 
        call sread: Эта команда вызывает функцию sread. В контексте вызова функции, значения в регистрах ECX и EDX используются в качестве аргументов функции sread. Функция sread не определена в       предоставленных исходниках, но обычно она читает данные из указанного источника 6
 
    
    3. Для чего используется инструкция “call atoi”?
    
    - Функция atoi в языке программирования C используется для преобразования строки в целочисленное значение. Она принимает строку в качестве аргумента и возвращает ее значение в виде целого числа. Название atoi происходит от "ASCII to Integer", что означает "преобразование ASCII в целое число
    
    4. Какие строки листинга 6.4 отвечают за вычисления варианта?
    
    xor edx,edx
    mov ebx,20
    div ebx
    inc edx
   
    5. В какой регистр записывается остаток от деления при выполнении инструкции “div ebx”?
    
    - Разорвано в регистре eax
 
    6. Для чего используется инструкция “inc edx”?
    
    - В контексте inc edx edx — это 32-битный регистр общего назначения. Эта инструкция увеличивает значение в регистре edx на единицу.
    
    7. Какие строки листинга 6.4 отвечают за вывод на экран результата вычислений?
    
    mov eax,rem
    call sprint
    mov eax,edx
    call iprintLF
 

# Задание для самостоятельной работы

Вариант 15

Написать программу вычисления выражения 𝑦 = 𝑓(𝑥). Программа должна выводить
выражение для вычисления, выводить запрос на ввод значения 𝑥, вычислять заданное выражение в зависимости от введенного 𝑥, выводить результат вычислений. Вид
функции 𝑓(𝑥) выбрать из таблицы 6.3 вариантов заданий в соответствии с номером
полученным при выполнении лабораторной работы. Создайте исполняемый файл и
проверьте его работу для значений 𝑥1 и 𝑥2 из 6.3.


![Вариант 15](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab06/report/image/Screenshot from 2023-11-18 16-07-42.png)


  __КОММЕНТАРИЙ:__ Создал файл под названием independentWork.asm В этом файле я написал код, позволяющий решить выражение для варианта 15.
  
  
![исполняемый файл](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab06/report/image/Screenshot from 2023-11-18 19-18-33.png) 
 
  __КОММЕНТАРИЙ:__ Создал исполняемый файл.
  
  

# Выводы

Я приобрел навыки арифметических инструкций на языке ассемблера nasm.
