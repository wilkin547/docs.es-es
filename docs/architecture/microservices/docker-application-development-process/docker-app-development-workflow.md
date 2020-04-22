---
title: Flujo de trabajo de desarrollo para aplicaciones de Docker
description: Comprenda los detalles del flujo de trabajo para desarrollar aplicaciones basadas en Docker. Comience paso a paso, profundice en algunos detalles para optimizar Dockerfiles y termine con el flujo de trabajo simplificado disponible cuando se usa Visual Studio.
ms.date: 01/30/2020
ms.openlocfilehash: 2f380c840e186c345f9222aa6b0cf1097a74874e
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389198"
---
# <a name="development-workflow-for-docker-apps"></a>Flujo de trabajo de desarrollo para aplicaciones de Docker

El ciclo de vida de desarrollo de una aplicación se inicia en el equipo de cada desarrollador, donde se programa la aplicación con el lenguaje preferido y se prueba en el entorno local. Con este flujo de trabajo, no importa el lenguaje, el marco ni la plataforma que se elija, ya que siempre se desarrollan y se prueban contenedores de Docker en local.

Cada contenedor (una instancia de una imagen de Docker) incluye los siguientes componentes:

- Una selección de sistema operativo, por ejemplo, una distribución de Linux, Windows Nano Server o Windows Server Core.

- Archivos agregados durante el desarrollo, por ejemplo, archivos binarios de código fuente y aplicación.

- Información de configuración, como configuración de entorno y dependencias.

## <a name="workflow-for-developing-docker-container-based-applications"></a>Flujo de trabajo para desarrollar aplicaciones basadas en contenedor de Docker

En esta sección se explica el flujo de trabajo de desarrollo de *bucle interno* para aplicaciones basadas en contenedor de Docker. Flujo de trabajo de bucle interno significa que no se tiene en cuenta el flujo de trabajo general de DevOps, que puede incluir hasta implementación en producción, y solo se centra en el trabajo de desarrollo realizado en el equipo del desarrollador. Los pasos iniciales para configurar el entorno no se incluyen, ya que se realizan solo una vez.

Una aplicación se compone de sus propios servicios, además de bibliotecas adicionales (dependencias). Estos son los pasos básicos que normalmente se realizan al compilar una aplicación de Docker, como se muestra en la figura 5-1.

:::image type="complex" source="./media/docker-app-development-workflow/life-cycle-containerized-apps-docker-cli.png" alt-text="Diagrama que muestra los 7 pasos necesarios para crear una aplicación en contenedor.":::
Proceso de desarrollo de aplicaciones de Docker: 1. Programar la aplicación, 2. Escribir Dockerfiles, 3. Crear imágenes definidas en Dockerfiles, 4. (Opcional) Crear servicios en el archivo docker-compose.yml, 5. Ejecutar contenedor o aplicación docker-compose, 6. Probar la aplicación o los microservicios, 7. Insertar en el repositorio y repetir.
:::image-end:::

**Figura 5-1**. Flujo de trabajo paso a paso para el desarrollo de aplicaciones en contenedor de Docker

En esta sección se detalla el proceso completo y se explica cada paso importante centrándose en un entorno de Visual Studio.

Cuando se usa un enfoque de desarrollo de editor/CLI (por ejemplo, Visual Studio Code más la CLI de Docker en macOS o Windows), es necesario conocer cada paso, generalmente más detalladamente que si se usa Visual Studio. Para obtener más información sobre cómo trabajar en un entorno de CLI, vea el libro electrónico [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/) (Ciclo de vida de las aplicaciones en contenedor de Docker con plataformas y herramientas de Microsoft).

Al usar Visual Studio 2019, muchos de esos pasos se controlan de forma automática, lo que mejora considerablemente la productividad. Esto es así especialmente con Visual Studio 2019 y cuando el destino son aplicaciones de varios contenedores. Por ejemplo, con un solo clic, Visual Studio agrega `Dockerfile` y el archivo `docker-compose.yml` a los proyectos con la configuración de la aplicación. Al ejecutar la aplicación en Visual Studio, compila la imagen de Docker y ejecuta la aplicación de varios contenedores directamente en Docker; incluso permite depurar varios contenedores al mismo tiempo. Estas características aumentan la velocidad de desarrollo.

Pero que Visual Studio realice esos pasos automáticamente no significa que no sea necesario saber lo que ocurre en segundo plano con Docker. Por lo tanto, la guía siguiente detalla cada paso.

