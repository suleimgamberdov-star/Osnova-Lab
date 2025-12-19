---
## Front matter
lang: ru-RU
title: Лабораторная работа №8
subtitle: Планировщики событий
author:
  - Сулейм Гамбердов
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 17 октября 2025

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

Получить практические навыки работы с планировщиками событий **cron** и **at** в операционной системе Linux.  
Изучить способы настройки периодических и одноразовых заданий, а также проверить их выполнение на практике.

# Ход выполнения работы

## Проверка состояния службы crond

![Проверка статуса службы crond](Screenshot_1.png){ #fig:001 width=80% }

## Изучение конфигурации /etc/crontab

![Просмотр конфигурации /etc/crontab](Screenshot_2.png){ #fig:002 width=80% }

## Добавление нового задания в crontab

![Создание задания в crontab](Screenshot_3.png){ #fig:003 width=80% }

## Проверка работы cron

![Изменение задания cron для рабочих дней](Screenshot_4.png){ #fig:004 width=80% }

## Создание сценария eachhour

![Создание скрипта eachhour в /etc/cron.hourly](Screenshot_5.png){ #fig:005 width=80% }

## Настройка файла расписания в /etc/cron.d

![Создание файла задания eachhour в /etc/cron.d](Screenshot_6.png){ #fig:006 width=80% }

## Работа с планировщиком at

![Проверка службы atd](Screenshot_7.png){ #fig:007 width=80% }

# Итоги работы

## Вывод

В ходе лабораторной работы были изучены основные механизмы автоматизации задач в Linux с использованием планировщиков **cron** и **at**.  
Полученные навыки позволяют эффективно организовывать выполнение системных процессов без участия пользователя и обеспечивают стабильную работу серверных служб.
