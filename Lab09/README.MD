### Лабораторная работа9. Конфигурация безопасности коммутатора

# Топология

![image](https://user-images.githubusercontent.com/89464074/175300599-a117a12b-ffc0-4a94-bdc4-5b4e54e7f91a.png)

- Настройка роутера по инструкции задания

![image](https://user-images.githubusercontent.com/89464074/175353616-c451c2fb-f7fc-43fd-a418-bb19414b876e.png)

возникла ошибка при вводе директивы ip dhcp relay information trusted

![image](https://user-images.githubusercontent.com/89464074/175353761-f28b73a2-0ebe-4ce8-84b1-30bcf12d9d7a.png)


![image](https://user-images.githubusercontent.com/89464074/175290138-5ea59640-70de-41d8-bdc7-1584dc4794c9.png)


- Настройка коммутаторов S1 и S2, создание VLAN:
- Настроим коммутаторы S1 и S2, зададим имя и description для активных портов:
![image](https://user-images.githubusercontent.com/89464074/175304862-5bc8ceb7-5322-47e1-bcd1-00d99f4e1448.png)
![image](https://user-images.githubusercontent.com/89464074/175354974-2646f8e3-2828-4a07-82bd-a276d28a6579.png)

- Создадим VLAN 10 на S1 и S2, укажем IP-адрес (по таблице задания) и шлюз по-умолчанию:

![image](https://user-images.githubusercontent.com/89464074/175356680-72221ee6-451f-42dd-af0b-693d61a0b596.png)

(примечание - ошибка в адресе на S1, в процессе всплыло - исправлено)

- Создаем VLAN 333 и 999 коммутаторах S1 и S2

![image](https://user-images.githubusercontent.com/89464074/175360187-4beb0b6b-7da0-4c07-8fb9-09de7233194f.png)

###Настройки безопасности коммутатора.

- Релизация магистральных соединений 802.1Q.

![image](https://user-images.githubusercontent.com/89464074/175363417-c96dec9b-3da4-4d7a-bda7-75b781f15e56.png)
![image](https://user-images.githubusercontent.com/89464074/175363533-e2e45741-c2bc-445d-8be4-9b4abb9c7da1.png)

- Смотрим результат при помощи команды sh int trunk

![image](https://user-images.githubusercontent.com/89464074/175363996-5dd94f2f-708d-4ef2-9753-879239f6d4f8.png)

При помощи команды switchport nonegotiate на портах f0/1 коммутаторов S1 и S2 было отключено согласование DTP.

![image](https://user-images.githubusercontent.com/89464074/175366136-fa1453f3-7f71-4793-8275-5b61e1f513ad.png)

- Порты f0/5-6 коммутатора S1 и порт s0/18 коммутатора S2 привязываются к VLAN 10

![image](https://user-images.githubusercontent.com/89464074/175367552-07b616da-b947-4602-b8bd-c156ea2d1a45.png)
