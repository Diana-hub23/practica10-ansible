FROM ubuntu:20.04

# Instalar Apache + SSH
RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y tzdata apache2 openssh-server && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Crear directorio para SSH
RUN mkdir /var/run/sshd

# Configurar contraseña para root
RUN echo "root:clave123" | chpasswd

# Permitir login root por SSH
RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config

# Página HTML inicial
RUN echo "<h1>hello world desde Servidor configurado con Ansible DIANA TEJEDA </h1>" > /var/www/html/index.html

# Exponer puertos
EXPOSE 80 22

# Iniciar Apache + SSH
CMD service apache2 start && /usr/sbin/sshd -D

