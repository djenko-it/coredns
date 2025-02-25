# Installation de coredns


Étape 2 : Créer la structure de fichiers
Créez un répertoire pour votre projet CoreDNS, par exemple coredns-docker, et structurez-le comme suit :

```
coredns-docker/
├── docker-compose.yml
├── Corefile
└── zones/ (optionnel, pour les fichiers de zone)
```

Tester le DNS


```
 dig @localhost www.example.org                                                                                                                                  130 ↵

; <<>> DiG 9.18.28-1~deb12u2-Debian <<>> @localhost www.example.org
; (2 servers found)
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 1730
;; flags: qr aa rd; QUERY: 1, ANSWER: 1, AUTHORITY: 1, ADDITIONAL: 1
;; WARNING: recursion requested but not available

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; COOKIE: 9b8a5aa0d6db3c3e (echoed)
;; QUESTION SECTION:
;www.example.org.               IN      A

;; ANSWER SECTION:
www.example.org.        3600    IN      A       192.168.1.101

;; AUTHORITY SECTION:
example.org.            3600    IN      NS      ns1.example.org.

;; Query time: 3 msec
;; SERVER: ::1#53(localhost) (UDP)
;; WHEN: Tue Feb 25 21:43:34 CET 2025
;; MSG SIZE  rcvd: 127
```