# Домашнее задание к занятию "`Резервное копирование`" - `Гак Ярослав`

---

### Задание 1

- Составьте команду rsync, которая позволяет создавать зеркальную копию домашней директории пользователя в директорию `/tmp/backup`
- Необходимо исключить из синхронизации все директории, начинающиеся с точки (скрытые)
- Необходимо сделать так, чтобы rsync подсчитывал хэш-суммы для всех файлов, даже если их время модификации и размер идентичны в источнике и приемнике.
- На проверку направить скриншот с командой и результатом ее выполнения

### Ответ 1

Команду rsync

```
rsync -avc --delete --exclude '.*' /home/kuliaev/ /tmp/backup/
```

![alt text](https://github.com/Anudora41/sflt-hw-s/blob/main/rsync.png)
![alt text](https://github.com/Anudora41/sflt-hw-s/blob/main/rs2.png)

---

### Задание 2

- Написать скрипт и настроить задачу на регулярное резервное копирование домашней директории пользователя с помощью rsync и cron.
- Резервная копия должна быть полностью зеркальной
- Резервная копия должна создаваться раз в день, в системном логе должна появляться запись об успешном или неуспешном выполнении операции
- Резервная копия размещается локально, в директории `/tmp/backup`
- На проверку направить файл crontab и скриншот с результатом работы утилиты.

### Ответ 2

![alt text](https://github.com/Anudora41/sflt-hw-s/blob/main/crontab.png)

Скрипт rsync.sh

```
#!/bin/bash

source=$HOME 
dest='/tmp/backup/'

rsync_sending=$(rsync -avc --delete --exclude '.*' $source $dest  2>&1 | sed  '/^#\|^$\| *#/d' | awk 'NR==1 {print $1}')

if [ -d "$dest" ]; then
        if [ $rsync_sending == "sending" ] ; then
                logger "backup created Successfully";
        else
                logger "backup no create";
        fi
else
        logger "backup dir not found";
fi
```

Работа утилиты

![alt text](https://github.com/Anudora41/sflt-hw-s/blob/main/result%20util.png)

---
