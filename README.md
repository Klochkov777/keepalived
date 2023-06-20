# admin-zabbix
<<<<<<< HEAD
=======
# Домашнее задание к занятию "`Zabbix 1`" - `Klochkov Vladimir`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1

`Приведите ответ в свободной форме........`

1. [link screen authorization](https://github.com/Klochkov777/admin-zabbix/blob/master/screen/task1.1.png)
2. Вместо Apache был установлен nginx и вместо zabbix-agent был установлен zabbix-agent2. Использовалась версия linux Debian11, zabbix 6.4, postgresql-13. Все это было сделано по рекомендации лектора и на выполнение задания существенного влияния не оказало. Были применены для установки следующие команды:
* sudo wget https://repo.zabbix.com/zabbix/6.4/debian/pool/main/z/zabbix-release/zabbix-release_6.4-1+debian11_all.deb
* sudo dpkg -i zabbix-release_6.4-1+debian11_all.deb
* sudo apt update
* sudo apt install zabbix-server-pgsql zabbix-frontend-php php7.4-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent2
* sudo apt install postgresql-13
* sudo -u postgres createuser --pwprompt zabbix
* sudo -u postgres createdb -O zabbix zabbix
* zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
* Отредактировал файл /etc/zabbix/zabbix_server.conf:  DBPassword=password
* Отредактировал файл /etc/zabbix/nginx.conf -- раскоментировал: # listen 8080;  # server_name example.com;
* systemctl restart zabbix-server zabbix-agent nginx php7.4-fpm
* systemctl enable zabbix-server zabbix-agent nginx php7.4-fpm


### Задание 2

1. [link screen authorization](https://github.com/Klochkov777/admin-zabbix/blob/master/screen/task2.1.png)
2. [link screen hosts connected](https://github.com/Klochkov777/admin-zabbix/blob/master/screen/task2.2.png)
3. [link screen log](https://github.com/Klochkov777/admin-zabbix/blob/master/screen/task2.3.png)
4. Для выполнения задания не пользовался bash. Был использован графический интерфейс zabbix. Поэтому команд не предоставляю.

>>>>>>> bae5bb3 (finished task1.2)
