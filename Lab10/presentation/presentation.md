---
## Front matter
lang: ru-RU
title: Лабораторная работа №10
subtitle: Основы работы с модулями ядра операционной системы
author:
  - Сулейм Гамбердов
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 22 октября 2025

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

Получить навыки работы с утилитами управления модулями ядра операционной системы Linux.

# Ход выполнения работы

## Просмотр устройств и драйверов

![Вывод команды lspci -k](Screenshot_1.png){ #fig:001 width=80% }

## Просмотр загруженных модулей

![Список загруженных модулей ядра](Screenshot_2.png){ #fig:002 width=80% }

## Загрузка модуля ext4

![Информация о модуле ext4](Screenshot_3.png){ #fig:003 width=80% }

## Выгрузка модулей ext4 и xfs

![Выгрузка модулей ext4 и xfs](Screenshot_4.png){ #fig:004 width=80% }

## Работа с модулем bluetooth

![Информация о модуле bluetooth](Screenshot_5.png){ #fig:005 width=80% }  

## Работа с модулем bluetooth

![Параметры модуля bluetooth](Screenshot_6.png){ #fig:006 width=80% }

## Обновление ядра

![Список доступных версий ядра](Screenshot_7.png){ #fig:007 width=80% }  

## Обновление ядра

![Процесс обновления ядра и системы](Screenshot_8.png){ #fig:008 width=80% } 

## Обновление ядра
 
![Проверка новой версии ядра](Screenshot_9.png){ #fig:009 width=80% }

# Итоги работы

## Вывод

В ходе выполнения лабораторной работы были изучены основные принципы работы с модулями ядра Linux.  
Рассмотрены команды для просмотра устройств, загрузки, выгрузки и анализа параметров модулей, а также процесс обновления ядра.  
Полученные навыки позволяют эффективно администрировать систему и управлять её компонентами на уровне ядра.
