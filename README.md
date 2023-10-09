# dig
# Realiza una consulta “dig www.danielcastelao.org” e identifica el significado de cada parte de la respuesta IN, CNAME, A, QUERY SECTION, ANSWER SECTION, AUTHORITY SECTION, etc
; <<>> DiG 9.18.19-1~deb12u1-Debian <<>> www.danielcastelao.org
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 986
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 4096
;; QUESTION SECTION:
;www.danielcastelao.org.                IN      A

;; ANSWER SECTION:
www.danielcastelao.org. 796     IN      A       178.211.133.37

;; Query time: 4 msec
;; SERVER: 8.8.8.8#53(8.8.8.8) (UDP)
;; WHEN: Tue Oct 03 16:12:24 CEST 2023
;; MSG SIZE  rcvd: 67


IN:
<<>> DiG 9.18.19-1~deb12u1-Debian <<>> www.danielcastelao.org A
CNAME:
	DiG 9.18.19-1~deb12u1-Debian
A:
	opcode: QUERY, status: NOERROR, id: 12994
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1
 OPT PSEUDOSECTION
	EDNS: version: 0, flags:; udp: 4096
QUERY SECTION:
	www.danielcastelao.org.                IN      A
ANSWER SECTION:
www.danielcastelao.org. 796     IN      A       178.211.133.37
AUTHORITY SECTION:
	danielcastelao.org.     900     IN      SOA     ns1.hover.com. dnsmaster.hover.com. 1294400577 10800 3600 604800 300
ADDITIONAL:
	;; Query time: 4 msec
;; SERVER: 8.8.8.8#53(8.8.8.8) (UDP)
;; WHEN: Tue Oct 03 16:12:24 CEST 2023
;; MSG SIZE  rcvd: 67



# Realiza las consultas de nombres: moodle.danielcastelao.org, www.danielcastelao.org ¿Diferencias? 
moodle.danielcastelao.org
; <<>> DiG 9.18.19-1~deb12u1-Debian <<>> moodle.danielcastelao.org
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 40552
;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1220
; COOKIE: 03252d25493de66456ac727d651c27e9ef82ee09007f6b60 (good)
;; QUESTION SECTION:
;moodle.danielcastelao.org.     IN      A

;; ANSWER SECTION:
moodle.danielcastelao.org. 841  IN      CNAME   ns.danielcastelao.org.
ns.danielcastelao.org.  841     IN      A       2.136.232.50

;; Query time: 8 msec
;; SERVER: 8.8.8.8#53(8.8.8.8) (UDP)
;; WHEN: Tue Oct 03 16:40:41 CEST 2023
;; MSG SIZE  rcvd: 115

www.danielcastelao.org
; <<>> DiG 9.18.19-1~deb12u1-Debian <<>> www.danielcastelao.org
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 34040
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 4096
;; QUESTION SECTION:
;www.danielcastelao.org.                IN      A

;; ANSWER SECTION:
www.danielcastelao.org. 353     IN      A       178.211.133.37

;; Query time: 0 msec
;; SERVER: 8.8.8.8#53(8.8.8.8) (UDP)
;; WHEN: Tue Oct 03 16:41:35 CEST 2023
;; MSG SIZE  rcvd: 67


# Como podemos ver las diferencias que hay son en el answer section ya que en el moodle.daniel… tiene dos respuestas tanto del principal como de la dirección de enlace y en la otra solo la principal.
## También observamos los cambios en el tiempo de respuesta y el id.
## Así como cambia también los opcode.

## Con relación al dominio www.danielcastelao.org, averigua el nombre y dirección IP de los servidores de DNS autoritativos de dicho dominio. ¿Por qué normalmente suelen ser 2 servidores autoritativos? 

asir2@A09equipo20:~/Escritorio/SRI/dig$ dig www.danielcastelao.org

; <<>> DiG 9.18.19-1~deb12u1-Debian <<>> www.danielcastelao.org
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 59247
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 512
;; QUESTION SECTION:
;www.danielcastelao.org.                IN      A

;; ANSWER SECTION:
www.danielcastelao.org. 763     IN      A       178.211.133.37

;; Query time: 288 msec
;; SERVER: 8.8.8.8#53(8.8.8.8) (UDP)
;; WHEN: Mon Oct 09 17:36:45 CEST 2023
;; MSG SIZE  rcvd: 67



# Realice las consultas de nombres inversas: 130.206.164.68 y de otras direcciones IP que se te ocurran. 

asir2@A09equipo20:~/Escritorio/SRI/dig$ dig -x 130.206.164.68

; <<>> DiG 9.18.19-1~deb12u1-Debian <<>> -x 130.206.164.68
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 22495
;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 512
;; QUESTION SECTION:
;68.164.206.130.in-addr.arpa.   IN      PTR

