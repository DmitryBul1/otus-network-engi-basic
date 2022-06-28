# Лабораторная работа 11. Настройка и проверка расширенных списков контроля доступа.

### Топология

### Базовые настройки для обоих роутеров

![image](https://user-images.githubusercontent.com/89464074/175990294-51e9fbac-83d5-439b-843c-5a568bb30449.png)

### Базовые настройки для коммутаторов

![image](https://user-images.githubusercontent.com/89464074/175993992-714d1889-4353-4006-8b78-f205e870f23d.png)

### Создаем перечень VLAN на обоих коммутаторах по заданию

![image](https://user-images.githubusercontent.com/89464074/175995196-8b246d40-1153-4c48-b897-d1b805fb9783.png)

- Настроим VLAN 20 на коммутаторах, SVI и шлюз по-молчанию

![image](https://user-images.githubusercontent.com/89464074/175998437-df0bd676-6afc-49ad-8143-ef5bc52a4cd6.png)

- Отправляем неиспользуемые порты в ParkingLot на обоих коммутаторах

![image](https://user-images.githubusercontent.com/89464074/175999834-7edf4ebc-e08a-4d3a-85d7-50de5fca1beb.png)

- Назначим используемые порты коммутаторов соответствующим VLANам

![image](https://user-images.githubusercontent.com/89464074/176001262-224be494-36fe-4f05-9410-c153305ecf2a.png)

![image](https://user-images.githubusercontent.com/89464074/176002120-77948680-53ad-4e4c-82d2-4b07cb0ae21b.png)

### Настроим транки аналогично для обоих коммутаторов

![image](https://user-images.githubusercontent.com/89464074/176004381-7de83d9c-1b77-45cb-bd72-8e05c5e041e6.png)

- Настроим магистральный интерфейс F0/5 на коммутаторе S1 до роутера R1

### Настройка маршрутизации

- Настройка маршрутизации между сетями VLAN на R1. Настроим подинтерфейсы

![image](https://user-images.githubusercontent.com/89464074/176010144-4227857e-d695-47b2-9ee5-9887edf9ed7b.png)

- Добавим loopback на R1

![image](https://user-images.githubusercontent.com/89464074/176008822-9c8f25d0-bc4b-40aa-a46b-d1df86d99e2b.png)

![image](https://user-images.githubusercontent.com/89464074/176010010-97cc493f-4683-4aa2-b73e-d57da062a71d.png)

### R2 маршрут по-умолчанию

![image](https://user-images.githubusercontent.com/89464074/176019528-235caaf7-3f80-4502-a5f1-d63d21fe1db1.png)


### Настройки удаленного доступа
- Добавим пользователя на все сетевые устройства, подключим SSH

![image](https://user-images.githubusercontent.com/89464074/176012458-eb6276f8-ef59-4eb3-85ea-f8e8a27720a3.png)

![image](https://user-images.githubusercontent.com/89464074/176012992-64b600a6-8e9c-4bb6-a5df-2e365681e503.png)

- Защищенные веб-службы с проверкой подлинности на R1 включить не удалось, т.к Cisco PT 8 не принял команду ip http secure-service.

- Далее настроим узлы в соответствии с таблицей и проведем эхо-запросы по заданию.

![image](https://user-images.githubusercontent.com/89464074/176097354-5dad00a7-2228-4a69-852c-82c42f95c49c.png)

![image](https://user-images.githubusercontent.com/89464074/176097512-b4aedaa5-362a-4970-9dd6-9b781bf03f78.png)

- Подключение по SSH с PC-B на R1 

![image](https://user-images.githubusercontent.com/89464074/176100260-21e658a4-0638-42bc-bc88-fcf7faa9b08c.png)
![image](https://user-images.githubusercontent.com/89464074/176100391-b7817965-255c-4d1a-8842-e9badd6eb312.png)

![image](https://user-images.githubusercontent.com/89464074/176100495-167f1a4d-0ed8-4f5e-ac21-0f7ffd7020e5.png)
![image](https://user-images.githubusercontent.com/89464074/176100603-09e8fad9-1d14-46fa-bc90-0d601c8c59a4.png)









