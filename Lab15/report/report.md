---
## Front matter
title: "Отчёт по лабораторной работе №15"
subtitle: "Управление логическими томами"
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

Получить навыки управления логическими томами.

# Ход выполнения

## Создание физического тома

1. На диске **/dev/sdb** создан новый раздел размером 300 MiB.  
   Тип изменён на **Linux LVM (8e)**. Таблица разделов записана.

   ![Создание раздела LVM на /dev/sdb](Screenshot_1.png){ #fig:001 width=80% }

2. Таблица разделов обновлена, затем создан физический том **/dev/sdb1**.  
   Проверка `pvs` подтверждает успешное создание PV.

## Создание группы томов и логического тома

3. Создана группа томов **vgdata**, в которую добавлен физический том /dev/sdb1.  
   Команды `vgs` и `pvs` отображают корректную привязку.

   ![Создание VG и проверка](Screenshot_2.png){ #fig:002 width=80% }

4. Создан логический том **lvdata**, использующий 50% свободного пространства VG.  
   На нём создана файловая система ext4 и создан каталог /mnt/data для монтирования.

   ![Создание LV, файловой системы и каталога](Screenshot_3.png){ #fig:003 width=80% }

5. В `/etc/fstab` добавлена строка для автоматического монтирования логического тома.  

   ![Изменение fstab](Screenshot_4.png){ #fig:004 width=80% }

6. Проверено автоматическое монтирование. Логический том смонтирован в /mnt/data.

   ![Проверка монтирования](Screenshot_5.png){ #fig:005 width=80% }

## Расширение логических томов

7. С помощью fdisk создан второй раздел **/dev/sdb2**, также типа **8e (Linux LVM)**.

   ![Создание раздела /dev/sdb2](Screenshot_6.png){ #fig:006 width=80% }

8. Новый раздел преобразован в физический том и добавлен в VG.  
   Свободное пространство группы увеличено.

   ![Создание PV, расширение VG, проверка lvs и df](Screenshot_7.png){ #fig:007 width=80% }

9. Логический том увеличен на 50% свободного пространства VG.  
   Файловая система увеличена онлайн.

   ![Увеличение LV и проверка](Screenshot_8.png){ #fig:008 width=80% }

## Уменьшение логического тома

10. Перед уменьшением выполнена проверка файловой системы.  
    После этого уменьшены и файловая система, и логический том.  
    Проверка `lvs` и `df -h` подтверждает корректность результата.

    ![Уменьшение LV и проверка](Screenshot_9.png){ #fig:009 width=80% }

# Самостоятельная работа

## Создание логического тома lvgroup

1. На диске **/dev/sdc** создан новый раздел размером 600 MiB.  
   Тип раздела изменён на **Linux LVM (8e)**. Таблица разделов успешно записана.

   ![Создание раздела на /dev/sdc](Screenshot_10.png){ #fig:010 width=80% }

2. Раздел **/dev/sdc1** преобразован в физический том.  
   Создана группа томов **vggroup** и в ней создан логический том **lvgroup**, использующий всё доступное пространство.

   ![Создание PV, VG и LV](Screenshot_11.png){ #fig:011 width=80% }

3. Логический том lvgroup отформатирован в файловой системе **XFS**.

4. В файл `/etc/fstab` добавлена строка для постоянного монтирования:


![Настройка fstab](Screenshot_12.png){ #fig:012 width=80% }

5. Проверено монтирование после перезагрузки — файловая система успешно подключается.

![Проверка монтирования и df](Screenshot_13.png){ #fig:013 width=80% }

## Расширение логического тома

6. На диске **/dev/sdc** создан второй раздел **/dev/sdc2** размером 450 MiB, также с типом LVM (8e).

![Создание /dev/sdc2](Screenshot_14.png){ #fig:014 width=80% }

7. Раздел /dev/sdc2 добавлен как физический том и расширил группу томов **vggroup**.  
Объём устройства lvgroup увеличен на 150 MiB и расширена файловая система XFS.

![Расширение PV, VG и LV](Screenshot_15.png){ #fig:015 width=80% }

## Проверка результатов

8. Команды `pvs`, `vgs`, `lvs` и `df -h` подтверждают успешное увеличение размера логического тома и соответствующее расширение файловой системы XFS.

![Проверка увеличенного тома](Screenshot_16.png){ #fig:016 width=80% }

# Контрольные вопросы

1. В разметке GUID (GPT) для работы с LVM используется тип раздела  
   **0x8e00 — Linux LVM**.

2. Создать группу томов **vggroup**, содержащую физический том */dev/sdb3*  
   и использующую физический экстент 4 MiB, можно командой:

```
vgcreate -s 4M vggroup /dev/sdb3
```

3. Краткую сводку физических томов и групп томов показывает команда:

```
pvs
```

4. Чтобы добавить весь диск **/dev/sdd** в группу томов, нужно:  
- сначала создать на нём LVM-раздел (тип 8e),  
- затем выполнить:

```
pvcreate /dev/sdd1
vgextend <имя_группы> /dev/sdd1
```

5. Создать логический том **lvvol1** размером 6 MiB можно командой:

```
lvcreate -n lvvol1 -L 6M <имя_группы>
```

6. Добавить **100 МБ** в логический том **lvvol1** можно командой:

```
lvextend -L +100M <имя_группы>/lvvol1
```

7. Первый шаг, если в группе томов недостаточно места:  
**добавить новый физический том в группу томов**, выполнив:

```
pvcreate /dev/<новый_раздел>
vgextend <имя_группы> /dev/<новый_раздел>
```

8. Чтобы при расширении логического тома автоматически увеличивалась файловая система, используется опция:

```
lvextend -r ...
```

9. Список доступных логических томов можно посмотреть командой:

```
lvs
```

10. Проверить целостность файловой системы на */dev/vgdata/lvdata* можно:

```
e2fsck /dev/vgdata/lvdata
```

# Заключение

В ходе выполнения работы были последовательно изучены и реализованы операции по управлению логическими томами в Linux. Были созданы физические тома, группы томов и логические тома, выполнено их форматирование и постоянное монтирование через файл fstab. На практике отработаны операции расширения и уменьшения томов с одновременным изменением размеров файловых систем. Полученные навыки позволяют эффективно управлять дисковым пространством, рационально распределять ресурсы и обеспечивать гибкость хранения данных в современных Linux-системах.
