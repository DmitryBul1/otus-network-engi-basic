# Лабораторная работа 10. Настройка протокола OSPFv2 для одной области
### Топология

![image](https://user-images.githubusercontent.com/89464074/175122489-7f493812-8ef0-4e0b-a11d-492e85a0fc49.png)


### Часть 1. Создание сети и настройка основных параметров устройства

Топология была создана в соответствии с заданием, произведена базовая настройка для роутеров R1 и R2, а также для коммутаторов S1 и S2.
Настроим интерфейсы для каждого из устройств.

- Настройка и просмотр интерфейсов R1

![image](https://user-images.githubusercontent.com/89464074/175110868-b8fca644-a46a-4cac-8350-e7b4cf78c1bd.png)
![image](https://user-images.githubusercontent.com/89464074/175111040-20befca5-5152-4565-a9db-d5d876ed19cc.png)

![image](https://user-images.githubusercontent.com/89464074/175111524-a0989391-feb2-43b6-a9dc-154086accc1a.png)

(Примечание к отчетному скину выше - сперва промахнулся и ip адрес присвоил интерфейсу g0/0/0, когда заметил, отправил его в шатдаун)

- Аналогично для R2:

![image](https://user-images.githubusercontent.com/89464074/175112646-3004606f-1f10-4ddb-a66e-8a1f10df18f9.png)


### Часть 2. Настройка и проверка базовой работы протокола OSPFv2 для одной области
- В режиме конфигурации OSPF с идентификатором 56 настраиваем идентификаторы роутеров и инструкцию сети между ними в area 0

![image](https://user-images.githubusercontent.com/89464074/175115024-27af6eb8-6087-47a2-bdcd-ae974caa80a0.png)
![image](https://user-images.githubusercontent.com/89464074/175115584-d7c32b91-3748-4fa8-8eb4-cfc7afd24a92.png)

- Проверка отношений смежности между роутерами:

![image](https://user-images.githubusercontent.com/89464074/175117557-7fd05008-ac35-45cb-ada2-e915b411810b.png)

На роутере R2 также была добавлена сеть loopback 192.168.0.0 255.255.255.0 в Area 0 

![image](https://user-images.githubusercontent.com/89464074/175118433-48b1a970-12f9-4006-9a64-9475ecf319f4.png)

На роутере R1 появился маршрут к сети 192.168.0.0 255.255.255.0.

![image](https://user-images.githubusercontent.com/89464074/175119793-d198b1c3-1aaa-4bd3-a0d0-01eff2bd3bb4.png)

State DR получил роутер R1

![image](https://user-images.githubusercontent.com/89464074/175218938-114cbc3c-efa4-4fe9-ad13-e9d4cd9034dc.png)

Проверка таблицы маршрутизации R1 на наличие сети loopback R2, а также пинг на 192.168.1.1

![image](https://user-images.githubusercontent.com/89464074/175122121-c91da78c-d178-4833-98e3-41d6208604a6.png)


### Часть 3. Оптимизация и проверка конфигурации OSPFv2 для одной области

На R1 и R2 установлены таймеры hello-interval 30 и dead-interval 120, для R1 установлено значение priority 50
Для R1 пропишем статический маршрут по умолчанию, который использует интерфейс 
Loopback 1 в качестве интерфейса выхода и выполним команду default-information originate.

![image](https://user-images.githubusercontent.com/89464074/175773310-8c6267c4-f6b3-45be-9b5c-c082819dd3d4.png)

![image](https://user-images.githubusercontent.com/89464074/175773295-94b4da10-91d4-49c5-9a48-053b33ec5eca.png)

Далее на R2 командой ip ospf network point-to-point настраиваем loopback1 как сеть P-t-P.

![image](https://user-images.githubusercontent.com/89464074/175773228-a371239b-a7d1-47ee-a1f9-8664e4079e74.png)

На роутере R2 среди маршрутов OSPF отображается только маршрут по-умолчанию с R1.

![image](https://user-images.githubusercontent.com/89464074/175773474-c2535458-1821-45f3-b229-474aa91b30c4.png)


Указание на предотвращение отправки объявлений OSPF в сеть Loopback 1 на R2.

![image](https://user-images.githubusercontent.com/89464074/175773773-0b81803b-4740-4fe5-862c-1622cc0d14e2.png)

На R1 и R2 изменяем базовую пропускную способность:

![image](https://user-images.githubusercontent.com/89464074/175773878-e17d416c-7011-4599-b1aa-8d824c1a36c2.png)

Просмотр настроек на R1

![image](https://user-images.githubusercontent.com/89464074/175773958-bebb1e30-4415-454f-a4d7-62637cd68663.png)
![image](https://user-images.githubusercontent.com/89464074/175773994-9568f20c-e94f-4caf-ac8e-1b61a0358307.png)

Проверяем пинг с R2 на loopback1 роутера R1. Пинг прошел успешно.

![image](https://user-images.githubusercontent.com/89464074/175774041-5dec9ca4-db24-4fff-8c63-7f58ab321f1b.png)



