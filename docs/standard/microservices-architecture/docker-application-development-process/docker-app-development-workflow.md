---
title: Flujo de trabajo de desarrollo para aplicaciones de Docker
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Flujo de trabajo de desarrollo para aplicaciones de Docker
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 5a53aee4261a5a0bfc25b3520c50cf505b84f287
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="development-workflow-for-docker-apps"></a>Flujo de trabajo de desarrollo para aplicaciones de Docker

El ciclo de vida de desarrollo de aplicación se inicia en el equipo del desarrollador, donde el desarrollador de códigos de la aplicación utilizando el lenguaje que prefieran y comprueba de forma local. Independientemente del lenguaje, marco de trabajo y la plataforma que elige el desarrollador, con este flujo de trabajo, el desarrollador es siempre desarrollar y probar contenedores de Docker, pero hacerlo localmente.

Cada contenedor (una instancia de una imagen de Docker) incluye los siguientes componentes:

-   Una selección de sistema operativo (por ejemplo, una distribución de Linux, Windows Nano Server o Windows Server Core).

-   Archivos agregados por el programador (archivos binarios de aplicación, etcetera).

-   Información de configuración (configuración de entorno y las dependencias).

## <a name="workflow-for-developing-docker-container-based-applications"></a>Flujo de trabajo para desarrollar aplicaciones basadas en contenedor de Docker

Esta sección se describe la *bucle interno* flujo de trabajo de desarrollo para aplicaciones basadas en contenedor de Docker. El flujo de trabajo de bucle interna significa no está teniendo en cuenta el flujo de trabajo de DevOps más amplio y solo se centra en el trabajo de desarrollo realizado en el equipo del desarrollador. Los pasos iniciales para configurar el entorno no se incluyen, ya que los que se realizan solo una vez.

Una aplicación se compone de sus propios servicios, además de bibliotecas adicionales (dependencias). Éstos son los pasos básicos que normalmente utilizan al compilar una aplicación de Docker, como se muestra en la figura 5-1.

![](./media/image1.png)

**Figura 5-1.** Flujo de trabajo de paso a paso para el desarrollo de aplicaciones en contenedores de Docker

En esta guía, se detalla todo este proceso y se explica cada paso importante centrándose en un entorno de Visual Studio.