![Imagen del paso 1.](./media/docker-app-development-workflow/step-1-code-your-app.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a>Paso 1. Empezar a programar y crear la aplicación inicial o la base de referencia del servicio

El desarrollo de una aplicación de Docker es similar al desarrollo de una aplicación sin Docker. La diferencia es que al desarrollar para Docker, la aplicación o los servicios que se están implementando y probando se ejecutan en contenedores de Docker en el entorno local (una instalación de máquina virtual de Linux realizada por Docker o directamente Windows si se usan contenedores de Windows).

### <a name="set-up-your-local-environment-with-visual-studio"></a>Configurar el entorno local con Visual Studio

Para empezar, asegúrese de que tiene instalado [Docker Community Edition (CE)](https://docs.docker.com/docker-for-windows/) para Windows, como se explica en estas instrucciones:

[Get started with Docker CE for Windows (Introducción a Docker CE para Windows)](https://docs.docker.com/docker-for-windows/)

Además, se necesita Visual Studio 2019 16.4 o posterior con la carga de trabajo **Desarrollo multiplataforma de .NET Core** instalada, como se muestra en la figura 5-2.

![Captura de pantalla de la selección de desarrollo multiplataforma de .NET Core.](./media/docker-app-development-workflow/dotnet-core-cross-platform-development.png)

**Figura 5-2**. Selección de la carga de trabajo **Desarrollo multiplataforma de .NET Core** durante la instalación de Visual Studio 2019

Puede empezar a programar la aplicación en .NET sin formato (normalmente en .NET Core si va a usar contenedores) incluso antes de habilitar Docker en la aplicación e implementar y probar en Docker. Pero se recomienda empezar a trabajar en Docker tan pronto como sea posible, ya que es el entorno real y se pueden detectar los problemas a la mayor brevedad. Se recomienda encarecidamente porque Visual Studio facilita tanto el trabajo con Docker que casi parece transparente: el mejor ejemplo al depurar aplicaciones de varios contenedores desde Visual Studio.

### <a name="additional-resources"></a>Recursos adicionales

- **Get started with Docker CE for Windows** (Introducción a Docker CE para Windows) \
  <https://docs.docker.com/docker-for-windows/>

- **Visual Studio 2019** \
  [https://visualstudio.microsoft.com/downloads/](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

![Imagen del paso 2.](./media/docker-app-development-workflow/step-2-write-dockerfile.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a>Paso 2. Crear un Dockerfile relacionado con una imagen base existente de .NET

Necesita un Dockerfile para cada imagen personalizada que quiera compilar; también necesita un Dockerfile para cada contenedor que se vaya a implementar, tanto si se implementa automáticamente desde Visual Studio como manualmente mediante la CLI de Docker (comandos docker run y docker-compose). Si la aplicación contiene un único servicio personalizado, necesita un solo Dockerfile. Si la aplicación contiene varios servicios (como en una arquitectura de microservicios), necesita un Dockerfile para cada servicio.

El Dockerfile se coloca en la carpeta raíz de la aplicación o el servicio. Contiene los comandos que indican a Docker cómo configurar y ejecutar la aplicación o el servicio en un contenedor. Puede crear un Dockerfile de forma manual en el código y agregarlo al proyecto junto con las dependencias de .NET.

Con Visual Studio y sus herramientas para Docker, esta tarea solo exige unos clics. Al crear un proyecto en Visual Studio 2019, hay una opción denominada **Habilitar compatibilidad con Docker**, como se muestra en la figura 5-3.

![Captura de pantalla que muestra la casilla Enable Docker Support (Habilitar compatibilidad con Docker).](./media/docker-app-development-workflow/enable-docker-support-check-box.png)

**Figura 5-3**. Habilitación de la compatibilidad con Docker al crear un nuevo proyecto de ASP.NET Core en Visual Studio 2019

También puede habilitar la compatibilidad con Docker en un proyecto de aplicación web de ASP.NET Core existente haciendo clic con el botón derecho en el proyecto, en el **Explorador de soluciones**, y seleccionando **Agregar** > **Compatibilidad con Docker...** , como se muestra en la figura 5-4.

![Captura de pantalla que muestra la opción Docker Support (Compatibilidad con Docker) en el menú Add (Agregar).](./media/docker-app-development-workflow/add-docker-support-option.png)

**Figura 5-4**. Habilitación de la compatibilidad con Docker en un proyecto existente de Visual Studio 2019

Esta acción agrega un *Dockerfile* al proyecto con la configuración necesaria y solo está disponible en los proyectos de ASP.NET Core.

De forma similar, Visual Studio también puede agregar un archivo `docker-compose.yml` para toda la solución con la opción **Agregar > Compatibilidad con el orquestador de contenedores...** . En el paso 4 se examina esta opción más detalladamente.

### <a name="using-an-existing-official-net-docker-image"></a>Uso de una imagen de Docker de .NET oficial existente

Normalmente se compila una imagen personalizada para el contenedor además de una imagen base que se obtiene de un repositorio oficial como el registro [Docker Hub](https://hub.docker.com/). Eso es precisamente lo que sucede en segundo plano cuando se habilita la compatibilidad con Docker en Visual Studio. El Dockerfile usa una imagen `dotnet/core/aspnet` existente.

Anteriormente se ha explicado qué imágenes y repositorios de Docker se pueden usar según el marco de trabajo y el sistema operativo elegidos. Por ejemplo, si quiere usar ASP.NET Core (Linux o Windows), la imagen que se debe usar es `mcr.microsoft.com/dotnet/core/aspnet:3.1`. Por lo tanto, debe especificar qué imagen base de Docker va a usar para el contenedor. Se hace mediante la incorporación de `FROM mcr.microsoft.com/dotnet/core/aspnet:3.1` al Dockerfile. Visual Studio lo hace de forma automática, pero si va a actualizar la versión, actualice este valor.

El uso de un repositorio de imágenes de .NET oficial de Docker Hub con un número de versión garantiza que haya las mismas características de lenguaje disponibles en todos los equipos (incluido el desarrollo, las pruebas y la producción).

En el ejemplo siguiente se muestra un Dockerfile de ejemplo para un contenedor de ASP.NET Core.

```Dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
ARG source
WORKDIR /app
EXPOSE 80
COPY ${source:-obj/Docker/publish} .
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

En este caso, la imagen se basa en la versión 3.1 de la imagen de Docker de ASP.NET Core oficial (multiarquitectura para Linux y Windows). Es el valor `FROM mcr.microsoft.com/dotnet/core/aspnet:3.1`. [Para obtener más información sobre esta imagen base, consulte la página [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) (Imagen de Docker de .NET Core)]. En el Dockerfile, también debe indicar a Docker que escuche en el puerto TCP que se vaya a usar en tiempo de ejecución (en este caso, el puerto 80, como se ha configurado con el valor EXPOSE).

Puede especificar otros valores de configuración en el Dockerfile, según el lenguaje y el marco que use. Por ejemplo, la línea ENTRYPOINT con `["dotnet", "MySingleContainerWebApp.dll"]` indica a Docker que ejecute una aplicación .NET Core. Si usa el SDK y la CLI de .NET Core (dotnet CLI) para compilar y ejecutar la aplicación .NET, este valor sería diferente. La conclusión es que la línea ENTRYPOINT y otros valores pueden variar según el lenguaje y la plataforma que se elijan para la aplicación.

### <a name="additional-resources"></a>Recursos adicionales

- **Compilación de imágenes de Docker para aplicaciones .NET Core** \
  [https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images](/aspnet/core/host-and-deploy/docker/building-net-docker-images)

- **Compile su propia imagen**. En la documentación oficial de Docker.\
  <https://docs.docker.com/engine/tutorials/dockerimages/>

- **Mantenerse actualizado con imágenes de contenedor de .NET** \
  <https://devblogs.microsoft.com/dotnet/staying-up-to-date-with-net-container-images/>

- **Uso conjunto de .NET y Docket: actualización de DockerCon de 2018** \
  <https://devblogs.microsoft.com/dotnet/using-net-and-docker-together-dockercon-2018-update/>

### <a name="using-multi-arch-image-repositories"></a>Uso de repositorios de imágenes multiarquitectura

Un solo repositorio puede contener variantes de plataforma, como una imagen de Linux y una imagen de Windows. Esta característica permite a los proveedores como Microsoft (creadores de imágenes base) crear un único repositorio que cubra varias plataformas (es decir, Linux y Windows). Por ejemplo, el repositorio [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) disponible en el registro Docker Hub proporciona compatibilidad con Linux y Windows Nano Server mediante el mismo nombre de repositorio.

Si especifica una etiqueta, se toma como destino una plataforma explícita, como en los casos siguientes:

- `mcr.microsoft.com/dotnet/core/aspnet:3.1-buster-slim` \
  Destino: solo entorno de ejecución .NET Core 3.1 en Linux

- `mcr.microsoft.com/dotnet/core/aspnet:3.1-nanoserver-1909` \
  Destino: solo entorno de ejecución .NET Core 3.1 en Windows Nano Server

Pero, si se especifica el mismo nombre de imagen, incluso con la misma etiqueta, las imágenes multiarquitectura (como la imagen `aspnet`) usan la versión de Linux o Windows según el sistema operativo del host de Docker que se vaya a implementar, como se muestra en el ejemplo siguiente:

- `mcr.microsoft.com/dotnet/core/aspnet:3.1` \
  Arquitectura múltiple: solo entorno de ejecución .NET Core 3.1 en Linux o Windows Nano Server según el sistema operativo del host de Docker

De esta forma, al extraer una imagen de un host de Windows, se extrae la variante de Windows, y al extraer el mismo nombre de imagen de un host de Linux, se extrae la variante de Linux.

### <a name="multi-stage-builds-in-dockerfile"></a>Compilaciones de varias fases en Dockerfile

El Dockerfile es similar a un script por lotes. Es similar a lo que haría si tuviera que configurar el equipo desde la línea de comandos.

Comienza con una imagen base que configura el contexto inicial, es como el sistema de archivos de inicio, que se coloca sobre el sistema operativo del host. No es un sistema operativo, pero se puede considerar como "el" sistema operativo dentro del contenedor.

La ejecución de cada línea de comandos crea una nueva capa en el sistema de archivos con los cambios de la anterior, por lo que, cuando se combinan, generan el sistema de archivos resultante.

Dado que cada nueva capa "descansa" sobre la anterior y el tamaño de la imagen resultante aumenta con cada comando, las imágenes pueden llegar a tener un gran tamaño si tienen que incluir, por ejemplo, el SDK necesario para compilar y publicar una aplicación.

Aquí es donde las compilaciones de varias fases entran en escena (a partir de Docker 17.05 y posterior) para hacer su magia.

La idea central es que puede separar el proceso de ejecución del Dockerfile en fases, donde una fase es una imagen inicial seguida de uno o más comandos, y la última fase determina el tamaño final de la imagen.

En resumen, las compilaciones de varias fases permiten dividir la creación en "fases" distintas y, luego, ensamblar la imagen final al tomar solo los directorios pertinentes de las fases intermedias. La estrategia general para usar esta característica es:

1. Usar una imagen base de SDK (no importa su tamaño), con todo lo necesario para compilar y publicar la aplicación en una carpeta

2. Usar una imagen base pequeña de solo el entorno de ejecución y copiar la carpeta de publicación de la fase anterior para generar una pequeña imagen final.

Probablemente la mejor manera de comprender las fases es analizar un archivo Dockerfile en detalle, línea a línea, así que vamos a comenzar con el Dockerfile inicial creado por Visual Studio al agregar compatibilidad con Docker a un proyecto y, luego, realizaremos algunas optimizaciones.

El Dockerfile inicial podría ser algo parecido a esto:

```Dockerfile
 1  FROM mcr.microsoft.com/dotnet/core/aspnet:3.1 AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build
 6  WORKDIR /src
 7  COPY src/Services/Catalog/Catalog.API/Catalog.API.csproj …
 8  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.AspNetCore.HealthChecks …
 9  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions.HealthChecks …
10  COPY src/BuildingBlocks/EventBus/IntegrationEventLogEF/ …
11  COPY src/BuildingBlocks/EventBus/EventBus/EventBus.csproj …
12  COPY src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.csproj …
13  COPY src/BuildingBlocks/EventBus/EventBusServiceBus/EventBusServiceBus.csproj …
14  COPY src/BuildingBlocks/WebHostCustomization/WebHost.Customization …
15  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions …
16  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions …
17  RUN dotnet restore src/Services/Catalog/Catalog.API/Catalog.API.csproj
18  COPY . .
19  WORKDIR /src/src/Services/Catalog/Catalog.API
20  RUN dotnet build Catalog.API.csproj -c Release -o /app
21
22  FROM build AS publish
23  RUN dotnet publish Catalog.API.csproj -c Release -o /app
24
25  FROM base AS final
26  WORKDIR /app
27  COPY --from=publish /app .
28  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

Y estos son los detalles, línea a línea:

- **Línea 1:** Comience una fase con una imagen base "pequeña" de solo el entorno de ejecución, denomínela **base** para referencia.

- **Línea 2:** Cree el directorio **/app** de la imagen.

- **Línea 3:** Exponga el puerto **80**.

- **Línea 5:** Comience una nueva fase con una imagen "grande" para compilar y publicar. Denomínela **build** como referencia.

- **Línea 6:** Cree un directorio **/src** en la imagen.

- **Línea 7:** Hasta la línea 16, copie los archivos del proyecto **.csproj** a los que se hace referencia para poder restaurar los paquetes más adelante.

- **Línea 17:** Restaure los paquetes del proyecto **Catalog.API** y los proyectos a los que se hace referencia.

- **Línea 18:** Copie **todo el árbol de directorio de la solución** (excepto los archivos o directorios incluidos en el archivo **.dockerignore**) en el directorio **/src** de la imagen.

- **Línea 19:** Cambie la carpeta actual al proyecto **Catalog.API**.

- **Línea 20:** Compile el proyecto (y otras dependencias del proyecto) y use como salida el directorio **/app** de la imagen.

- **Línea 22:** Comience una nueva fase a partir de la compilación. Denomínela **publish** como referencia.

- **Línea 23:** Publique el proyecto (y las dependencias) y use como salida el directorio **/app** de la imagen.

- **Línea 25:** Comience una nueva fase a partir de **base** y denomínela **final**.

- **Línea 26:** Cambie el directorio actual a **/app**.

- **Línea 27:** Copie el directorio **/app** de la fase **publish** en el directorio actual.

- **Línea 28:** Defina el comando que se va a ejecutar cuando se inicie el contenedor.

Ahora vamos a examinar algunas optimizaciones para mejorar el rendimiento del proceso completo, lo que, en el caso de eShopOnContainers, significa aproximadamente 22 minutos o más para compilar la solución completa en contenedores de Linux.

Puede aprovechar la característica de caché de capas de Docker, que es bastante sencilla: si la imagen base y los comandos son los mismos que algunos ejecutados previamente, puede usar la capa resultante sin necesidad de ejecutar los comandos, con lo que se ahorra algo de tiempo.

Así, vamos a centrarnos en la fase **build**, las líneas 5 y 6 son prácticamente iguales, pero las líneas 7-17 son diferentes para cada servicio de eShopOnContainers, así que se tienen que ejecutar cada vez, pero si ha cambiado las líneas 7-16 a:

```Dockerfile
COPY . .
```

Luego, sería igual para cada servicio, se copiaría la solución completa y se crearía una capa más grande pero:

1. El proceso de copia solo se ejecutaría la primera vez (y al recompilar si se modifica un archivo) y se usaría la memoria caché para todos los demás servicios y

2. Puesto que la imagen más grande se produce en una fase intermedia, no afecta al tamaño final de la imagen.

La siguiente optimización importante implica al comando `restore` ejecutado en la línea 17, que también es diferente para cada servicio de eShopOnContainers. Si cambia esa línea a:

```Dockerfile
RUN dotnet restore
```

Restauraría los paquetes de toda la solución, pero, de nuevo, lo haría una sola vez, en lugar de las 15 veces con la estrategia actual.

Pero `dotnet restore` únicamente se ejecuta si hay un solo archivo de proyecto o solución en la carpeta, así que lograrlo es un poco más complicado y la forma de solucionarlo, sin entrar en demasiados detalles, es esta:

1. Agregue las líneas siguientes a **.dockerignore**:

   - `*.sln`, para omitir todos los archivos de solución del árbol de la carpeta principal

   - `!eShopOnContainers-ServicesAndWebApps.sln`, para incluir solo este archivo de solución.

2. Incluya el argumento `/ignoreprojectextensions:.dcproj` en `dotnet restore`, de modo que también omita el proyecto docker-compose y solo restaure los paquetes de la solución eShopOnContainers-ServicesAndWebApps.

Para la optimización final, resulta que la línea 20 es redundante, ya que la línea 23 también compila la aplicación y viene, básicamente, justo después de la línea 20, así que ahí tenemos otro comando que usa mucho tiempo.

El archivo resultante es entonces:

```Dockerfile
 1  FROM mcr.microsoft.com/dotnet/core/aspnet:3.1 AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS publish
 6  WORKDIR /src
 7  COPY . .
 8  RUN dotnet restore /ignoreprojectextensions:.dcproj
 9  WORKDIR /src/src/Services/Catalog/Catalog.API
10  RUN dotnet publish Catalog.API.csproj -c Release -o /app
11
12  FROM base AS final
13  WORKDIR /app
14  COPY --from=publish /app
15  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

### <a name="creating-your-base-image-from-scratch"></a>Creación de la imagen base desde cero

Puede crear su propia imagen base de Docker desde cero. Este escenario no se recomienda para usuarios que se están iniciando en Docker, pero si quiere establecer los bits específicos de su propia imagen base, puede hacerlo.

### <a name="additional-resources"></a>Recursos adicionales

- **Multi-arch .NET Core images** (Imágenes de .NET Core multiarquitectura).\
  <https://github.com/dotnet/announcements/issues/14>

- **Create a base image (Crear una imagen base)** . Documentación oficial de Docker.\
  <https://docs.docker.com/develop/develop-images/baseimages/>

![Imagen del paso 3.](./media/docker-app-development-workflow/step-3-create-dockerfile-defined-images.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a>Paso 3. Crear las imágenes de Docker personalizadas e insertar la aplicación o el servicio en ellas

Debe crear una imagen relacionada para cada servicio de la aplicación. Si la aplicación está formada por un único servicio o aplicación web, solo necesita una imagen.

Tenga en cuenta que las imágenes de Docker se compilan automáticamente en Visual Studio. Los pasos siguientes solo son necesarios para el flujo de trabajo de editor/CLI y se explican para aclarar lo que sucede en segundo plano.

Como desarrollador, debe desarrollar y probar en local hasta que inserte una característica o cambio completados en el sistema de control de código fuente (por ejemplo, en GitHub). Esto significa que tiene que crear las imágenes de Docker e implementar contenedores en un host de Docker local (máquina virtual de Windows o Linux) y ejecutar, probar y depurar en esos contenedores locales.

Para crear una imagen personalizada en el entorno local mediante la CLI de Docker y el Dockerfile, puede usar el comando docker build, como se muestra en la figura 5-5.

![Captura de pantalla que muestra la salida de la consola del comando de compilación de Docker.](./media/docker-app-development-workflow/run-docker-build-command.png)

**Figura 5-5**. Creación de una imagen personalizada de Docker

De forma opcional, en lugar de ejecutar directamente docker build desde la carpeta del proyecto, primero puede generar una carpeta que se pueda implementar con las bibliotecas de .NET y los binarios necesarios mediante la ejecución de `dotnet publish` y, luego, usar el comando `docker build`.

Esto crea una imagen de Docker con el nombre `cesardl/netcore-webapi-microservice-docker:first`. En este caso, :first es una etiqueta que representa una versión determinada. Puede repetir este paso para cada imagen personalizada que tenga que crear para la aplicación de Docker compuesta.

Cuando una aplicación se compone de varios contenedores (es decir, es una aplicación de varios contenedores), también puede usar el comando `docker-compose up --build` para compilar todas las imágenes relacionadas con un solo comando al usar los metadatos expuestos en los archivos relacionados docker-compose.yml.

Puede encontrar las imágenes existentes en el repositorio local mediante el comando docker images, como se muestra en la figura 5-6.

![Salida de consola del comando docker images, que muestra las imágenes existentes en la consola.](./media/docker-app-development-workflow/view-existing-images-with-docker-images.png)

**Figura 5-6**. Visualización de imágenes existentes mediante el comando docker images

### <a name="creating-docker-images-with-visual-studio"></a>Creación de imágenes de Docker con Visual Studio

Cuando se usa Visual Studio para crear un proyecto con compatibilidad con Docker, no se crea una imagen de forma explícita. La imagen se crea automáticamente al presionar **F5** (o **Ctrl-F5**) para ejecutar el servicio o la aplicación a los que se ha aplicado Docker. Este paso es automático en Visual Studio y no lo verá, pero es importante saber lo que ocurre en segundo plano.

![Imagen del paso 4 opcional.](./media/docker-app-development-workflow/step-4-define-services-docker-compose-yml.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a>Paso 4. Definir los servicios en docker-compose.yml al compilar una aplicación de Docker de varios contenedores

El archivo [docker-compose.yml](https://docs.docker.com/compose/compose-file/) permite definir un conjunto de servicios relacionados para implementarlos como una aplicación compuesta con comandos de implementación. También configura sus relaciones de dependencia y la configuración en tiempo de ejecución.

Para usar un archivo docker-compose.yml, debe crear el archivo en la carpeta de solución principal o raíz, con contenido similar al del ejemplo siguiente:

```yml
version: '3.4'

services:

  webmvc:
    image: eshop/web
    environment:
      - CatalogUrl=http://catalog-api
      - OrderingUrl=http://ordering-api
    ports:
      - "80:80"
    depends_on:
      - catalog-api
      - ordering-api

  catalog-api:
    image: eshop/catalog-api
    environment:
      - ConnectionString=Server=sqldata;Port=1433;Database=CatalogDB;…
    ports:
      - "81:80"
    depends_on:
      - sqldata

  ordering-api:
    image: eshop/ordering-api
    environment:
      - ConnectionString=Server=sqldata;Database=OrderingDb;…
    ports:
      - "82:80"
    extra_hosts:
      - "CESARDLBOOKVHD:10.0.75.1"
    depends_on:
      - sqldata

  sqldata:
    image: mssql-server-linux:latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

Este archivo docker-compose.yml es una versión simplificada y combinada. Contiene datos de configuración estáticos para cada contenedor (como el nombre de la imagen personalizada), que siempre son necesarios, junto con información de configuración que puede depender del entorno de implementación, como la cadena de conexión. En secciones posteriores se enseña a dividir la configuración de docker-compose.yml en varios archivos docker-compose y a reemplazar los valores según el entorno y el tipo de ejecución (depuración o versión).

El ejemplo de archivo docker-compose.yml define cuatro servicios: el servicio `webmvc` (una aplicación web), dos microservicios (`ordering-api` y `basket-api`) y un contenedor de fuente de datos, `sqldata`, según el servidor de SQL Server para Linux que se ejecute como contenedor. Cada servicio se implementa como un contenedor, por lo que se necesita una imagen de Docker para cada uno de ellos.

El archivo docker-compose.yml especifica no solo qué contenedores se van a usar, sino cómo se configuran individualmente. Por ejemplo, la definición del contenedor `webmvc` en el archivo .yml:

- Usa una imagen `eshop/web:latest` precompilada. Pero también puede configurar la imagen de modo que se compile como parte de la ejecución de docker-compose con una configuración adicional basada en una compilación: sección del archivo docker-compose.

- Inicializa dos variables de entorno (CatalogUrl y OrderingUrl).

- Reenvía el puerto 80 expuesto en el contenedor al puerto 80 externo del equipo de host.

- Vincula la aplicación web al catálogo y el servicio de orden con el valor depends_on. Esto hace que el servicio espere hasta que se inician los servicios.

Se volverá a hablar del archivo docker-compose.yml en una sección posterior, cuando se trate la implementación de microservicios y aplicaciones de varios contenedores.

### <a name="working-with-docker-composeyml-in-visual-studio-2019"></a>Trabajo con docker-compose.yml en Visual Studio 2019

Además de agregar un Dockerfile a un proyecto, como se ha mencionado antes, Visual Studio 2017 (a partir de la versión 15.8 en adelante) puede agregar compatibilidad de orquestador con Docker Compose a una solución.

Cuando se agrega compatibilidad de orquestador de contenedores, como se muestra en la figura 5-7, por primera vez, Visual Studio crea el Dockerfile para el proyecto y un nuevo proyecto (sección servicio) en la solución con varios archivos `docker-compose*.yml` globales y, luego, agrega el proyecto a esos archivos. Luego puede abrir los archivos docker-compose.yml y actualizarlos con otras características.

Tiene que repetir esta operación para cada proyecto que quiera incluir en el archivo docker-compose.yml.

En el momento de redactar este artículo, Visual Studio admite los orquestadores **Docker Compose** y **Kubernetes/Helm**.

![Captura de pantalla que muestra la opción Container Orchestrator Support (Compatibilidad con orquestador de contenedores) en el menú contextual del proyecto.](./media/docker-app-development-workflow/add-container-orchestrator-support-option.png)

**Figura 5-7**. Adición de compatibilidad con Docker en Visual Studio 2019 al hacer clic con el botón derecho en un proyecto de ASP.NET Core

Después de agregar compatibilidad de orquestador a la solución en Visual Studio, también se ve un nuevo nodo (en el archivo de proyecto `docker-compose.dcproj`) en el Explorador de soluciones que contiene los archivos docker-compose.yml agregados, como se muestra en la figura 5-8.

![Captura de pantalla del nodo docker-compose en el Explorador de soluciones.](./media/docker-app-development-workflow/docker-compose-tree-node.png)

**Figura 5-8**. Nodo de árbol **docker-compose** agregado en el Explorador de soluciones de Visual Studio 2019

Puede implementar una aplicación de varios contenedores con un único archivo docker-compose.yml mediante el comando `docker-compose up`. Pero Visual Studio agrega un grupo de ellos para que pueda reemplazar valores en función del entorno (desarrollo o producción) y el tipo de ejecución (versión o depuración). Esta capacidad se explica en secciones posteriores.

![Imagen del paso 5.](./media/docker-app-development-workflow/step-5-run-containers-compose-app.png)

## <a name="step-5-build-and-run-your-docker-application"></a>Paso 5. Compilar y ejecutar la aplicación

Si la aplicación solo tiene un contenedor, puede ejecutarla mediante su implementación en el host de Docker (máquina virtual o servidor físico). Sin embargo, si la aplicación contiene varios servicios, se puede implementar como aplicación compuesta, ya sea mediante un solo comando de la CLI `docker-compose up)` o con Visual Studio, que usará ese comando en segundo plano. Echemos un vistazo a las distintas opciones.

### <a name="option-a-running-a-single-container-application"></a>Opción A: Ejecución de una aplicación de un solo contenedor

#### <a name="using-docker-cli"></a>Uso de la CLI de Docker

Puede ejecutar un contenedor de Docker mediante el comando `docker run`, como se muestra en la figura 5-9:

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

El comando anterior crea una nueva instancia de contenedor a partir de la imagen especificada cada vez que se ejecuta. Puede usar el parámetro `--name` para asignar un nombre al contenedor y, luego, usar `docker start {name}` (o el identificador del contenedor o el nombre automático) para ejecutar una instancia de contenedor existente.

![Captura de pantalla de la ejecución de un contenedor de Docker mediante el comando docker run.](./media/docker-app-development-workflow/use-docker-run-command.png)

**Figura 5-9**. Ejecución de un contenedor de Docker mediante el comando docker run

En este caso, el comando enlaza el puerto interno 5000 del contenedor con el puerto 80 del equipo de host. Esto significa que el host escucha en el puerto 80 y reenvía al puerto 5000 del contenedor.

El hash que se muestra es el identificador del contenedor y además se le ha asignado un nombre legible aleatorio si no se ha usado la opción `--name`.

#### <a name="using-visual-studio"></a>Uso de Visual Studio

Si no ha agregado compatibilidad de orquestador de contenedores, también puede ejecutar una aplicación de un solo contenedor si presiona **Ctrl-F5** y además puede usar **F5** para depurar la aplicación del contenedor. El contenedor se ejecuta localmente mediante docker run.

### <a name="option-b-running-a-multi-container-application"></a>Opción B: Ejecución de una aplicación de varios contenedores

En la mayoría de los escenarios de empresa, una aplicación de Docker se compone de varios servicios, lo que significa que hay que ejecutar una aplicación de varios contenedores, como se muestra en la figura 5-10.

![Máquina virtual con varios contenedores de Docker](./media/docker-app-development-workflow/vm-with-docker-containers-deployed.png)

**Figura 5-10**. Máquina virtual con contenedores de Docker implementados

#### <a name="using-docker-cli"></a>Uso de la CLI de Docker

Para ejecutar una aplicación de varios contenedores con la CLI de Docker, use el comando `docker-compose up`. Este comando usa el archivo **docker-compose.yml** que hay en el nivel de solución para implementar una aplicación de varios contenedores. La figura 5-11 muestra los resultados de la ejecución del comando desde el directorio principal de la solución, que contiene el archivo docker-compose.yml.

![Vista de pantalla de la ejecución del comando docker-compose up](./media/docker-app-development-workflow/results-docker-compose-up.png)

**Figura 5-11**. Resultados del ejemplo al ejecutar el comando docker-compose up

Después de la ejecución del comando docker-compose up, la aplicación y sus contenedores relacionados se implementan en el host de Docker, como se muestra en la figura 5-10.

#### <a name="using-visual-studio"></a>Uso de Visual Studio

La ejecución de una aplicación de varios contenedores mediante Visual Studio 2019 no puede ser más sencilla. Simplemente presione **Ctrl-F5** para ejecutar o **F5** para depurar, como de costumbre, con lo que se configura el proyecto **docker-compose** como proyecto de inicio.  Visual Studio controla toda la configuración necesaria, por lo que puede crear puntos de interrupción como de costumbre y depurar lo que finalmente se convierte en procesos independientes que se ejecutan en "servidores remotos", con el depurador ya adjuntado, con facilidad.

Como se ha mencionado antes, cada vez que se agrega compatibilidad con soluciones de Docker a un proyecto de una solución, ese proyecto se configura en el archivo global (nivel de solución) docker-compose.yml, lo que permite ejecutar o depurar la solución completa al mismo tiempo. Visual Studio inicia un contenedor para cada proyecto que tiene habilitada la compatibilidad con soluciones de Docker y realiza todos los pasos internos automáticamente (dotnet publish, docker build, etc.).

Si quiere echar un vistazo al trabajo monótono, vea el archivo:

`{root solution folder}\obj\Docker\docker-compose.vs.debug.g.yml`

Lo importante aquí es que, como se muestra en la figura 5-12, en Visual Studio 2019 hay un comando adicional de **Docker** para la acción de la tecla F5. Esta opción permite ejecutar o depurar una aplicación de varios contenedores mediante la ejecución de todos los contenedores definidos en los archivos docker-compose.yml en el nivel de solución. La capacidad de depurar las soluciones de varios contenedores significa que puede establecer varios puntos de interrupción, cada uno en un proyecto diferente (contenedor) y, durante la depuración desde Visual Studio, detenerse en los puntos de interrupción definidos en los distintos proyectos y en ejecución en contenedores diferentes.

![Captura de pantalla de la barra de herramientas de depuración de Visual Studio ejecutando un proyecto docker-compose.](./media/docker-app-development-workflow/debug-toolbar-docker-compose-project.png)

**Figura 5-12**. Ejecución de aplicaciones de varios contenedores en Visual Studio 2019

### <a name="additional-resources"></a>Recursos adicionales

- **Implementación de un contenedor de ASP.NET en un host remoto de Docker** \
  <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker>

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a>Nota sobre las pruebas y la implementación con orquestadores

Los comandos docker-compose up y docker run (o la ejecución y depuración de los contenedores en Visual Studio) son adecuados para probar contenedores en el entorno de desarrollo. Sin embargo, no debe usar este enfoque para implementaciones de producción donde se deba tener como destino orquestadores como [Kubernetes](https://kubernetes.io/) o [Service Fabric](https://azure.microsoft.com/services/service-fabric/). Si usa Kubernetes, tiene que usar [pods](https://kubernetes.io/docs/concepts/workloads/pods/pod/) para organizar los contenedores y los [servicios](https://kubernetes.io/docs/concepts/services-networking/service/) para conectarlos en red. También se usan [implementaciones](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) organizar la creación y la modificación de pods.

![Imagen del paso 6.](./media/docker-app-development-workflow/step-6-test-app-microservices.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a>Paso 6. Probar la aplicación de Docker con el host local de Docker

Este paso varía en función de lo que haga la aplicación. En una aplicación web de .NET Core sencilla implementada como un único contenedor o servicio, puede acceder al servicio si abre un explorador en el host de Docker y va a ese sitio, como se muestra en la figura 5-13. (Si la configuración del Dockerfile asigna el contenedor a un puerto del host distinto al 80, incluya el puerto del host en la dirección URL).

![Captura de pantalla de la respuesta de localhost/API/valores.](./media/docker-app-development-workflow/test-docker-app-locally-localhost.png)

**Figura 5-13**. Ejemplo de prueba de la aplicación de Docker en local mediante localhost

Si localhost no apunta a la IP del host de Docker (de forma predeterminada, al usar Docker CE, debería hacerlo), para ir al servicio, use la dirección IP de la tarjeta de red del equipo.

Tenga en cuenta que esta dirección URL en el explorador usa el puerto 80 para el ejemplo de contenedor determinado que se está analizando. Pero, internamente, las solicitudes se redirigen al puerto 5000, porque así es como se ha implementado con el comando docker run, como se ha explicado en el paso anterior.

También puede probar la aplicación con la CURL del terminal, como se muestra en la figura 5-14. En una instalación de Docker en Windows, el valor predeterminado de la IP del host de Docker es siempre 10.0.75.1, además de la dirección IP real del equipo.

![Salida de consola de la obtención de http://10.0.75.1/API/values con CURL.](./media/docker-app-development-workflow/test-docker-app-locally-curl.png)

**Figura 5-14**. Ejemplo de prueba de la aplicación de Docker en local mediante CURL

### <a name="testing-and-debugging-containers-with-visual-studio-2019"></a>Prueba y depuración de contenedores con Visual Studio 2019

Al ejecutar y depurar contenedores con Visual Studio 2019, puede depurar la aplicación de .NET prácticamente de la misma manera que como lo haría al realizar la ejecución sin contenedores.

### <a name="testing-and-debugging-without-visual-studio"></a>Pruebas y depuración sin Visual Studio

Si su desarrollo se basa en el enfoque de editor/CLI, la depuración de contenedores es más difícil y es probable que prefiera hacerlo mediante la generación de seguimientos.

### <a name="additional-resources"></a>Recursos adicionales

- **Depuración de aplicaciones en un contenedor de Docker local** \
  [https://docs.microsoft.com/visualstudio/containers/edit-and-refresh](/visualstudio/containers/edit-and-refresh)

- **Steve Lasker. Compilar, depurar e implementar aplicaciones ASP.NET Core con Docker.** Video. \
  <https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115>

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a>Flujo de trabajo simplificado al desarrollar contenedores con Visual Studio

En la práctica, el flujo de trabajo cuando se usa Visual Studio es mucho más sencillo que si se usa el enfoque de editor/CLI. La mayoría de los pasos que necesita Docker relacionados con el Dockerfile y los archivos docker-compose.yml están ocultos o se han simplificado con Visual Studio, como se muestra en la figura 5-15.

:::image type="complex" source="./media/docker-app-development-workflow/simplified-life-cycle-containerized-apps-docker-cli.png" alt-text="Diagrama que muestra los cinco pasos simplificados necesarios para crear una aplicación.":::
Proceso de desarrollo de aplicaciones de Docker: 1. Programar la aplicación, 2. Escribir Dockerfiles, 3. Crear imágenes definidas en Dockerfiles, 4. (Opcional) Crear servicios en el archivo docker-compose.yml, 5. Ejecutar contenedor o aplicación docker-compose, 6. Probar la aplicación o los microservicios, 7. Insertar en el repositorio y repetir.
:::image-end:::

**Figura 5-15**. Flujo de trabajo simplificado al desarrollar con Visual Studio

Además, debe realizar el paso 2 (agregar compatibilidad con Docker a los proyectos) una sola vez. Por lo tanto, el flujo de trabajo es similar a las tareas de desarrollo habituales cuando se usa .NET para cualquier otro desarrollo. Debe saber qué está sucediendo en segundo plano (el proceso de compilación de imágenes, qué imágenes base usa, la implementación de contenedores, etc.) y, a veces, también debe editar el Dockerfile o el archivo docker-compose.yml para personalizar comportamientos. Pero con Visual Studio se simplifica enormemente la mayor parte del trabajo, lo que mejora mucho la productividad.

### <a name="additional-resources"></a>Recursos adicionales

- **Desarrollo de Docker de .NET con Visual Studio 2017, de Steve Lasker** \
  <https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111>

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a>Uso de comandos de PowerShell en un Dockerfile para configurar contenedores de Windows

Los [contenedores de Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/index) permiten convertir las aplicaciones de Windows existentes en imágenes de Docker e implementarlas con las mismas herramientas que el resto del ecosistema de Docker. Para usar contenedores de Windows, ejecute comandos de PowerShell en el Dockerfile, como se muestra en el ejemplo siguiente:

```Dockerfile
FROM mcr.microsoft.com/windows/servercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

En este caso se usa una imagen base de Windows Server Core (el valor FROM) y se instala IIS con un comando de PowerShell (el valor RUN). Del mismo modo, también se pueden usar comandos de PowerShell para configurar otros componentes como ASP.NET 4.x, .NET 4.6 o cualquier otro software de Windows. Por ejemplo, el siguiente comando en un Dockerfile configura ASP.NET 4.5:

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a>Recursos adicionales

- **aspnet-docker/Dockerfile.** Comandos de PowerShell de ejemplo para ejecutar desde Dockerfiles a fin de incluir características de Windows.\
  <https://github.com/Microsoft/aspnet-docker/blob/master/4.7.1-windowsservercore-ltsc2016/runtime/Dockerfile>

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](../multi-container-microservice-net-applications/index.md)
