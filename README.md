# otus-nfs

Vagrant стенд для NFS или SAMBA
NFS или SAMBA на выбор:

vagrant up должен поднимать 2 виртуалки: сервер и клиент
на сервер должна быть расшарена директория
на клиента она должна автоматически монтироваться при старте (fstab или autofs)
в шаре должна быть папка upload с правами на запись
- требования для NFS: NFSv3 по UDP, включенный firewall

# Работоспособность

Поднимаем кластер `vagrant up`

Проверяем на клиенте папку `test` для юзера vagrant

```
[vagrant@client ~]$ ll /mnt/upload/
total 4
-rw-r--r--. 1 vagrant vagrant 22 Jan 10 07:01 test
```
