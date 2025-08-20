
## Eine Übersicht aller Schnittstellen eines Routers mit ihrer IP-Adresse

>`Routert` show ip interface brief
>`Router#` show ipv6 interface brief

## IPv4-Adresse auf Switch konfigurieren 

>`Switch(config)#` interface vlan 1 Switch(config-if)# no shutdown
>`Switch(config-if)#` ip address [192.168.1.2](http://192.168.1.2 "http://192.168.1.2/") [255.255.255.0](http://255.255.255.0 "http://255.255.255.0/")
>`Switch(config-if)#` exit

## IPv4- und IPv6-Adresse auf Router konfigurieren

>`Router>` enable
>`Router#` configure terminal
>`Router(config)#` interface FastEtherneto/0
>`Router(config-if)#` ip address [192.168.1.1](http://192.168.1.1 "http://192.168.1.1/") [255.255.255.0](http://255.255.255.0 "http://255.255.255.0/")
>`Router(config-if)#` ipv6 address 2001:0db8:0:1::1/64
>`Router(config-if)#` no shutdown
>`Router(config-if)#` exit
## Switch/ Router benennen

>`Router>` enable
>`Router#` configure terminal
>`Router(config)#` hostname RTA

## User EXEC-Passwort für alle Linien setzen (cisco)

>`RTA(config)#` line console 0
>`RTA(config-line)#` password cisco
>`RTA(config-line)#` login
>`RTA(config-line)#` exit
>`RTA(config)#` line vty o 4
>`RTA(config-line)#` password cisco
>`RTA(config-line)#` login
>`RTA(config-line)#` exit
## Verschlüsseltes Privileged EXEC-Passwort (class)

>`RTA(config)#` enable secret class

## Alle Klartext-Passwörter verschlüsseln

>`RTA(config)#` service password-encryption

## Banner konfigurieren

>`RTA(config)#` banner motd # Zugang ist geschützt! #

## Standard-Gateway für Switch konfigurieren

>`Switch(config)#` ip default-gateway [192.168.1.1](http://192.168.1.1 "http://192.168.1.1/")
## Konfiguration speichern

>`Switch#` copy running-config startup-config