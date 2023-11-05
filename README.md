# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #2 выполнил(а):
- Абросимова Марина Михайловна
- РИ-220931
  
Отметка о выполнении заданий:

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | * | 20 |

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

## Цель работы
Разработать оптимальный баланс для десяти уровней игры Dragon Picker.

## Задание 1

Ход работы:
- Предложить вариант изменения найденных переменных для 10 уровней в игре. Визуализировать изменение уровня сложности в таблице.

На скриншоте красной рамной выделены 4 переменные, влияющие на уровень сложности:

![2023-11-05_15-25-42](https://github.com/Marishka-A/Workshop3/assets/126682278/bcb645a7-c828-4b30-8d1c-82f2101ff2e5)

Изучив все переменные я пришла к выводу, что уровень сложности можно увеличивать с помощью увеличения значения переменных Speed, Left Right Dictance, Chance Direction и уменьшения переменной Time Between Egg Dragon.

Формула повышения сложности: 
Difficulty = Speed + Left Right Dictance + Chance Direction + Time Between Egg Dragon

![2023-11-05_15-49-18](https://github.com/Marishka-A/Workshop3/assets/126682278/2b2552cd-7112-4c4b-ac57-ea06e394c2f3)


## Задание 2:

Ход работы:
- Создать 10 сцен на Unity с изменяющимся уровнем сложности.

Скрин из Unity с десятью уровнями, увеличивающимися по сложности изходя из приведенной ранее таблици:

![2023-11-05_16-13-22](https://github.com/Marishka-A/Workshop3/assets/126682278/6bae39b5-7b36-40a2-98a8-3c83d384ad77)

Также эти уровни (сцены) придожены к этому репозиторию. Можно ознакомиться с ними изнутри.

## Задание 3:
Ход работы: 
-  Заполнить google-таблицу данными из Python. В Python данные также должны быть визуализированы.

По сделанной уже ранее таблици сложности уровней, я заполнила google-таблицу с помощью кода на Python, предварительно подключив API.

![2023-11-05_19-24-57](https://github.com/Marishka-A/Workshop3/assets/126682278/7e745096-aab3-4855-bc19-83ede52c3e81)

  Скрипт:
  ```py
import gspread
import numpy as np
gc = gspread.service_account(filename='unitydatascience2-cfc42e20a895.json')
sh = gc.open("DataSciense")
speed = 1.00
timeBetweenEgg = 5.00
leftRightDist = 10.00
chanceDir = 0.01
i = 0
end = 8
while i <= end:     
    i += 1
    if i == 0:
        continue
    else:
        sh.sheet1.update(('A' + str(i+1)), i)
        sh.sheet1.update(('B' + str(i+2)), speed*i)
        sh.sheet1.update(('C' + str(i+2)), leftRightDist+0.5*i)
        sh.sheet1.update(('D' + str(i+2)), chanceDir+0.003*i)
        sh.sheet1.update(('E' + str(i+2)), timeBetweenEgg-0.4*i)
```

## Выводы

В ходе лабороторной работы было предложено 10 различнвх уровней сложности для игры Dragon Picker и определены переменные от которых зависит сложность игры. Далее эти 10 сцен были реализованны с помощью Unity, а затем на основе первого задания была создана и заполнена с помощью google-таблица.


## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
