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

Приобретение практических навыков работы в Midnight Commander. Освоение инструкций
языка ассемблера mov и int.

# Задание

## Порядок выполнения лабораторной работы

1. Откройте Midnight Commander

    __user@dk4n31:~$ mc__
  
![mc](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-09 09-27-10.png)

    __комментарий__:Открыл Midnight Commander на терминале
    

2. Пользуясь клавишами ↑ , ↓ и Enter перейдите в каталог ~/work/arch-pc созданный
при выполнении лабораторной работы №4


    __комментарий__:С помощью стрелки Enter и клавиш я открыл каталог Arch-PC.


3. С помощью функциональной клавиши F7 создайте папку lab05  и перейдите
в созданный каталог  

![~/work/arch-pc](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-09 09-28-50.png)


    __комментарий__:Используя функциональную клавишу F7, я создал папку  lab05.
   
   
4. Пользуясь строкой ввода и командой touch создайте файл lab5-1.asm 

 ![lab5-1.asm ](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-09 09-31-02.png)
 
 
    __комментарий__:С помощью команды touch я создал ассемблерный файл lab5-1.asm.
 

5. С помощью функциональной клавиши F4 откройте файл lab5-1.asm для редактирования во встроенном редакторе.

![nano](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-09 09-35-47.png)    


    __комментарий__:Я открыл файл lab5-1.asm.
   

6. Введите текст программы из листинга 5.1 (можно без комментариев), сохраните изменения и закройте файл.

![листинга 5.1](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-09 10-00-55.png)  

    __комментарий__:Текст из листинга 5.1 я скопировал в файл lab5-1.asm.

 
 7. С помощью функциональной клавиши F3 откройте файл lab5-1.asm для просмотра.
Убедитесь, что файл содержит текст программы.

![f3](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-09 10-05-43.png)

    __комментарий__:С помощью функциональной клавиши f3 я просмотрел, чтобы убедиться, что файл сохранен.
 
 
 8. Оттранслируйте текст программы lab5-1.asm в объектный файл. Выполните компоновку объектного файла и запустите получившийся исполняемый файл. Программа выводит строку 'Введите строку:' и ожидает ввода с клавиатуры. На запрос введите Ваши ФИО.

![объектный файл](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-09 10-12-51.png)

![объектный файл](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-09 10-13-59.png)

    __комментарий__:Перевел текст программы lab5-1.asm в объектный файл


9. Скачайте файл in_out.asm со страницы курса в ТУИС.

![in_out.asm](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-09 13-48-30.png)


    __комментарий__:Скачал файл со страницы курса в ТУИС.
    
 
10. Подключаемый файл in_out.asm должен лежать в том же каталоге, что и файл с программой, в которой он используется.    

В одной из панелей mc откройте каталог с файлом lab5-1.asm. В другой панели каталог
со скаченным файлом in_out.asm (для перемещения между панелями используйте Tab ).
Скопируйте файл in_out.asm в каталог с файлом lab5-1.asm с помощью функциональной
клавиши F5.

![Перенос в каталог lab05](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-09 13-53-35.png)
    
    
    __комментарий__:Передайте скачанный файл в лабораторию 5.
    

11. С помощью функциональной клавиши F6 создайте копию файла lab5-1.asm с именем
lab5-2.asm. Выделите файл lab5-1.asm, нажмите клавишу F6 , введите имя файла
lab5-2.asm и нажмите клавишу Enter.

![lab5-2.asm.](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-11 20-58-54.png)
    
    
![lab5-2.asm.](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-11 20-42-42.png)


12. Исправьте текст программы в файле lab5-2.asm с использование подпрограмм из
внешнего файла in_out.asm (используйте подпрограммы sprintLF, sread и quit) в
соответствии с листингом 5.2. Создайте исполняемый файл и проверьте его работу.


![sprintLF, sread и quit](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-11 22-41-02.png)   
    
    
    
    __комментарий__:Исправил текст программы в файле lab5-2.asm с помощью подпрограммы из внешнего файла in_out.asm  


13. В файле lab5-2.asm замените подпрограмму sprintLF на sprint. Создайте исполняемый файл и проверьте его работу. В чем разница?
   
![sprint](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-11 22-41-16.png)   


   __комментарий__:Я изменил srintLF на sprint.
   
   
![](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-11 22-42-14.png)








# Задание для самостоятельной работы

1. Создайте копию файла lab5-1.asm. Внесите изменения в программу (без использования внешнего файла in_out.asm), так чтобы она работала по следующему алгоритму:
  • вывести приглашение типа “Введите строку:”;
  • ввести строку с клавиатуры;
  • вывести введённую строку на экран.

![lab5-3.asm](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-11 22-50-47.png)


![lab5-3.asm](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-11 23-25-46.png)


2. Получите исполняемый файл и проверьте его работу. На приглашение ввести строку
введите свою фамилию.


![lab5-3.asm](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-11 22-58-10.png)



3. Создайте копию файла lab5-2.asm. Исправьте текст программы с использование подпрограмм из внешнего файла in_out.asm, так чтобы она работала по следующему
  алгоритму:
   • вывести приглашение типа “Введите строку:”;
   • ввести строку с клавиатуры;
   • вывести введённую строку на экран. 
   
![](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-11 22-59-53.png)  

![](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-11 23-00-37.png) 


4. Создайте исполняемый файл и проверьте его работу.

![](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-11 23-00-05.png)

![](/home/lupupachileshe/work/study/2023-2024/Архитектура_компьютера/arch_pc/study_2023-2024_arh-pc/labs/lab05/report/image/Screenshot from 2023-11-11 23-02-05.png)


# Выводы


Я научился работать с Midnight Commander и языком ассемблера asm.

