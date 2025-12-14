---
## Front matter
lang: ru-RU
title: Лабораторная работа №15
subtitle: Управление логическими томами
author:
  - Сулейм Гамбердов
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 24 ноября 2025

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

Получить практические навыки создания, расширения и уменьшения логических томов в Linux с использованием LVM.

# Выполнение работы

## Разметка диска /dev/sdb

![Создание раздела LVM](Screenshot_1.png){ width=80% }

## Создание VG и LV

![Создание VG и LV](Screenshot_2.png){ width=80% }

## Форматирование и монтирование

![Создание ФС и каталога](Screenshot_3.png){ width=80% }

## Автомонтирование

![Добавление записи в fstab](Screenshot_4.png){ width=80% }

## Проверка монтирования

![Монтирование выполнено](Screenshot_5.png){ width=80% }

## Создание второго раздела

![Создание /dev/sdb2](Screenshot_6.png){ width=80% }

## Расширение VG и LV

![Расширение PV, VG и LV](Screenshot_7.png){ width=80% }

## Online resize

![Увеличенный LV](Screenshot_8.png){ width=80% }

## Проверка ФС и уменьшение тома

![Уменьшенный LV](Screenshot_9.png){ width=80% }

# Самостоятельная работа

## Создание lvgroup и PV на /dev/sdc

![Создание PV и LV](Screenshot_10.png){ width=80% }

## Создание VG и LV

![Создание LVM на sdc](Screenshot_11.png){ width=80% }

## Монтирование через fstab

![fstab](Screenshot_12.png){ width=80% }

## Проверка монтирования

![Проверка после загрузки](Screenshot_13.png){ width=80% }

## Создание нового PV

![Создание /dev/sdc2](Screenshot_14.png){ width=80% }

## Увеличение LV и ФС XFS

![Расширение XFS](Screenshot_15.png){ width=80% }

## Итоговое состояние томов

![Сводная проверка](Screenshot_16.png){ width=80% }

# Итоги работы

## Вывод

В ходе выполнения работы были отработаны навыки управления LVM: создание и настройка физических томов, групп томов и логических томов, операции расширения и уменьшения томов, а также работа с файловыми системами. Полученный опыт позволяет эффективно управлять дисковыми ресурсами Linux.
