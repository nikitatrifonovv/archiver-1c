# Archie archiver 1C

Утилита на OneScript для создания бекапов баз данных 1С.

## Конфигурация
Рядом с исполняемым файлом должен находится файл конфигурации по умолчанию `arch.cfg`. При необходимости его можно заменить с помощью аргумента `-cfg`.
Запись в конфигурации выглядит следующим образом: `Ключ=Значение`

## Как использовать

### Локальная архивация
 ```
 archie.exe local -i <значение> -o <значение> -c <значение> -hr <значение> -z [максимальный|минимальный|оптимальный]
        -i - Путь к папке с БД 1с.
        -o - Путь к папке с архивами БД (Если такой нет, то будет создана)
        -c - Количество копий БД.
        -hr - Количество часов с момента прошлого изменения БД для архивации.
        -z - Уровень архивации (значения: [максимальный|минимальный|оптимальный])
        -cfg - файл конфигурации (необязательно)
        -h - Справка.
 ```
 
 ### Облачная архивация (Сбердиск)
 #### 1. Авторизация
 При первом запуске утилита запросит авторизацию через Сбердиск и автоматически сохранит данные входа.
 #### 2. Добавление сетевого расположения Windows
 После авторизации в консоль будут выведены URL адрес расположения, логин, пароль. С их помощью нужно вручную добавить сетевое расположение. Подробнее тут [Добавить сетевое расположение](https://techarks.ru/general/osobennosti/dobavit-setevoe-raspolozhenie-podklyuchit-ftp-disk-v-windows-10-8-7/#:~:text=%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%BD%D0%BE%D0%BC%D1%83%20FTP%2D%D0%B4%D0%B8%D1%81%D0%BA%D1%83.-,%D0%94%D0%BE%D0%B1%D0%B0%D0%B2%D0%B8%D1%82%D1%8C%20%D1%81%D0%B5%D1%82%D0%B5%D0%B2%D0%BE%D0%B5%20%D1%80%D0%B0%D1%81%D0%BF%D0%BE%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5,-%D0%95%D1%81%D0%BB%D0%B8%20%D0%B2%D1%8B%20%D1%85%D0%BE%D1%82%D0%B8%D1%82%D0%B5)
 #### 3. Команда
 ```
 archie.exe cloud -i <значение> -o <значение> -c <значение> -hr <значение> -z [максимальный|минимальный|оптимальный]
        -i - Путь к папке с БД 1с.
        -d - Буква облачного диска (Строго до -o, Z по умолчанию)
        -o - Путь к папке с архивами БД на удалённом облаке (\path\to\backups)
        -c - Количество копий БД.
        -hr - Количество часов с момента прошлого изменения БД для архивации.
        -z - Уровень архивации (значения: [максимальный|минимальный|оптимальный])
        -cfg - файл конфигурации (необязательно)
        -h - Справка.
 ```
