---
title: Flujo de trabajo de desarrollo para aplicaciones de Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Flujo de trabajo de desarrollo para aplicaciones de Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/05/2018
ms.openlocfilehash: bc6b1796ed7b12a04affc521ac2efee515c48ae2
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53150555"
---
# <a name="development-workflow-for-docker-apps"></a>Flujo de trabajo de desarrollo para aplicaciones de Docker

El ciclo de vida de desarrollo de una aplicación se inicia en el equipo de cada desarrollador, donde programa la aplicación con su lenguaje preferido y la prueba en el entorno local. Independientemente del lenguaje, el marco de trabajo y la plataforma que elija el desarrollador, con este flujo de trabajo, siempre desarrolla y prueba contenedores de Docker, aunque lo hace en local.

Cada contenedor (una instancia de una imagen de Docker) incluye los siguientes componentes:

- Una selección de sistema operativo (por ejemplo, una distribución de Linux, Windows Nano Server o Windows Server Core).

- Archivos agregados por el desarrollador (binarios de aplicación, etc.).

- Información de configuración (configuración de entorno y dependencias).

## <a name="workflow-for-developing-docker-container-based-applications"></a>Flujo de trabajo para desarrollar aplicaciones basadas en contenedor de Docker

En esta sección se explica el flujo de trabajo de desarrollo de *bucle interno* para aplicaciones basadas en contenedor de Docker. El flujo de trabajo de bucle interno significa que no se tiene en cuenta el flujo de trabajo general de DevOps y solo se centra en el trabajo de desarrollo realizado en el equipo del desarrollador. Los pasos iniciales para configurar el entorno no se incluyen, ya que se realizan solo una vez.

Una aplicación se compone de sus propios servicios, además de bibliotecas adicionales (dependencias). Estos son los pasos básicos que normalmente se realizan al compilar una aplicación de Docker, como se muestra en la figura 5-1.

![Gráfico del flujo de trabajo paso a paso para el desarrollo de aplicaciones en contenedor de Docker](./media/image1.png)

**Figura 5-1**. Flujo de trabajo paso a paso para el desarrollo de aplicaciones en contenedor de Docker

En esta guía se detalla el proceso completo y se explica cada paso importante centrándose en un entorno de Visual Studio.

Cuando se usa un enfoque de desarrollo de editor/CLI (por ejemplo, Visual Studio Code más la CLI de Docker en macOS o Windows), es necesario conocer cada paso, generalmente más detalladamente que si se usa Visual Studio. Para obtener más información sobre cómo trabajar en un entorno de CLI, vea el libro electrónico [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/) (Ciclo de vida de las aplicaciones en contenedor de Docker con plataformas y herramientas de Microsoft).

Cuando se usa Visual Studio, muchos de esos pasos se controlan de forma automática, lo que mejora considerablemente la productividad. Esto es así especialmente con Visual Studio 2017 y cuando el destino son aplicaciones de varios contenedores. Por ejemplo, con un solo clic, Visual Studio agrega el *Dockerfile* y los archivos *docker-compose.yml* a los proyectos con la configuración de la aplicación. Al ejecutar la aplicación en Visual Studio, compila la imagen de Docker y ejecuta la aplicación de varios contenedores directamente en Docker. Incluso permite depurar varios contenedores al mismo tiempo. Estas características aumentan la velocidad de desarrollo.

En las instrucciones siguientes se explica lo que sucede con Docker "en segundo plano".

