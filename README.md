# vlan


# ДЗ
    
    Бонды и вланы

    в Office1 в тестовой подсети появляется сервера с доп интерфесами и адресами
    в internal сети testLAN

        testClient1 - 10.10.10.254
        testClient2 - 10.10.10.254
        testServer1- 10.10.10.1
        testServer2- 10.10.10.1

    равести вланами
    testClient1 <-> testServer1
    testClient2 <-> testServer2

    между centralRouter и inetRouter
    "пробросить" 2 линка (общая inernal сеть) и объединить их в бонд 
    проверить работу c отключением интерфейсов

---

# Выполнение  
## Стенд   
![](https://github.com/MaxOOOOON/vlan/blob/main/pictures/network23-1801-024140.png)    

### Запуск стенда 

    vagrant up 

### Проверка бонда через отключения одного из интерфейсов
![](https://github.com/MaxOOOOON/vlan/blob/main/pictures/Screenshot_20211114_205703.png)   
    
![](https://github.com/MaxOOOOON/vlan/blob/main/pictures/Screenshot_20211114_205926.png)    



### Проверка vlan между клиентом и сервером     
    
![](https://github.com/MaxOOOOON/vlan/blob/main/pictures/Screenshot_20211114_210048.png)    
