# Práctica 10 – Automatización de Servidores con Ansible

En esta práctica se automatizó la implementación de dos servidores web usando **Ansible** y **Docker**.  
El objetivo fue configurar automáticamente Apache en dos contenedores Ubuntu y desplegar una página web personalizada.

---

## 🚀 Tecnologías utilizadas
- **Docker**
- **Docker Compose**
- **Ubuntu**
- **Apache2**
- **Ansible**

---

## 🧱 Estructura del proyecto

practica10-ansible/
│── ansible/
│ ├── Dockerfile
│ ├── hosts
│ └── setup.yml
│── docker/
│ └── Dockerfile
│── docker-compose.yml
│── inventory.ini
└── setup.yml

---

## ⚙️ ¿Qué automatiza Ansible?

El playbook `setup.yml` ejecuta:

1. Instalación de Apache (`apache2`)
2. Creación del archivo `/var/www/html/index.html`
3. Reinicio del servicio Apache dentro de cada contenedor

---

## ▶️ Cómo ejecutar el proyecto

### 1. Levantar los contenedores
```bash
docker-compose up -d
2. Probar acceso manual por SSH
ssh root@127.0.0.1 -p 2221
ssh root@127.0.0.1 -p 2222


Clave: clave123

3. Ejecutar el playbook
ansible-playbook -i inventory.ini setup.yml
La página desplegada contiene un mensaje personalizado:

“🚀 Hola Mundo desde Ansible 🚀”

Ambos servidores muestran la misma página:

http://localhost:8081

http://localhost:8082

Repositorio GitHub con todo el código del proyecto:
👉 https://github.com/Diana-hub23/practica10-ansible


✨ Autor

Diana Tejeda
Práctica realizada para la materia Centro de Cómputos / Infraestructura.
