---
title: Flujo de trabajo de desarrollo de bucle interior para aplicaciones de Docker
description: Obtenga información sobre el flujo de trabajo de desarrollo de bucle interior para aplicaciones de Docker.
ms.date: 01/06/2021
ms.openlocfilehash: 78c593890d56a6888d4c4ea6752497918222ebee
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970590"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a>Flujo de trabajo de desarrollo de bucle interior para aplicaciones de Docker

Antes de desencadenar el flujo de trabajo de bucle exterior que comprende el ciclo completo de DevOps, todo comienza en la máquina de cada desarrollador, al codificar la propia aplicación, utilizar sus lenguajes o plataformas preferidos y probarla localmente (figura 4-21). Pero en todos los casos, tendrá un aspecto importante en común, con independencia del lenguaje, el marco o las plataformas que elija. En este flujo de trabajo concreto, los contenedores de Docker siempre se desarrollan y se prueban en este entorno y no otro, pero en local.

![Diagrama que muestra el concepto de un entorno de desarrollo de bucle interno.](./media/docker-apps-inner-loop-workflow/inner-loop-development-context.png)

**Figura 4-21**. Contexto de desarrollo de bucle interno

El contenedor o la instancia de una imagen de Docker contiene estos componentes:

- Una selección de sistema operativo (por ejemplo, una distribución de Linux o Windows)

- Archivos agregados por el desarrollador (por ejemplo, binarios de aplicación)

- Información de configuración (por ejemplo, configuración de entorno y dependencias)

- Instrucciones sobre los procesos que debe ejecutar Docker

Puede configurar el flujo de trabajo de desarrollo de bucle interno que usa Docker como proceso (lo que se describe en la sección siguiente). Tenga en cuenta que no se incluyen los pasos iniciales para configurar el entorno, ya que basta con hacerlo una vez.

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a>Compilación de una sola aplicación en un contenedor de Docker con Visual Studio Code y la CLI de Docker

Las aplicaciones se componen de sus propios servicios, además de bibliotecas adicionales (dependencias).

La figura 4-22 muestra los pasos básicos que normalmente hay que llevar a cabo para compilar una aplicación de Docker, seguidos de una descripción detallada de cada paso.

![Diagrama que muestra los siete pasos necesarios para crear una aplicación en contenedores.](./media/docker-apps-inner-loop-workflow/life-cycle-containerized-apps-docker-cli.png)

**Figura 4-22**. Flujo de trabajo general del ciclo de vida de aplicaciones en contenedor con la CLI de Docker

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a>Paso 1: Inicio de la codificación en Visual Studio Code y creación de la instantánea inicial de la aplicación o el servicio

La forma de desarrollar una aplicación es similar a la forma en que se lleva a cabo sin Docker. La diferencia es que durante el desarrollo, la aplicación o los servicios que se están implementando y probando se ejecutan en contenedores de Docker situados en el entorno local (como una VM Linux o Windows).

**Configuración del entorno local**

Con las últimas versiones de Docker Desktop para Mac y Windows, desarrollar aplicaciones de Docker es más fácil que nunca y la configuración es sencilla.

> [!TIP]
> Para obtener instrucciones sobre cómo configurar Docker Desktop para Windows, vaya a <https://docs.docker.com/docker-for-windows/>.
>
> Para obtener instrucciones sobre cómo configurar Docker Desktop para Mac, vaya a <https://docs.docker.com/docker-for-mac/>.

Además, necesitará un editor de código para que realmente pueda desarrollar su aplicación al tiempo que usa la CLI de Docker.

