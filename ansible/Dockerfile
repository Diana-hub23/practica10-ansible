FROM ubuntu:22.04

RUN apt update && \
    apt install -y openssh-server python3 apache2 && \
    mkdir /var/run/sshd

RUN echo "<h1>Hola desde \$(hostname)</h1>" > /var/www/html/index.html

RUN echo "root:root" | chpasswd

RUN sed -i 's/^#\?PermitRootLogin.*/PermitRootLogin yes/' /etc/ssh/sshd_config && \
    sed -i 's/^#\?PasswordAuthentication.*/PasswordAuthentication yes/' /etc/ssh/sshd_config

EXPOSE 22
EXPOSE 80

CMD ["/usr/sbin/sshd", "-D"]
