---
title: Flujo de trabajo de desarrollo de bucle interior para aplicaciones de Docker
description: Obtenga información sobre el flujo de trabajo de "bucle interno" para el desarrollo de aplicaciones de Docker.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 1134ff439235609db840c85a1e67bc9fe4ccec84
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835686"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a>Flujo de trabajo de desarrollo de bucle interior para aplicaciones de Docker

Antes de desencadenar el flujo de trabajo del bucle exterior que abarca el DevOps completa del ciclo, todo comienza en el equipo de cada desarrollador, codificación de la propia aplicación, con sus lenguajes preferidos o plataformas y probarlo localmente (figura 4-21). Pero en todos los casos, tendrá un aspecto importante en común, con independencia de qué lenguaje, marco o plataformas elija. En este flujo de trabajo específico, siempre desarrolla y prueba contenedores de Docker, pero localmente.

![Paso 1: código, ejecución y depuración](./media/image18.png)

**Figura 4-21**. Contexto de desarrollo de bucle interno

El contenedor o la instancia de una imagen de Docker contiene estos componentes:

-   Una selección de sistema operativo (por ejemplo, una distribución de Linux o Windows)

- Archivos agregados por el desarrollador (por ejemplo, archivos binarios de aplicación)

-   Configuración (por ejemplo, configuración del entorno y dependencias)

- Instrucciones para los procesos que ejecutar docker

Puede configurar el flujo de trabajo de desarrollo de bucle interno que usa Docker como el proceso (descrito en la sección siguiente). Tenga en cuenta que los pasos iniciales para configurar el entorno no se incluyen, ya que basta con hacerlo una vez.

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a>Creación de una sola aplicación en un contenedor de Docker con Visual Studio Code y CLI de Docker

Las aplicaciones se componen de sus propios servicios, además de bibliotecas adicionales (dependencias).

Figura 4-22 muestra los pasos básicos que normalmente se necesitan para llevar a cabo al compilar una aplicación de Docker, seguida de una descripción detallada de cada paso.

![Información general del flujo de trabajo: Paso 1: código, paso 2: escribir Dockerfiles, paso 3: creación de imágenes definidas con Dockerfiles, paso 4: definir los servicios con el archivo docker-Compose, paso 5: ejecutar contenedores o aplicaciones compuestas, paso 6: prueba de aplicaciones, paso 7: de inserción para que comience el bucle exterior (canalizaciones de CI/CD) o continuar de veloping.](./media/image19.png)

**Figura 4-22**. Flujo de trabajo de alto nivel para el ciclo de vida de aplicaciones de Docker en contenedor mediante la CLI de Docker

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a>Paso 1: Empezar a programar en Visual Studio Code y crear la instantánea inicial de aplicación/servicio

La manera de desarrollar la aplicación es similar a la manera de que hacerlo sin Docker. La diferencia es que al desarrollar, implementar y probar su aplicación o servicios que se ejecutan dentro de contenedores de Docker que se colocan en su entorno local (por ejemplo, una VM Linux o Windows).

**Configurar el entorno local**

Con las últimas versiones de Docker para Mac y Windows, es más fácil que nunca para desarrollar aplicaciones de Docker y el programa de instalación es sencilla.

> [! INFORMACIÓN]
>
> Para obtener instrucciones sobre cómo configurar Docker para Windows, vaya a <https://docs.docker.com/docker-for-windows/>.
>
>Para obtener instrucciones sobre cómo configurar Docker para Mac, vaya a <https://docs.docker.com/docker-for-mac/>.

Además, necesitará un editor de código para que realmente puede desarrollar su aplicación a la vez mediante la CLI de Docker.

