## practica-bind9 - configuración de zona - comprobación
```
;
; BIND data file for oadri.gal
;
$TTL	604800
@	IN	SOA	oadri.gal. root.oadri.gal. (
			      2		; Serial
			 604800		; Refresh
			  86400		; Retry
			2419200		; Expire
			 604800 )	; Negative Cache TTL
;
@	IN	NS	oadri.gal.
@	IN	A	10.1.0.254
www	IN	CNAME	oadri.gal.
TXT	IN	TXT	un txt
```

### ejecución del comando dig oadri.gal en el contenedor cliente
```
root@7bf79f432b7d:/# dig oadri.gal

; <<>> DiG 9.16.1-Ubuntu <<>> oadri.gal
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 3928
;; flags: qr aa rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; COOKIE: d5b6b79d5dd6ba94010000006197938db886b14d2140b450 (good)
;; QUESTION SECTION:
;oadri.gal.                     IN      A

;; ANSWER SECTION:
oadri.gal.              604800  IN      A       10.1.0.254

;; Query time: 10 msec
;; SERVER: 127.0.0.11#53(127.0.0.11)
;; WHEN: Fri Nov 19 13:07:41 CET 2021
;; MSG SIZE  rcvd: 82

```
