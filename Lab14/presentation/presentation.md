---
## Front matter
lang: ru-RU
title: Лабораторная работа №14
subtitle: Партиции, файловые системы и монтирование
author:
  - Сулейм Гамбердов
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 13 ноября 2025

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

Получить навыки создания разделов, работы с файловыми системами и монтирования в Linux.

# Создание разделов MBR

## Просмотр дисков

![Список дисков через fdisk -l](Screenshot_1.png){ width=80% }

## Разметка диска через fdisk

![Справка по командам fdisk](Screenshot_2.png){ width=80% }

## Создание основного раздела 300 MiB

![Создание основного раздела](Screenshot_3.png){ width=80% }

## Проверка структуры и синхронизация

![Проверка раздела и /proc/partitions](Screenshot_4.png){ width=80% }

# Расширенные и логические разделы

## Создание extended-раздела и логического внутри него

![Создание расширенного раздела](Screenshot_5.png){ width=80% }

## Создание extended-раздела и логического внутри него

![Проверка логического раздела](Screenshot_6.png){ width=80% }

# Создание swap

## Разметка и изменение типа раздела

![Создание swap-раздела](Screenshot_7.png){ width=80% }

## Активация swap

![Активация swap и free -m](Screenshot_8.png){ width=80% }

# GPT-разметка через gdisk

## Создание GPT-таблицы и первого раздела

![Просмотр GPT через gdisk](Screenshot_9.png){ width=80% }

## Создание GPT-таблицы и первого раздела

![Создание GPT-раздела](Screenshot_10.png){ width=80% }

## Проверка структуры

![Готовая разметка GPT](Screenshot_11.png){ width=80% }

# Форматирование файловых систем

## XFS и EXT4

![Форматирование](Screenshot_12.png){ width=80% }

# Ручное монтирование

## Монтирование EXT4

![Монтирование EXT4](Screenshot_13.png){ width=80% }

# Автоматическое монтирование через /etc/fstab

## Получение UUID

![UUID через blkid](Screenshot_14.png){ width=80% }

## Настройка /etc/fstab

![Редактирование fstab](Screenshot_15.png){ width=80% }

## Проверка монтирования

![df -h](Screenshot_16.png){ width=80% }

# Самостоятельная часть

## Добавление GPT-разделов

![Создание разделов на GPT](Screenshot_17.png){ width=80% }

## Добавление GPT-разделов

![Форматирование ext4 и swap](Screenshot_18.png){ width=80% }

## Итоги проверки

![Проверка монтирования и swap](Screenshot_20.png){ width=80% }

# Итоги работы

## Вывод

В ходе лабораторной работы выполнено создание разделов MBR и GPT, форматирование файловых систем XFS и EXT4, настройка разделов подкачки, ручное и автоматическое монтирование через /etc/fstab. Получены практические навыки администрирования дисковой подсистемы Linux.
