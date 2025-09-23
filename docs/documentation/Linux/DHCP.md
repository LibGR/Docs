# Mission 2 : DHCP
> [!NOTE]
> Liam BOIGEGRAIN 901

Paramétrage du réseaux en IP Fixe :

![](../media/documentation/Linux/DHCP/000.png)


Mise à jours du serveur et redémarrage :

```
sudo apt update && sudo apt upgrade -y && sudo reboot now
```

Installation du service DHCP :

```
sudo apt install kea-dhcp4-server -y
```

Sauvegarde du fichier de configuration d'origine :

```
sudo mv /etc/kea/kea-dhcp4.conf /etc/kea/kea-dhcp4.conf.bak
```

Confirmation de la carte réseau utilisé pour le DHCP (ici ens3) :

```
etudiant@debian:~$ ip a
2: ens3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 50:6b:8d:9e:cf:ef brd ff:ff:ff:ff:ff:ff
    altname enp0s3
    inet 172.16.53.2/24 brd 172.16.53.255 scope global ens3
       valid_lft forever preferred_lft forever
    inet6 fe80::526b:8dff:fe9e:cfef/64 scope link 
       valid_lft forever preferred_lft forever
```

Configuration du service DHCP : 

```
sudo nano /etc/kea/kea-dhcp4.conf
```

```
{
  "Dhcp4": {
    "interfaces-config": {
      "interfaces": [
        "ens3"
      ]
    },
    "valid-lifetime": 691200,
    "renew-timer": 345600,
    "rebind-timer": 604800,
    "authoritative": true,
    "lease-database": {
      "type": "memfile",
      "persist": true,
      "name": "/var/lib/kea/kea-leases4.csv",
      "lfc-interval": 3600
    },
    "subnet4": [
      {
        "subnet": "192.168.3.0/26",
        "pools": [
          {
            "pool": "192.168.3.2 - 192.168.3.62"
          }
        ],
        "option-data": [
          {
            "name": "routers",
            "data": "192.168.3.1"
          },
          {
            "name": "domain-name-servers",
            "data": "1.1.1.1"
          }
        ]
      },
      {
        "subnet": "192.168.3.64/26",
        "pools": [
          {
            "pool": "192.168.3.66 - 192.168.3.126"
          }
        ],
        "option-data": [
          {
            "name": "routers",
            "data": "192.168.3.65"
          },
          {
            "name": "domain-name-servers",
            "data": "1.1.1.1"
          }
        ]
      },
      {
        "subnet": "192.168.3.128/27",
        "pools": [
          {
            "pool": "192.168.3.130 - 192.168.3.158"
          }
        ],
        "option-data": [
          {
            "name": "routers",
            "data": "192.168.3.129"
          },
          {
            "name": "domain-name-servers",
            "data": "1.1.1.1"
          }
        ]
      },
      {
        "subnet": "192.168.3.160/27",
        "pools": [
          {
            "pool": "192.168.3.162 - 192.168.3.190"
          }
        ],
        "option-data": [
          {
            "name": "routers",
            "data": "192.168.3.161"
          },
          {
            "name": "domain-name-servers",
            "data": "1.1.1.1"
          }
        ]
      },
      {
        "subnet": "192.168.3.192/27",
        "pools": [
          {
            "pool": "192.168.3.194 - 192.168.3.222"
          }
        ],
        "option-data": [
          {
            "name": "routers",
            "data": "192.168.3.193"
          },
          {
            "name": "domain-name-servers",
            "data": "1.1.1.1"
          }
        ]
      },
      {
        "subnet": "192.168.3.224/28",
        "pools": [
          {
            "pool": "192.168.3.226 - 192.168.3.238"
          }
        ],
        "option-data": [
          {
            "name": "routers",
            "data": "192.168.3.225"
          },
          {
            "name": "domain-name-servers",
            "data": "1.1.1.1"
          }
        ]
      }
    ]
  }
}
```

Redémarrage du service : 

```
sudo systemctl restart kea-dhcp4-server.service
```

Vérification de son bon fonctionnement :

```
sudo systemctl status kea-dhcp4-server.service
```

```
● kea-dhcp4-server.service - Kea IPv4 DHCP daemon
     Loaded: loaded (/lib/systemd/system/kea-dhcp4-server.service; enabled; preset: enabled)
     Active: active (running) since Mon 2025-09-15 11:40:39 CEST; 1min 26s ago
       Docs: man:kea-dhcp4(8)
   Main PID: 930 (kea-dhcp4)
      Tasks: 5 (limit: 2142)
     Memory: 2.6M
        CPU: 35ms
     CGroup: /system.slice/kea-dhcp4-server.service
             └─930 /usr/sbin/kea-dhcp4 -c /etc/kea/kea-dhcp4.conf
```
