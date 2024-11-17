# Rmp-Nginx
Se implementara un servicio de streaming con Rtmp & Nginx con el uso de Docker

# implementacion de servidor Nginx-Rtmp con docker 

# Instalacion de docker 
- Instalar docker-ce y containerd, habilitar el firewalld el cual lo necesita docker
```
sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

sudo dnf check-update
sudo dnf install docker-ce docker-ce-cli containerd.io
sudo systemctl start firewalld
sudo systemctl start docker
sudo systemctl status docker
```
1. PASO 1 Ejecutar este comando para descargar Nginx & Rtmp
```
docker run -d -p 80:80 -p 1935:1935 --name nginx-rtmp tiangolo/nginx-rtmp
```
_NOTA_: Esto descargará y ejecutará una imagen Docker que ya tiene Nginx con el módulo RTMP habilitado.

2. Paso 2: Verificar el contenedor
Para asegurarte de que la imagen esté funcionando correctamente, puedes usar los siguientes comandos:

Verificar el estado del contenedor:
```
sudo docker ps
```
Comprobar si los puertos están abiertos:
```
ss -tuln | grep :80
ss -tuln | grep :1935
```
3. paso 3 configurar obs para transmitir
```
rtmp://192.168.20.101:1935/live/
```
4. paso 4 Configuracion de vlc para ver la trasmision
```
rtmp://192.168.20.101:1935/live/
```
_NOTA_: Tanto en obs y en vlc la ip va a variar dependiendo la red 

# Comprobaciones de usuario
Correr el servicio recuerde ir amentando el numero despes de rtmp-5
```
sudo docker run -d -p 80:80 -p 1935:1935 --name nginx-rtmp-5 tiangolo/nginx-rtmp
```

comprobar la ip  enp08
```
ip a
```
