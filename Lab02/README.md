# Лабораторная работа 2. Просмотр таблицы MAC-адресов коммутатора.
### Часть 1. Создание и настройка сети
- Топология

![image](https://user-images.githubusercontent.com/89464074/131843044-4f97c3a9-73f1-451d-8d96-2de7b902a006.png)

- Настроим сетевые интерфейсы компьютеров PC-A и PC-B:
![image](https://user-images.githubusercontent.com/89464074/131844243-dc5a25f4-eb2b-4d10-8601-7a1ead8a9d59.png) ![image](https://user-images.githubusercontent.com/89464074/131844407-1a944791-cf7a-415d-96a7-4d66e1cf70ec.png)

- Инициализируем перезагрузку коммутаторов командой **reload** и настроим базовые параметры через консоль (смена имени хоста, установка IP-адреса, защита паролями режима EXEC, консольной линии и линий VTY)

![image](https://user-images.githubusercontent.com/89464074/132118028-32d09088-01fe-40a4-a198-73a1f1947fd2.png)
![image](https://user-images.githubusercontent.com/89464074/132118191-4979eede-0df0-4d61-9c13-3772fa2a0daa.png)





### Часть 2. Часть 2. Изучение таблицы МАС-адресов коммутатора.

- Используем команду ipconfig /all в командных строках компьютеров PC-A и PC-B:

![image](https://user-images.githubusercontent.com/89464074/132118337-193243be-039d-47be-ab42-3cc4337fb8ca.png) ![image](https://user-images.githubusercontent.com/89464074/132118372-fb73e87c-e42d-45a2-a114-d2992c290637.png)



MAC-адрес компьютера PC-A: **0003.E4A6.7A62**

MAC-адрес компьютера PC-B: **00D0.BA14.6491**

- Подключаемся к коммутаторам S1 и S2 через консоль и выполняем команду **show interface F0/1**

![image](https://user-images.githubusercontent.com/89464074/132118404-4e555c73-8be3-4447-9775-139b0490e618.png) ![image](https://user-images.githubusercontent.com/89464074/132118431-d81f36ec-5c47-4c88-af58-d1e5d87c1a9b.png)

МАС-адрес коммутатора S1 Fast Ethernet 0/1: **0060.7044.5501 (bia 0060.7044.5501)**

МАС-адрес коммутатора S2 Fast Ethernet 0/1: **00e0.f978.db01 (bia 00e0.f978.db01)**

- Подключаемся к S2 и командой **show mac address-table** отображаем таблицу MAC-адресов:

![image](https://user-images.githubusercontent.com/89464074/132118530-e453f269-0b0d-429e-b9b2-2cb7aff0d4ee.png)

В таблице записан только MAC-адрес коммутатора S1 **0060.7044.5501** порта **f0/1**.

- Очистим таблицу MAC-адресов на коммутаторе S2, используя команду **clear mac address-table dynamic **

![image](https://user-images.githubusercontent.com/89464074/132118642-92e572c4-0d4d-4469-924e-d70dad0272d4.png)

Полсле очистки таблицы и повторного просмотра отображается только MAC коммутатора S1.

После выполнения эхо-запросов с узлов PC-A и PC-B таблица MAC-адресов на S2 выглядит так:
![image](https://user-images.githubusercontent.com/89464074/132118780-8374a14e-6b1a-4c60-a95c-b4cc545b0860.png)

Появился MAC-адрес компьютера PC-A **0003.E4A6.7A62**, с отображаемым портом f0/1, потому как его адрес попал в коммутатор S2 через коммутатор S1.
Также отображается MAC-адрес компьютера PC-B **00D0.BA14.6491** с портом f0/18, так как он подключен к S2 напрямую.

- На компьютере PC-B выполняем команду **arp -a**:

![image](https://user-images.githubusercontent.com/89464074/132119098-7a40c5d7-89f4-4cd7-8f70-57f1722c2817.png)

Отображается адрес коммутатора S2.

- Выполняем эхо-запросы с узла PC-B на узел PC-A и коммутаторы S1 и S2:

![image](https://user-images.githubusercontent.com/89464074/132119179-e8161f91-28be-41e5-95ce-4f6614750f3b.png)

Ответы пришли от всех устройств.

- Подключаемся к S2 для повторного анализа таблицы MAC-адресов:

![image](https://user-images.githubusercontent.com/89464074/132119237-afa15f99-e0c5-49a6-b2de-165dd7f0c3dd.png)

Добавился новый адрес **00d0.ff34.8b7d** с портом f0/1 (данный адрес относится к порту коммутатора S1 f0/6, к которому напрямую подключен компьютер PC-A).

- Повторно выполняем команду **arp -a** на компьютере PC-B:

![image](https://user-images.githubusercontent.com/89464074/132119385-87618985-9ec9-4c3d-a6ad-439d60163317.png)

Появились адреса всех устройств (PC-A, S1 и S2).
