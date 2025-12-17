---
## Front matter
lang: ru-RU
title: Лабораторная работа №16
subtitle: Программный RAID
author:
  - Сулейм Гамбердов
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 05 декабря 2025

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

# Цель работы

## Основная цель

Освоить создание, настройку и администрирование программных RAID-массивов с помощью утилиты **mdadm** в Linux.

# Ход выполнения работы

## Проверка наличия дисков

![Проверка наличия дисков](Screenshot_1.png){ #fig:001 width=80% }

## Создание разделов

![Создание разделов](Screenshot_2.png){ #fig:002 width=80% }

## Проверка типа разделов

![Проверка типа разделов](Screenshot_3.png){ #fig:003 width=80% }

## Изменение типа на RAID autodetect

![Тип разделов RAID](Screenshot_4.png){ #fig:004 width=80% }

## Инициализация массива RAID 1

![Создание RAID-массива](Screenshot_5.png){ #fig:005 width=80% }

## Состояние массива RAID 1

![Состояние RAID 1](Screenshot_6.png){ #fig:006 width=80% }

## Создание ФС и монтирование

![Создание ФС и монтирование](Screenshot_7.png){ #fig:007 width=80% }

## Настройка автомонтирования

![fstab настройка](Screenshot_8.png){ #fig:008 width=80% }

## Симуляция сбойного диска

![Сбой диска](Screenshot_9.png){ #fig:009 width=80% }

## Очистка и остановка массива

![Удаление массива](Screenshot_10.png){ #fig:010 width=80% }

## Создание массива и добавление hotspare

![Добавление hotspare](Screenshot_11.png){ #fig:011 width=80% }

## Состояние массива с hotspare

![Состояние hotspare](Screenshot_12.png){ #fig:012 width=80% }

## Автоматическое замещение при отказе

![Hotspare замещает отказавший диск](Screenshot_13.png){ #fig:013 width=80% }

## Очистка массива

![Очистка RAID](Screenshot_14.png){ #fig:014 width=80% }

## Исходный RAID 1

![Создание RAID1 вновь](Screenshot_15.png){ #fig:015 width=80% }

## Состояние перед преобразованием

![Состояние RAID1](Screenshot_16.png){ #fig:016 width=80% }

## Изменение уровня массива до RAID 5

![Преобразование в RAID5](Screenshot_17.png){ #fig:017 width=80% }

## Увеличение количества устройств

![Grow RAID5](Screenshot_18.png){ #fig:018 width=80% }

# Выводы

## Итоги работы

В рамках лабораторной работы были изучены:

- принципы работы программных RAID-массивов;
- создание RAID 1 и RAID 5 при помощи утилиты **mdadm**;
- работа с горячим резервом (hot spare);
- симуляция отказов и восстановление работоспособности массива;
- преобразование RAID 1 в RAID 5 без потери данных.

Полученные навыки позволяют эффективно администрировать дисковые подсистемы Linux и обеспечивать отказоустойчивость хранения данных.

