---
## Front matter
lang: ru-RU
title: Лабораторная работа №13
subtitle: Фильтр пакетов (firewalld)
author:
  - Сулейм Гамбердов
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 07 ноября 2025

## Formatting pdf / slides
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

Получить навыки настройки пакетного фильтра Linux с помощью инструментов:

- **firewall-cmd** (CLI)
- **firewall-config** (GUI)

# Ход выполнения

## Определение параметров брандмауэра

![Определение зоны по умолчанию](Screenshot_1.png){ #fig:001 width=80% }

## Просмотр настроек зоны

![Сравнение конфигурации зоны](Screenshot_2.png){ #fig:002 width=80% }

## Добавление сервиса (runtime)

Сервис VNC добавлен во временную конфигурацию.

![Добавление vnc-server](Screenshot_3.png){ #fig:003 width=80% }

## Перезагрузка и потеря изменений

![После перезапуска службы vnc-server исчезает](Screenshot_4.png){ #fig:004 width=80% }

## Добавление сервиса (permanent)

![Добавление сервиса permanently](Screenshot_5.png){ #fig:005 width=80% }

## Активация постоянной конфигурации

![vnc-server активирован](Screenshot_6.png){ #fig:006 width=80% }

## Добавление портов

![Добавление порта 2022](Screenshot_7.png){ #fig:007 width=80% }

## Выбор режима Permanent

![Выбор режима Permanent](Screenshot_8.png){ #fig:008 width=80% }

## Добавление порта через GUI

![Добавление порта 2022/udp](Screenshot_9.png){ #fig:009 width=80% }

## Активация изменений

![Настройки вступили в силу после reload](Screenshot_10.png){ #fig:010 width=80% }

## Выполненные действия

![Итоговая конфигурация](Screenshot_12.png){ #fig:011 width=80% }

# Заключение

## Вывод

В ходе работы были освоены:

- управление брандмауэром через **CLI и GUI**
- добавление и удаление служб и портов
- различие между runtime и permanent конфигурациями

Получены практические навыки администрирования сетевой безопасности в Linux.
