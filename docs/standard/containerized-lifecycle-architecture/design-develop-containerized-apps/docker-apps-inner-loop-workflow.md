---
title: Flujo de trabajo de desarrollo de bucle interior para aplicaciones de Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: f7acb60e6136c0250d18bdce23ac21fb6aa80b34
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148868"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a>Flujo de trabajo de desarrollo de bucle interior para aplicaciones de Docker

Antes de desencadenar el flujo de trabajo del bucle exterior que abarca el DevOps completa del ciclo, todo comienza en el equipo de cada desarrollador, codificación de la propia aplicación, con sus lenguajes preferidos o plataformas y probarlo localmente (figura 4-14). Pero en todos los casos, tendrá un punto muy importante en común, con independencia de qué lenguaje, marco o plataformas elija. En este flujo de trabajo específico, siempre desarrolla y prueba contenedores de Docker, pero localmente.

![](./media/image18.png)

Figura 4-14: Contexto de desarrollo de bucle interno

El contenedor o la instancia de una imagen de Docker contiene estos componentes:

-   Una selección de sistema operativo (por ejemplo, una distribución de Linux o Windows)

-   Archivos agregados por el desarrollador (por ejemplo, archivos binarios de aplicación)

-   Configuración (por ejemplo, configuración del entorno y dependencias)

-   Instrucciones para los procesos que ejecutar docker

Puede configurar el flujo de trabajo de desarrollo de bucle interno que usa Docker como el proceso (descrito en la sección siguiente). Tenga en cuenta que los pasos iniciales para configurar el entorno no se incluye, porque es necesario hacer una sola vez.

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a>Creación de una sola aplicación en un contenedor de Docker con Visual Studio Code y CLI de Docker

Las aplicaciones se componen de sus propios servicios, además de bibliotecas adicionales (dependencias).

Figura 4-15 muestra los pasos básicos que normalmente se necesitan para llevar a cabo al compilar una aplicación de Docker, seguida de una descripción detallada de cada paso.

![](./media/image19.png)

Figura 4-15: Flujo de trabajo de alto nivel para el ciclo de vida de aplicaciones de Docker en contenedor mediante la CLI de Docker

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a>Paso 1: Empezar a programar en Visual Studio Code y crear la instantánea inicial de aplicación/servicio

La manera de desarrollar la aplicación es bastante similar a la manera de que hacerlo sin Docker. La diferencia es que al desarrollar, implementar y probar su aplicación o servicios que se ejecutan dentro de contenedores de Docker que se colocan en su entorno local (por ejemplo, una VM Linux o Windows).

**Configurar el entorno local**

Con las últimas versiones de Docker para Mac y Windows, es más fácil que nunca para desarrollar aplicaciones de Docker y el programa de instalación es sencilla.