;; ANSWER SECTION:
68.164.206.130.in-addr.arpa. 7200 IN    PTR     s164m68.unavarra.es.
68.164.206.130.in-addr.arpa. 7200 IN    PTR     pluto.tlm.unavarra.es.

;; Query time: 36 msec
;; SERVER: 8.8.8.8#53(8.8.8.8) (UDP)
;; WHEN: Mon Oct 09 17:32:15 CEST 2023
;; MSG SIZE  rcvd: 113


asir2@A09equipo20:~/Escritorio/SRI/dig$ dig -x 8.8.8.8

; <<>> DiG 9.18.19-1~deb12u1-Debian <<>> -x 8.8.8.8
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 39934
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 512
;; QUESTION SECTION:
;8.8.8.8.in-addr.arpa.          IN      PTR

;; ANSWER SECTION:
8.8.8.8.in-addr.arpa.   18323   IN      PTR     dns.google.

;; Query time: 16 msec
;; SERVER: 8.8.8.8#53(8.8.8.8) (UDP)
;; WHEN: Mon Oct 09 17:35:00 CEST 2023
;; MSG SIZE  rcvd: 73

¿A qué servidor DNS estás consultando? ¿Cómo lo puede cambiar sin tocar los ficheros de configuración del sistema? 

 SERVER: 8.8.8.8#53(8.8.8.8) (UDP)
dig @servidor_dns_deseado nombre_de_dominio

# Obten el registro SOA (Start of Authoriy) del dominio moodle.danielcastelao.org preguntándoselo al servidor DNS de google, y preguntándoselo directamente al servidor primario del dominio danielcastelao.org. 
; <<>> DiG 9.18.19-1~deb12u1-Debian <<>> @8.8.8.8 SOA danielcastelao.org
; (1 server found)
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 38561
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 512
;; QUESTION SECTION:
;danielcastelao.org.            IN      SOA

;; ANSWER SECTION:
danielcastelao.org.     900     IN      SOA     ns1.hover.com. dnsmaster.hover.com. 1294400577 10800 3600 604800 300

;; Query time: 116 msec
;; SERVER: 8.8.8.8#53(8.8.8.8) (UDP)
;; WHEN: Mon Oct 09 18:01:18 CEST 2023
;; MSG SIZE  rcvd: 106

# Consulta la dirección IP de www.elpais.com. ¿Cuánto tiempo almacenará en cache su DNS local este registro de recurso? Pregunta varias veces a su DNS local por esta dirección. ¿Qué observas en el TTL del registro de recurso?

; <<>> DiG 9.18.19-1~deb12u1-Debian <<>> www.elpais.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 19856
;; flags: qr rd ra; QUERY: 1, ANSWER: 3, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 512
;; QUESTION SECTION:
;www.elpais.com.                        IN      A

;; ANSWER SECTION:
www.elpais.com.         229     IN      CNAME   prisa-us-eu.map.fastly.net.
prisa-us-eu.map.fastly.net. 15  IN      A       199.232.194.133
prisa-us-eu.map.fastly.net. 15  IN      A       199.232.198.133

;; Query time: 16 msec
;; SERVER: 8.8.8.8#53(8.8.8.8) (UDP)
;; WHEN: Mon Oct 09 18:05:57 CEST 2023
;; MSG SIZE  rcvd: 115

# Descubre el TTL de diferentes nombres de dominio de servicios que conozca ¿A qué se puede deber esas diferencias? 
; <<>> DiG 9.18.19-1~deb12u1-Debian <<>> planetadeagostini.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 31273
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 512
;; QUESTION SECTION:
;planetadeagostini.com.         IN      A

;; ANSWER SECTION:
planetadeagostini.com.  21600   IN      A       213.192.253.113

;; Query time: 48 msec
;; SERVER: 8.8.8.8#53(8.8.8.8) (UDP)
;; WHEN: Mon Oct 09 18:23:27 CEST 2023
;; MSG SIZE  rcvd: 66

Determina el TTL máximo (original) de un nombre de dominio.

planetadeagostini.com.  21600   IN      A       213.192.253.113

# Averigua cuantas máquinas (diferentes direcciones IP) están detrás del dominio web www.google.es. ¿Obtiene siempre las mismas y en el mismo orden? ¿Por qué? 

# Pregunta ahora lo mismo a un servidor raíz (por ejemplo J.ROOTSERVERS.NET) y compruebe en la respuesta si dicho servidor acepta el modo recursivo. 

# Si queremos ver todas las preguntas que hace el servidor de DNS, que opción tenemos que usar, averigua la dirección IP de www.timesonline.co.uk. ¿Qué pasos ha dado? 

# Utilizando la información disponible a través del DNS determina (nombre y dirección IP) la máquina o máquinas que actúan como servidoras de correo del dominio danielcastelao.org.

# ¿Puedes obtener los registros AAAA de www.facebook.com? ¿A qué corresponden? 


