---
title: Flujo de trabajo de desarrollo de bucle interno para las aplicaciones de Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: cda9aa77ca033dced8b6b30538f19f28a5fa63a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a>Flujo de trabajo de desarrollo de bucle interno para las aplicaciones de Docker

Antes de desencadenar el flujo de trabajo de bucle exterior que abarca el DevOps todo ciclo, todo comienza en la máquina de cada programador, codificación de la propia aplicación, usando sus plataformas o idiomas preferidos y probándolo localmente (figura 4-14). Pero en todos los casos, tendrá un aspecto muy importante en común, independientemente del lenguaje, marco de trabajo o plataformas elija. En este flujo de trabajo concreto, siempre se desarrollar y probar contenedores de Docker, pero localmente.

![](./media/image18.png)

Contexto de desarrollo de bucle interno de la figura 4-14:

El contenedor o la instancia de una imagen de Docker contendrá estos componentes:

-   Una selección de sistema operativo (por ejemplo, una distribución de Linux o Windows)

-   Archivos agregados por el programador (por ejemplo, archivos binarios de aplicación)

-   Configuración (por ejemplo, configuración de entorno y las dependencias)

-   Instrucciones para la que procesa al ejecutar Docker

Puede configurar el flujo de trabajo de desarrollo de bucle interno que utiliza Docker como el proceso (descrito en la sección siguiente). Tenga en cuenta que los pasos iniciales para configurar el entorno no se incluye, porque debe hacer una sola vez.

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a>Creación de una aplicación única dentro de un contenedor de Docker con código de Visual Studio y la CLI de Docker

Las aplicaciones se componen de sus propios servicios, además de bibliotecas adicionales (dependencias).

Figura 4-15 muestra los pasos básicos que suele ser preciso para llevar a cabo al compilar una aplicación de Docker, seguida de una descripción detallada de cada paso.

![](./media/image19.png)

Figura 4-15: flujo de trabajo de alto nivel para el ciclo de vida de Docker en contenedores aplicaciones mediante la CLI de Docker

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a>Paso 1: Comenzar a codificar en código de Visual Studio y cree la línea de base inicial de aplicación/servicio

La manera de desarrollar la aplicación es bastante similar a la manera de que hacerlo sin necesidad de Docker. La diferencia es que al desarrollar, implementar y pruebe la aplicación o los servicios que se ejecutan dentro de los contenedores de Docker que se coloca en su entorno local (por ejemplo, una VM Linux o Windows).

**Configuración del entorno local**

Con las versiones más recientes de Docker para Mac y Windows, es más fácil que nunca para desarrollar aplicaciones de Docker y el programa de instalación es sencilla.

