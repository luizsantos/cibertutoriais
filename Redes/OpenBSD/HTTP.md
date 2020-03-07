

OpenBSD - Servidor Apache HTTP
========================

>**UTFPR - Universidade Tecnológica Federal do Paraná, campus Campo Mourão**  
>Autor: **Prof. Dr. Luiz Arthur Feitosa dos Santos**  
>E-mail: **<luizsantos@utfpr.edu.br>**  

## Introdução

## Instalação

Procurar o pacote:

```console
# pkg_info -Q httpd
apache-httpd-2.4.41
bozohttpd-20190228
darkhttpd-1.12
libmicrohttpd-0.9.66
lighttpd-1.4.54
lighttpd-1.4.54-ldap
lighttpd-1.4.54-ldap-mysql
lighttpd-1.4.54-mysql
p5-HTTPD-Log-Filter-1.08p2
sthttpd-2.26.4p4
```

Instalar:

```console
dacom# pkg_info -Q httpd
apache-httpd-2.4.41
bozohttpd-20190228
darkhttpd-1.12
libmicrohttpd-0.9.66
lighttpd-1.4.54
lighttpd-1.4.54-ldap
lighttpd-1.4.54-ldap-mysql
lighttpd-1.4.54-mysql
p5-HTTPD-Log-Filter-1.08p2
sthttpd-2.26.4p4
``` 

## Verificando o status do serviço:

Basicamente há duas opções:
1. Com o comando ``netstat``:
```console
# netstat -a -p tcp
Active Internet connections (including servers)
Proto   Recv-Q Send-Q  Local Address          Foreign Address        (state)
tcp          0      0  192.168.56.101.ssh     192.168.56.1.33122     ESTABLISHED
tcp          0      0  *.ssh                  *.*                    LISTEN
tcp          0      0  localhost.smtp         *.*                    LISTEN
Active Internet connections (including servers)
Proto   Recv-Q Send-Q  Local Address          Foreign Address        (state)
tcp6         0      0  *.ssh                  *.*                    LISTEN
tcp6         0      0  fe80::1%lo0.smtp       *.*                    LISTEN
tcp6         0      0  localhost.smtp         *.*                    LISTEN
```
2. Com o comando ``fstat``:

```console
# fstat | grep ':80'
```

Bem, nestes dois casos o servidor Apache não está em execução, pois não há nenhuma porta relacionada com HTTP na saída do ``netstat`` e principalmente não há processos relacionados com a porta TCP/80 no ``fstat``.

## Iniciando/Parando o servidor:



## Referências

* <https://dev.to/nabbisen/setting-up-openbsds-httpd-web-server-4p9f>
* <http://www.h-i-r.net/p/hirs-secure-openbsd-apache-mysql-and.html>

