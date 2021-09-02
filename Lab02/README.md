# Лабораторная работа 2. Просмотр таблицы MAC-адресов коммутатора.
### Часть 1. Создание и настройка сети
- Топология

![image](https://user-images.githubusercontent.com/89464074/131843044-4f97c3a9-73f1-451d-8d96-2de7b902a006.png)

Откройте окно конфигурации
a.	Настройте имена устройств в соответствии с топологией.
b.	Настройте IP-адреса, как указано в таблице адресации.
c.	Назначьте cisco в качестве паролей консоли и VTY.
d.	Назначьте class в качестве пароля доступа к привилегированному режиму EXEC.
- Настроим базовые параметры коммутаторов S1 и S2 через консоль (смена имени хоста, установка IP-адреса, защита паролями режима EXEC, консольной линии и линий VTY)

![image](https://user-images.githubusercontent.com/89464074/131839512-945b0804-c9df-4037-bfde-8d293127286b.png) ![image](https://user-images.githubusercontent.com/89464074/131841837-bd12c1e4-a6f9-4b4a-8286-9a3eb3ade946.png)

- Настроим сетевые интерфейсы компьютеров PC-A и PC-B:
![image](https://user-images.githubusercontent.com/89464074/131844243-dc5a25f4-eb2b-4d10-8601-7a1ead8a9d59.png) ![image](https://user-images.githubusercontent.com/89464074/131844407-1a944791-cf7a-415d-96a7-4d66e1cf70ec.png)

### Часть 2. Часть 2. Изучение таблицы МАС-адресов коммутатора.

- Используем команду ipconfig /all в командных строках компьютеров PC-A и PC-B:
![image](https://user-images.githubusercontent.com/89464074/131844929-081419a7-155d-4df5-a38a-937abb9966b6.png)![image](https://user-images.githubusercontent.com/89464074/131845002-4fdc59fb-f4ec-4540-8112-460facd3e0a9.png)

MAC-адрес компьютера PC-A: **00E0.F7A0.67DE**
MAC-адрес компьютера PC-B: **0060.47E5.C7C0**

- Подключаемся к коммутаторам S1 и S2 через консоль и выполняем команду **show interface F0/1 **

![image](https://user-images.githubusercontent.com/89464074/131845707-82454613-c7ff-480a-a333-5dcb042bda06.png)![image](https://user-images.githubusercontent.com/89464074/131845864-556b235f-1046-4706-aa81-97b0e6b41266.png)




