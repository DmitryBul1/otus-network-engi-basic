# Лабораторная работа 13. Настройка протоколов CDP, LLDP, NTP.

### Топология

# Часть 1. Базовые настройки

- Настроим маршрутизатор R1

![image](https://user-images.githubusercontent.com/89464074/176669175-33fdf505-0fc9-4901-b845-1bb8c0ea35bd.png)

- Настроим коммутаторы S1 и S2

![image](https://user-images.githubusercontent.com/89464074/176669991-bc0fa1e0-7f9b-4255-940a-525bd15c3fb1.png)


# Часть 2. Обнаружение сетевых устройств

- На R1 используем команду show cdp, чтобы рассмотреть активные интерфейсы

![image](https://user-images.githubusercontent.com/89464074/176671803-2f6e69f5-71df-4100-b9a0-327e42be779d.png)

По-умолчанию CDP включен, участвуют в объявлениях все интерфейсы - vlan, g0/0/0 и g0/0/1. В активном состоянии находится g0/0/1.

- С роутера R1 определим версию ОС коммутатора S1

![image](https://user-images.githubusercontent.com/89464074/176672361-581f4396-a099-47fa-bfb5-92419ab84010.png)

Версия ОС на S1 - 15.0(2)SE4.

- На S1 выполним команду show cdp traffic (ошибка выполнения)

![image](https://user-images.githubusercontent.com/89464074/176673231-f6c19559-d4d1-4159-9dbc-5bb0eeaaa14f.png)

- Команда sh cdp neighbors позволяет посмотреть, какие интерфейсы каких устройств работают с CDP

![image](https://user-images.githubusercontent.com/89464074/176674706-6b4933b1-7f7e-4e4e-b80a-913ea936faa4.png)
![image](https://user-images.githubusercontent.com/89464074/176674383-33e73062-85cc-45f3-a07c-9eff18be1237.png)


- При активации VLAN 1 на S1 стала доступна информация об ip адресе:

![image](https://user-images.githubusercontent.com/89464074/176673697-9754a7f1-2921-4e48-bdb9-2a2a8d6d20b4.png)

- Отключим CDP для всех интерфейсов на каждом устройстве командой no cdp run

![image](https://user-images.githubusercontent.com/89464074/176675875-872bb952-6a80-4cf8-9592-7d3d735f502e.png)

# Часть 3. Обнаружение сетевых ресурсов с помощью протокола LLDP

- Командой lldp run включаем lldp на каждом устройстве
(примечание - команда с S1 "show lldp entry S2", указанная в задании, завершилась с обшибкой)

![image](https://user-images.githubusercontent.com/89464074/176678520-b7f30702-0b3e-4118-b4ee-fa8e113d825d.png)

![image](https://user-images.githubusercontent.com/89464074/176678606-65ea70ed-44e9-4878-9d56-99a2f66e4228.png)

# Часть 4. Настройка NTP
- Настроим время на роутере R1 в формате UTC

![image](https://user-images.githubusercontent.com/89464074/176824675-35d1215e-ec46-4305-a0a2-f4aa516001a4.png)

- Активируем NTP на R1 с указанием уровня слоя master 4

![image](https://user-images.githubusercontent.com/89464074/176826080-1675fa69-566c-4417-b0f0-776179f44222.png)
![image](https://user-images.githubusercontent.com/89464074/176826861-7b778132-0f41-4d31-9d6b-38fa3b74129e.png)

- Настроим клиентов NTP

Часы коммутаторов не настроены

![image](https://user-images.githubusercontent.com/89464074/176826380-356dc0b3-25b0-4b12-b208-c9418eb22ce0.png)

- Укажем для клиентов источником времени интерфейс g0/0/1 роутера R1 и дождемся синхронизации

![image](https://user-images.githubusercontent.com/89464074/176829450-ce5b63b9-4567-461b-bd4f-b5eab3d982d4.png)
![image](https://user-images.githubusercontent.com/89464074/176829248-2d7997ed-bde8-41f2-a3b5-ccac5fdcf1a9.png)

По прошествии некоторого времени, синхронизация времени с R1 завершилась успешно.










