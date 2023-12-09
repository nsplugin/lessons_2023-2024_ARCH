---
## Front matter
title: "Отчёт по лабораторной работе 5"
subtitle: "Дисциплина: архитектура компьютера"
author: "Плугин Никита"

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

Целью работы является приобретение практических навыков работы в Midnight Commander. 
Освоение инструкций языка ассемблера mov и int.

# Задания

1. Изучить основы работы с Midnight Commander

2. Изучить инструкции ассемблера

3. Выполнить самостоятельное задание по изменению программы

# Теоретическое введение

Midnight Commander (или просто mc) — это программа, которая позволяет просматривать
структуру каталогов и выполнять основные операции по управлению файловой системой,
т.е. mc является файловым менеджером. Midnight Commander позволяет сделать работу с
файлами более удобной и наглядной.

Программа на языке ассемблера NASM, как правило, состоит из трёх секций: секция кода
программы (SECTION .text), секция инициированных (известных во время компиляции)
данных (SECTION .data) и секция неинициализированных данных (тех, под которые во
время компиляции только отводится память, а значение присваивается в ходе выполнения
программы) (SECTION .bss).

# Выполнение лабораторной работы

## Работа в Midnight Commander

1. Открыл Midnight Commander. Перешел в каталог ~/work/arch-pc. 
Создал каталог lab05 (рис. [-@fig:001])

![Создание каталога](image/01.png){ #fig:001 width=70%, height=70% }

2. Создал файл lab05-1.asm (рис. [-@fig:002])

![Создание файла lab05-1.asm](image/02.png){ #fig:002 width=70%, height=70% }

3. Открыл файл на редактирование. Написал код. (рис. [-@fig:003])

![Программа lab05-1.asm](image/03.png){ #fig:003 width=70%, height=70% }

4. Открыл файл для просмотра и убедился, что он содержит написанный код. (рис. [-@fig:004])

![Просмотр файла lab05-1.asm](image/04.png){ #fig:004 width=70%, height=70% }

5. Получил исполняемый файл программы и провреил его работу.(рис. [-@fig:005])

![Проверка программы lab05-1.asm](image/05.png){ #fig:005 width=70%, height=70% }

## Подключение внешнего файла in_out.asm

6. Скачал файл in_out.asm. Добавил файл in_out.asm в рабочий каталог. 
Скопировал lab05-1.asm в lab05-2.asm. (рис. [-@fig:006])

![Копирование файла](image/06.png){ #fig:006 width=70%, height=70% }

7. Написал код программы lab05-2.asm. (рис. [-@fig:007]) 
Скомпилировал программу и провреил запуск. (рис. [-@fig:008])

![Программа lab05-2.asm](image/07.png){ #fig:007 width=70%, height=70% }

![Проверка программы lab05-2.asm](image/08.png){ #fig:008 width=70%, height=70% }

8. В файле lab5-2.asm я заменил подпрограмму sprintLF на sprint (рис. [-@fig:009]). 
Затем я снова собрал исполняемый файл (рис. [-@fig:010]). 
Теперь после вывода строки она не завершается символом перехода на новую строку.

![Программа lab05-2.asm](image/09.png){ #fig:009 width=70%, height=70% }

![Проверка программы lab05-2.asm](image/10.png){ #fig:010 width=70%, height=70% }

##  Задание для самостоятельной работы

1. Скопировал программу lab05-1.asm и изменил код, чтобы программа выводила 
приглашение типа "Введите строку:", затем считывала строку с клавиатуры 
и выводила введенную строку на экран. (рис. [-@fig:011], рис. [-@fig:012])

![Программа lab05-3.asm](image/11.png){ #fig:011 width=70%, height=70% }

![Проверка программы lab05-3.asm](image/12.png){ #fig:012 width=70%, height=70% }

2. Также я скопировал программу lab05-2.asm и внес соответствующие изменения в код, 
чтобы программа выводила приглашение типа "Введите строку:", 
затем считывала строку с клавиатуры и выводила введенную строку на экран.(рис. [-@fig:013], рис. [-@fig:014])

![Программа lab05-4.asm](image/13.png){ #fig:013 width=70%, height=70% }

![Проверка программы lab05-4.asm](image/14.png){ #fig:014 width=70%, height=70% }

Отличие этих двух реализаций заключается в том, что файл in_out.asm содержит уже 
готовые подпрограммы для обеспечения ввода/вывода. 
Таким образом, нам остается только разместить данные в нужных регистрах и 
вызвать желаемую подпрограмму с помощью инструкции call.

# Выводы

Научились писать базовые ассемблерные программы. Освоили ассемблерные инструкции mov и int.

# Источники

1. [Архитектура ЭВМ](https://esystem.rudn.ru/course/view.php?id=108)