![Gráfico del paso 1: programación de la aplicación](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a>Paso 1. Empezar a programar y crear la aplicación inicial o la base de referencia del servicio

El desarrollo de una aplicación de Docker es similar al desarrollo de una aplicación sin Docker. La diferencia es que al desarrollar para Docker, la aplicación o los servicios que se están implementando y probando se ejecutan en contenedores de Docker en el entorno local. El contenedor puede ser un contenedor de Linux o de Windows.

### <a name="set-up-your-local-environment-with-visual-studio"></a>Configurar el entorno local con Visual Studio

Para empezar, asegúrese de que tiene instalado [Docker Community Edition (CE)](https://www.docker.com/community-edition) para Windows, como se explica en estas instrucciones:

[Get started with Docker CE for Windows (Introducción a Docker CE para Windows)](https://docs.docker.com/docker-for-windows/)

Además, se necesita Visual Studio 2017 con la carga de trabajo **Desarrollo multiplataforma de .NET Core** instalada, como se muestra en la figura 5-2.

![](./media/image3.png)

**Figura 5-2**. Selección de la carga de trabajo **.NET Core y Docker** durante la instalación de Visual Studio 2017

Puede empezar a programar la aplicación en .NET sin formato (normalmente en .NET Core si va a usar contenedores) incluso antes de habilitar Docker en la aplicación e implementar y probar en Docker. Pero se recomienda empezar a trabajar en Docker tan pronto como sea posible, ya que es el entorno real y se pueden detectar los problemas a la mayor brevedad. Se recomienda encarecidamente porque Visual Studio facilita tanto el trabajo con Docker que casi parece transparente: el mejor ejemplo al depurar aplicaciones de varios contenedores desde Visual Studio.

### <a name="additional-resources"></a>Recursos adicionales

- **Get started with Docker CE for Windows (Introducción a Docker CE para Windows)**

   [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)

- **Visual Studio 2017**

   [*https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs*](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

![Gráfico del paso 2: escritura de elementos Dockerfile](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a>Paso 2. Crear un Dockerfile relacionado con una imagen base existente de .NET

Necesita un Dockerfile para cada imagen personalizada que quiera compilar; también para cada contenedor que se vaya a implementar, tanto si se implementa de forma automática desde Visual Studio como manualmente mediante la CLI de Docker (los comandos docker run y docker-compose). Si la aplicación contiene un único servicio personalizado, necesita un solo Dockerfile. Si la aplicación contiene varios servicios (como en una arquitectura de microservicios), necesita un Dockerfile para cada servicio.

El Dockerfile se coloca en la carpeta raíz de la aplicación o el servicio. Contiene los comandos que indican a Docker cómo configurar y ejecutar la aplicación o el servicio en un contenedor. Puede crear un Dockerfile de forma manual en el código y agregarlo al proyecto junto con las dependencias de .NET.

Con Visual Studio Tools para Docker, esta tarea solo exige unos clics. Al crear un proyecto en Visual Studio 2017, hay una opción denominada **Habilitar compatibilidad con Docker**, como se muestra en la figura 5-3.

![Habilitación de la compatibilidad con Docker al crear un nuevo proyecto en Visual Studio 2017](./media/image5.png)

**Figura 5-3**. Habilitación de la compatibilidad con Docker al crear un nuevo proyecto en Visual Studio 2017

También puede habilitar la compatibilidad con Docker en un proyecto de aplicación web de .NET Core existente haciendo clic con el botón derecho en el proyecto en el **Explorador de soluciones** y seleccionando **Agregar** > **Compatibilidad con Docker**, como se muestra en la figura 5-4.

![Opción de menú Agregar compatibilidad con Docker en Visual Studio](./media/add-docker-support.png)

**Figura 5-4**. Habilitación de la compatibilidad con Docker en un proyecto existente de Visual Studio 2017

Esta acción agrega un *Dockerfile* al proyecto con la configuración necesaria y solo está disponible en los proyectos de aplicación web de .NET Core.

Para agregar un archivo *docker-compose.yml* para toda la solución, haga clic con el botón derecho en el proyecto en el **Explorador de soluciones** y seleccione **Agregar** > **Compatibilidad con el orquestador de contenedores**, como se muestra en la figura 5-5.

![Opción de menú para agregar compatibilidad con el orquestador de contenedores en Visual Studio](./media/add-container-orchestrator-support.png)

**Figura 5-5**. Adición de compatibilidad con el orquestador de contenedores a un proyecto existente en Visual Studio 2017

En las siguientes secciones se describe la información incluida en cada uno de esos archivos. Visual Studio puede hacer este trabajo automáticamente, aunque resulta útil entender qué contiene un Dockerfile.

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a>Opción A: crear un proyecto mediante una imagen de Docker de .NET oficial existente

Normalmente se compila una imagen personalizada para el contenedor sobre una imagen base que se puede obtener de un repositorio oficial en el registro [Docker Hub](https://hub.docker.com/). Eso es precisamente lo que sucede en segundo plano cuando se habilita la compatibilidad con Docker en Visual Studio. El Dockerfile usa una imagen de aspnetcore existente.

Anteriormente se ha explicado qué imágenes y repositorios de Docker se pueden usar según el marco de trabajo y el sistema operativo elegidos. Por ejemplo, si quiere usar ASP.NET Core (Linux o Windows), la imagen que se debe usar es microsoft/aspnetcore:2.0. Por lo tanto, debe especificar qué imagen base de Docker va a usar para el contenedor. Para ello hay que agregar FROM microsoft/aspnetcore:2.0 al Dockerfile. Visual Studio lo hace de forma automática, pero si va a actualizar la versión, actualice este valor.

El uso de un repositorio de imágenes de .NET oficial de Docker Hub con un número de versión garantiza que haya las mismas características de lenguaje disponibles en todos los equipos (incluido el desarrollo, las pruebas y la producción).

En el ejemplo siguiente se muestra un Dockerfile de ejemplo para un contenedor de ASP.NET Core.

```Dockerfile
FROM microsoft/aspnetcore:2.0

ARG source

WORKDIR /app

EXPOSE 80

COPY ${source:-obj/Docker/publish} .

ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

En este caso, el contenedor se basa en la versión 2.0 de la imagen de Docker de ASP.NET Core oficial (multiarquitectura para Linux y Windows). Es el valor `FROM microsoft/aspnetcore:2.0`. (Para obtener más información sobre esta imagen base, vea las páginas [ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) (Imagen de Docker de ASP.NET Core) y [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) (Imagen de Docker de .NET Core)). En el Dockerfile, también debe indicar a Docker que escuche en el puerto TCP que se vaya a usar en tiempo de ejecución (en este caso, el puerto 80, como se ha configurado con el valor EXPOSE).

Puede especificar otros valores de configuración en el Dockerfile, según el lenguaje y el marco de trabajo que use. Por ejemplo, la línea ENTRYPOINT con \["dotnet", "MySingleContainerWebApp.dll"\] indica a Docker que ejecute una aplicación de .NET Core. Si usa el SDK y la CLI de .NET Core (dotnet CLI) para compilar y ejecutar la aplicación de .NET, este valor sería diferente. La conclusión es que la línea ENTRYPOINT y otros valores pueden variar según el lenguaje y la plataforma que se elijan para la aplicación.

### <a name="additional-resources"></a>Recursos adicionales

- **Creación de imágenes de Docker para aplicaciones de .NET Core**

   [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](../../../core/docker/building-net-docker-images.md)

- **Compile su propia imagen**. En la documentación oficial de Docker.

   [*https://docs.docker.com/engine/tutorials/dockerimages/*](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a>Uso de repositorios de imágenes multiarquitectura

Un solo repositorio puede contener variantes de plataforma, como una imagen de Linux y una imagen de Windows. Esta característica permite a los proveedores como Microsoft (creadores de imágenes base) crear un único repositorio que cubra varias plataformas (es decir, Linux y Windows). Por ejemplo, el repositorio [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) disponible en el registro Docker Hub proporciona compatibilidad con Linux y Windows Nano Server mediante el mismo nombre de repositorio.

Si especifica una etiqueta, se toma como destino una plataforma explícita, como en los casos siguientes:

- **microsoft/aspnetcore:2.0.0-jessie**

        .NET Core 2.0 runtime-only on Linux

- **microsoft/aspnetcore:2.0.0-nanoserver**

        .NET Core 2.0 runtime-only on Windows Nano Server

Pero, y esto es nuevo desde mediados de 2017, si se especifica el mismo nombre de imagen, incluso con la misma etiqueta, las nuevas imágenes multiarquitectura (como la imagen de aspnetcore compatible con la multiarquitectura) usan la versión de Linux o Windows según el sistema operativo del host de Docker que se vaya a implementar, como se muestra en el ejemplo siguiente:

- **microsoft/aspnetcore:2.0**

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

De esta forma, al extraer una imagen de un host de Windows, se extrae la variante de Windows, y al extraer el mismo nombre de imagen de un host de Linux, se extrae la variante de Linux.

### <a name="option-b-creating-your-base-image-from-scratch"></a>Opción B: crear la imagen base desde cero

Puede crear su propia imagen base de Docker desde cero. Este escenario no se recomienda para usuarios que se están iniciando en Docker, pero si quiere establecer los bits específicos de su propia imagen base, puede hacerlo.

### <a name="additional-resources"></a>Recursos adicionales

- **Multi-arch .NET Core images (Imágenes de .NET Core multiarquitectura)**.

   https://github.com/dotnet/announcements/issues/14

- **Create a base image (Crear una imagen base)**. Documentación oficial de Docker.

   [*https://docs.docker.com/engine/userguide/eng-image/baseimages/*](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![Gráfico del paso 3: creación de imágenes](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a>Paso 3. Crear las imágenes de Docker personalizadas e insertar la aplicación o el servicio en ellas

Debe crear una imagen relacionada para cada servicio de la aplicación. Si la aplicación está formada por un único servicio o aplicación web, solo necesita una imagen.

Las imágenes de Docker se compilan de forma automática en Visual Studio. Los pasos siguientes solo son necesarios para el flujo de trabajo de editor/CLI y se explican para aclarar lo que sucede en segundo plano.

Como desarrollador, debe desarrollar y probar en local hasta que inserte una característica o cambio completados en el sistema de control de código fuente (por ejemplo, en GitHub). Esto significa que tiene que crear las imágenes de Docker e implementar contenedores en un host de Docker local (máquina virtual de Windows o Linux) y ejecutar, probar y depurar en esos contenedores locales.

Para crear una imagen personalizada en el entorno local mediante la CLI de Docker y el Dockerfile, puede usar el comando docker build, como se muestra en la figura 5-5.

![Creación de una imagen personalizada de Docker](./media/image8.png)

**Figura 5-5**. Creación de una imagen personalizada de Docker

De forma opcional, en lugar de ejecutar directamente docker build desde la carpeta del proyecto, primero puede generar una carpeta que se pueda implementar con las bibliotecas de .NET y los binarios necesarios mediante la ejecución de dotnet publish y, luego, usar el comando docker build.

Esto creará una imagen de Docker con el nombre **cesardl/netcore-webapi-microservice-docker:first**. En este caso, :first es una etiqueta que representa una versión determinada. Puede repetir este paso para cada imagen personalizada que tenga que crear para la aplicación de Docker compuesta.

Cuando una aplicación se compone de varios contenedores (es decir, es una aplicación de varios contenedores), también puede usar el comando docker-compose up --build para compilar todas las imágenes relacionadas con un solo comando al usar los metadatos expuestos en los archivos relacionados docker-compose.yml.

Puede encontrar las imágenes existentes en el repositorio local mediante el comando docker images, como se muestra en la figura 5-6.

![Visualización de imágenes existentes mediante el comando docker images](./media/image9.png)

**Figura 5-6**. Visualización de imágenes existentes mediante el comando docker images

### <a name="creating-docker-images-with-visual-studio"></a>Creación de imágenes de Docker con Visual Studio

Cuando se usa Visual Studio para crear un proyecto con compatibilidad con Docker, no se crea una imagen de forma explícita. Por el contrario, la imagen se crea automáticamente al presionar **F5** para ejecutar el servicio o la aplicación a los que se ha aplicado Docker. Este paso es automático en Visual Studio y no lo verá, pero es importante saber lo que ocurre en segundo plano.

![Gráfico del paso 4: definición de los servicios](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a>Paso 4. Definir los servicios en docker-compose.yml al compilar una aplicación de Docker de varios contenedores

El archivo [docker-compose.yml](https://docs.docker.com/compose/compose-file/) permite definir un conjunto de servicios relacionados para implementarlos como una aplicación compuesta con comandos de implementación.

Para usar un archivo docker-compose.yml, debe crear el archivo en la carpeta de solución principal o raíz, con contenido similar al del ejemplo siguiente:

```yml
version: '3'

services:

  webmvc:
    image: eshop/web
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
    ports:
      - "80:80"
    depends_on:
      - catalog.api
      - ordering.api

  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=sql.data;Database=CatalogDB;…
    ports:
      - "81:80"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=OrderingDb;…
    ports:
      - "82:80"
    extra_hosts:
      - "CESARDLBOOKVHD:10.0.75.1"
    depends_on:
      - sql.data

  sql.data:
    image: mssql-server-linux:latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

Este archivo docker-compose.yml es una versión simplificada y combinada. Contiene datos de configuración estáticos para cada contenedor (como el nombre de la imagen personalizada), que siempre se aplican, junto con información de configuración que puede depender del entorno de implementación, como la cadena de conexión. En secciones posteriores aprenderá a dividir la configuración de docker-compose.yml en varios archivos docker-compose y a sustituir los valores según el entorno y el tipo de ejecución (depuración o versión).

El ejemplo de archivo docker-compose.yml define cuatro servicios: el servicio webmvc (una aplicación web), dos microservicios (catalog.api y ordering.api) y un contenedor de fuente de datos, sql.data, según el servidor de SQL Server para Linux que se ejecute como contenedor. Cada servicio se implementa como un contenedor, por lo que se necesita una imagen de Docker para cada uno de ellos.

El archivo docker-compose.yml especifica no solo qué contenedores se van a usar, sino cómo se configuran individualmente. Por ejemplo, la definición del contenedor webmvc en el archivo .yml:

- Usa una imagen precompilada eshop/web:latest. Pero también puede configurar la imagen de modo que se compile como parte de la ejecución de docker-compose con una configuración adicional basada en una compilación: sección del archivo docker-compose.

- Inicializa dos variables de entorno (CatalogUrl y OrderingUrl).

- Reenvía el puerto 80 expuesto en el contenedor al puerto 80 externo del equipo de host.

- Vincula la aplicación web al catálogo y el servicio de orden con el valor depends\_on. Esto hace que el servicio espere hasta que se inician los servicios.

Se volverá a hablar del archivo docker-compose.yml en una sección posterior, cuando se trate la implementación de microservicios y aplicaciones de varios contenedores.

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a>Trabajo con docker-compose.yml en Visual Studio 2017

Al agregar compatibilidad con el orquestador de contenedores a un proyecto de aplicación web, como se muestra en la figura 5-7, Visual Studio agrega una sección de servicio (proyecto) a la solución que contiene un archivo docker-compose.yml. Es una forma sencilla de empezar a crear la solución de varios contenedores.

![Elemento de menú para agregar compatibilidad con el orquestador de contenedores en Visual Studio](./media/add-container-orchestrator-support.png)

**Figura 5-7**. Adición de compatibilidad con Docker en Visual Studio 2017 al hacer clic con el botón derecho en un proyecto de ASP.NET Core

Al agregar compatibilidad con el orquestador de contenedores, se agrega el elemento Dockerfile al proyecto (si todavía no existe). También se agrega información de configuración a un archivo docker-compose.yml global en el nivel de la solución. Verá un nuevo nodo de proyecto (el archivo de proyecto *docker-compose.dcproj*) en el **Explorador de soluciones** que contiene el archivo docker-compose.yml, como se muestra en la figura 5-8.

![Nodo de docker-compose en el Explorador de soluciones](./media/docker-compose-files.png)

**Figura 5-8**. Nodo de árbol **docker-compose** agregado en el Explorador de soluciones de Visual Studio 2017

Luego puede abrir el archivo docker-compose.yml y actualizarlo con características adicionales.

Puede implementar una aplicación de varios contenedores con un único archivo docker-compose.yml mediante el comando `docker-compose up`.

![Gráfico del paso 5: ejecución de la aplicación](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a>Paso 5. Compilar y ejecutar la aplicación

Si la aplicación solo tiene un contenedor, puede ejecutarla mediante su implementación en el host de Docker (máquina virtual o servidor físico). Pero si la aplicación contiene varios servicios, se puede implementar como una aplicación compuesta, ya sea mediante un solo comando de la CLI (docker-compose up) o con Visual Studio, que usará ese comando en segundo plano. Echemos un vistazo a las distintas opciones.

### <a name="option-a-run-a-single-container-app"></a>Opción A: ejecución de una aplicación de contenedor único

#### <a name="docker-cli"></a>CLI de Docker

Puede ejecutar un contenedor de Docker mediante el comando docker run, como se muestra en la figura 5-9:

```console
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![Ejecución de un contenedor de Docker mediante el comando docker run](./media/image13.png)

**Figura 5-9**. Ejecución de un contenedor de Docker mediante el comando docker run

En este caso, el comando enlaza el puerto interno 5000 del contenedor con el puerto 80 del equipo de host. Esto significa que el host escucha en el puerto 80 y reenvía al puerto 5000 del contenedor.

#### <a name="visual-studio"></a>Programa para la mejora

Si no ha agregado compatibilidad con el orquestador de contenedores, también puede presionar **F5** para ejecutar una aplicación de contenedor único en Visual Studio. El contenedor se ejecuta localmente mediante docker run.

### <a name="option-b-run-a-multi-container-app"></a>Opción B: Ejecución de una aplicación de varios contenedores

En la mayoría de los escenarios de empresa, una aplicación de Docker se compone de varios servicios, lo que significa que hay que ejecutar una aplicación de varios contenedores, como se muestra en la figura 5-10.

![Gráfico en el que se muestra una máquina virtual con contenedores de Docker implementados](./media/image14.png)

**Figura 5-10**. Máquina virtual con contenedores de Docker implementados

#### <a name="docker-cli"></a>CLI de Docker

Para ejecutar una aplicación de varios contenedores con la CLI de Docker, puede ejecutar el comando docker-compose up. Este comando usa el archivo docker-compose.yml que hay en el nivel de solución para implementar una aplicación de varios contenedores. La figura 5-11 muestra los resultados de la ejecución del comando desde el directorio principal del proyecto, que contiene el archivo docker-compose.yml.

![Resultados del ejemplo al ejecutar el comando docker-compose up](./media/image15.png)

**Figura 5-11**. Resultados del ejemplo al ejecutar el comando docker-compose up

Después de la ejecución del comando docker-compose up, la aplicación y sus contenedores relacionados se implementan en el host de Docker.

#### <a name="visual-studio"></a>Programa para la mejora

La ejecución de una aplicación de varios contenedores con Visual Studio 2017 es sencilla. No solo se puede ejecutar la aplicación de varios contenedores, sino que es posible depurar todos sus contenedores directamente desde Visual Studio mediante el establecimiento de puntos de interrupción regulares.

Como se ha mencionado antes, cada vez que se agrega compatibilidad con el orquestador de contenedores a un proyecto de una solución, ese proyecto se configura en el archivo docker-compose.yml global (en el nivel de solución), lo que permite ejecutar o depurar la solución completa al mismo tiempo. Visual Studio inicia un contenedor para cada proyecto que tiene habilitada la compatibilidad con soluciones de Docker y realiza todos los pasos internos de forma automática (dotnet publish, docker build, etc.).

Lo importante aquí es que, como se muestra en la figura 5-12, en Visual Studio 2017 hay un comando adicional de **Docker** para la acción de la tecla **F5**. Esta opción permite ejecutar o depurar una aplicación de varios contenedores mediante la ejecución de todos los contenedores definidos en los archivos docker-compose.yml en el nivel de solución. La capacidad de depurar las soluciones de varios contenedores significa que puede establecer varios puntos de interrupción, cada uno en un proyecto diferente (contenedor) y, durante la depuración desde Visual Studio, detenerse en los puntos de interrupción definidos en los distintos proyectos y en ejecución en contenedores diferentes.

![Ejecución de aplicaciones de varios contenedores en Visual Studio 2017](./media/image16.png)

**Figura 5-12**. Ejecución de aplicaciones de varios contenedores en Visual Studio 2017

### <a name="additional-resources"></a>Recursos adicionales

-  **Implementar un contenedor de ASP.NET en un host remoto de Docker**

   [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a>Nota sobre las pruebas y la implementación con orquestadores

Los comandos docker-compose up y docker run (o la ejecución y depuración de los contenedores en Visual Studio) son adecuados para probar contenedores en el entorno de desarrollo. Pero no debería usar este enfoque si el destino son clústeres y orquestadores de Docker como Docker Swarm, Mesosphere DC/OS o Kubernetes. Si está usando un clúster como [modo Docker Swarm](https://docs.docker.com/engine/swarm/) (disponible en Docker CE para Windows y Mac a partir de la versión 1.12), debe implementar y probar con otros comandos, como [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) para servicios únicos. Si va a implementar una aplicación formada por varios contenedores, use [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) y [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) para implementar la aplicación compuesta como una *pila*. Para más información, vea la entrada de blog [Introducing Experimental Distributed Application Bundles (Introducción a los lotes de aplicaciones experimentales distribuidos)](https://blog.docker.com/2016/06/docker-app-bundle/) en la documentación de Docker. en el sitio de Docker.

En [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) y [Kubernetes](https://kubernetes.io/docs/user-guide/deployments/) se usarían además comandos y scripts de implementación diferentes.

![Gráfico del paso 6](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a>Paso 6. Probar la aplicación de Docker con el host local de Docker

Este paso varía en función de lo que haga la aplicación. En una aplicación web de .NET Core sencilla implementada como un único contenedor o servicio, puede acceder al servicio si abre un explorador en el host de Docker y va a ese sitio, como se muestra en la figura 5-13. (Si la configuración del Dockerfile asigna el contenedor a un puerto del host distinto al 80, incluya el puerto del host en la dirección URL).

![Ejemplo de prueba de la aplicación de Docker en local mediante localhost](./media/image18.png)

**Figura 5-13**. Ejemplo de prueba de la aplicación de Docker en local mediante localhost

Si localhost no apunta a la IP del host de Docker (de forma predeterminada, al usar Docker CE, debería hacerlo), para ir al servicio, use la dirección IP de la tarjeta de red del equipo.

Esta dirección URL en el explorador usa el puerto 80 para el ejemplo de contenedor determinado que se está analizando. Pero, internamente, las solicitudes se redirigen al puerto 5000, porque así es como se ha implementado con el comando docker run, como se ha explicado en el paso anterior.

También puede probar la aplicación con la CURL del terminal, como se muestra en la figura 5-14. En una instalación de Docker en Windows, el valor predeterminado de la IP del host de Docker es siempre 10.0.75.1, además de la dirección IP real del equipo.

![Ejemplo de prueba de la aplicación de Docker en local mediante CURL](./media/image19.png)

**Figura 5-14**. Ejemplo de prueba de la aplicación de Docker en local mediante CURL

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a>Prueba y depuración de contenedores con Visual Studio 2017

Al ejecutar y depurar los contenedores con Visual Studio 2017, puede depurar la aplicación de .NET prácticamente de la misma manera que como lo haría al ejecutar sin contenedores.

### <a name="testing-and-debugging-without-visual-studio"></a>Pruebas y depuración sin Visual Studio

Si está desarrollando con el enfoque de editor/CLI, la depuración de contenedores es más difícil y se prefiere hacer mediante la generación de seguimientos.

### <a name="additional-resources"></a>Recursos adicionales

- **Depuración de aplicaciones en un contenedor de Docker local**

   [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

- **Steve Lasker. Compilar, depurar e implementar aplicaciones ASP.NET Core con Docker.** Video.

   [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a>Flujo de trabajo simplificado al desarrollar contenedores con Visual Studio

En la práctica, el flujo de trabajo cuando se usa Visual Studio es mucho más sencillo que si se usa el enfoque de editor/CLI. La mayoría de los pasos que necesita Docker relacionados con el Dockerfile y los archivos docker-compose.yml están ocultos o se han simplificado con Visual Studio, como se muestra en la figura 5-15.

![Flujo de trabajo simplificado al desarrollar con Visual Studio](./media/image20.png)

**Figura 5-15**. Flujo de trabajo simplificado al desarrollar con Visual Studio

Además, debe realizar el paso 2 (agregar compatibilidad con Docker a los proyectos) una sola vez. Por lo tanto, el flujo de trabajo es similar a las tareas de desarrollo habituales cuando se usa .NET para cualquier otro desarrollo. Debe saber qué está sucediendo en segundo plano (el proceso de compilación de imágenes, qué imágenes base usa, la implementación de contenedores, etc.) y, a veces, también debe editar el Dockerfile o el archivo docker-compose.yml para personalizar comportamientos. Pero con Visual Studio se simplifica enormemente la mayor parte del trabajo, lo que mejora mucho la productividad.

### <a name="additional-resources"></a>Recursos adicionales

- **Steve Lasker. .NET Docker Development with Visual Studio 2017** (Desarrollo de Docker de .NET con Visual Studio 2017, de Steve Lasker)

   [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)

- **Jeffrey T. Fritz. Put a .NET Core App in a Container with the new Docker Tools for Visual Studio** (Colocación de una aplicación de .NET Core en un contenedor con las nuevas Herramientas de Docker para Visual Studio)

   [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a>Uso de comandos de PowerShell en un Dockerfile para configurar contenedores de Windows

Los [contenedores de Windows](/virtualization/windowscontainers/about/) permiten convertir las aplicaciones de Windows existentes en imágenes de Docker e implementarlas con las mismas herramientas que el resto del ecosistema de Docker. Para usar contenedores de Windows, ejecute comandos de PowerShell en el Dockerfile, como se muestra en el ejemplo siguiente:

```Dockerfile
FROM microsoft/windowsservercore

LABEL Description="IIS" Vendor="Microsoft" Version="10"

RUN powershell -Command Add-WindowsFeature Web-Server

CMD [ "ping", "localhost", "-t" ]
```

En este caso se usa una imagen base de Windows Server Core (el valor FROM) y se instala IIS con un comando de PowerShell (el valor RUN). Del mismo modo, también se pueden usar comandos de PowerShell para configurar otros componentes como ASP.NET 4.x, .NET 4.6 o cualquier otro software de Windows. Por ejemplo, el siguiente comando en un Dockerfile configura ASP.NET 4.5:

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a>Recursos adicionales

- **aspnet-docker/Dockerfile.** Example Powershell commands to run from dockerfiles to include Windows features (Comandos de PowerShell de ejemplo para ejecutar desde Dockerfiles a fin de incluir características de Windows).

   [*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](../multi-container-microservice-net-applications/index.md)