Microsoft ofrece Visual Studio Code, que es un editor de código ligero compatible con Windows, Linux y macOS y que proporciona IntelliSense con [compatibilidad con numerosos lenguajes](https://code.visualstudio.com/docs/languages/overview) (JavaScript,. NET, Go, Java, Ruby, Python y la mayoría de lenguajes modernos), [depuración](https://code.visualstudio.com/Docs/editor/debugging), [integración con Git](https://code.visualstudio.com/Docs/editor/versioncontrol) y [compatibilidad con extensiones](https://code.visualstudio.com/docs/extensions/overview). Este editor es muy adecuado para desarrolladores de macOS y Linux. En Windows, también puede usar Visual Studio.

> [!TIP]
> Para instrucciones sobre cómo instalar Visual Studio Code para Windows, Linux o macOS, vaya a <https://code.visualstudio.com/docs/setup/setup-overview/>.
>
> Para obtener instrucciones sobre cómo configurar Docker para Mac, vaya a <https://docs.docker.com/docker-for-mac/>.

Puede trabajar con la CLI de Docker y escribir el código con cualquier editor de código, pero el uso de Visual Studio Code con la extensión de Docker facilita la creación de archivos `Dockerfile` y `docker-compose.yml` en el área de trabajo. También puede ejecutar tareas y scripts en el IDE de Visual Studio Code que ejecuten comandos de Docker con la CLI de Docker que se encuentra debajo.

La extensión de Docker para VS Code ofrece las siguientes características:

- Generación automática de archivos `Dockerfile` y `docker-compose.yml`

- Sugerencias de mantenimiento del puntero y resaltado de sintaxis en archivos `docker-compose.yml` y `Dockerfile`

- IntelliSense (finalizaciones) para archivos `Dockerfile` y `docker-compose.yml`

- Linting (errores y advertencias) en archivos `Dockerfile`

- Integración con la paleta de comandos (F1) para los comandos de Docker más comunes

- Integración con el explorador para administrar imágenes y contenedores

- Implementación de imágenes de DockerHub y de instancias de Azure Container Registry en Azure App Service

Para instalar la extensión de Docker, presione Ctrl+Mayús+P, escriba `ext install` y ejecute el comando Instalar extensión para que aparezca la lista de extensiones de Marketplace. A continuación, escriba **docker** para filtrar los resultados y luego seleccione la extensión de compatibilidad con Docker, tal y como se muestra en la figura 4-23.

![Vista de la extensión de Docker para VS Code.](media/docker-apps-inner-loop-workflow/install-docker-extension-vs-code.png)

**Figura 4-23**. Instalación de la extensión de Docker para Visual Studio Code

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-nodejs-and-ruby"></a>Paso 2: Creación de un DockerFile relacionado con una imagen existente (entornos de desarrollo o sistemas operativos estándar como .NET, Node.js y Ruby)

Necesitará un `DockerFile` por imagen personalizada que quiera crear y por contenedor que quiera implementar. Si la aplicación se compone de un único servicio personalizado, necesita un solo `DockerFile`. Pero si la aplicación se compone de varios servicios (como en una arquitectura de microservicios), necesitará un `Dockerfile` por servicio.

El archivo `DockerFile` normalmente se coloca en la carpeta raíz de la aplicación o el servicio y contiene los comandos necesarios para que Docker sepa cómo configurar y ejecutar esa aplicación o ese servicio. Puede crear el elemento `DockerFile` y agregarlo al proyecto junto con el código (node.js, .NET, etc.) o, si no está familiarizado con el entorno, eche un vistazo a la siguiente sugerencia.

> [!TIP]
> Puede usar la extensión de Docker como guía al usar los archivos `Dockerfile` y `docker-compose.yml` relacionados con los contenedores de Docker. Con el tiempo, es probable que escriba este tipo de archivos sin esta herramienta, pero el uso de la extensión de Docker es un buen punto de partida que acelerará su curva de aprendizaje.

En la figura 4-24 puede ver los pasos necesarios para agregar archivos de Docker a un proyecto con la extensión de Docker para VS Code:

1. Abra la paleta de comandos, escriba "**docker**" y seleccione "**Add Docker Files to Workspace**" (Agregar archivos de Docker al área de trabajo).
2. Selección de la plataforma de aplicación (ASP.NET Core)
3. Selección del sistema operativo (Linux)
4. Inclusión de archivos de Docker Compose opcionales
5. Especificación de los puertos para publicar (80, 443)
6. Seleccionar el proyecto

![Pasos para agregar archivos de Docker con la extensión de Docker](media/docker-apps-inner-loop-workflow/add-docker-files-to-workspace-command.png)

**Figura 4-24**. Archivos de Docker agregados con el comando **Add Docker files to Workspace** (Agregar archivos de Docker al área de trabajo)

Cuando agregue un documento DockerFile, especifique la imagen base de Docker que va a usar (como el uso de `FROM mcr.microsoft.com/dotnet/aspnet`). Normalmente, creará la imagen personalizada sobre una imagen base que obtendrá de cualquier repositorio oficial en el [registro de Docker Hub](https://hub.docker.com/) (como una [imagen para .NET](https://hub.docker.com/_/microsoft-dotnet/) o la correspondiente [para Node.js](https://hub.docker.com/_/node/)).

> [!TIP]
> Tiene que repetir este procedimiento para cada proyecto de la aplicación, aunque la extensión le pide que sobrescriba el archivo de Docker Compose generado después de la primera vez. Debe responder que no quiere sobrescribirlo, para que la extensión cree archivos independientes de Docker Compose que después pueda combinar manualmente, antes de ejecutar Docker Compose.

**_Uso de una imagen oficial de Docker existente_**

El uso de un repositorio oficial de una pila de lenguaje con un número de versión garantiza que haya las mismas características de lenguaje disponibles en todas las máquinas (incluidas las de desarrollo, pruebas y producción).

Este es un DockerFile de ejemplo para un contenedor de .NET:

```dockerfile
FROM mcr.microsoft.com/dotnet/aspnet:5.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build
WORKDIR /src
COPY ["src/WebApi/WebApi.csproj", "src/WebApi/"]
RUN dotnet restore "src/WebApi/WebApi.csproj"
COPY . .
WORKDIR "/src/src/WebApi"
RUN dotnet build "WebApi.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "WebApi.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "WebApi.dll"]
```

En este caso, la imagen se basa en la versión 5.0 de la imagen oficial de Docker para ASP.NET Core (multiarquitectura de Linux y Windows), según la línea `FROM mcr.microsoft.com/dotnet/aspnet:5.0`. (Para obtener más información sobre este tema, vea las páginas sobre la [imagen de Docker de ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-aspnet/) y la [imagen de Docker de .NET](https://hub.docker.com/_/microsoft-dotnet/)).

En el Dockerfile, también puede indicar a Docker que escuche el puerto TCP que se va a usar en tiempo de ejecución (por ejemplo, el puerto 80 o 443).

Puede especificar otros valores de configuración en el Dockerfile, según el lenguaje y el marco que use. Por ejemplo, la línea `ENTRYPOINT` con `["dotnet", "WebMvcApplication.dll"]` indica a Docker que ejecute una aplicación de .NET. Si usa el SDK y la CLI de .NET (`dotnet CLI`) para compilar y ejecutar la aplicación de .NET, este valor sería diferente. El punto clave aquí es que la línea ENTRYPOINT y otros valores varían según el lenguaje y la plataforma que se elijan para la aplicación.

> [!TIP]
> Para obtener más información sobre cómo crear imágenes de Docker para aplicaciones de .NET, vaya a <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.
>
> Para más información sobre cómo crear sus propias imágenes, vaya a <https://docs.docker.com/engine/tutorials/dockerimages/>.

**Uso de repositorios de imágenes multiarquitectura**

Un solo nombre de imagen en un repositorio puede contener variantes de plataforma, como una imagen de Linux y una imagen de Windows. Esta característica permite a los proveedores como Microsoft (creadores de imágenes base) crear un único repositorio que cubra varias plataformas (es decir, Linux y Windows). Por ejemplo, el repositorio [dotnet/aspnet](https://hub.docker.com/_/microsoft-dotnet-aspnet/), disponible en el registro de Docker Hub, proporciona compatibilidad con Linux y Windows Nano Server mediante el mismo nombre de imagen.

Al extraer la imagen [dotnet/aspnet](https://hub.docker.com/_/microsoft-dotnet-aspnet/) de un host de Windows, se extrae la variante de Windows, y al extraer el mismo nombre de imagen de un host de Linux, se extrae la variante de Linux.

**_Creación de la imagen base desde cero_**

Puede crear su propia imagen de base de Docker desde cero, tal y como se explica en este [artículo](https://docs.docker.com/engine/userguide/eng-image/baseimages/) de Docker. Probablemente este escenario no sea el más adecuado para usuarios que acaban de iniciarse en Docker, pero si quiere establecer los bits específicos de su propia imagen base, puede hacerlo.

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a>Paso 3: Creación de imágenes personalizadas de Docker insertando su servicio en ellas

Por cada servicio personalizado que incluya su aplicación, deberá crear una imagen relacionada. Si la aplicación consta de un único servicio o aplicación web, solo necesitará una imagen.

> [!NOTE]
> Si se tiene en cuenta el "flujo de trabajo de bucle exterior de DevOps", las imágenes se crearán mediante un proceso de compilación automatizado cada vez que el código fuente se inserte en un repositorio de Git (integración continua), por lo que las imágenes se crearán en ese entorno global a partir de su código fuente.
>
> Pero antes de contemplar la posibilidad de ir a esa ruta de bucle externo, tiene que asegurarse de que la aplicación de Docker funciona correctamente para que no inserte código que pudiera no funcionar correctamente en el sistema de control de código fuente (Git, etc.).
>
> Por lo tanto, cada desarrollador debe realizar en primer lugar todo el proceso de bucle interno para probarlo localmente y continuar desarrollando hasta que quiera insertar una característica completa o cambiarla al sistema de control de código fuente.

Para crear una imagen en el entorno local y usar el Dockerfile, puede emplear el comando build de Docker, como se muestra en la figura 4-25, porque ya etiqueta la imagen automáticamente y compila las imágenes para todos los servicios de la aplicación con un comando simple.

![Captura de pantalla que muestra la salida de la consola del comando build de Docker Compose.](media/docker-apps-inner-loop-workflow/run-docker-build-command.png)

**Figura 4-25**. Ejecución de la compilación de Docker

Si lo prefiere, en lugar de ejecutar directamente `docker build` desde la carpeta del proyecto, puede generar primero una carpeta implementable con las bibliotecas.NET necesarias mediante la ejecución del comando `dotnet publish` y la posterior ejecución de `docker build`.

En este ejemplo se crea una imagen de Docker de nombre `webapi:latest` (`:latest` es una etiqueta, como una versión específica). Puede seguir este paso para cada imagen personalizada que tenga que crear para la aplicación de Docker compuesta con varios contenedores. Pero en la siguiente sección va a ver que es más fácil hacerlo mediante `docker-compose`.

Puede encontrar las imágenes existentes en el repositorio local (la máquina de desarrollo) mediante el comando `docker images`, como se muestra en la figura 4-26.

![Salida de consola del comando docker images, que muestra las imágenes existentes en la consola.](media/docker-apps-inner-loop-workflow/view-existing-images-with-docker-images.png)

**Figura 4-26**. Visualización de imágenes existentes con docker images

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a>Paso 4: Definición de los servicios en docker-compose.yml al compilar una aplicación de Docker compuesta de varios contenedores

Con el archivo `docker-compose.yml`, puede definir un conjunto de servicios relacionados para implementarlos como una aplicación compuesta con los comandos de implementación que se explican en la sección siguiente.

Cree ese archivo en la carpeta principal o raíz de su solución; debe tener un contenido similar al que se muestra en este archivo `docker-compose.yml`:

```yml
version: "3.4"

services:
  webapi:
    image: webapi
    build:
      context: .
      dockerfile: src/WebApi/Dockerfile
    ports:
      - 51080:80
    depends_on:
      - redis
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://+:80

  webapp:
    image: webapp
    build:
      context: .
      dockerfile: src/WebApp/Dockerfile
    ports:
      - 50080:80
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://+:80
      - WebApiBaseAddress=http://webapi

  redis:
    image: redis
```

En este caso concreto, este archivo define tres servicios: el servicio API web (el servicio personalizado), una aplicación web y el servicio Redis (un popular servicio de caché). Cada servicio se implementa como un contenedor, por lo que debe usar una imagen de Docker concreta para cada uno. En el caso de esta aplicación concreta:

- El servicio API web se compila a partir del Dockerfile del directorio `src/WebApi/Dockerfile`.

- El puerto de host 51080 se reenvía al puerto 80 expuesto en el contenedor `webapi`.

- El servicio API web depende del servicio Redis

- La aplicación web accede al servicio API web mediante la dirección interna: `http://webapi`.

- El servicio Redis usa la [imagen pública más reciente de Redis](https://hub.docker.com/_/redis/) extraída del registro de Docker Hub. [Redis](https://redis.io/) es un popular sistema de caché para aplicaciones de servidor.

### <a name="step-5-build-and-run-your-docker-app"></a>Paso 5: Compilación y ejecución de la aplicación de Docker

Si la aplicación tiene un solo contenedor, para ejecutarla tan solo tiene que implementarla en el host de Docker (máquina virtual o servidor físico). Aunque si la aplicación se compone de varios servicios también tendrá que _componerla_. Veamos las distintas opciones.

**_Opción A: Ejecución de un único contenedor o servicio_**

Puede ejecutar la imagen de Docker mediante el comando docker run, tal y como se muestra aquí:

```console
docker run -t -d -p 50080:80 webapp:latest
```

En el caso de esta implementación en particular, las solicitudes enviadas al puerto 50080 en el host se van a redirigir al puerto interno 80.

**_Opción B: Redacción y ejecución de una aplicación de varios contenedores_**

En la mayoría de los escenarios empresariales, una aplicación de Docker se compone de varios servicios. En estos casos, puede ejecutar el comando `docker-compose up` (figura 4-27), que va a usar el archivo docker-compose.yml creado anteriormente. Al ejecutar este comando se compilan todas las imágenes personalizadas y se implementa la aplicación compuesta con todos sus contenedores relacionados.

![Salida de consola del comando docker-compose up.](media/docker-apps-inner-loop-workflow/results-docker-compose-up.png)

**Figura 4-27**. Resultados de la ejecución del comando "docker-compose up"

Después de ejecutar `docker-compose up`, se implementa la aplicación y sus contenedores relacionados en el host de Docker, tal y como se muestra en la figura 4-28, en la representación de la máquina virtual.

![Máquina virtual que ejecuta una aplicación de varios contenedores.](./media/docker-apps-inner-loop-workflow/vm-with-docker-containers-deployed.png)

**Figura 4-28**. Máquina virtual con contenedores de Docker implementados

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a>Paso 6: Prueba de la aplicación de Docker (localmente, en la máquina virtual de CD local)

Este paso varía en función de lo que haga la aplicación.

En "Hola mundo", una API web sencilla de .NET que se implementa como contenedor o servicio único, solo tiene que acceder al servicio facilitando el puerto TCP especificado en el DockerFile.

En el host de Docker, abra un explorador y navegue a ese sitio; debe ver la aplicación o el servicio en ejecución, tal y como se muestra en la figura 4-29.

![Vista de explorador de la respuesta de localhost/API/valores.](media/docker-apps-inner-loop-workflow/test-docker-app-locally-localhost.png)

**Figura 4-29**. Prueba de la aplicación de Docker en local mediante el explorador

Observe que usa el puerto 50080, pero internamente se redirige al puerto 80, porque así es como se han implementado con `docker compose`, como se ha explicado anteriormente.

Puede probar con el explorador si usa CURL desde el terminal, como se muestra en la figura 4-30.

![Resultado de CURL obtenido de http://localhost:51080/WeatherForecast](media/docker-apps-inner-loop-workflow/test-docker-app-locally-curl.png)

**Figura 4-30**. Prueba de una aplicación de Docker en local mediante CURL

**Depuración de un contenedor que se ejecuta en Docker**

Visual Studio Code admite la depuración de Docker si usa Node.js y otras plataformas como, por ejemplo, contenedores de .NET.

También puede depurar contenedores de .NET o .NET Framework en Docker cuando se usa Visual Studio para Windows o Mac, tal y como se describe en la sección siguiente.

> [!TIP]
> Para más información sobre la depuración de contenedores de Docker de Node.js, consulte <https://blog.docker.com/2016/07/live-debugging-docker/> y <https://docs.microsoft.com/archive/blogs/user_ed/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more>.

> [!div class="step-by-step"]
> [Anterior](docker-apps-development-environment.md)
> [Siguiente](visual-studio-tools-for-docker.md)
