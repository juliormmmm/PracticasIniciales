# Manual: Instalación de Ubuntu en Máquina Virtual y Configuración de Apache

## 1. Requisitos Previos

- **Software necesario:**
  - VirtualBox o VMware
  - Imagen ISO de Ubuntu (descargar desde [ubuntu.com](https://ubuntu.com))
- **Hardware recomendado:**
  - 4GB de RAM (mínimo)
  - 20GB de espacio en disco

## 2. Creación de la Máquina Virtual

1. Abre VirtualBox o VMware.
2. Crea una nueva máquina virtual y asigna:
   - **Nombre:** Ubuntu Server
   - **Tipo:** Linux
   - **Versión:** Ubuntu (64-bit)
3. Asigna al menos **4GB de RAM**.
4. Crea un disco duro virtual de **20GB o más** (formato VDI o VMDK).
5. Monta la imagen ISO de Ubuntu en la unidad de CD/DVD de la máquina virtual.

## 3. Instalación de Ubuntu

1. Inicia la máquina virtual y selecciona "Instalar Ubuntu".
2. Sigue las instrucciones en pantalla:
   - Selecciona el idioma y la distribución del teclado.
   - Configura la red (puede ser DHCP o estática).
   - Crea un usuario y contraseña.
   - Escoge "Borrar disco e instalar Ubuntu" si es una instalación nueva.
3. Espera a que finalice la instalación y reinicia la máquina.

## 4. Instalación de Apache

1. Abre una terminal y actualiza los paquetes:
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```
2. Instala el servidor Apache:
   ```bash
   sudo apt install apache2 -y
   ```
3. Verifica el estado del servicio:
   ```bash
   sudo systemctl status apache2
   ```
   - Si no está activo, ejecuta:
     ```bash
     sudo systemctl start apache2
     ```
   - Para activarlo al inicio del sistema:
     ```bash
     sudo systemctl enable apache2
     ```

## 5. Verificación del Servidor Apache

1. Abre un navegador web y accede a `http://localhost` o la IP de la máquina virtual.
2. Si Apache está funcionando correctamente, verás la página de bienvenida de Apache.

## 6. Configuración del Firewall (Opcional)

Si estás usando `ufw`, permite el tráfico en el puerto 80:
```bash
sudo ufw allow 80/tcp
sudo ufw enable
```

## 7. Conclusión

Con estos pasos, has instalado Ubuntu en una máquina virtual y configurado un servidor Apache. Puedes comenzar a desplegar sitios web en la carpeta `/var/www/html/`.

¡Listo para usar tu servidor web en Ubuntu!
