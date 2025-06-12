<h1>ENTORNOS DE DESARROLLO EN LA AUTOMATIZACION DE REDES</h1>

# Indice

1. [Introduccion](#1-introduccion)  
2. [Desarrollo](#2-desarrollo)  
   - [2.1 Descripcion de las herramientas utilizadas para automatizacion](#21-dhupa)  
     - [2.1.1 Docker Engine](#211-de)  
     - [2.1.2 Docker Compose](#212-dc)  
     - [2.1.3 Docker Swagger](#213-ds)  
   - [2.2 Procedimiento de instalacion](#22-pdi)  
     - [2.2.1 Instalacion tecnica de herramientas necesarias](#221-ithn)  
     - [2.2.2 Instalacion tecnica de Docker](#222-itd)  
     - [2.2.3 Instalacion tecnica de Git](#223-itg)  
   - [2.3 Evidencia de pruebas de verificacion de funcionamiento](#23-epvf)  
     - [2.3.1 Imagen Hello-world](#231-hw)  
     - [2.3.2 Archivo .YML](#232-yml)  
3. [Conclusion](#3-conclusion)

## 1. INTRODUCCION <a name="#1-introduccion"></a>
<p>En el presente reporte se documenta el procedimiento realizado para la instalación, configuración y verificación del funcionamiento de herramientas de automatización de redes utilizadas en la Unidad I del curso "Automatización de Infraestructura Digital". Se abordan las herramientas principales como Docker Engine, Docker Compose y Docker Swagger, así como el entorno de desarrollo empleado, incluyendo Visual Studio Code (VSCode), Git y los plugins necesarios. Este archivo README busca ser una guía técnica clara y reproducible, útil tanto para estudiantes como profesionales que desean automatizar la infraestructura de red mediante contenedores.

Durante el proceso, se ejecutaron pruebas para verificar el correcto funcionamiento del entorno de desarrollo, como la ejecución de la imagen “hello-world” con Docker, y el despliegue de un archivo .yml usando Docker Compose para comprobar la creación y ejecución de contenedores. Además, se incluye una lista de verificación y recursos de comunidades colaborativas que sirvieron de apoyo durante el proceso. El objetivo es dejar documentado un procedimiento funcional que sirva como base para la automatización de infraestructura en proyectos futuros.</p>

# 2. DESARROLLO <a name="#2-desarrollo"></a>

# 2.1 DESCRIPCION DE LAS HERRAMIENTAS PARA LA AUTOMATIZACION <a name="#21-dhupa"></a>
# 2.1.1 DOCKER ENGINE <a name="#211-de"></a>
<p>Motor de contenedores que permite crear, ejecutar y gestionar contenedores de forma eficiente. Facilita la implementacion de aplicaciones empaquetadas con todas sus dependencias.</p>

# 2.1.2 DOCKER COMPOSE <a name="#212-dc"></a>
<p>Herramienta para definir y correr aplicaciones Docker multicontenedor mediante archivos .yml, permitiendo una gestion centralizada y automatizada.</p>

# 2.1.3 DOCKER SWAGGER <a name="#213-ds"></a>
<p>Herramienta para la documentacion y prueba de APIs RESTful. Permite crear interfaces interactivas para consumir y probar servicios de forma sencilla y visual.</p>

# 2.2 PROCEDIMIENTO DE INSTALACION <a name="##22-pdi"></a>
# 2.2.1 INSTALACION TECNICA DE HERRAMIENTAS NECESARIAS <a name="#221-ithn"></a>
# 2.2.2 INSTALACION TECNICA DE DOCKER <a name="#222-itd"></a>
INSTALACION
Ir a https://docs.docker.com/engine/install/ubuntu y seguir las instrucciones.
- Paso 1: Actualizar el sistema
```shell
    sudo apt-get update
```
<p>Este comando actualiza la lista de paquetes disponibles y sus versiones desde los repositorios configurados en tu sistema.</p>

- Paso 2: Instalar certificados y curl
```shell
    sudo apt-get install ca-certificates curl
```
<p>Este comando asegura que el sistema reconozca certificados digitales de sitios seguros.</p>

- Paso 3: Crear directorio para guardar la clave GPG
```shell
    sudo install -m 0755 -d /etc/apt/keyrings
```
<p>Crear el directorio /etc/apt/keyrings y otorgarle permisos de lectura y ejecucion.</p>

- Paso 4: Descargar la clave GPG de Docker
```shell
    sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
```
<p>Descargar la clave publica y guardarla en /etc/apt/keyrings/docker.asc </p>

- Paso 5: Dar permisos de lectura a la clave
```shell
    sudo chmod a+r /etc/apt/keyrings/docker.asc
```
<p>Permite que el archivo sea legible por todos los usuarios del sistema para que apt pueda usarlo.</p>

- Paso 6: Agregar el repositorio de Docker a APT
```shell
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

- Paso 7: Instalar la ultima version de los paquetes de Docker
```shell
    sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

- Paso 8: Verificar que la instalacion sea exitosa
```shell
    sudo docker run hello-world
```

- Paso 9: Crear el docker group
```shell
    sudo groupadd docker
```

- Paso 10: Añade tu usuario al docker grupo
```shell
    sudo usermod -aG docker $USER
```

- Paso 11: Para activar cambios en el grupo
```shell
    newgrp docker
```

- Paso 12: Verificar  que pueda ejecutar dockercomandos sin sudo.
```shell
    docker run hello-world
```

- Para activar cambios en el grupo
```shell
newgrp docker
```

## Comandos basicos
Lista de comandos basicos de docker
- **Listar las imagenes disponibles en el sistema**
```shell
docker ps -a
```

- **Inicializar un contenedor:**
```shell
        docker start [nombre o ID]
```

- **Ver los Logs de los contenedores:**
```shell
        docker logs [nombre contenedor]
```

- **Detener los contenedores**
```shell
        docker stop [nombre contenedor]
```

- **Eliminar un contenedor:**
```shell
        docker rm [nombre o ID]
```

- **Eliminar una imagen:**
```shell
        docker image rm [nombre o ID]
```

# Repositorio de Docker
[Repositorio](https://hub.docker.com)

# Crear imagen a partir de un archivo Dockerfile
```shell
docker build -t nameapp:tag --no-cache--build-arg JAR_FILE=target/*.jar .
```

# Levantar un contenedor a partir de una imagen
```shell
docker run -p 80:80 -p 8080:8080 --name containername nameapp:tag
```

# 2.2.3 INSTALACION TECNICA DE GIT <a name="#223-itg"></a>

```shell
sudo apt install git

```

# GUÍA BASICA GIT

- inicializar GIT
```shell
git init
```

- Cambiar el nombre de las ramas
```
git branch -m [rama-anterior] [nuevo-nombre]
git branch -m master main
```

- Pasar los archivos (modificados y/o agregados) al area de preparacion (Stagin area)
```
git add .
```

- Realizar el commit
```
git commit -m "Creacion del proyecto"
```

- Configuracion de usuario y correo
```
git config --global user.name "Yazmin Rincon"

git config --global user.email "azrayos01@gmail.com"
```

- Ver lista de configuracion
```
git config --list
```

# 2.3 EVIDENCIA DE PRUEBAS DE VERIFICACION DE FUNCIONAMIENTO <a name="#23-epvf"></a>

# 2.3.1 IMAGEN HELLO-WORLD <a name="#231-hw"></a>
<img src=\imagenes\HELLO.png>

# 2.3.2 ARCHIVO .YML <a name="#232-yml"></a>
<img src=\imagenes\yml.png>

# 3 CONCLUSION <a name="#3-conclusion"></a>

<p>Durante el desarrollo de esta actividad, adquirí conocimientos sólidos sobre la instalación, configuración y verificación de un entorno de desarrollo moderno orientado a la automatización de redes digitales. El proceso implicó el uso de herramientas actuales y ampliamente adoptadas en la industria, como Docker y Docker Compose, las cuales permiten encapsular aplicaciones y servicios dentro de contenedores, facilitando su despliegue, escalabilidad y mantenimiento. Gracias a estas herramientas, fue posible establecer un entorno funcional y reproducible, lo cual es fundamental en proyectos de infraestructura digital.

La realización de pruebas como la ejecución de la imagen "hello-world" y el despliegue de servicios mediante archivos .YML confirmaron que las herramientas fueron instaladas y configuradas correctamente. Estos ensayos prácticos permitieron validar la operatividad del entorno y aseguraron que se encuentra listo para soportar desarrollos más complejos en fases posteriores del curso o en proyectos reales.

Además, durante esta experiencia aprendí a recurrir a recursos de comunidades colaborativas en línea, como foros técnicos, documentación oficial y repositorios públicos, los cuales resultaron fundamentales para la resolución de errores, la comprensión de conceptos avanzados y la mejora general del proceso. Este enfoque no solo me permitió avanzar de forma más eficiente, sino que también fortaleció mi capacidad para investigar y aplicar soluciones técnicas por mi cuenta.

En resumen, esta actividad no solo me brindó una introducción práctica al uso de herramientas de automatización modernas, sino que también consolidó mis competencias en la administración de entornos digitales, promoviendo buenas prácticas y reforzando mi perfil profesional en el ámbito de las redes inteligentes y la ciberseguridad.</p>
