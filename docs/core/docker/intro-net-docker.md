---
title: "Introducción a .NET y Docker"
description: "Descripción Docker y .NET Core"
keywords: .NET, .NET Core, Docker
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
manager: wpickett
ms.custom: mvc
ms.openlocfilehash: 1c9ce7a008c86d1c245ce8b7d616e05fcb3d4bbc
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="introduction-to-net-and-docker"></a>Introducción a .NET y Docker

 Este artículo proporciona una introducción e información general conceptual de trabajar con .NET en Docker. 

## <a name="docker-packaging-your-apps-to-deploy-and-run-anywhere"></a>Docker: Empaquetar las aplicaciones existentes para implementar y ejecutar desde cualquier lugar

[Docker](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-defined) es una plataforma abierta que permite a los desarrolladores y administradores de compilación [imágenes](https://docs.docker.com/glossary/?term=image), distribuir y ejecutar aplicaciones distribuidas en un entorno con aislamiento flexible denominado un [contenedor](https://www.docker.com/what-container). Este enfoque permite la administración de ciclo de vida de aplicación eficaz entre el desarrollo, preguntas y respuestas y entornos de producción.
 
El [plataforma Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) utiliza la [motor de Docker](https://docs.docker.com/engine/docker-overview/#docker-engine) para generar y empaquetar aplicaciones como rápidamente [imágenes de Docker](https://docs.docker.com/glossary/?term=image) creado con los archivos escritos el [Dockerfile ](https://docs.docker.com/glossary/?term=Dockerfile) formato que, a continuación, implementa y ejecuta en un [superpuesto contenedor](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).

Puede crear sus propios [superpuesto imágenes](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) como dockerfiles o utilizar existentes desde un [registro](https://docs.docker.com/glossary/?term=registry), como [Docker Hub](https://docs.docker.com/glossary/?term=Docker%20Hub).

El [relación entre los contenedores de Docker, imágenes y registros](https://docs.microsoft.com/dotnet/standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries) es un concepto importante cuando [en contenedores diseñar y compilar las aplicaciones o microservicios](https://docs.microsoft.com/dotnet/standard/microservices-architecture/architect-microservice-container-applications/). Este enfoque reduce en gran medida el tiempo entre el desarrollo e implementación.

### <a name="further-reading-and-watching"></a>Información adicional (y ver)

* [Contenedores basados en Windows: desarrollo de aplicaciones modernas con control de nivel empresarial.](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be)
* [Introducción a docker](https://docs.docker.com/engine/docker-overview/)
* [Dockerfile en contenedores de Windows](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [Procedimientos recomendados para escribir Dockerfiles](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)
* [Creación de imágenes de Docker para las aplicaciones de .NET Core](../docker/building-net-docker-images.md)


### <a name="getting-net-docker-images"></a>Obtener imágenes de Docker de .NET

Las imágenes de Docker oficial de .NET se crearon y optimizaron Microsoft. Están disponibles públicamente en los repositorios de Microsoft en Docker Hub. Cada repositorio puede contener varias imágenes, dependiendo de las versiones de .NET y en versiones de sistema operativo. Repositorios de imagen mayoría proporcionan etiquetado amplia para ayudarle a seleccionar una versión de un marco concreto y un sistema operativo (distribución de Linux o versión de Windows).

## <a name="scenario-based-guidance"></a>Escenario de asistencia telefónica

El intento de Microsoft de los repositorios de .NET es tener repositorios granular y tiene el foco, que representan un escenario específico o carga de trabajo.

El `microsoft/aspnetcore` imágenes se optimizan para las aplicaciones de ASP.NET Core en Docker, por lo que pueden empezar a contenedores con mayor rapidez.

Las imágenes de .NET Core (`microsoft/dotnet`) están diseñados para las aplicaciones de consola basadas en .NET Core. Por ejemplo, procesos por lotes, los trabajos Web de Azure y otros escenarios de consola deben utilizar imágenes optimizadas de .NET Core.

El escenario más evidente horizontal para el uso de las aplicaciones de Docker y .NET es para la implementación de producción y de hospedaje. Esto resulta que producción es un caso y los otros son igualmente útiles. Estos escenarios no son específicos de. NET, pero deberían aplicarse a la mayoría de las plataformas para desarrolladores.

* **Instalar baja fricción** , puede probar .NET sin una instalación local. Simplemente descargar una imagen de Docker con .NET en ella.

* **Desarrollar en un contenedor** : puede desarrollar en un entorno coherente, lo entornos de desarrollo y producción similar (evitando problemas como el estado global en equipos de desarrollador). Visual Studio Tools para Docker incluso permiten iniciar un contenedor directamente desde Visual Studio.

* **En un contenedor de prueba** , puede probar en un contenedor, lo que reduce errores debidos a entornos no está configurados correctamente u otros cambios quedan atrás desde la última prueba.

* **Compilar en un contenedor** : puede compilar código en un contenedor, evitando la necesidad de configurar correctamente las máquinas de compilación compartidos para varios entornos, pero en su lugar, se mueve a un "BYOC" (traiga su propio contenedor) enfoque.

* **Implementación en todos los entornos** , puede implementar una imagen a través de todos los entornos. Este enfoque reduce errores debido a diferencias de configuración, suele cambiar el comportamiento de la imagen a través de configuración externo (por ejemplo, variables de entorno insertado).

[Instrucciones generales](https://docs.microsoft.com/dotnet/standard/microservices-architecture/net-core-net-framework-containers/general-guidance) para decidir entre .NET Core y .NET Framework para el desarrollo de contenedor de Docker.

### <a name="common-docker-development-scenarios"></a>Escenarios comunes de desarrollo de Docker

#### <a name="net-core"></a>Núcleo de .NET

**Recursos principales de .NET**

 Elija los ejemplos de .NET Core que se ajusten a los escenarios de interés. Todas las instrucciones de ejemplo describen cómo tener como destino Windows o Linux Docker imágenes en hosts de Windows, Linux o Mac OS.

Los ejemplos usan el núcleo de .NET 2.0. Usan Docker [varias etapa compilación](https://github.com/dotnet/announcements/issues/18) y [arch varias etiquetas](https://github.com/dotnet/announcements/issues/14) según proceda.

* [Imágenes de .NET core en DockerHub](https://hub.docker.com/r/microsoft/dotnet/)

* [Dockerize una aplicación .NET Core](https://docs.docker.com/engine/examples/dotnetcore/)

* Este ejemplo de .NET Core Docker se muestra cómo [utilizará Docker en el proceso de desarrollo de .NET Core](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev). El ejemplo funciona con contenedores de Linux y Windows.

* Este ejemplo de .NET Core Docker muestra un patrón de prácticas recomendado para [crear imágenes de Docker para las aplicaciones de .NET Core para entornos de producción.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod) El ejemplo funciona con contenedores de Linux y Windows.

* Esto [ejemplo .NET Core Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) muestra un patrón de prácticas recomendado para la creación de imágenes de Docker para [independiente de las aplicaciones de .NET Core](https://docs.microsoft.com/dotnet/core/deploying/). Utilizado para el contenedor más pequeño de producción sin una de las ventajas de [compartir imágenes base entre contenedores](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/). Sin embargo, se podrían compartir capas inferiores de Docker.

#### <a name="arm32--raspberry-pi"></a>ARM32 / frambuesa Pi

* [Anuncio de .NET core en tiempo de ejecución ARM32 compilaciones](https://github.com/dotnet/announcements/issues/29)

* [ARM32 / images frambuesa Pi .NET Core en DockerHub](https://hub.docker.com/r/microsoft/dotnet/)

* [ARM32 / Pi frambuesas .NET Core Docker los ejemplos en GitHub](https://github.com/dotnet/dotnet-docker-samples#arm32--raspberry-pi)

#### <a name="net-framework"></a>.NET Framework

* [Imágenes de .NET framework en DockerHub](https://hub.docker.com/r/microsoft/dotnet-framework/) este repositorio contiene ejemplos que muestran diversas configuraciones de Docker de .NET Framework. Puede utilizar estas imágenes como base de sus propias imágenes de Docker.

**.NET framework 4.7**

[La [dotnet-framework: 4.7 ejemplo](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) muestra el uso básico "Hola a todos" de la [.NET Framework 4.7](https://docs.microsoft.com/dotnet/framework/whats-new/index#introducing-the-net-framework-47). Muestra cómo puede compilar e implementar la aplicación de confianza en el [imagen de docker de .NET Framework 4.7](https://github.com/Microsoft/dotnet-framework-docker/blob/master/4.7/Dockerfile).

**.NET framework 4.6.2**

El [dotnet-framework: 4.6.2 ejemplo](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) muestra el uso básico "Hola a todos" de la [.NET Framework 4.6.2](https://docs.microsoft.com/dotnet/framework/whats-new/index#whats-new-in-the-net-framework-462). Muestra cómo puede compilar e implementar la aplicación de confianza en el [imagen de docker de .NET Framework 4.6.2](https://github.com/Microsoft/dotnet-framework-docker/tree/master/4.6.2).

**.NET framework 3.5**

 El [dotnet-ejemplo: 3.5 framework](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) muestra el uso básico "Hola a todos" de [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker/tree/master/3.5). Muestra cómo puede compilar e implementar un proyecto de basarse en .NET Framework 3.5 en Docker.

#### <a name="aspnet-core"></a>ASP.NET Core

* [Este ejemplo de ASP.NET Core Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) muestra un patrón de prácticas recomendado para la creación de imágenes de Docker para ASP.NET Core aplicaciones de producción. El ejemplo funciona con contenedores de Linux y Windows.

* [Imágenes de ASP.NET Core en DockerHub](https://hub.docker.com/r/microsoft/aspnetcore-build/)

* [Imágenes de ASP.NET Core en GitHub](https://github.com/aspnet/aspnet-docker)

#### <a name="aspnet-framework"></a>Marco de ASP.NET 

* [Imágenes de marco de ASP.NET en DockerHub](https://hub.docker.com/r/microsoft/aspnet/)

* [Aplicación de formularios Web Forms ASP.NET en el ejemplo de .NET Framework 4.6.2](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/aspnetapp)

#### <a name="windows-communication-framework-wcf"></a>Windows Communication Framework (WCF)

* [Imágenes de Windows Communication Framework (WCF) en DockerHub](https://hub.docker.com/r/microsoft/wcf/)

* [Imágenes de Windows Communication Framework (WCF) en GitHub](https://github.com/microsoft/iis-docker)

* [Ejemplos de Docker de Windows Communication Framework (WCF) mediante completa de .NET Framework 4.6.2](https://github.com/Microsoft/wcf-docker-samples)

#### <a name="internet-information-server-iis"></a>Servidor de Internet Information Server (IIS)

* [Imágenes de Internet Information Server (IIS) en DockerHub](https://hub.docker.com/r/microsoft/iis/)

* [Imágenes de Internet Information Server (IIS) en GitHub](https://github.com/microsoft/wcf-docker)

### <a name="interact-with-other-microsoft-stack-container-images"></a>Interactuar con otras imágenes de contenedor de pila de Microsoft

#### <a name="microsoft-sql-server"></a>Microsoft SQL Server

* [Ejecutar Microsoft SQL Server para la imagen del contenedor de 2017 Linux con inicio rápido de Docker](https://docs.microsoft.com/sql/linux/quickstart-install-connect-docker)

* [Microsoft SQL Server para las imágenes de Linux en DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [Imágenes de Microsoft SQL Server para contenedores de Windows en DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows/)

* [Imágenes de Microsoft SQL Server Express Edition para contenedores de Windows en DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows-express/)

* [Imágenes de Microsoft SQL Server Developer Edition para contenedores de Windows en DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows-developer/)

#### <a name="visual-studio-team-services-vsts-agent"></a>Agente Visual Studio Team Services (VSTS)

* [Imágenes de Visual Studio Team Services (VSTS) agente en DockerHub](https://hub.docker.com/r/microsoft/vsts-agent/)

* [Imágenes de Visual Studio Team Services (VSTS) agente en GitHub](https://github.com/Microsoft/vsts-agent-docker)

#### <a name="operations-management-suite-oms-linux-agent"></a>Agente de Operations Management Suite (OMS) Linux

* [Introducción al agente de Operations Management Suite (OMS) Linux](https://github.com/Microsoft/OMS-Agent-for-Linux/blob/master/docs/Docker-Instructions.md#overview)

* [Imágenes de Operations Management Suite (OMS) en DockerHub](https://hub.docker.com/r/microsoft/vsts-agent/) 

* [Imágenes de Operations Management Suite (OMS) en GitHub](https://github.com/Microsoft/OMS-docker)

#### <a name="microsoft-azure-command-line-interface-cli"></a>Interfaz de línea de comandos (CLI) de Microsoft Azure

* [Imágenes de Microsoft Azure interfaz de línea de comandos (CLI) en DockerHub](Docker image for Microsoft Azure Command Line Interface) 

* [Imágenes de Microsoft Azure interfaz de línea de comandos (CLI) en GitHub](https://github.com/Microsoft/OMS-docker)

> [!Note]
> Si no tiene una suscripción de Azure, [Regístrese hoy](https://azure.microsoft.com/free/?b=16.48) para una cuenta gratuita de 30 días y get 200 dólares en créditos de Azure para probar cualquier combinación de los servicios de Azure.
>

#### <a name="microsoft-azure-cosmos-db-emulator-windows-containers-only"></a>Emulador de Cosmos DB de Microsoft Azure (solo los contenedores de Windows)

* [Imágenes del emulador de base de datos de Microsoft Azure Cosmos en DockerHub](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator) 

* [Usar el emulador de base de datos de Cosmos de Azure para desarrollo local y las pruebas](https://docs.microsoft.com/azure/cosmos-db/local-emulator#developing-with-the-emulator)

## <a name="exploring-the-rich-docker-development-ecosystem"></a>Explorar el amplio ecosistema de desarrollo de Docker

Ahora que ha aprendido sobre la plataforma Docker y las imágenes de Docker diferentes, el paso siguiente consiste en explorar el amplio ecosistema de Docker. Los vínculos siguientes muestran cómo las herramientas de Microsoft complementan desarrollo del contenedor.

* [Usar conjuntamente .NET y Docker](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/) 
* [Diseñar y desarrollar aplicaciones .NET basadas en Microservicio y contenedor múltiples](../standard/microservices-architecture/multi-container-microservice-net-applications)
* [Extensión de Visual Studio código Docker](https://code.visualstudio.com/docs/languages/dockerfile) 
* [Obtenga información acerca de cómo usar Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/) 
* [Ejemplo de introducción de obtención de Service Fabric](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/)
* [Ventajas de los contenedores de Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/index#video-overview)
* [Trabajar con herramientas de Docker de Visual Studio](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Implementación de imágenes de Docker desde el registro de contenedor de Azure a las instancias de contenedor de Azure](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [Depuración con el código de Visual Studio](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [Obtener las manos con Visual Studio para Mac, contenedores y el código sin servidor en la nube](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [Introducción a Docker y Visual Studio para Mac laboratorio](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

## <a name="next-steps"></a>Pasos siguientes

* [Obtenga información acerca de los aspectos básicos de Docker con .NET Core](../docker/docker-basics-dotnet-core.md)
* [Creación de imágenes de Docker de núcleo de .NET](../docker/building-net-docker-images)