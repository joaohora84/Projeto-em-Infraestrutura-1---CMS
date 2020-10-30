# Relatório instalação Wordpress


### Objetivo

Mostrar como instalar e configurar o WordPress no Linux Server

### Primeiro temos que configurar o mysql para o WordPress

Presumindo que já temos o mysql instalado, vamos logar no mysql, criar um **DataBase**, e criar um usuário de acesso a este banco para o WordPress.

### Primeiro criamos um banco de dados chamado wordpress:

**> CREATE DATABASE wordpress CHARACTER SET UTF8 COLLATE UTF8**

### Criamos o usuário para este banco: 

**> CREATE USER 'wordpress'@'%' IDENTIFIED BY '1233';**

### Agora damos privilégios para este usuário:

**> GRANT ALL PRIVILEGES ON wordpress.** **TO 'wordpress'@'%';**

**> FLUSH PRIVILEGES;**


### Após configurado o mysql, e supondo que o Apache já está instalado, vamos para a instalação e configuração do WordPress

### Baixe a última versão do WordPress e extraia o pacote:

**cd /tmp**

**wget https://wordpress.org/latest.tar.gz**

**tar -zxvf latest.tar.gz**

### Vamos mover a pasta wordpress para dentro o diretório raiz do Apache e dê ao usuário **www-data** controle total sobre o diretório do wordpress:

**mv wordpress /var/www/html/**

**chown www-data.www-data /var/www/html/wordpress/* -R**

### Vamos agora criar o arquivo wp-config.php:

**cd /var/www/html/wordpress**

**mv wp-config.samble.php wp-config.php**

**nano wp-config.php**

### Dentro do arquivo wp-config.php, edite as informações de conexão do banco de dados de acordo com o que foi criado no início, informando: **DB_NAME, DB_USDER, DB_PASSWORD** :

### Aqui está as configurações como ficarão: 

  define('DB_NAME', 'wordpress');

  define('DB_USER', 'wordpress');

  define('DB_PASSWORD', '1233');

  define('DB_HOST', 'localhost');

  define('DB_CHARSET', 'utf8');

  define('DB_COLLATE', '');

### Por fim, vamos acessar o wordpress pelo navegador. Para isso basta informar no browser o IP do servidor seguido da pasta wordpress: 

  **http://192.168.100.34/wordpress**

### Com isso o assinstente de instação do WordPress será apresentado.

  Na tela que aparece é só inserir as informações de acesso solicitadas e pronto, você poderá acessar o seu WordPress.



### Referência

[Instalando o WordPress no Ubuntu - ITEXPERT.TIPS](https://itexpert.tips/pt-br/wordpress-pt-br/instalando-o-wordpress-no-ubuntu-linux/)

[Como instalar o WordPress no Ubuntu - HOSTINGER.COM.BR](https://www.hostinger.com.br/tutoriais/como-instalar-wordpress-ubuntu/#Instale-e-Configure-Apache-2)










