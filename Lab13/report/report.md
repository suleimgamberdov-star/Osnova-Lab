---
## Front matter
title: "Отчёт по лабораторной работе №13"
subtitle: "Фильтр пакетов"
author: "Сулейм Гамбердов"

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

Получить навыки настройки пакетного фильтра в Linux.

# Ход выполнения

## Управление брандмауэром с помощью *firewall-cmd*

1. Получены административные права через `su -`.  
   Определена зона, используемая по умолчанию — активной зоной оказалась **public**.

   ![Определение зоны по умолчанию](Screenshot_1.png){ #fig:001 width=80% }

2. Выполнен просмотр доступных зон брандмауэра. Система содержит несколько предопределённых зон, включая *public*, *home*, *work*, *internal* и другие.

3. Получен перечень всех предустановленных служб, поддерживаемых брандмауэром. На экране отображён длинный список сервисов.

4. Выполнен просмотр служб, разрешённых в текущей зоне.  

5. Для сравнения выведены сведения о конфигурации активной зоны двумя способами: общий вывод и вывод с указанием зоны.  
   Результаты совпали, так как активная зона — **public**.

   ![Сравнение list-all и list-all --zone](Screenshot_2.png){ #fig:002 width=80% }

6. Добавлена служба **vnc-server** в конфигурацию времени выполнения.  
   Повторная проверка списка разрешённых служб показала, что она успешно появилась.

   ![Добавление vnc-server во временную конфигурацию](Screenshot_3.png){ #fig:003 width=80% }

7. Выполнена перезагрузка службы брандмауэра. После перезапуска служба **vnc-server** исчезла из конфигурации.

   ![После перезапуска службы vnc-server исчезает](Screenshot_4.png){ #fig:004 width=80% }

   Причина: служба была добавлена только во временную конфигурацию (runtime), которая не сохраняется на диск.

8. Служба добавлена повторно, но уже в постоянную конфигурацию (на диск).  
   После выполнения команда показывает, что сервис существует только в постоянной части и ещё не активирован.

   ![Добавление службы в постоянную конфигурацию](Screenshot_5.png){ #fig:005 width=80% }

9. Перезагружена конфигурация брандмауэра. Служба **vnc-server** отобразилась в активной конфигурации.

   ![Сервис vnc-server добавлен и активен](Screenshot_6.png){ #fig:006 width=80% }

10. В конфигурацию добавлен порт **2022** по протоколу TCP, изменения сделаны постоянными.  
    После перезагрузки конфигурации порт появился в текущей конфигурации брандмауэра.

    ![Добавление порта 2022/tcp](Screenshot_7.png){ #fig:007 width=80% }

## Управление брандмауэром с помощью *firewall-config*

1. Запущено приложение *firewall-config* из терминала. При запуске система запросила пароль пользователя с правами администратора.

2. В верхней части окна открыт список конфигураций, выбран режим **Permanent**. Это обеспечивает сохранение всех изменений как постоянных.

   ![Выбор режима Permanent](Screenshot_8.png){ #fig:008 width=80% }

3. В левой панели выбрана зона **public**. На вкладке *Services* отмечены службы **http**, **https** и **ftp**, благодаря чему к ним разрешён доступ.

4. Перейдя на вкладку *Ports*, выполнено добавление порта. В появившемся окне введено:
   - Port: `2022`
   - Protocol: `udp`

   После нажатия OK порт был внесён в список.

   ![Добавление порта 2022/udp](Screenshot_9.png){ #fig:009 width=80% }

5. Приложение *firewall-config* закрыто.

6. В терминале выведена текущая конфигурация брандмауэра. Порт и службы ещё не активны, так как изменения внесены только в постоянную конфигурацию.

   ![Проверка конфигурации перед reload](Screenshot_10.png){ #fig:010 width=80% }

7. Выполнена перезагрузка конфигурации с помощью `firewall-cmd --reload`, после чего повторный вывод параметров подтвердил применение изменений: службы и порт отобразились в списке активных.

   ![Настройки вступили в силу после reload](Screenshot_11.png){ #fig:011 width=80% }

## Самостоятельная работа

1. Настроена конфигурация, разрешающая доступ к службам:

   - **telnet**
   - **imap**
   - **pop3**
   - **smtp**

2. Добавление услуги **telnet** выполнено в командной строке. Затем команда выполнена повторно с флагом `--permanent`, чтобы изменить конфигурацию на постоянную.

3. Через графический интерфейс *firewall-config* добавлены службы **imap**, **pop3**, **smtp**. Службы выбраны в списке на вкладке *Services* для зоны *public*.

4. Выполнена перезагрузка конфигурации `firewall-cmd --reload`. Проверка списка активных параметров показала, что все службы и порт находятся в постоянной конфигурации и активированы.

   ![Итоговая конфигурация с telnet, imap, pop3, smtp](Screenshot_12.png){ #fig:012 width=80% }


# Контрольные вопросы

1. Перед началом работы с менеджером конфигурации брандмауэра **firewall-config** должна быть запущена служба **firewalld**.

2. Добавление UDP-порта **2355** в зону по умолчанию выполняется командой:
   `firewall-cmd --add-port=2355/udp`

3. Для отображения полной конфигурации брандмауэра во всех зонах используется команда:
   `firewall-cmd --list-all-zones`

4. Удаление службы **vnc-server** из текущей конфигурации выполняется командой:
   `firewall-cmd --remove-service=vnc-server`

5. Применение конфигурации, добавленной с параметром `--permanent`, выполняется командой:
   `firewall-cmd --reload`

6. Проверка активной конфигурации и подтверждение внесённых изменений выполняется командой:
   `firewall-cmd --list-all`

7. Добавление интерфейса **eno1** в зону *public* выполняется с помощью:
   `firewall-cmd --zone=public --add-interface=eno1`

8. Если интерфейс добавляется без указания зоны, он будет помещён в **зону по умолчанию**.
   Узнать её можно командой:
   `firewall-cmd --get-default-zone`


# Заключение

В ходе работы были изучены основные приёмы управления брандмауэром в Linux с использованием инструментов **firewall-cmd** и **firewall-config**. На практике были выполнены задачи по добавлению и удалению служб, открытию TCP/UDP-портов, а также различению временной и постоянной конфигураций. Через GUI и командную строку были настроены службы telnet, imap, pop3 и smtp, что позволило закрепить навыки администрирования.  
