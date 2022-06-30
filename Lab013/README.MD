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

- Команда sh cdp neighbors позволяет посмотреть, какие интерфейсы работают с CDP

![image](https://user-images.githubusercontent.com/89464074/176674706-6b4933b1-7f7e-4e4e-b80a-913ea936faa4.png)
![image](https://user-images.githubusercontent.com/89464074/176674383-33e73062-85cc-45f3-a07c-9eff18be1237.png)


- При активации VLAN 1 на S1 стала доступна информация об ip адресе:

![image](https://user-images.githubusercontent.com/89464074/176673697-9754a7f1-2921-4e48-bdb9-2a2a8d6d20b4.png)

- Отключим CDP глобально на всех устройствах командой 


