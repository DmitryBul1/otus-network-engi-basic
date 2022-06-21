# Лабораторная работа 6. Внедрение маршрутизации между виртуальными локальными сетями

### Топология по заданию:



### Часть 1. Создание сети и настройка основных параметров устройства

- Настраиваем маршрутизатор R1

![image](https://user-images.githubusercontent.com/89464074/174739254-85c6ae63-6b3a-44e1-b0bf-87a4c1b00c97.png)

![image](https://user-images.githubusercontent.com/89464074/174740230-b405a519-665f-42b5-921f-97146d57b672.png)

- Настраиваем базовые параметры для коммутаторов S1 и S2

![image](https://user-images.githubusercontent.com/89464074/174741993-b81c768b-bf51-41cc-bc53-93908fb8d800.png)

![image](https://user-images.githubusercontent.com/89464074/174741862-37a91d82-0e91-4653-b0d3-006b19f2446e.png)

![image](https://user-images.githubusercontent.com/89464074/174742958-a186f97c-a02a-4a85-84b0-e57bb16427cd.png)

- Настраиваем узлы PC-A и PC-B в соответствии с таблицей адресации:

![image](https://user-images.githubusercontent.com/89464074/174753806-213dc1b1-c8f5-4cac-b9f1-e7adaf241a4b.png)

![image](https://user-images.githubusercontent.com/89464074/174753943-54bd917f-17e6-4016-afc2-3dc00bbbbb8c.png)

### Часть 2. Создание сетей и назначение портов коммутаторов

- Создаем виланы аналогично для обоих коммутаторов в соответствии с таблицей VLAN

![image](https://user-images.githubusercontent.com/89464074/174761819-8684ba6c-85e8-4200-875a-531924898489.png)

- Настроим SVI и шлюз по-умолчанию

![image](https://user-images.githubusercontent.com/89464074/174767507-a010a801-0b69-40c0-8be7-4fed5d441c8f.png)

- Распределим порты коммутаторов по VLAN в соотв. с таблицей

![image](https://user-images.githubusercontent.com/89464074/174768412-5765eae6-f8d0-4048-b325-06aa4264b8df.png)

![image](https://user-images.githubusercontent.com/89464074/174768835-eed43a1d-9e96-4869-bc18-e021813d465e.png)

![image](https://user-images.githubusercontent.com/89464074/174769535-c46b12fd-5fca-4fc3-957d-a9cd011fbe61.png)

- Создаем VLAN 1000 на обоих коммутаторах, настройка магистралей

![image](https://user-images.githubusercontent.com/89464074/174778423-269a1ab1-089e-462f-925a-cd5abb287816.png)

![image](https://user-images.githubusercontent.com/89464074/174779449-fdc535f8-5c69-483b-ac16-ca61afc79b8d.png)

- Проверяем настройки магистрали:

![image](https://user-images.githubusercontent.com/89464074/174781540-5699e300-e8f0-476e-868f-9993798c4f7e.png)
![image](https://user-images.githubusercontent.com/89464074/174781358-7e645e30-cfb2-4227-ad2c-730a548bee16.png)