Microsoft proporciona código de Visual Studio, que es un editor de código ligero que es compatible con Mac, Windows y Linux y proporciona IntelliSense con [soporte para numerosos lenguajes](https://code.visualstudio.com/docs/languages/overview) (JavaScript,. NET, Go, Java, Ruby, Python y más lenguajes modernos) [depuración](https://code.visualstudio.com/Docs/editor/debugging), [integración con Git](https://code.visualstudio.com/Docs/editor/versioncontrol) y [compatibilidad con extensiones](https://code.visualstudio.com/docs/extensions/overview). Este editor es una opción ideal para desarrolladores de Mac y Linux. En Windows, también se puede usar la aplicación completa de Visual Studio.

> [! INFORMACIÓN]
>
> Para obtener instrucciones sobre cómo instalar Visual Studio código para Windows, Mac o Linux, vaya a <https://code.visualstudio.com/docs/setup/setup-overview/>.
>
> Para obtener instrucciones sobre cómo configurar Docker para Mac, vaya a <https://docs.docker.com/docker-for-mac/>.

También puede trabajar con la CLI de Docker y escribir el código con cualquier editor de código, pero con Visual Studio Code con la extensión Docker facilita la tarea al autor `Dockerfile` y `docker-compose.yml` archivos en el área de trabajo. También puede ejecutar las tareas y las secuencias de comandos del IDE de Visual Studio código para ejecutar comandos de Docker mediante la CLI de Docker debajo.

La extensión Docker para VS Code proporciona las siguientes características:

- Automática `Dockerfile` y `docker-compose.yml` generación de archivos

- Sugerencias de sintaxis resaltado y mantenga el puntero para `docker-compose.yml` y `Dockerfile` archivos

- IntelliSense (finalización) para `Dockerfile` y `docker-compose.yml` archivos

- Detección de errores (errores y advertencias) para `Dockerfile` archivos

- Integración de paleta (F1) para los comandos más comunes de Docker de comando

- Integración del explorador para administrar imágenes y contenedores

- Implementar imágenes de docker hub y Azure Container Registry en Azure App Service

Para instalar la extensión de Docker, presione Ctrl + Mayús + P, escriba `ext install`, y, a continuación, ejecute el comando de la extensión de instalación para que aparezca la lista de extensiones de Marketplace. A continuación, escriba **docker** para filtrar los resultados y, a continuación, seleccione la extensión de la compatibilidad con Docker, como se muestra en la figura 4-23.

![Vista de la extensión Docker para VS Code.](./media/image20.png)

**Figura 4-23**. Instalar la extensión de Docker en Visual Studio Code

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a>Paso 2: Crear un DockerFile relacionado con una imagen existente (sin formato del sistema operativo o entornos de desarrollo como Ruby, Node.js y .NET Core)

Necesitará un `DockerFile` por una imagen personalizada que se crea y por contenedor para implementarse. Si la aplicación se compone de un único servicio personalizado, necesita un único `DockerFile`. Pero si la aplicación se compone de varios servicios (como en una arquitectura de microservicios), necesitará una `Dockerfile` por servicio.

El `DockerFile` normalmente se coloca en la carpeta raíz de su aplicación o servicio y contiene los comandos necesarios para que Docker sepa cómo configurar y ejecutar esa aplicación o servicio. Puede crear su `DockerFile` y agréguelo al proyecto junto con el código (node.js, .NET Core, etc.), o bien si está familiarizado con el entorno, eche un vistazo a la siguiente sugerencia.

> [!TIP]
>
> Puede usar la extensión Docker para guiar al usar el `Dockerfile` y `docker-compose.yml` los archivos relacionados con los contenedores de Docker. Finalmente, probablemente se va a escribir estos tipos de archivos sin esta herramienta, pero con la extensión de Docker es un buen punto de partida que acelerará la curva de aprendizaje.

En la figura 4-24, puede ver cómo docker-compose se agrega el archivo mediante la extensión Docker para VS Code.

![Vista de la consola de la extensión Docker para VS Code.](./media/image24.png)

**Figura 4-24**. Archivos de docker que se agregan utilizando la **archivos de Docker de agregar al comando del área de trabajo**

Cuando se agrega un DockerFile, especificar qué imagen de Docker básica que va a usar (como el uso de `FROM microsoft/aspnetcore`). Normalmente se compilará la imagen personalizada sobre una imagen base que se obtiene desde cualquier repositorio oficial en el [registro de Docker Hub](https://hub.docker.com/) (como un [imágenes para .NET Core](https://hub.docker.com/r/microsoft/dotnet/) o lo [para Node.js](https://hub.docker.com/_/node/)).

***Use una imagen de Docker oficial existente***

Uso de un repositorio oficial de una pila de lenguaje con un número de versión garantiza que las mismas características de lenguaje están disponibles en todos los equipos (incluido el desarrollo, pruebas y producción).

Este es un DockerFile de ejemplo para un contenedor de .NET Core:

```Dockerfile
# Base Docker image to use  
FROM microsoft/dotnet:2.1-aspnetcore-runtime
  
# Set the Working Directory and files to be copied to the image  
ARG source  
WORKDIR /app  
COPY ${source:-bin/Release/PublishOutput} .  
  
# Configure the listening port to 80 (Internal/Secured port within Docker host)  
EXPOSE 80  
  
# Application entry point  
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

En este caso, la imagen se basa en la versión 2.1 de la imagen de Docker de ASP.NET Core oficial (multiarquitectura para Linux y Windows), según la línea `FROM microsoft/dotnet:2.1-aspnetcore-runtime`. (Para obtener más información acerca de este tema, consulte el [imagen de Docker de ASP.NET Core](https://hub.docker.com/r/microsoft/aspnetcore/) página y el [imagen de Docker de .NET Core](https://hub.docker.com/r/microsoft/dotnet/) página).

En el DockerFile, también puede indicar a Docker para escuchar el puerto TCP que va a utilizar en tiempo de ejecución (por ejemplo, el puerto 80).

Puede especificar otros valores de configuración en el Dockerfile, según el lenguaje y el marco que use. Por ejemplo, el `ENTRYPOINT` línea con `["dotnet", "MySingleContainerWebApp.dll"]` indica a Docker para ejecutar una aplicación .NET Core. Si está usando el SDK y la CLI de .NET Core (`dotnet CLI`) para compilar y ejecutar la aplicación. NET, este valor sería diferente. El punto clave aquí es que la línea ENTRYPOINT y otros valores de configuración dependen del lenguaje y plataforma que elija para su aplicación.

> [! INFORMACIÓN]
>
> Para obtener más información sobre la creación de imágenes de Docker para aplicaciones .NET Core, vaya a <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.
>
> Para más información acerca de cómo crear sus propias imágenes, vaya a <https://docs.docker.com/engine/tutorials/dockerimages/>.

**Usar repositorios de imágenes multiarquitectura**

Un nombre de imagen única en un repositorio puede contener variantes de plataforma, como una imagen de Linux y una imagen de Windows. Esta característica permite a los proveedores como Microsoft (creadores de imágenes base) crear un único repositorio que cubra varias plataformas (es decir, Linux y Windows). Por ejemplo, el [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repositorio disponible en el registro de Docker Hub proporciona compatibilidad para Linux y Windows Nano Server mediante el mismo nombre de imagen.

Extrayendo el [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) imagen desde un host de Windows extrae la variante de Windows, mientras que extraer el mismo nombre de imagen de un host Linux extrae la variante de Linux.

***Crear su imagen base desde cero***

Puede crear su propia imagen de base de Docker desde cero como se explica en este [artículo](https://docs.docker.com/engine/userguide/eng-image/baseimages/) de Docker. Este escenario es probablemente no lo mejor para usted si está empezando con Docker, pero si desea establecer los bits específicos de su propia imagen base, puede hacerlo.

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a>Paso 3: Crear las imágenes de Docker personalizadas insertar su servicio en él

Para cada servicio personalizado que consta de la aplicación, deberá crear una imagen relacionada. Si la aplicación se compone de un único servicio o aplicación web, necesitará una imagen de única.

> [!NOTE]
>
> Teniendo en cuenta el "bucle exterior DevOps flujo de trabajo", las imágenes se creará un proceso de compilación automatizada siempre que inserte el código fuente en un repositorio de Git (integración continua), por lo que las imágenes se crearán en el entorno global de su código fuente.
>
> Pero antes de que se considere la posibilidad de ir a esa ruta de bucle externo, es necesario asegurarse de que la aplicación de Docker realmente funciona correctamente para que no inserción código que podría no funcionar correctamente en el sistema de control de código fuente (Git, etcetera.).
>
> Por lo tanto, cada desarrollador en primer lugar debe hacer todo el proceso de bucle interno para probar localmente y continuar desarrollando hasta que desean insertar una característica completa o cambio en el sistema de control de origen.

Para crear una imagen en su entorno local y mediante el DockerFile, puede usar el comando docker build, como se muestra en la figura 4-25 (también puede ejecutar `docker-compose up --build` para aplicaciones compuestas por varios contenedores y servicios).

![Salida de la consola de la compilación de docker-Compose, que muestra el progreso de descarga de imágenes.](./media/image25.png)

**Figura 4-25**. Ejecuta la compilación de docker

Opcionalmente, en lugar de ejecutar directamente `docker build` desde la carpeta del proyecto, primero puede generar una carpeta que se pueden implementar con las bibliotecas de .NET que sea necesarias, mediante la ejecución `dotnet publish` comando y, a continuación, ejecute `docker build`.

Este ejemplo crea una imagen de Docker con el nombre `cesardl/netcore-webapi-microservice-docker:first` (`:first` es una etiqueta, como una versión específica). Puede realizar este paso para cada imagen personalizada, deberá crear la aplicación de Docker compuesta con varios contenedores.

Puede encontrar las imágenes existentes en el repositorio local (el equipo de desarrollo) utilizando el docker de comando de imágenes, como se muestra en la figura 4-26.

![Salida de imágenes de docker de comando, que muestra las imágenes existentes en la consola.](./media/image26.png)

**Figura 4-26**. Visualización de imágenes existente con imágenes de docker

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a>Paso 4: Definir los servicios en docker-compose.yml al compilar una aplicación compuesta de Docker con varios servicios

Con el `docker-compose.yml` archivo, puede definir un conjunto de servicios relacionados para implementarse como una aplicación compuesta con los comandos de implementación se explica en la sección paso siguiente.

Creación de ese archivo en la ventana principal o la carpeta raíz de la solución; debe tener contenido similar al que se muestra en este `docker-compose.yml` archivo:

```yml
version: '3.4'
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

- Compilar desde el archivo DockerFile en el directorio actual

- Reenviar el puerto 80 expuesto en el contenedor al puerto 81 en el equipo host

- Montar el directorio del proyecto en el host a/Code dentro del contenedor, lo que permite modificar el código sin tener que volver a generar la imagen

- Vincular el servicio web para el servicio redis

El servicio redis usa el [imagen más reciente de redis pública](https://hub.docker.com/_/redis/) extrae del registro de Docker Hub. [Redis](https://redis.io/) es un sistema de caché populares para aplicaciones de servidor.

### <a name="step-5-build-and-run-your-docker-app"></a>Paso 5: Compilar y ejecutar la aplicación de Docker

Si la aplicación tiene solo un único contenedor, solo deberá ejecutarla mediante su implementación en el Host de Docker (máquina virtual o servidor físico). Sin embargo, si la aplicación se compone de varios servicios, deberá *componerla*, demasiado. Vamos a ver las distintas opciones.

***Opción A: Ejecutar un único contenedor o servicio***

Puede ejecutar la imagen de Docker mediante el comando docker run, como se muestra aquí:

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

Para esta implementación concreta, se deberá redirigir las solicitudes enviadas al puerto 80 al puerto interno 5000. Ahora la aplicación está escuchando en el puerto 80 en el nivel de host externo.

***Opción B: Redactar y ejecutar una aplicación de varios contenedores***

En la mayoría de los escenarios empresariales, una aplicación de Docker se compone de varios servicios. En estos casos, puede ejecutar el `docker-compose up` comando (figura 4-27), que utilizará el archivo docker-compose.yml que ha creado anteriormente. Ejecutar este comando implementa una aplicación compuesta con todos sus contenedores relacionados.

![Salida de la consola el-comando docker compose up.](./media/image27.png)

**Figura 4-27**. Resultados de ejecutar el comando "docker-compose up"

Después de ejecutar `docker-compose up`, implementar la aplicación y sus contenedores relacionados en el Host de Docker, como se muestra en la figura 4-28, en la representación de la máquina virtual.

![Máquina virtual que ejecuta aplicaciones de varios contenedores.](./media/image28.png)

**Figura 4-28**. Máquina virtual con contenedores de Docker implementados

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a>Paso 6: Probar la aplicación de Docker (localmente, en la máquina virtual local de CD)

Este paso variarán dependiendo de lo que hace la aplicación.

En un núcleo .NET simple "Hello World" implementar como un único contenedor o el servicio de Web API, solo sería necesario acceder al servicio proporcionando el puerto TCP especificado en el archivo DockerFile.

Si localhost no está activado, para navegar a su servicio, busque la dirección IP para la máquina mediante este comando:

```console
docker-machine {IP} {YOUR-CONTAINER-NAME}
```

En el host de Docker, abra un explorador y navegue a ese sitio; debería ver su aplicación o servicio que se está ejecutando, como se muestra en la figura 4-29.

![Vista del explorador de la respuesta de localhost/API/values.](./media/image29.png)

**Figura 4-29**. Probar la aplicación de Docker local mediante localhost

Tenga en cuenta que está utilizando el puerto 80, pero internamente se redirige al puerto 5000, ya que es cómo se implementó con `docker run`, tal y como se explicó anteriormente.

Puede probar esto con CURL desde el terminal. En una instalación de Docker en Windows, la dirección IP predeterminada es 10.0.75.1, como se muestra en la figura 4-30.

![Salida de la introducción de la consola la http://10.0.75.1/API/values con curl](./media/image30.png)

**Figura 4-30**. Probar una aplicación de Docker localmente mediante CURL

**Depuración de un contenedor que se ejecutan en Docker**

Visual Studio Code admite la depuración de Docker si usa Node.js y otras plataformas como contenedores de .NET Core.

También se pueden depurar contenedores .NET Core o .NET Framework en Docker cuando se usa Visual Studio para Windows o Mac, como se describe en la sección siguiente.

> [! INFORMACIÓN]
>
> Para más información sobre la depuración de contenedores de Node.js Docker, vaya a <https://blog.docker.com/2016/07/live-debugging-docker/> y <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>.

>[!div class="step-by-step"]
>[Anterior](docker-apps-development-environment.md)
>[Siguiente](visual-studio-tools-for-docker.md)
