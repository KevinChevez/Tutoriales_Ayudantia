# Tutorial - ¿Cómo instalar Docker en Linux Ubuntu (Terminal)?
![Imagen Inicial](./images/DockerUbuntu.png "Imagen inicial")

## 1. Conocimientos previos - breve
  * ¿Qué es Docker?
 
 >Docker es una herramienta, un sistema de administración de contenedores, lanzado oficialmente en 2013. El sistema es extremadamente útil al escalar, actualizar y migrar a otro servidor. - (Coleman, 2020)
 
 Básicamente sirve para crear los contenedores haciendo uso de diferentes imágenes las cuales representan distintos servicios a usar en los sistemas operativos donde se trabajará, estos espacios alojados y considerados como contenedores pueden ser fácilmente configurados a partir de la ejecución de comandos que ayuden en el proceso, siendo así efectivo la creación y alojamiento de subsistemas o servicios que evitan el uso de sus creaciones o usos mediante virtualización y/o máquinas virtuales.
 
 Para más información sobre la documentación de Docker visite el siguiente [enlace🔗](https://docs.docker.com/).
 
 Si desea saber más sobre los comandos que usa Docker en la línea de comandos visite el siguiente [enlace🔗](https://docs.docker.com/engine/reference/commandline/cli/).
 
 * Video referencia Docker y Contenedores.
 
 [![Video referencial](https://img.youtube.com/vi/kkfZs0vJFyU/0.jpg)](https://www.youtube.com/watch?v=kkfZs0vJFyU)

## 2. Tutorial

 1. Actualizar apt de Ubuntu mediante la terminal usando el siguiente comando:
 ```
 $ sudo apt-get update -y & sudo apt-get upgrade -y
 ```

 2. Instalar paquetes necesarios para permitir que apt haga uso de paquetes a través de HTTPS:
 ```
 $ sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
 ```

 3. Añadir la clave GPG del repositorio oficial de Docker, en su sistema mediante el siguiente comando:
 ```
 $ sudo mkdir -p /etc/apt/keyrings
 $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
 ```

 4. Configurar el repositorio usando el siguiente comando:
 ```
 $ echo \
   "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
 ```

 5. Instalar el Docker Engine usando los siguiente comando para actualizar el paquete index e instalar la versión más reciente de Docker Engine:
 ```
 $ sudo apt-get update
 $ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
 ```

 6. Por último verifica que se haya instalado correctamente Docker en tu máquina haciendo uso de los siguientes comandos:
 ```
 $ sudo service docker start
 $ sudo docker run hello-world
 ```
 Si todo salió bien, entonces deberá salir en consola el mensaje Hola mundo que se escribió junto a otra información, esto sucederá debido a que se crea una imagen de test para imprimir el mensaje por consolar y luego se cierra.
 
## 3. Referencias
* Docker. (s.f.). Install Docker Engine on Ubuntu. Recuperado el 25 de September de 2022, de Docker Docs: https://docs.docker.com/engine/install/ubuntu/
* Coleman, D. (27 de Abril de 2022). Server space. Recuperado el 25 de Septiembre de 2022, de Qué es Docker?: https://serverspace.io/es/support/help/what-is-docker/
