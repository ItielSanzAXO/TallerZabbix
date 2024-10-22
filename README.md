# Taller Zabbix
Repositorio de introducción a Zabbix

1. Descargar e instalar el paquete de Zabbix 7.0:
   
   ```bash
   wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest+ubuntu24.04_all.deb
   ```
   ```bash
   dpkg -i zabbix-release_latest+ubuntu24.04_all.deb
   ```
   ```bash
   apt update
   ```

2. Configurar la base de datos:
   - Crear una base de datos para Zabbix.
   - Importar el esquema de base de datos:
   
   ```bash
   mysql -uroot -p
   password
    mysql> create database zabbix character set utf8mb4 collate utf8mb4_bin;
    mysql> create user zabbix@localhost identified by 'password';
    mysql> grant all privileges on zabbix.* to zabbix@localhost;
    mysql> set global log_bin_trust_function_creators = 1;
    mysql> quit;
  ```

   ```bash
   zcat /usr/share/doc/zabbix-server-mysql/schema.sql.gz | mysql -u root -p zabbix_db
   ```
