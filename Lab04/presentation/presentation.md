---
## Front matter
lang: ru-RU
title: Лабораторная работа №4
subtitle: Работа с программными пакетами
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

Получить навыки работы с репозиториями и менеджерами пакетов в Linux.

# Ход выполнения работы

## Работа с репозиториями

![Просмотр файлов репозиториев](Screenshot_1.png){ #fig:001 width=80% }

## Список репозиториев

![Список репозиториев](Screenshot_2.png){ #fig:002 width=80% }

## Поиск пакетов

![Поиск пакетов с ключевым словом user](Screenshot_3.png){ #fig:003 width=80% }

## Установка и удаление nmap

![Установка пакета nmap](Screenshot_4.png){ #fig:004 width=80% }  

## Установка и удаление nmap

![Удаление пакета nmap](Screenshot_5.png){ #fig:005 width=80% }

## Работа с группами пакетов

![Работа с группами пакетов](Screenshot_6.png){ #fig:006 width=80% }  

## Работа с группами пакетов

![Информация и установка группы RPM Development Tools](Screenshot_7.png){ #fig:007 width=80% }  

## Работа с группами пакетов

![Удаление группы RPM Development Tools](Screenshot_8.png){ #fig:008 width=80% }

## История транзакций dnf

![История транзакций и откат действий](Screenshot_9.png){ #fig:009 width=80% }

## Установка lynx

![Загрузка пакета lynx](Screenshot_10.png){ #fig:010 width=80% }  

## Установка lynx

![Поиск и установка пакета lynx](Screenshot_11.png){ #fig:011 width=80% }

## Проверка и информация о lynx

![Проверка принадлежности файла пакету](Screenshot_12.png){ #fig:012 width=80% } 

## Проверка и информация о lynx
 
![Информация о пакете lynx](Screenshot_13.png){ #fig:013 width=80% }

## Содержимое и документация lynx

![Список файлов пакета](Screenshot_14.png){ #fig:014 width=80% }  

## Содержимое и документация lynx

![Список документации пакета](Screenshot_15.png){ #fig:015 width=80% }

## Конфигурация и запуск lynx

![Запуск lynx](Screenshot_16.png){ #fig:016 width=80% }  

## Конфигурация и запуск lynx

![Конфигурационные файлы lynx](Screenshot_17.png){ #fig:017 width=80% }

## Установка и проверка файла

![Установка и проверка расположения исполняемого файла](Screenshot_18.png){ #fig:018 width=80% }

## Информация о пакете

![Информация о пакете dnsmasq](Screenshot_19.png){ #fig:019 width=80% }

## Содержимое и документация

![Список файлов пакета](Screenshot_20.png){ #fig:020 width=80% }  

## Содержимое и документация

![Руководство dnsmasq](Screenshot_21.png){ #fig:021 width=80% }

## Конфигурационные файлы dnsmasq

![Конфигурационные файлы dnsmasq](Screenshot_22.png){ #fig:022 width=80% }

# Итоги работы

## Вывод

В ходе работы были изучены приёмы управления пакетами в Linux с помощью **dnf** и **rpm**: установка, удаление, работа с группами, проверка документации и анализ содержимого пакетов.
