# Домашнее задание к занятию "`Кластеризация и балансировка нагрузки`" - `Гак Ярослав`

---

### Задание 1

- Запустите два simple python сервера на своей виртуальной машине на разных портах
- Установите и настройте HAProxy, воспользуйтесь материалами к лекции по [ссылке](https://github.com/netology-code/sflt-homeworks/tree/main/2)
- Настройте балансировку Round-robin на 4 уровне.
- На проверку направьте конфигурационный файл haproxy, скриншоты, где видно перенаправление запросов на разные серверы при обращении к HAProxy.

### Ответ 1

[fial.haproxy](https://github.com/Anudora41/sflt-hw-s/blob/main/HAProxy.cfg) 
  
![alt text](https://github.com/Anudora41/sflt-hw-s/blob/main/servers.png)

![alt text](https://github.com/Anudora41/sflt-hw-s/blob/main/haproxy1.png)

---

### Задание 2

- Запустите три simple python сервера на своей виртуальной машине на разных портах
- Настройте балансировку Weighted Round Robin на 7 уровне, чтобы первый сервер имел вес 2, второй - 3, а третий - 4
- HAproxy должен балансировать только тот http-трафик, который адресован домену example.local
- На проверку направьте конфигурационный файл haproxy, скриншоты, где видно перенаправление запросов на разные серверы при обращении к HAProxy c использованием домена example.local и без него.

### Ответ 2

[fail.haproxy](https://github.com/Anudora41/sflt-hw-s/blob/main/HAProxy2.cfg)


![alt text](https://github.com/Anudora41/sflt-hw-s/blob/main/chast1.png)

![alt text](https://github.com/Anudora41/sflt-hw-s/blob/main/chast2.png)

![alt text](https://github.com/Anudora41/sflt-hw-s/blob/main/haproxy2.png)

---
