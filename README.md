# Documentacion
Javier Monterroso        201700831
Alberto Ixcop            201700831
## Usuarios IAM
## Arquitectura
### Instancias de EC2
#### Paso 1
Desde la interfaz de AWS irnos al apartado de EC2 y buscar la pestaña de instancias, desde ahi seleccionamos la opcion de lanzar instancia
#### Paso 2
Se selecciona la imagen de ubuntu 20, con la capa gratuita y cuando llegamos a la tercer pestaña de configuracion seleccionarmos nuestra vpc y subnet publica de la siguiente manera
![image](https://user-images.githubusercontent.com/14981793/130138267-408dbaf7-a801-4aee-9604-89a2b64832c2.png)
#### Paso 3
Se deja todo por defecto y en el paso 6 se crea un nuevo grupo de seguridad llamado SSH
![image](https://user-images.githubusercontent.com/14981793/130138531-18577305-b4ce-4521-98bc-86a5ce1efda4.png)
#### Paso 4 
Se repite todo el proceso para crear la segunda instancia de EC2 con la red privada, si el proceso salio correctamente nuestras instancias se verian de la siguiente manera
![image](https://user-images.githubusercontent.com/14981793/130139114-e4ce6714-56a3-44ed-b8f6-8048c437da49.png)
### Docker Engine
#### Paso 1
Nos conectamos con el protocolo ssh usando termius, luego ejecutamos el comando sudo apt-get update para actualizar 
#### Paso 2
 sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
#### Paso 3
 curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
#### Paso 4
 echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
#### Paso 5
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
### Docker Compose
#### Paso 1
Run this command to download the current stable release of Docker Compose:
 sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
#### Paso 2
Apply executable permissions to the binary:
sudo chmod +x /usr/local/bin/docker-compose
#### Paso 3
Si los ultimos pasos fueron correctos podremos ver el siguiente output
![image](https://user-images.githubusercontent.com/14981793/136709416-de05b814-e0dc-4de0-b068-f28e160b5de2.png)
