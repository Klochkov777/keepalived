#keepalived
<<<<<<< HEAD
=======
# Домашнее задание к занятию "`Keepalived/vrrp`" - `Klochkov Vladimir`


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

1. Рабочая конфигурация ноды Master:
* vrrp_instance failover_test {
* state MASTER
* interface enp0s8
* virtual_router_id 10
* priority 110
* advert_int 4
* authentication {
* auth_type AH
* auth_pass 1111
* }
* unicast_peer {
* 192.168.1.103
* }
* virtual_ipaddress {
* 192.168.1.50 dev enp0s8 label enp0s8:vip
* }
* }

2. Рабочая конфигурация ноды Backup:
* vrrp_instance failover_test {
* state BACKUP
* interface enp0s8
* virtual_router_id 10
* priority 110
* advert_int 4
* authentication {
* auth_type AH
* auth_pass 1111
* }
* unicast_peer {
* 192.168.1.104
* }
* virtual_ipaddress {
* 192.168.1.50 dev enp0s8 label enp0s8:vip
* }
* }

2. Скриншоты
 - Конфигурация обеих нод [link screen configuration master and backup nodes](https://github.com/Klochkov777/keepalived/blob/master/screen/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-06-20%2002-38-33.png)
 - отображение появления у ноды master (слева) на интерфейсе enp0s8 c ip 192.168.1.103 виртуального ip 192.168.1.50 [link MASTER ip a](https://github.com/Klochkov777/keepalived/blob/master/screen/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-06-20%2002-09-45.png)
 - отображение появления у ноды master (слева) и у ноды backup (справа) на интерфейсах enp0s8 c ip 192.168.1.103 и ip 192.168.1.104 виртуальных ip 192.168.1.50 [link MASTER ip a and BACKUP ip a](https://github.com/Klochkov777/keepalived/blob/master/screen/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-06-20%2002-39-13.png)
 - скрин что у обеих нод сервисы запущены [link services started](https://github.com/Klochkov777/keepalived/blob/master/screen/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-06-20%2003-18-17.png)
 - enp0s8 в state DOWN у MASTER (слева) ip 192.168.1.103, при этом с хоста пингую и делаю tcpdump на хосте (нижняя часть скрина) по ip 192.168.1.103, что является доказательством корректной работы keepalived  [link master down, keepalived workable](https://github.com/Klochkov777/keepalived/blob/master/screen/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20%D0%BE%D1%82%202023-06-20%2003-06-18.png)