**Obtener más información** para obtener instrucciones sobre cómo configurar Docker para Windows, vaya a [ https://docs.docker.com/docker-for-windows/ ](https://docs.docker.com/docker-for-windows/).

Para obtener instrucciones sobre cómo configurar Docker para Mac, vaya a <https://docs.docker.com/docker-for-mac/>.

Además, necesitará un editor de código para que realmente puede desarrollar su aplicación a la vez mediante la CLI de Docker.

Microsoft proporciona código de Visual Studio, que es un editor de código ligero que es compatible con Mac, Windows y Linux y proporciona IntelliSense con [soporte para numerosos lenguajes](https://code.visualstudio.com/docs/languages/overview) (JavaScript,. NET, Go, Java, Ruby, Python y más lenguajes modernos) [depuración](https://code.visualstudio.com/Docs/editor/debugging), [integración con Git](https://code.visualstudio.com/Docs/editor/versioncontrol) y [compatibilidad con extensiones](https://code.visualstudio.com/docs/extensions/overview). Este editor es una opción ideal para desarrolladores de Mac y Linux. En Windows, también se puede usar la aplicación completa de Visual Studio.

**Obtener más información** para obtener instrucciones sobre cómo instalar Visual Studio para Windows, Mac o Linux, vaya a <https://code.visualstudio.com/docs/setup/setup-overview/>.

También puede trabajar con la CLI de Docker y escribir el código con cualquier editor de código, pero si usa Visual Studio Code, hace que resulte fácil al autor de Dockerfile y los archivos docker-compose.yml en el área de trabajo. Además, puede ejecutar tareas de Visual Studio Code desde el IDE que le solicitará las secuencias de comandos que se pueden ejecutar operaciones elaboradas mediante la CLI de Docker debajo.

Código de Visual Studio proporciona una extensión, que deberá instalar. Para ello, presione Ctrl + Mayús + P, escriba **instalar ext**, y, a continuación, ejecutar las extensiones: Instale el comando de extensión para que aparezca la lista de extensiones de Marketplace. A continuación, escriba **docker** para filtrar los resultados y, a continuación, seleccione el Dockerfile y Docker Compose archivo (yml) extensión del soporte técnico, como se muestra en la figura 4-16.

![](./media/image20.png)

Figura 4-16: Instalar la extensión de Docker en Visual Studio Code

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a>Paso 2: Crear un DockerFile relacionado con una imagen existente (sin formato del sistema operativo o entornos de desarrollo como Ruby, Node.js y .NET Core)

Necesita un DockerFile por contenedor para implementarse y una imagen personalizada que se crea, por lo tanto, si la aplicación se compone de un único servicio personalizado, tendrá un solo DockerFile. Sin embargo, si la aplicación se compone de varios servicios (como en una arquitectura de microservicios), necesitará un Dockerfile por servicio.

El DockerFile se coloca normalmente en la carpeta raíz de su aplicación o servicio y contiene los comandos necesarios para que Docker sepa cómo configurar y ejecutar esa aplicación o servicio. Puede crear el archivo DockerFile y agréguelo al proyecto junto con el código (node.js, .NET Core, etc.), o bien si está familiarizado con el entorno, eche un vistazo a la siguiente sugerencia.

> [!TIP]
> Puede usar una herramienta de línea de comandos denominada [yo docker](https://github.com/Microsoft/generator-docker), que aplica la técnica scaffolding archivos desde el proyecto en el lenguaje que prefiera y agrega los archivos de configuración de Docker necesarios. Básicamente, para ayudar a desarrolladores principiantes, crea el archivo DockerFile adecuado, docker-compose.yml y otras secuencias de comandos asociados para compilar y ejecutar los contenedores de Docker. Este generador de yeoman le pedirá que con unas cuantas preguntas, que pide su host de contenedor de lenguaje y el destino de desarrollo seleccionado.

![Yo docker](./media/image21.png)

Por ejemplo, la figura 4-17 muestra dos capturas de pantalla de los terminales en Windows y en el equipo Mac, en ambos casos, con yo docker, lo que generará los proyectos de código muestra (actualmente .NET Core, Golang y Node.js como idiomas admitidos) ya está configurados para funcionar en parte superior de Docker.

![](./media/image22.PNG)  ![](./media/image23.png)

Figura 4-17: yo docker herramienta de comandos en Windows (izquierda) y en un equipo Mac

Figura 4-18 se presenta un ejemplo que usa yo docker una vez que un proyecto existente de .NET Core en el lugar donde se ha aplicado scaffolding.

![](./media/image24.PNG)

Figura 4-18: yo docker con un núcleo de .NET existentes del proyecto en su lugar

En el DockerFile, especificar qué imagen de Docker básica que va a usar (por ejemplo, mediante "desde microsoft/dotnet:1.0.0-core"). Normalmente se compilará la imagen personalizada en una imagen base que se puede obtener desde cualquier repositorio oficial en la parte superior del [registro de Docker Hub](https://hub.docker.com/) (como un [imágenes para .NET Core](https://hub.docker.com/r/microsoft/dotnet/) o un [para Node.js](https://hub.docker.com/_/node/)).

***Opción A: Use una imagen de Docker oficial existente***

Uso de un repositorio oficial de una pila de lenguaje con un número de versión garantiza que las mismas características de lenguaje están disponibles en todos los equipos (incluido el desarrollo, pruebas y producción).

Siguiente es un DockerFile de ejemplo para un contenedor de .NET Core:

```
# Base Docker image to use
FROM microsoft/aspnetcore:1.0.1\

# Set the Working Directory and files to be copied to the image
ARG source
WORKDIR /app
COPY ${source:-bin/Release/PublishOutput} .

# Configure the listening port to 80 (Internal/Secured port within Docker host)
EXPOSE 80

# Application entry point
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

En este caso, usa la versión 1.0.1 de la imagen oficial de Docker de ASP.NET Core para Linux denominado microsoft/aspnetcore:1.0.1. Para obtener más información, consulte el [página de la imagen de Docker de ASP.NET Core](https://hub.docker.com/r/microsoft/aspnetcore/) y [página de la imagen de Docker de .NET Core](https://hub.docker.com/r/microsoft/dotnet/). También podría estar utilizando otra imagen comparable como nodo: 4-onbuild para Node.js o muchas otras imágenes preconfiguradas para los lenguajes de desarrollo, que están disponibles en [Docker Hub](https://hub.docker.com/explore/).

En el DockerFile, también debe indicar a Docker que escucha el puerto TCP que va a utilizar en tiempo de ejecución (por ejemplo, el puerto 80).

Hay otras líneas de configuración que se puede agregar en el DockerFile, según el lenguaje o marco que usa, por lo que Docker sabe cómo ejecutar la aplicación. Por ejemplo, se necesita la línea ENTRYPOINT con \["dotnet", "MyCustomMicroservice.dll"\] para ejecutar una aplicación .NET Core, aunque puede tener varias variantes según el enfoque para compilar y ejecutar su servicio. Si usa el SDK y la CLI de dotnet para compilar y ejecutar la aplicación. NET, sería ligeramente diferente. La conclusión es que la línea ENTRYPOINT más líneas adicionales serán diferentes según el lenguaje o plataforma que elija para su aplicación.

**Obtener más información** para obtener información sobre la creación de imágenes de Docker para aplicaciones .NET Core, vaya a <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.

Para más información acerca de cómo crear sus propias imágenes, vaya a [ https://docs.docker.com/engine/\ dockerimages/tutoriales/](https://docs.docker.com/engine/tutorials/dockerimages/).

**Repositorios de imágenes multiplataforma**

Como contenedores de Windows se vuelven más predominantes, un único repositorio puede contener variantes de plataforma, como una imagen de Windows y Linux. Se trata de una nueva característica incluida en Docker que hace posible que utilizan un único repositorio para abarcar varias plataformas, como los proveedores de [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repositorio, que está disponible en el registro de DockerHub. Extraer esta imagen de un host de Windows como la característica cobra vida, se extrae la variante de Windows, mientras que extraer el mismo nombre de imagen de un host Linux extraerá la variante de Linux.

***Opción B: Crear su imagen base desde cero***

Puede crear su propia imagen de base de Docker desde cero como se explica en este [artículo](https://docs.docker.com/engine/userguide/eng-image/baseimages/) de Docker. Este es un escenario que probablemente no es mejor para usted si está empezando con Docker, pero si desea establecer los bits específicos de su propia imagen base, puede hacerlo.

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a>Paso 3: Crear las imágenes de Docker personalizadas insertar su servicio en él

Para cada servicio personalizado que consta de la aplicación, deberá crear una imagen relacionada. Si la aplicación se compone de un único servicio o aplicación web, necesitará una imagen de única.

> [!NOTE]
> Teniendo en cuenta el "bucle exterior DevOps flujo de trabajo", las imágenes se creará un proceso de compilación automatizada siempre que inserte el código fuente en un repositorio de Git (integración continua), por lo que las imágenes se crearán en el entorno global de su código fuente.

Sin embargo, antes de que se considere la posibilidad de ir a esa ruta de bucle exterior, debemos asegurarnos de que la aplicación de Docker realmente funciona correctamente para que no inserción código que podría no funcionar correctamente en el sistema de control de código fuente (Git, etcetera.).

Por lo tanto, cada desarrollador en primer lugar debe hacer todo el proceso de bucle interno para probar localmente y continuar desarrollando hasta que desean insertar una característica completa o cambio en el sistema de control de origen.

Para crear una imagen en su entorno local y mediante el DockerFile, puede usar el comando docker build, como se muestra en la figura 4-19 (también puede ejecutar docker-compose up--de compilación de aplicaciones compuestas por varios contenedores y servicios).

![](./media/image25.png)

Figura 4-19: Ejecuta la compilación de docker

Si lo desea, en lugar de ejecutar directamente docker construido a partir de la carpeta del proyecto, primero puede generar una carpeta que se pueden implementar con las bibliotecas de .NET necesarias mediante la ejecución de dotnet publicar el comando y, a continuación, ejecute la compilación de docker.

En este ejemplo, esto crea una imagen de Docker con el nombre cesardl/netcore-webapi-microservicio-docker: first (: first es una etiqueta, como una versión específica). Puede realizar este paso para cada imagen personalizada, deberá crear la aplicación de Docker compuesta con varios contenedores.

Puede encontrar las imágenes existentes en el repositorio local (el equipo de desarrollo) utilizando el docker de comando de imágenes, como se muestra en la figura 4-20.

![](./media/image26.png)

Figura 4-20: Visualización de imágenes existente con imágenes de docker

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a>Paso 4: (Opcional) Definir los servicios en docker-compose.yml al compilar una aplicación compuesta de Docker con varios servicios

Con el archivo docker-compose.yml puede definir un conjunto de servicios relacionados para implementarse como una aplicación compuesta con los comandos de implementación que se explica en la sección paso siguiente.

Debe crear ese archivo en la ventana principal o la carpeta raíz de la solución; debe tener un contenido similar al siguiente archivo docker-compose.yml:

```yml
version: '2'
services:
  web:
    build: .
    ports:
     - "81:80"
    volumes:
     - .:/code
    depends_on:
     - redis
  redis:
    image: redis
```

En este caso concreto, este archivo define dos servicios: el servicio web (el servicio personalizado) y el servicio redis (un servicio de caché popular). Cada servicio se implementará como un contenedor, por lo que necesitamos utilizar una imagen de Docker concreta para cada uno. Para este servicio web en particular, la imagen debe hacer lo siguiente:

-   Compilar desde el archivo DockerFile en el directorio actual

-   Reenviar el puerto 80 expuesto en el contenedor al puerto 81 en el equipo host

-   Montar el directorio del proyecto en el host a/Code dentro del contenedor, lo que permite modificar el código sin tener que volver a generar la imagen

-   Vincular el servicio web para el servicio redis

El servicio redis usa el [imagen más reciente de redis pública](https://hub.docker.com/_/redis/) extrae del registro de Docker Hub. [Redis](https://redis.io/) es un sistema muy popular de caché para aplicaciones de servidor.

### <a name="step-5-build-and-run-your-docker-app"></a>Paso 5: Compilar y ejecutar la aplicación de Docker

Si la aplicación tiene solo un único contenedor, solo deberá ejecutarla mediante su implementación en el Host de Docker (máquina virtual o servidor físico). Sin embargo, si la aplicación se compone de varios servicios, deberá *componerla*, demasiado. Vamos a ver las distintas opciones.

***Opción A: Ejecutar un único contenedor o servicio***

Puede ejecutar la imagen de Docker mediante el comando docker run, como se muestra aquí:

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

Tenga en cuenta que para esta implementación concreta, se deberá se redirigiendo las solicitudes enviadas al puerto 80 al puerto interno 5000. Ahora, la aplicación está escuchando en el puerto 80 en el nivel de host externo.

***Opción B: Redactar y ejecutar una aplicación de varios contenedores***

En la mayoría de los escenarios empresariales, una aplicación de Docker se compone de varios servicios. En estos casos, puede ejecutar el comando docker-compose copia (figura 4-21), que va a utilizar el archivo docker-compose.yml que ha creado anteriormente. Ejecutar este comando implementa una aplicación compuesta con todos sus contenedores relacionados.

![](./media/image27.png)

Figura 4-21: Resultados de ejecutar el comando "docker-compose up"

Después de ejecutar docker-compose seguridad, implementar la aplicación y sus contenedores relacionados en el Host de Docker, como se muestra en la figura 4-22, en la representación de la máquina virtual.

![](./media/image28.png)

Figura 4-22: Máquina virtual con contenedores de Docker implementados

Docker compose de nota de seguridad y ejecución de docker podría ser suficiente para probar los contenedores en el entorno de desarrollo, pero puede que no los use en absoluto si se esperan trabajar con clústeres de Docker y orquestadores como Docker Swarm, Mesosphere DC/OS o Kubernetes Para poder escalar verticalmente. Si usa un clúster como [modo Docker Swarm](https://docs.docker.com/engine/swarm/) (disponible en Docker para Windows y Mac desde la versión 1.12), debe implementar y probar con otros comandos, como crear servicio de docker para servicios únicos, o cuando haya implementar una aplicación que se compone de varios contenedores, usar docker compose agrupación y myBundleFile, de implementación de docker mediante la implementación de la aplicación compuesta como una pila, como se explica en el artículo [paquetes de aplicaciones distribuidas](https://blog.docker.com/2016/06/docker-app-bundle/) de Docker.

Para [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) y [Kubernetes](https://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) usaría los comandos de implementación diferentes y secuencias de comandos, también.

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a>Paso 6: Probar la aplicación de Docker (localmente, en la máquina virtual local de CD)

Este paso variarán dependiendo de lo que hace la aplicación.

En un muy .NET Core API Web simple "Hello World" implementar como un único contenedor o servicio, solo sería necesario acceder al servicio proporcionando el puerto TCP especificado en el archivo DockerFile.

Si localhost no está activado, para navegar a su servicio, busque la dirección IP para la máquina mediante este comando:

docker-machine ip *su nombre de contenedor*

En el host de Docker, abra un explorador y navegue a ese sitio; debería ver su aplicación o servicio que se está ejecutando, como se muestra en la figura 4-23.

![](./media/image29.png)

Figura 4-23: Probar la aplicación de Docker local mediante localhost

Tenga en cuenta que está utilizando el puerto 80, pero internamente se ha redireccionado al puerto 5000, ya que es cómo se implementa con docker en ejecución, como se explicó anteriormente.

Puede probar esto con CURL desde el terminal. En una instalación de Docker en Windows, la dirección IP predeterminada es 10.0.75.1, como se muestra en la figura 4-24.

![](./media/image30.png)

Figura 4-24: Probar una aplicación de Docker localmente mediante CURL

**Depuración de un contenedor que se ejecutan en Docker**

Visual Studio Code admite la depuración de Docker si usa Node.js y otras plataformas como contenedores de .NET Core.

También se pueden depurar contenedores .NET Core en Docker cuando se usa Visual Studio, como se describe en la sección siguiente.

**Más información:** para más información sobre la depuración de contenedores de Node.js Docker, vaya a <https://blog.docker.com/2016/07/live-debugging-docker/> y [ https://blogs.msdn.microsoft.com/\ usuario\_ed/2016/02/27 / Visual-Studio-Code-New-Features-13-big-Debugging-Updates-Rich-Object-Hover-Conditional-Breakpoints-Node-js-mono-More/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).

>[!div class="step-by-step"]
>[Anterior](docker-apps-development-environment.md)
>[Siguiente](visual-studio-tools-for-docker.md)