**Obtener más información** para obtener instrucciones sobre cómo configurar Docker para Windows, vaya a [ https://docs.docker.com/docker-for-windows/ ](https://docs.docker.com/docker-for-windows/).

Para obtener instrucciones sobre cómo configurar Docker para Mac, vaya a <https://docs.docker.com/docker-for-mac/>.

Además, deberá un editor de código para que realmente puede desarrollar su aplicación mientras usa la CLI de Docker.

Microsoft proporciona el código de Visual Studio, que es un editor de código ligero que es compatible con Mac, Windows y Linux y proporciona IntelliSense con [admite muchos idiomas](https://code.visualstudio.com/docs/languages/overview) (JavaScript,. NET, vaya, Java, Ruby, Python y más lenguajes modernos), [depuración](https://code.visualstudio.com/Docs/editor/debugging), [integración con Git](https://code.visualstudio.com/Docs/editor/versioncontrol) y [compatibilidad con las extensiones](https://code.visualstudio.com/docs/extensions/overview). Este editor es una excelente elección para los desarrolladores Mac y Linux. En Windows, también puede usar la aplicación completa de Visual Studio.

**Obtener más información** para obtener instrucciones acerca de cómo instalar Visual Studio para Windows, Mac o Linux, vaya a [ http://code.visualstudio.com/docs/setup/setup-overview/https://docs.docker.com/docker-for-mac/ ](http://code.visualstudio.com/docs/setup/setup-overview/https:/docs.docker.com/docker-for-mac/).

También puede trabajar con CLI de Docker y escribir el código con cualquier editor de código, pero si usa código de Visual Studio, permite que los fáciles de autor Dockerfile y docker compose.yml archivos en el área de trabajo. Además, puede ejecutar tareas de código de Visual Studio desde el IDE, que le solicitará las secuencias de comandos que se pueden ejecutar operaciones elaboradas con CLI de Docker debajo.

Código de Visual Studio proporciona una extensión, que debe instalar. Para ello, presione Ctrl + Mayús + P, escriba **instalar ext**, y, a continuación, ejecutar las extensiones: comando de la extensión de instalación para que aparezca la lista de extensiones de Marketplace. A continuación, escriba **docker** para filtrar los resultados y, a continuación, seleccione el archivo Dockerfile y redactar Dockerfile (yml) extensión de soporte técnico, como se muestra en la figura 4-16.

![](./media/image20.png)

Figura 4-16: instalar la extensión Docker en el código de Visual Studio

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a>Paso 2: Crear un archivo DockerFile relacionada con una imagen existente (sistema operativo sin formato o entornos de desarrollo como el principal. NET, Node.js y Ruby)

Necesitará un DockerFile por una imagen personalizada que se crea y por contenedor para implementarse, por lo tanto, si la aplicación está formada por un único servicio personalizado, necesitará un DockerFile único. Sin embargo, si la aplicación está compuesta de varios servicios (como en una arquitectura microservicios), necesitará un Dockerfile por cada servicio.

El DockerFile se coloca normalmente en la carpeta raíz de su aplicación o servicio y contiene los comandos necesarios para que ese Docker sepa cómo configurar y ejecutar esa aplicación o servicio. Puede crear el archivo DockerFile y agregarlo al proyecto junto con el código (node.js, .NET Core, etc.), o bien si está familiarizado con el entorno, eche un vistazo a la siguiente sugerencia.

> [!TIP]
> Puede usar una herramienta de línea de comandos denominada [yo docker](https://github.com/Microsoft/generator-docker), que scaffolds archivos desde el proyecto en el idioma que elija y agrega los archivos de configuración de Docker necesarios. Básicamente, para ayudar a los desarrolladores de introducción, crea el DockerFile adecuado, docker compose.yml y otras secuencias de comandos asociadas para compilar y ejecutar los contenedores de Docker. Este generador yeoman le pedirá que con unas cuantas preguntas que pedir el host del contenedor de lenguaje y el destino de desarrollo seleccionada.

![Yo docker](./media/image21.png)

Por ejemplo, en la figura 4-17 muestra dos capturas de pantalla de los terminales en Windows y en un equipo Mac, en ambos casos, ejecute yo docker, lo que generará los proyectos de código muestra (actualmente .NET Core, Golang y Node.js como idiomas admitidos) ya está configurados para que funcionen en parte superior de Docker.

![](./media/image22.PNG)  ![](./media/image23.png)

Figura 4-17: yo docker herramienta de comandos en Windows (izquierda) y en un equipo Mac

Figura 4-18 presenta un ejemplo de cómo utilizar yo docker después de tener un proyecto existente de .NET Core en su lugar para ser scaffolding.

![](./media/image24.PNG)

Figura 4-18: yo docker con un núcleo de .NET existentes del proyecto en su lugar

Desde el DockerFile, especificar qué imagen de Docker base que vamos a usar (por ejemplo, mediante "de microsoft/dotnet:1.0.0-core"). Normalmente, se compilará la imagen personalizada encima de una imagen base que puede obtener desde cualquier repositorio oficial en el [registro de Docker Hub](https://hub.docker.com/) (como un [imagen para .NET Core](https://hub.docker.com/r/microsoft/dotnet/) o un [para Node.js](https://hub.docker.com/_/node/)).

***Opción A: usar una imagen de Docker oficial existente***

El uso de un repositorio de una pila de idioma oficial con un número de versión, se garantiza que las mismas características de lenguaje están disponibles en todos los equipos (incluido el desarrollo, pruebas y producción).

Aquí te mostramos un ejemplo de DockerFile para un contenedor de .NET Core:

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

En este caso, que está usando la versión 1.0.1 de la imagen de Docker de núcleo de ASP.NET oficial para Linux denominada microsoft/aspnetcore:1.0.1. Para obtener más información, consulte el [página de la imagen de Docker de ASP.NET Core](https://hub.docker.com/r/microsoft/aspnetcore/) y [página de la imagen de Docker de .NET Core](https://hub.docker.com/r/microsoft/dotnet/). También podría estar utilizando otra imagen comparable como nodo: 4-onbuild para Node.js o muchas otras imágenes preconfiguradas de lenguajes de programación, que están disponibles en [Docker Hub](https://hub.docker.com/explore/).

En el DockerFile, también debe indicar a Docker que debe escuchar al puerto TCP que va a utilizar en tiempo de ejecución (por ejemplo, el puerto 80).

Hay otras líneas de configuración que se puede agregar en el DockerFile según el idioma/framework que está utilizando, por lo que Docker sabe cómo ejecutar la aplicación. Por ejemplo, necesita la línea de punto de entrada con \["dotnet", "MyCustomMicroservice.dll"\] para ejecutar una aplicación .NET Core, aunque puede tener varias variantes según el enfoque para compilar y ejecutar el servicio. Si usa el SDK y dotnet CLI para generar y ejecutar la aplicación. NET, sería ligeramente diferente. La conclusión es que la línea de punto de entrada más líneas adicionales pueden variar en función del lenguaje o plataforma que elija para su aplicación.

**Obtener más información** para obtener información sobre la creación de imágenes de Docker para las aplicaciones de .NET Core, vaya a <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.

Para más información acerca de cómo crear sus propias imágenes, vaya a [ https://docs.docker.com/engine/\tutoriales/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).

**Repositorios de imágenes multiplataforma**

Contenedores de Windows se vuelven más frecuentes, un solo repositorio puede contener las variantes de la plataforma, como una imagen de Windows y Linux. Esta es una característica nueva que entran en Docker que permite a los proveedores usar un solo repositorio para abarcar varias plataformas, como [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repositorio, que está disponible en el registro de DockerHub. Tal como la característica se activa, extraer esta imagen de un host de Windows extraerá la variante de Windows, mientras que extraer el mismo nombre de imagen de un host Linux extraerá la variante de Linux.

***Opción B: crear la imagen base desde el principio***

Puede crear su propia imagen de base de Docker desde el principio como se explica en este [artículo](https://docs.docker.com/engine/userguide/eng-image/baseimages/) de Docker. Se trata de un escenario que probablemente no es mejor para usted si están iniciándose con Docker, pero si desea establecer los bits específicos de su propia imagen base, puede hacerlo.

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a>Paso 3: Crear imágenes personalizadas Docker incrustar su servicio en él

Para cada servicio personalizado que consta de la aplicación, debe crear una imagen relacionada. Si la aplicación está formada por un único servicio o una aplicación web, necesitará solo una única imagen.

> [!NOTE]
> Teniendo en cuenta el "bucle exterior DevOps flujo de trabajo", las imágenes se creará un proceso automatizado de compilación siempre que insertar el código fuente en un repositorio de Git (integración continua) por lo que las imágenes se creará en el entorno global de su código fuente.

Sin embargo, antes de que se tenga en cuenta si va a esa ruta de bucle externo, es necesario para asegurarse de que la aplicación de Docker realmente funciona correctamente para que no insertar código que podría no funcionar correctamente el sistema de control de código fuente (Git, etcetera).

Por lo tanto, cada desarrollador en primer lugar debe realizar todo el proceso de bucle interno para una prueba local y continuar desarrollando hasta que desean insertar una característica completa o cambiar el sistema de control de código fuente.

Para crear una imagen en su entorno local y usar el DockerFile, puede usar el comando de compilación de docker, como se muestra en la figura 4-19 (también puede ejecutar redactar docker: compilar aplicaciones compuestas por varios contenedores o servicios).

![](./media/image25.png)

Figura 4-19: ejecuten la compilación de docker

Si lo desea, en lugar de ejecutar directamente docker construido a partir de la carpeta del proyecto, primero puede generar una carpeta que se pueden implementar con las bibliotecas de .NET necesarias mediante el uso de la ejecución dotnet comando Publicar y, a continuación, ejecute la compilación de docker.

En este ejemplo, esto crea una imagen de Docker con el nombre cesardl/netcore-webapi-microservicio-docker: primero (: en primer lugar es una etiqueta, como una versión específica). Puede realizar este paso para cada imagen personalizada que se debe crear para su aplicación de Docker compuesta con varios contenedores.

Se pueden encontrar las imágenes existentes en el repositorio local (el equipo de desarrollo) mediante el docker comandos de imágenes, como se muestra en la figura 4-20.

![](./media/image26.png)

Figura 4-20: ver imágenes existentes con imágenes de docker

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a>Paso 4: (Opcional) definir los servicios en docker compose.yml al compilar una aplicación de Docker compuesta con varios servicios

Con el archivo compose.yml de docker puede definir un conjunto de servicios relacionados que desee implementar como una aplicación compuesta con los comandos de implementación que se explica en la sección paso siguiente.

Debe crear ese archivo en la ventana principal o la carpeta raíz de la solución; debe tener un contenido similar al archivo docker compose.yml siguientes:

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

En este caso concreto, este archivo define dos servicios: el servicio web (el servicio personalizado) y el servicio de redis (un servicio de caché populares). Cada servicio se implementará como un contenedor, por lo que debemos usar una imagen de Docker concreta para cada uno. Para este servicio web determinado, la imagen debe hacer lo siguiente:

-   Compilar desde el archivo DockerFile en el directorio actual

-   Reenviar el puerto 80 en el contenedor para el puerto 81 en el equipo host expuesto

-   Montar el directorio del proyecto en el host a /code dentro del contenedor, lo que permite modificar el código sin tener que volver a generar la imagen

-   Vincular el servicio web para el servicio de redis

El servicio de redis utiliza el [imagen redis pública más reciente](https://hub.docker.com/_/redis/) extraídos del registro de Docker Hub. [Redis](https://redis.io/) es un sistema muy popular de caché para aplicaciones de servidor.

### <a name="step-5-build-and-run-your-docker-app"></a>Paso 5: Compilar y ejecutar la aplicación de Docker

Si la aplicación tiene solo un único contenedor, solo necesita ejecutar mediante la implementación en el Host Docker (virtual o servidor físico). Sin embargo, si la aplicación está formada por varios servicios, debe *componerla*, demasiado. Veamos las distintas opciones.

***Opción A: ejecutar un único contenedor o servicio***

Puede ejecutar la imagen de Docker mediante el comando docker run, tal y como se muestra aquí:

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

Tenga en cuenta que para esta implementación concreta, se le puede redirigir las solicitudes enviadas al puerto 80 para el puerto interno 5000. Ahora, la aplicación está escuchando en el puerto 80 en el nivel de host externo.

***Opción B: crear y ejecutar una aplicación de varios contenedores***

En la mayoría de los escenarios de empresa, una aplicación de Docker podría estar compuesta por varios servicios. Para estos casos, puede ejecutar el comando Crear docker seguridad (ilustración 4-21), que usará el archivo de docker compose.yml que podría haber creado previamente. Ejecutar este comando, implementa una aplicación compuesta con todos sus contenedores relacionados.

![](./media/image27.png)

Figura 4-21: resultados de ejecutar el comando "docker-crear una"

Después de ejecutar docker-crear una, implementar la aplicación y sus contenedores relacionados en el Host Docker, como se muestra en la figura 4-22, en la representación de la máquina virtual.

![](./media/image28.png)

Figura 4-22: VM con contenedores de Docker implementado

Tenga en cuenta docker crear una y docker ejecutar quizás sea suficiente para probar los contenedores en el entorno de desarrollo, pero podría no utilizarlos en absoluto si está esperando trabajar con clústeres de Docker y orchestrators como Docker Swarm, Mesosphere DC/OS o Kubernetes Para poder escalar verticalmente. Si está usando un clúster como [Docker Swarm modo](https://docs.docker.com/engine/swarm/) (disponible en Docker para Windows y Mac desde la versión 1.12), debe implementar y probar con los comandos adicionales, como crear servicio docker para servicios de inicio único, o cuando estés implementar una aplicación formada por varios contenedores, con docker crear agrupación y docker implementar myBundleFile, mediante la implementación de la aplicación compuesta como una pila, como se explica en el artículo [paquetes de aplicaciones distribuidas](https://blog.docker.com/2016/06/docker-app-bundle/) de Docker.

Para [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) y [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) usaría comandos de implementación diferentes y secuencias de comandos, también.

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a>Paso 6: Probar la aplicación de Docker (localmente, en la máquina virtual CD local)

Este paso variarán dependiendo de lo que está haciendo la aplicación.

En un muy .NET Core API Web simple "Hola mundo" implementado como un único contenedor o el servicio, solo sería necesario tener acceso al servicio proporcionando el puerto TCP especificado en el DockerFile.

Si localhost no está activado, para navegar a su servicio, busque la dirección IP de la máquina mediante este comando:

dirección ip del equipo de docker *el nombre del contenedor*

En el host Docker, abra un explorador y navegue a ese sitio; debería ver su aplicación o servicio en ejecución, como se muestra en la figura 4-23.

![](./media/image29.png)

Figura 4-23: probar la aplicación de Docker localmente mediante localhost

Tenga en cuenta que está utilizando el puerto 80, pero internamente se se redirige al puerto 5000, ya que ese es cómo se implementó con docker ejecutar, como se explicó anteriormente.

Puede probarlo mediante CURL desde el terminal. En una instalación de Docker en Windows, la dirección IP predeterminada es 10.0.75.1, como se muestra en la figura 4-24.

![](./media/image30.png)

Figura 4-24: probar una aplicación de Docker localmente mediante CURL

**Depuración de un contenedor con Docker**

Código de Visual Studio admite la depuración Docker si usas Node.js y otras plataformas como contenedores de .NET Core.

También puede depurar contenedores .NET Core en Docker cuando se utiliza Visual Studio, como se describe en la sección siguiente.

**Obtener más información:** para más información sobre la depuración de contenedores de Node.js Docker, vaya a <https://blog.docker.com/2016/07/live-debugging-docker/> y [ https://blogs.msdn.microsoft.com/\ usuario\_ed/2016/02/27 / Visual-Studio-Code-New-Features-13-big-Debugging-Updates-Rich-Object-Hover-Conditional-Breakpoints-Node-js-mono-More/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).


>[!div class="step-by-step"]
[Anterior] (docker-aplicaciones-desarrollo-environment.md) [siguiente] (visual-studio-herramientas-de-docker.md)
