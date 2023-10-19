# Домашнее задание к занятию "Система мониторинга Prometheus.Часть 2»" - `Согонов Алексей`

### Задание 1


![Название скриншота 1](https://github.com/SogonovAN/keepalived-hw/blob/main/1.JPG)`


---

### Задание 2

'''
#!/bin/bash

echo "" > /dev/tcp/192.168.111.5/80 && echo "0" || echo "Closed"
if [ -e /var/www/html/index.nginx-debian.html ]
then
echo "0" >> /dev/null
else
echo "1"
fi

'''

'''
vrrp_track_process check_nginx {
       process "nginx"
}
vrrp_script myscript {
script <"/home/yak14/myscript">
interval 3
}

vrrp_instance VI_1 {
        state MASTER
        interface enp0s3
        virtual_router_id 15
        priority 255
        advert_int 1

        virtual_ipaddress {

              192.168.111.15/24

        }

        track_process {

                   check_nginx
                   myscript


                }

}

'''

![Название скриншота 2](https://github.com/SogonovAN/keepalived-hw/blob/main/2.JPG)`

![Название скриншота 2](https://github.com/SogonovAN/keepalived-hw/blob/main/2.1.JPG)`


---



