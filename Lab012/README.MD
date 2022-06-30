# Лабораторная работа 12 - Настройка NAT для IPv4

### Топология

![image](https://user-images.githubusercontent.com/89464074/176600189-ee6b2619-0ed4-4a2d-bdfb-fa1625eb0fee.png)

![image](https://user-images.githubusercontent.com/89464074/176591086-1b70d1b5-a3b1-4166-a200-c545a4bb3c0e.png)

### Часть 1. Базовые настройки сетевого оборудования и узлов
- Настроим коммутаторы S1 и S2, присвоим адреса согласно таблице адресации и активируем VLANы

![image](https://user-images.githubusercontent.com/89464074/176597100-3a7b810a-47f7-4a1a-b34f-5856e2ca7e44.png)

- Настроим статические ip-адреса для узлов

![image](https://user-images.githubusercontent.com/89464074/176597459-edf262d5-e9ad-4a09-a4ad-97d37077d9f2.png)

- Настроим роутеры R1 и R2, присвоим адреса и активируем интерфейсы

![image](https://user-images.githubusercontent.com/89464074/176598750-34c71a07-7e6d-4457-b614-3c2fd1400c12.png)

![image](https://user-images.githubusercontent.com/89464074/176599792-8a483d8f-826a-4490-9393-7cbde1bd9a0c.png)

- На R2 добавим интерфейс Loopback1 и маршрут по-умолчанию до R1

![image](https://user-images.githubusercontent.com/89464074/176599960-76338d43-ba52-433d-bba0-ed1f831e3d9d.png)
![image](https://user-images.githubusercontent.com/89464074/176600050-0f8109d8-cb0d-43ba-a0e5-09c22bffc094.png)

### Часть 2
- Настроим NAT на R1, используя пул из трех адресов 209.165.200.226 - 209.165.200.228.

![image](https://user-images.githubusercontent.com/89464074/176601255-da907373-01ec-43d1-bdd1-84db2488619d.png)

- Проверим конфигурацию
Пинг с PC-B На Loopback1 изначально не прошел, пока на R1 не был прописан маршрут ip route 209.165.200.0 255.255.255.224 209.165.200.225, для связи целевой подсети с интерфейсом роутера R1.

![image](https://user-images.githubusercontent.com/89464074/176647110-70b21f36-911f-4920-ac4d-6c771c1b54aa.png)

- Рассмотрим таблицу NAT на R1 после эхо-запросов с PC-B и c PC-A

![image](https://user-images.githubusercontent.com/89464074/176647444-13078d6d-a5ca-4a99-ad84-4c9f1369150b.png)

![image](https://user-images.githubusercontent.com/89464074/176649512-e616660a-1631-4868-8f43-c4a0ebadae34.png)







### Часть 3
