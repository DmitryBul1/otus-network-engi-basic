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

![image](https://user-images.githubusercontent.com/89464074/175120482-0b549b9c-d280-4165-9f99-32fc174cd7bf.png)

State DR получил роутер R2

![image](https://user-images.githubusercontent.com/89464074/175120945-bc23907d-365e-4a80-83f0-29d5872155df.png)

Проверка таблицы маршрутизации R1 на наличие сети loopback R2, а также пинг на 192.168.1.1

![image](https://user-images.githubusercontent.com/89464074/175122121-c91da78c-d178-4833-98e3-41d6208604a6.png)


### Часть 3. Оптимизация и проверка конфигурации OSPFv2 для одной области
