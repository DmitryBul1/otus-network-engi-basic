# Лабораторная работа 1 (повторение) 
## Базовая настройка коммутатора
### Часть 1. Проверка конфигурации коммутатора по умолчанию

Подключаемся через консоль к ненастроенному коммутатору и командой show running-config смотрим файл запущенной конфигурации:

![L01NewPic01](https://user-images.githubusercontent.com/89464074/155875467-6e1bfc33-29a7-40ae-a20c-c8006e14c955.png)

![L01NewPic02](https://user-images.githubusercontent.com/89464074/155875753-9af0a21e-91dd-4e9f-851b-6ca653b9a14d.png) ![L01NewPic03](https://user-images.githubusercontent.com/89464074/155875781-7eacdc31-2dce-4399-a601-010e9f91dd4a.png)

![L01NewPic04](https://user-images.githubusercontent.com/89464074/155876040-6d0532da-90db-4299-aa68-0a3298ce8b76.png)

Отображена информация по устройству: 24 порта FastEthernet, 2 порта GigabitEthernet, линии VTY в диапазонах 0-4 и 5-15.
Сохраненной стартовой конфигурации в памяти устройства нет.

Анализ интерфейса VLAN командой show interface vlan1:

![L01NewPic05](https://user-images.githubusercontent.com/89464074/155876888-1cec7478-5e91-4f14-8f8a-785b77451da9.png)

VLAN1 имеет MAC-адрес 00e0.8fda.2bda и статус "отключен".

Подсоединямся к порту 6 при помощи кабеля ethernet.

![L01NewPic06](https://user-images.githubusercontent.com/89464074/155877018-c1419189-6693-46b2-8d51-cccee7aae852.png) 

Интерфейс FE0/6 активировался:

![L01NewPic07](https://user-images.githubusercontent.com/89464074/155877051-680fa6eb-9d85-4ebf-9929-6bce40199d1e.png)

Командой show version анализируем данные об IOS:

![L01NewPic08](https://user-images.githubusercontent.com/89464074/155877215-5985c512-be48-4633-bf3d-b20bfd9b7c16.png)

Версия ОС - Version 15.0(2)SE4
Файл образа во флэш-памяти - c2960-lanbasek9-mz.150-2.SE4.bin
Базовый MAC коммутатора - 00:17:59:A7:51:80

Свойства интерфейса F0/6, к которому подключен PC-1 (команда show interface f0/6)

![L01NewPic09](https://user-images.githubusercontent.com/89464074/155877445-36eb0099-dd07-4e61-8bbf-cf1614bee023.png)

Интерфейс включен.
Для включения пользуемся командой no shutdown в режиме конфигурации интерфейса.
Данный нтерфейс имеет MAC-адрес 00d0.58b8.d906
Настройки скорости и дуплекса по-умолчанию 100Mb/s и Full-duplex.

Анализ интерфейса VLAN:

![image](https://user-images.githubusercontent.com/89464074/155878131-d7078980-a147-4be1-b135-b227042b1c42.png)

Имя сети - default.
Порты сети VLAN: от f0/1 до f0/24 для FastEthernet и Gig0/1, Gig0/2 для GigabitEthernet.
Статус сети VLAN - active.
Тип сети - Default VLAN.

Анализ Flash-памяти:

![image](https://user-images.githubusercontent.com/89464074/155878256-d74bc3ac-a5bc-4209-b7df-c9987c325c59.png)

В памяти находтся образ ОС.

### Часть 2. Создание сети и настройка параметров

Настройка базовых параметров и присвоение IP-адреса виртуальному интерфейсу:

![image](https://user-images.githubusercontent.com/89464074/156507918-bca62985-4afa-4496-b0f3-58834af1b777.png)

Настройка доступа через консоль и настройка линий VTY:

![image](https://user-images.githubusercontent.com/89464074/156508441-40bf0faa-bef1-4272-a3a3-8a961d8302ca.png)

Настройка компьютера:

![image](https://user-images.githubusercontent.com/89464074/156508742-5e429874-7771-431b-b2cf-1e6314e92ffb.png)


### Часть 3. Проверка сетевых подключений

Подключение через консоль с компьютера PC1
![image](https://user-images.githubusercontent.com/89464074/156510875-7369fbc2-cae9-4b50-881d-6d2b36eb1454.png)




Просмотр интерфейса VLAN1

Полоса пропускания - 100000 Кбит, состояния интерфейса - активен.

















