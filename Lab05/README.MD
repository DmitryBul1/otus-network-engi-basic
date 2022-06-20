# Лабораторная работа 5. Доступ к сетевым устройствам по протоколу SSH

### Топология по заданию:
![image](https://user-images.githubusercontent.com/89464074/174649685-aebf9ece-25a9-47bb-842f-3ed0fd55f3c4.png)

### Часть 1. Настройка основных параметров устройств

- Первоначальная настройка роутера R1 с отключением поиска DNS, защитой консоли и линий VTY, а также с шифрованием паролей и прописью баннера:

![image](https://user-images.githubusercontent.com/89464074/174652626-c385b1f6-9f5b-4eee-bdf5-bdcb7dcf766f.png)

- Настроим и активируем интерфейс роутера G/0/01:

![image](https://user-images.githubusercontent.com/89464074/174654784-3d5737fc-e716-4cc7-90d7-057130c92e99.png)

- Настройка PC-A по исходным данным таблицы адресации и пробный эхо-запрос на шлюз:

![image](https://user-images.githubusercontent.com/89464074/174656165-cea4d746-a596-45ec-9351-eb77a36cadbf.png)

### Часть 2. Настройка маршрутизатора для доступа по протоколу SSH

- Указываем имя устройства и домен, создаем пользователя, создаем ключи шифрования:

![image](https://user-images.githubusercontent.com/89464074/174658032-380deeb7-53af-4ad3-a27b-d953f0a86894.png)

- Активируем протокол SSH на линиях VTY и сохраняем конфиг:

![image](https://user-images.githubusercontent.com/89464074/174658754-b7603899-18e6-40af-af85-5c8bd7273dd8.png)

- Тестируем подключение с PC-A:

![image](https://user-images.githubusercontent.com/89464074/174659150-907f0abb-30a4-459b-98b1-41daaee23852.png)
![image](https://user-images.githubusercontent.com/89464074/174659237-484db6f5-9d00-4ae2-b254-c6bc623d6c0a.png)

### Часть 3. Настройка коммутатора для доступа по протоколу SSH

- Настроим основные параметры коммутатора:

![image](https://user-images.githubusercontent.com/89464074/174660723-1e65bed6-a74a-4581-87c7-fb00246c9bf0.png)  ![image](https://user-images.githubusercontent.com/89464074/174660774-84a1c17f-d150-4b9e-aca9-7a0921e40774.png)

![image](https://user-images.githubusercontent.com/89464074/174661766-8d842d21-fc2b-4dbb-926b-2cd1120a172e.png)

- Поднимаем интерфейс vlan1 на коммутаторе:

![image](https://user-images.githubusercontent.com/89464074/174661871-f8f0fb6f-d2f4-499d-bed2-04da615b4b60.png)