Cuando se usa un enfoque de desarrollo de editor/CLI (por ejemplo, código de Visual Studio más CLI de Docker en macOS o Windows), debe conocer cada paso, generalmente con más detalle que si está utilizando Visual Studio. Para obtener más información acerca de cómo trabajar en un entorno de CLI, consulte el libro electrónico [ciclo de vida de aplicaciones en contenedores de Docker con Microsoft Platforms y herramientas](http://aka.ms/dockerlifecycleebook/).

Cuando se usa Visual Studio 2015 o Visual Studio de 2017, muchos de estos pasos se administran automáticamente, lo cual mejora considerablemente su productividad. Esto es especialmente cierto cuando usa Visual Studio de 2017 y contenedor varias aplicaciones de destino. Por ejemplo, con un solo clic, Visual Studio agrega el archivo Dockerfile y docker compose.yml a los proyectos con la configuración de la aplicación. Al ejecutar la aplicación en Visual Studio, crea la imagen de Docker y se ejecuta la aplicación contenedora múltiples directamente en Docker; incluso permite depurar varios contenedores al mismo tiempo. Estas características aumentará la velocidad de desarrollo.

Sin embargo, solo porque Visual Studio realiza estos pasos automática no significa que no es necesario saber lo que ocurre en debajo con Docker. Por lo tanto, en las indicaciones siguientes, se detalla cada paso.

![](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a>Paso 1. Comienza a escribir código y crear la aplicación inicial o la línea de base de servicio

Desarrollar una aplicación de Docker es similar a la manera de que desarrollar una aplicación sin Docker. La diferencia es que al desarrollar para Docker, va a implementar y probar su aplicación o servicios que se ejecutan dentro de los contenedores de Docker en su entorno local. El contenedor puede ser un contenedor de Linux o un contenedor de Windows.

### <a name="set-up-your-local-environment-with-visual-studio"></a>Configurar el entorno local con Visual Studio

Para comenzar, asegúrese de que tiene [Docker Community Edition (CE)](https://www.docker.com/community-edition) para Windows instalado, como se explica en las siguientes instrucciones:

[Introducción a Docker CE para Windows](https://docs.docker.com/docker-for-windows/)

Además, necesitará Visual Studio de 2017 instalado. Esto es preferible sobre Visual Studio 2015 con Visual Studio Tools para Docker complemento, porque Visual Studio de 2017 ha avanzado más compatibilidad con Docker, como compatibilidad para depurar contenedores. 2017 de Visual Studio incluye las herramientas de Docker si ha seleccionado la **.NET Core y Docker** carga de trabajo durante la instalación, tal como se muestra en la figura 5-2.

![](./media/image3.png)

**Figura 5-2**. Al seleccionar la **.NET Core y Docker** carga de trabajo durante la instalación de Visual Studio de 2017

Puede comenzar a codificar la aplicación en .NET sin formato (normalmente en .NET Core si va a utilizar los contenedores) incluso antes de habilitar a Docker en la aplicación e implementar y probar en Docker. Sin embargo, se recomienda que empezar a trabajar en Docker tan pronto como sea posible, ya que será el entorno real y se pueden detectar los problemas tan pronto como sea posible. Esto se recomienda porque Visual Studio resulta muy sencillo trabajar con Docker que casi parece transparente: el mejor ejemplo al depurar aplicaciones de contenedor múltiples desde Visual Studio.

### <a name="additional-resources"></a>Recursos adicionales

-   **Introducción a Docker CE para Windows**
    [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)

-   **Visual Studio de 2017**
    [*https://www.visualstudio.com/vs/visual-studio-2017/*](https://www.visualstudio.com/vs/visual-studio-2017/)

![](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a>Paso 2. Cree un Dockerfile relacionados con una imagen base existente de .NET

Necesita un Dockerfile para cada imagen personalizada que desee crear; También necesita un Dockerfile para cada contenedor para su implementación, tanto si implementa automáticamente en Visual Studio o manualmente mediante la CLI de Docker (ejecución de docker y docker-crear comandos). Si la aplicación contiene un único servicio personalizado, es necesario un Dockerfile único. Si la aplicación contiene varios servicios (como en una arquitectura microservicios), necesita un Dockerfile para cada servicio.

El Dockerfile se coloca en la carpeta raíz de la aplicación o servicio. Contiene los comandos que indican cómo configurar y ejecutar la aplicación o servicio en un contenedor de Docker. Manualmente, puede crear un archivo Dockerfile en el código y agregarlo al proyecto junto con sus dependencias de .NET.

En Visual Studio y sus herramientas de Docker, esta tarea requiere solo unos pocos clics del mouse. Cuando crea un nuevo proyecto en Visual Studio de 2017, hay una opción denominada **compatibilidad con el contenedor habilitar (Docker)**, tal y como se muestra en la figura 5-3.

![](./media/image5.png)

**Figura 5-3**. Habilitar la compatibilidad de Docker cuando se crea un nuevo proyecto en Visual Studio de 2017

También puede habilitar la compatibilidad de Docker en un proyecto nuevo o existente haciendo clic en el archivo de proyecto en Visual Studio y seleccionando la opción **proyecto compatible con el complemento Docker**, tal y como se muestra en la figura 5-4.

![](./media/image6.png)

**Figura 5-4**. Habilitar la compatibilidad de Docker en un proyecto existente de Visual Studio de 2017

Esta acción en un proyecto (por ejemplo, una aplicación Web ASP.NET o servicio de API Web), agrega un archivo Dockerfile al proyecto con la configuración necesaria. También se agrega un archivo de compose.yml de docker para la solución completa. En las siguientes secciones, se describe la información que se pasa a cada uno de esos archivos. Visual Studio puede hacer este trabajo por usted, pero resulta útil para comprender qué implica un Dockerfile.

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a>Opción A: crear un proyecto mediante una imagen de Docker .NET oficial existente

Suele generar una imagen personalizada para el contenedor de encima de una imagen base que se puede obtener desde un repositorio oficial en el [Docker Hub](https://hub.docker.com/) registro. Eso es precisamente lo que sucede en segundo plano cuando se habilita la compatibilidad con Docker en Visual Studio. El Dockerfile utilizará una imagen de aspnetcore existente.

Anteriormente se explica qué imágenes de Docker y repositorios puede usar, según el marco y el sistema operativo que ha elegido. Por ejemplo, si desea usar ASP.NET Core (Linux o Windows), la imagen utilizada es microsoft / aspnetcore:2.0. Por lo tanto, debe especificar qué imagen de Docker base que se utilizará para el contenedor. Hacerlo mediante la adición de microsoft / aspnetcore:2.0 en el Dockerfile. Esto se realizará automáticamente por Visual Studio, pero si fuera a actualizar la versión, actualice este valor.

El uso de un repositorio de imágenes .NET oficial de Docker Hub con un número de versión, se garantiza que las mismas características de lenguaje están disponibles en todos los equipos (incluido el desarrollo, pruebas y producción).

En el ejemplo siguiente se muestra un ejemplo de Dockerfile para un contenedor de ASP.NET Core.

```
FROM microsoft/aspnetcore:2.0
  
ARG source
  
WORKDIR /app
  
EXPOSE 80
  
COPY ${source:-obj/Docker/publish} .
  
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

En este caso, el contenedor se basa en la versión 2.0 de la imagen de Docker de núcleo de ASP.NET oficial (Multi-arch para Linux y Windows). Esta es la configuración `FROM microsoft/aspnetcore:2.0`. (Para obtener más información acerca de esta imagen base, vea la [imagen de Docker de ASP.NET Core](https://hub.docker.com/r/microsoft/aspnetcore/) página y la [imagen de Docker de .NET Core](https://hub.docker.com/r/microsoft/dotnet/) página.) En el Dockerfile, también debe indicar a Docker para que escuche en el puerto TCP que se va a usar en tiempo de ejecución (en este caso, el puerto 80, tal y como se configura con la opción de exponer).

Puede especificar opciones de configuración adicionales en el Dockerfile, dependiendo del lenguaje y framework que está utilizando. Por ejemplo, la línea de punto de entrada con \["dotnet", "MySingleContainerWebApp.dll"\] indica Docker para ejecutar una aplicación .NET Core. Si usas la CLI de núcleo de .NET (dotnet CLI) y el SDK para compilar y ejecutar la aplicación. NET, esta configuración sería diferente. La conclusión es que la línea de punto de entrada y otros valores de configuración pueden variar según la plataforma y el idioma que elija para su aplicación.

### <a name="additional-resources"></a>Recursos adicionales

-   **Creación de imágenes de Docker para las aplicaciones de .NET Core**
    [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images)

-   **Crear su propia imagen**. En la documentación oficial de Docker.
    [*https://docs.docker.com/Engine/tutorials/dockerimages/*](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a>Uso de imagen arch varios repositorios

Un repositorio único puede contener las variantes de la plataforma, como una imagen de Linux y una imagen de Windows. Esta característica permite a los proveedores como Microsoft (creadores de imagen base) crear un repositorio único para abarcar varias plataformas (es decir, Linux y Windows). Por ejemplo, el [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) repositorio disponible en el registro de Docker Hub proporciona compatibilidad con Linux y Windows Nano Server usando el mismo nombre de repositorio.

Si especifica una etiqueta, como destino una plataforma que sea explícita, como en los casos siguientes:

-   **Microsoft/aspnetcore:2.0.0-jessie**

        .NET Core 2.0 runtime-only on Linux 

-   **Microsoft/aspnetcore:2.0.0-nanoserver**

        .NET Core 2.0 runtime-only on Windows Nano Server

Sin embargo y esto es nuevo desde mediados de 2017, si especifica el mismo nombre de imagen, incluso con la misma etiqueta, las nuevas imágenes varias arch (por ejemplo, la imagen de aspnetcore que admite varios arch) utilizará la versión de Linux o Windows según el host Docker SO que se va a implementar , como se muestra en el ejemplo siguiente:

-   **Microsoft / aspnetcore:2.0**

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

Este modo, cuando se extraen de una imagen desde un host de Windows, extraerá la variante de Windows y extraer el mismo nombre de imagen de un host Linux extraerá la variante de Linux.

### <a name="option-b-creating-your-base-image-from-scratch"></a>Opción B: crear la imagen base desde el principio

Puede crear su propia imagen de base de Docker desde el principio. Este escenario no se recomienda para un usuario que se está iniciando con Docker, pero si desea establecer los bits específicos de su propia imagen base, puede hacerlo.

### <a name="additional-resources"></a>Recursos adicionales

-   **Arch varias imágenes de .NET Core**.
https://github.com/dotnet/Announcements/issues/14 
-   **Crear una imagen base**. Documentación oficial de Docker.
    [*https://docs.docker.com/Engine/userguide/ENG-Image/BaseImages/*](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a>Paso 3. Crear las imágenes del Docker personalizadas y lo inserte la aplicación o servicio en ellas

Para cada servicio en la aplicación, debe crear una imagen relacionada. Si la aplicación está formada por un único servicio o aplicación web, solo tiene una sola imagen.

Tenga en cuenta que las imágenes de Docker se generan automáticamente para usted en Visual Studio. Los pasos siguientes sólo son necesarios para el flujo de trabajo de editor/CLI y la explicación de por motivos de claridad sobre lo que ocurre debajo.

Como desarrollador, debe desarrollar y probar localmente hasta que pulse una completa de características o cambiar en el sistema de control de código fuente (por ejemplo, para GitHub). Esto significa que necesita para crear las imágenes de Docker y la implementación de contenedores en un host Docker local (Windows o Linux VM) y ejecutar, probar y depurar en esos contenedores locales.

Para crear una imagen personalizada en su entorno local mediante la CLI de Docker y el Dockerfile, puede usar el comando de compilación de docker, como se muestra en la figura 5-5.

![](./media/image8.png)

**Figura 5-5**. Crear una imagen personalizada de Docker

Si lo desea, en lugar de ejecutar directamente la compilación de docker desde la carpeta del proyecto, puede generar primero una carpeta que se pueden implementar con las bibliotecas .NET necesarias y los archivos binarios ejecutando dotnet publicación y, a continuación, use el comando de compilación de docker.

Esto creará una imagen de Docker con el nombre cesardl/netcore-webapi-microservicio-docker: primero. En este caso,: en primer lugar es una etiqueta que representa una versión específica. Puede repetir este paso para cada imagen personalizada que se debe crear para la aplicación de Docker compuesta.

Cuando se realiza una aplicación de varios contenedores (es decir, es una aplicación de contenedor de varios), también puede usar el docker redactar una--comando de compilación para generar todas las imágenes relacionadas con un solo comando mediante el uso de los metadatos expuestos en relacionado archivos de compose.yml de docker.

Se pueden encontrar las imágenes existentes en el repositorio local mediante el docker comandos de imágenes, tal como se muestra en la figura 5-6.

![](./media/image9.png)

**Figura 5-6.** Visualización de imágenes existentes mediante el comando de imágenes de docker

### <a name="creating-docker-images-with-visual-studio"></a>Creación de imágenes de Docker con Visual Studio

Cuando se utiliza Visual Studio para crear un proyecto con el soporte técnico de Docker, no cree explícitamente una imagen. En su lugar, la imagen se crea automáticamente cuando presione F5 y ejecute el servicio o aplicación dockerized. Este paso es automático en Visual Studio y no verá ocurrir, pero es importante que sepa lo que está ocurriendo en debajo.

![](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a>Paso 4. Definir los servicios en docker compose.yml al compilar una aplicación de Docker de contenedor múltiples

El [docker compose.yml](https://docs.docker.com/compose/compose-file/) archivo le permite definir un conjunto de servicios relacionados que desee implementar como una aplicación compuesta con comandos de implementación.

Para usar un archivo de compose.yml de docker, debe crear el archivo de la ventana principal o la carpeta raíz de la solución, con contenido parecidos a los en el ejemplo siguiente:

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

Tenga en cuenta que este archivo compose.yml docker es una versión simplificada y combinada. Contiene datos de configuración estática para cada contenedor (por ejemplo, el nombre de la imagen personalizada), que siempre se aplica, junto con información de configuración que podría depender en el entorno de implementación, como la cadena de conexión. En secciones posteriores, obtendrá información sobre cómo puede dividir la configuración de docker compose.yml en varios docker-crear archivos y valores de invalidación según el tipo de entorno y la ejecución (debug o release).

En el ejemplo de archivo de docker compose.yml define cinco servicios: el servicio de webmvc (una aplicación web), dos microservicios (catalog.api y ordering.api) y datos de un contenedor de origen, sql.data, en función de SQL Server para Linux que se ejecuta como un contenedor. Cada servicio se implementa como un contenedor, por lo que es necesaria para cada una imagen de Docker.

El archivo docker compose.yml especifica no solo se usan los contenedores, pero ¿cómo se configuran por separado. Por ejemplo, el webmvc definición de contenedor en el archivo .yml:

-   Usa un pregenerado compras o imagen de web: más reciente. Sin embargo, también puede configurar la imagen que se crea como parte de la redacción de docker la ejecución con una configuración adicional basada en una compilación: sección en el archivo docker-compose.

-   Inicializa dos variables de entorno (dirección URL de catálogo y OrderingUrl).

-   Reenvía el puerto 80 en el contenedor para el puerto 80 externo en el equipo host expuesto.

-   Vincula la aplicación web para el catálogo y el orden de servicio con la función\_en configuración. Esto hace que el servicio debe esperar hasta que se inician los servicios.

Cuando se incluye información sobre cómo implementar microservicios y contenedor varias aplicaciones, examinaremos el archivo compose.yml de docker en una sección posterior.

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a>Trabajar con docker-compose.yml en Visual Studio de 2017

Cuando se agrega compatibilidad con soluciones de Docker a un proyecto de servicio en una solución de Visual Studio, tal como se muestra en la figura 5-7, Visual Studio agrega un archivo Dockerfile al proyecto y agrega una sección de servicio (proyecto) en la solución con los archivos de compose.yml de docker. Es una forma sencilla de empezar a crear la solución de varios contenedores. A continuación, puede abrir los archivos de docker compose.yml y actualizarlas con características adicionales.

![](./media/image6.png)

**Figura 5-7**. Agregar compatibilidad de Docker en Visual Studio de 2017 haciendo clic en un proyecto de ASP.NET Core

Agregar compatibilidad con Docker en Visual Studio no solo el Dockerfile agrega al proyecto, pero agrega la información de configuración a varios archivos de compose.yml de docker global que se establecen en el nivel de solución.

Después de agregar compatibilidad de Docker a la solución en Visual Studio, también verá un nuevo nodo (en el archivo de proyecto docker compose.dcproj) en el Explorador de soluciones que contiene los archivos de compose.yml de docker agregada, como se muestra en la figura 5-8.

![](./media/image11.PNG)

**Figura 5-8**. El **crear docker** nodo de árbol que se agregó en el Explorador de soluciones de Visual Studio de 2017

Puede implementar una aplicación de contenedor de varios con un archivo único de compose.yml de docker mediante el crear docker comando. Sin embargo, Visual Studio agrega un grupo de ellos por lo que puede invalidar valores dependiendo del entorno (desarrollo frente a producción) y la ejecución de tipo (versión en comparación con depuración). Esta capacidad se explican en secciones posteriores.

![](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a>Paso 5. Compilar y ejecutar la aplicación de Docker

Si la aplicación solo tiene un único contenedor, puede ejecutar mediante la implementación en el host Docker (virtual o servidor físico). Sin embargo, si la aplicación contiene varios servicios, se puede implementar como una aplicación compuesta, ya sea mediante un solo comando CLI (docker-constituyen una), o con Visual Studio, que va a utilizar ese comando en segundo plano. Echemos un vistazo a las distintas opciones.

### <a name="option-a-running-a-single-container-with-docker-cli"></a>Opción A: ejecutando un contenedor único con CLI de Docker

Puede ejecutar un contenedor de Docker mediante el comando docker run, como se muestra en la figura 5-9:

```
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![](./media/image13.png)

**Figura 5-9**. Ejecución de un contenedor de Docker mediante el comando docker run

En este caso, el comando enlaza el puerto interno 5000 del contenedor al puerto 80 de la máquina host. Esto significa que el host está escuchando en el puerto 80 y reenvío al puerto 5000 en el contenedor.

### <a name="option-b-running-a-multi-container-application"></a>Opción B: ejecuta una aplicación de contenedor múltiples

En la mayoría de los escenarios de empresa, una aplicación de Docker podría estar compuesta por varios servicios, lo que significa que debe ejecutar una aplicación de contenedor de varios, como se muestra en la figura 5-10.

![](./media/image14.png)

**Figura 5-10**. Máquina virtual con contenedores de Docker implementado

#### <a name="running-a-multi-container-application-with-the-docker-cli"></a>Ejecuta una aplicación de contenedor múltiples con la CLI de Docker

Para ejecutar una aplicación de contenedor múltiples con la CLI de Docker, puede ejecutar el docker-crear comando. Este archivo usa el compose.yml docker de comandos que haya en el nivel de solución para implementar una aplicación de contenedor de varios. Figura 5-11 muestra los resultados cuando se ejecuta el comando desde el directorio principal del proyecto, que contiene el archivo compose.yml docker.

![](./media/image15.png)

**Figura 5-11**. En el ejemplo se produce cuando se ejecuta la redacción de docker comando

Después de la docker-crear la ejecución del comando, la aplicación y sus contenedores relacionados se implementan en el host Docker, como se muestra en la representación de la máquina virtual en la figura 5-10.

#### <a name="running-and-debugging-a-multi-container-application-with-visual-studio"></a>Ejecutar y depurar una aplicación de contenedor múltiples con Visual Studio 

Ejecuta una aplicación de contenedor múltiples mediante 2017 de Visual Studio no se puede obtener más sencilla. Solo no puede ejecutar la aplicación contenedora múltiples, pero es posible depurar todos sus contenedores directamente desde Visual Studio estableciendo puntos de interrupción normales.

Como se mencionó antes, cada vez que agregue compatibilidad con soluciones de Docker a un proyecto dentro de una solución, ese proyecto se configura en el archivo global (nivel de solución) docker-compose.yml, que le permite ejecutar o depurar la solución completa a la vez. Visual Studio inicia un contenedor para cada proyecto que tiene habilitada la compatibilidad de solución de Docker y realizar todos los pasos internos por usted (dotnet publica, compilación de docker, etcetera.).

La cuestión importante aquí es que, como se muestra en la figura 5-12, en Visual Studio de 2017 hay más **Docker** comando para la acción de tecla F5. Esta opción le permite ejecutar o depurar una aplicación de múltiples contenedor mediante la ejecución de todos los contenedores que se definen en los archivos de compose.yml de docker en el nivel de solución. La capacidad de depurar las soluciones de varios contenedores significa que puede establecer varios puntos de interrupción, cada punto de interrupción en un proyecto diferente (contenedor) y, durante la depuración de Visual Studio se detendrá en los puntos de interrupción definidos en distintos proyectos y en ejecución en contenedores diferentes.

![](./media/image16.png)

**Figura 5-12**. Contenedor de varias aplicaciones en ejecución en Visual Studio de 2017

### <a name="additional-resources"></a>Recursos adicionales

-   **Implementar un contenedor ASP.NET en un host remoto de Docker**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a>Una nota acerca de cómo probar e implementar con orchestrators

El docker redactar una y comandos de docker ejecutar (o se ejecuta y depuración de los contenedores en Visual Studio) son adecuados para probar los contenedores en el entorno de desarrollo. Pero no debería usar este enfoque si se dirige a los clústeres de Docker y orchestrators como Docker Swarm, Mesosphere DC/OS o Kubernetes. Si está usando un clúster como [Docker Swarm modo](https://docs.docker.com/engine/swarm/) (disponible en Docker CE para Windows y Mac desde la versión 1.12), debe implementar y probar con comandos adicionales, como [crear servicio docker](https://docs.docker.com/engine/reference/commandline/service_create/) para Servicios de inicio único. Si va a implementar una aplicación formada por varios contenedores, use [docker crear paquete](https://docs.docker.com/compose/reference/bundle/) y [docker implementar myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) para implementar la aplicación compuesta como un *pila*. Para obtener más información, consulte la entrada de blog [Introducción a paquetes de aplicaciones experimentales distribuidos](https://blog.docker.com/2016/06/docker-app-bundle/) en la documentación de Docker. en el sitio de Docker.

Para [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) y [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) usaría también secuencias de comandos y comandos de implementación diferentes.

![](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a>Paso 6. Probar la aplicación de Docker con el host local de Docker

Este paso variarán dependiendo de lo que está haciendo la aplicación. En una aplicación .NET Core Web simple que se implementa como un único contenedor o un servicio, puede tener acceso al servicio, abra un explorador en el host Docker y vaya a ese sitio tal como se muestra en la figura 5-13. (Si la configuración en el Dockerfile asigna el contenedor a un puerto en el host que es un valor distinto de 80, incluya la entrada de host en la URL.)

![](./media/image18.png)

**Figura 5-13**. Ejemplo de probar la aplicación de Docker localmente mediante localhost

Dirección IP del host si localhost no apunta a la Docker (de forma predeterminada, al usar Docker CE, que debería), para navegar a su servicio, utilice la dirección IP de la tarjeta de red de su equipo.

Tenga en cuenta que esta dirección URL en el explorador usa el puerto 80 para el ejemplo de contenedor determinado que se analice. Sin embargo, internamente las solicitudes se se redirige al puerto 5000, porque ese era cómo se implementó con el comando docker run, tal como se describe en el paso anterior.

También puede probar la aplicación con el doblez desde el terminal, tal como se muestra en la figura 5-14. En una instalación de Docker en Windows, el valor predeterminado de IP de Host de Docker es siempre 10.0.75.1 Además de la dirección IP real de su equipo.

![](./media/image19.png)

**Figura 5-14**. Ejemplo de probar la aplicación de Docker localmente mediante curl

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a>Probar y depurar contenedores con Visual Studio de 2017

Cuando se ejecutan y depuran los contenedores con 2017 de Visual Studio, puede depurar la aplicación de .NET de la misma manera como lo haría cuando se ejecuta sin contenedores.

### <a name="testing-and-debugging-without-visual-studio"></a>Probar y depurar sin Visual Studio

Si está desarrollando usando el enfoque de editor/CLI, contenedores de depuración es más difícil y que va a depurar mediante la generación de seguimientos.

### <a name="additional-resources"></a>Recursos adicionales

-   **Depuración de aplicaciones en un contenedor de Docker local**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

-   **Steve Lasker. Compilar, depurar, implementar aplicaciones de ASP.NET Core con Docker.** Vídeo.
    [*https://channel9.msdn.com/events/Visual-Studio/Visual-Studio-2017-Launch/T115*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a>Flujo de trabajo simplificada al desarrollar contenedores con Visual Studio

De hecho, el flujo de trabajo cuando se usa Visual Studio es mucho más sencilla que si se usa el enfoque de editor/CLI. La mayoría de los pasos necesarios para Docker relacionadas con el Dockerfile y docker compose.yml archivos se ocultan o se ha simplificado con Visual Studio, tal como se muestra en la figura 5-15.

![](./media/image20.png)

**Figura 5-15**. Flujo de trabajo simplificada al desarrollar con Visual Studio

Además, debe realizar el paso 2 (agregar compatibilidad de Docker a los proyectos de) una sola vez. Por lo tanto, el flujo de trabajo es similar a las tareas de desarrollo habitual cuando se usa .NET para otros entornos de desarrollo. Debe saber qué está sucediendo en segundo plano (el proceso de generación de imagen, qué imágenes base que usa, la implementación de contenedores, etc.) y a veces que también debe editar el archivo Dockerfile o compose.yml docker para personalizar los comportamientos. Pero se simplifica enormemente la mayoría del trabajo mediante Visual Studio, que se hace mucho más productivo.

### <a name="additional-resources"></a>Recursos adicionales

-   **Steve Lasker. Desarrollo de docker de .NET con Visual Studio de 2017**
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)

-   **Jeffrey T. Fritz. Coloque una aplicación básica de .NET en un contenedor con las nuevas herramientas de Docker para Visual Studio**
    [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a>Usar comandos de PowerShell en un archivo Dockerfile para configurar los contenedores de Windows 

[Contenedores de Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) que pueda convertir las aplicaciones de Windows existentes en las imágenes de Docker e implementarlas con las mismas herramientas que el resto del ecosistema de Docker. Para utilizar los contenedores de Windows, ejecute comandos de PowerShell en el Dockerfile, como se muestra en el ejemplo siguiente:

```
FROM microsoft/windowsservercore
  
LABEL Description="IIS" Vendor="Microsoft" Version="10"
  
RUN powershell -Command Add-WindowsFeature Web-Server
  
CMD [ "ping", "localhost", "-t" ]
```

En este caso, estamos usando una imagen base de Windows Server Core (el valor FROM) y la instalación de IIS con un comando de PowerShell (el valor de ejecución). De forma similar, también puede usar comandos de PowerShell para configurar los componentes adicionales como ASP.NET 4.x, .NET 4.6 o cualquier otro software de Windows. Por ejemplo, el siguiente comando en un archivo Dockerfile configura ASP.NET 4.5:

```
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a>Recursos adicionales

-   **ASPNET-docker/Dockerfile.** Comandos de Powershell de ejemplo para ejecutar desde dockerfiles para incluir características de Windows.
    [*https://github.com/Microsoft/ASPNET-docker/BLOB/Master/4.6.2/Dockerfile*](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
[Anterior] (index.md) [siguiente] (.. / net-core-single-containers-linux-windows-server-hosts/index.md)
