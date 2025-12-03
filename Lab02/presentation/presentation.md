---
## Front matter
lang: ru-RU
title: Лабораторная работа №2
subtitle: Управление пользователями и группами
author:
  - Сулейм Гамбердов
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 17 сентября 2025

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

Получить представление о работе с учётными записями пользователей и группами пользователей в Linux, а также освоить базовые команды администрирования.

# Ход выполнения работы

## Переключение учётных записей

![Переключение к root и проверка идентификаторов](Screenshot_1.png){ #fig:001 width=80% }

## Работа с sudo и группой wheel

![Редактирование /etc/sudoers с помощью visudo](Screenshot_2.png){ #fig:002 width=80% }

## Создание пользователей

![Создание пользователя alice и проверка его групп](Screenshot_3.png){ #fig:003 width=80% }

## Настройка параметров пользователей

![Редактирование параметров в /etc/login.defs](Screenshot_4.png){ #fig:004 width=80% }

## Настройка шаблонов профиля

![Изменение файла .bashrc в /etc/skel](Screenshot_5.png){ #fig:005 width=80% }

## Создание новых пользователей

![Создание пользователя carol и проверка его домашнего каталога](Screenshot_6.png){ #fig:006 width=80% }

## Управление паролями

![Просмотр и изменение записи пароля пользователя carol](Screenshot_7.png){ #fig:007 width=80% }

## Управление группами

![Проверка добавления carol в группу third](Screenshot_8.png){ #fig:008 width=80% }

# Итоги работы

## Вывод

В ходе работы были изучены приёмы управления пользователями и группами в Linux: создание и настройка учётных записей, работа с конфигурационными файлами, контроль параметров паролей и предоставление прав через группу wheel.
