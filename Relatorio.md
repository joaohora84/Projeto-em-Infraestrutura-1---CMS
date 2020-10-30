# Relatório instalação Wordpress


### Objetivo

Mostrar como instalar e configurar o WordPress no Linux Server

### Primeiro temos que configurar o mysql para o WordPress

Presumindo que já temos o mysql instalado, vamos logar no mysql, criar um **DataBase**, e criar um usuário de acesso a este banco para o WordPress.

* Primeiro criamos um banco de dados chamado wordpress:

**> CREATE DATABASE wordpress CHARACTER SET UTF8 COLLATE UTF8**

* Criamos o usuário para este banco: 

**> CREATE USER 'wordpress'@'%' IDENTIFIED BY '1233';**

* Agora damos privilégios para este usuário:

**> GRANT ALL PRIVILEGES ON wordpress.* TO 'wordpress'@'%';**
**> FLUSH PRIVILEGES;**

* 
