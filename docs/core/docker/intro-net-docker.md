---
title: Introducción a .NET y Docker
description: Descripción de Docker y .NET Core
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.custom: mvc
ms.openlocfilehash: 0fe3fcdee1c508f5c8165b7709ca08e42d0b1d55
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44251776"
---
# <a name="introduction-to-net-and-docker"></a>Introducción a .NET y Docker

En este artículo se proporciona información de tipo introductorio y general conceptual para trabajar con .NET en Docker.

## <a name="docker-packaging-your-apps-to-deploy-and-run-anywhere"></a>Docker: empaquetado de las aplicaciones existentes para implementar y ejecutar desde cualquier lugar

[Docker](../../standard/microservices-architecture/container-docker-introduction/docker-defined.md) es una plataforma abierta que permite a los desarrolladores y administradores compilar [imágenes](https://docs.docker.com/glossary/?term=image), así como enviar y ejecutar aplicaciones distribuidas en un entorno con aislamiento flexible denominado [contenedor](https://www.docker.com/what-container). Este enfoque hace posible una eficaz administración del ciclo de vida de las aplicaciones entre los entornos de desarrollo, control de la calidad y producción.
 
La [plataforma Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) utiliza el [motor de Docker](https://docs.docker.com/engine/docker-overview/#docker-engine) para generar y empaquetar rápidamente aplicaciones como [imágenes de Docker](https://docs.docker.com/glossary/?term=image) creadas con archivos escritos en el formato [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) que, a continuación, se implementan y ejecutan en un [contenedor con capas](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).

Puede crear sus propias [imágenes con capas](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers) como dockerfiles o utilizar las existentes desde un [registro](https://docs.docker.com/glossary/?term=registry), como [Docker Hub](https://docs.docker.com/glossary/?term=Docker%20Hub).

La [relación entre los contenedores, las imágenes y los registros de Docker](../../standard/microservices-architecture/container-docker-introduction/docker-containers-images-registries.md) es un concepto importante a la hora de [diseñar y compilar aplicaciones o microservicios en contenedores](../../standard/microservices-architecture/architect-microservice-container-applications/index.md). Este enfoque reduce en gran medida el tiempo que transcurre entre el desarrollo y la implementación.

### <a name="further-reading-and-watching"></a>Seguir leyendo (y viendo)

* [Contenedores basados en Windows: desarrollo de aplicaciones modernas con control de nivel empresarial.](https://www.youtube.com/watch?v=Ryx3o0rD5lY&feature=youtu.be)
* [Información general de Docker](https://docs.docker.com/engine/docker-overview/)
* [Dockerfile en contenedores de Windows](/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [Procedimientos recomendados para escribir Dockerfiles](https://docs.docker.com/engine/userguide/eng-image/dockerfile_best-practices/)
* [Creación de imágenes de Docker para aplicaciones de .NET Core](../docker/building-net-docker-images.md)


### <a name="getting-net-docker-images"></a>Obtención de imágenes de Docker de .NET

Las imágenes oficiales de Docker de .NET se han creado y optimizado por parte de Microsoft. Están disponibles públicamente en los repositorios de Microsoft en Docker Hub. Cada repositorio puede contener varias imágenes, dependiendo de las versiones de .NET y de las versiones del sistema operativo. La mayoría de repositorios de imágenes ofrecen un exhaustivo etiquetado que le ayuda a seleccionar una versión de un marco concreto y un sistema operativo (distribución de Linux o versión de Windows).

## <a name="scenario-based-guidance"></a>Información orientativa basada en escenarios

Lo que pretende Microsoft con los repositorios de .NET es disponer de repositorios orientados y detallados que representen un escenario o una carga de trabajo específicos.

Las imágenes de `microsoft/aspnetcore` se optimizan para las aplicaciones de ASP.NET Core en Docker, de manera que los contenedores puedan iniciar más rápido.

Las imágenes de .NET Core (`microsoft/dotnet`) están diseñadas para las aplicaciones de consola basadas en .NET Core. Por ejemplo, los procesos por lotes, las instancias de Azure WebJobs y otros escenarios de consola deben utilizar imágenes optimizadas de .NET Core.

El escenario horizontal más evidente para el uso de las aplicaciones de Docker y .NET es la implementación y el hospedaje en producción. Resulta que la producción es simplemente un escenario y el resto son igualmente útiles. Estos escenarios no son específicos de. NET, pero deberían aplicarse a la mayoría de las plataformas para desarrolladores.

* **Instalación de baja fricción**: puede probar .NET sin una instalación local. Simplemente descargue una imagen de Docker que contenga .NET.

* **Desarrollo en un contenedor**: puede llevar a cabo el desarrollo en un entorno coherente, creando similitudes entre los entornos de desarrollo y producción (evitando problemas de estado global en máquinas de desarrolladores). Visual Studio Tools para Docker incluso le permite iniciar un contenedor directamente desde Visual Studio.

* **Prueba en un contenedor**: puede probar en un contenedor, lo que reduce los errores debidos a entornos que no están configurados correctamente u otros cambios que permanecen desde la última prueba.

* **Compilación en un contenedor**: puede compilar código en un contenedor, sin que sea necesario configurar correctamente las máquinas de compilación compartidas para varios entornos. En su lugar, se utiliza un enfoque del tipo "traiga su propio contenedor".

* **Implementación en todos los entornos**: puede implementar una imagen en todos los entornos. Este enfoque reduce los errores debidos a diferencias de configuración,que suelen cambiar el comportamiento de la imagen a través de una configuración externa (por ejemplo, variables de entorno insertadas).

[Instrucciones generales](../../standard/microservices-architecture/net-core-net-framework-containers/general-guidance.md) para decidir entre .NET Core y .NET Framework para el desarrollo de contenedores de Docker.

### <a name="common-docker-development-scenarios"></a>Escenarios comunes de desarrollo de Docker

#### <a name="net-core"></a>Núcleo de .NET

**Recursos de .NET Core**

 Elija los ejemplos de .NET Core que se ajusten a los escenarios pertinentes. Todas las instrucciones de ejemplo describen cómo adaptar las imágenes de Docker de Windows o Linux desde hosts de Windows, Linux o macOS.

En estos ejemplos se usa .NET Core 2.0. Usan [compilación de varias etapas](https://github.com/dotnet/announcements/issues/18) y [etiquetas de varias arquitecturas](https://github.com/dotnet/announcements/issues/14) cuando corresponda.

* [Imágenes de .NET Core en DockerHub](https://hub.docker.com/r/microsoft/dotnet/)

* [Aplicar Docker a una aplicación .NET Core](https://docs.docker.com/engine/examples/dotnetcore/)

* En este ejemplo de Docker de .NET Core se muestra cómo [utilizar Docker en el proceso de desarrollo de .NET Core](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-dev). El ejemplo funciona con contenedores de Linux y Windows.

* En este ejemplo de Docker de .NET Core se muestra un patrón de prácticas recomendadas para [compilar imágenes de Docker para aplicaciones de .NET Core para entornos de producción.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod) El ejemplo funciona con contenedores de Linux y Windows.

* En este [ejemplo de Docker de .NET Core](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-selfcontained) se muestra un patrón de prácticas recomendadas para compilar imágenes de Docker para [aplicaciones de .NET Core independientes](../deploying/index.md). Se utiliza para el contenedor más pequeño de producción sin la ventaja de [compartir imágenes base entre contenedores](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/). Sin embargo, se podrían compartir las capas inferiores de Docker.

#### <a name="arm32--raspberry-pi"></a>ARM32 / Raspberry Pi

* [Anuncio de compilaciones de ARM32 para .NET Core Runtime](https://github.com/dotnet/announcements/issues/29)

* [Imágenes de ARM32 / Raspberry Pi .NET Core en DockerHub](https://hub.docker.com/r/microsoft/dotnet/)

* [Ejemplos de ARM32 / Raspberry Pi .NET Core Docker en GitHub](https://github.com/dotnet/dotnet-docker-samples#arm32--raspberry-pi)

#### <a name="net-framework"></a>.NET Framework

* [Imágenes de .NET Framework en DockerHub](https://hub.docker.com/r/microsoft/dotnet-framework/)

Este repositorio contiene ejemplos que muestran diversas configuraciones de Docker en .NET Framework. Puede utilizar estas imágenes como base para sus propias imágenes de Docker.

**.NET Framework 4.7**

En el [ejemplo dotnet-framework:4.7](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.7) se muestra el uso básico de "hello world" de [.NET Framework 4.7](../../framework/whats-new/index.md#v47). Muestra cómo puede compilar e implementar la aplicación que se basa en la [imagen de docker de .NET Framework 4.7](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-4.7/Dockerfile).

**.NET Framework 4.6.2**

El [ejemplo de dotnet-framework:4.6.2](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-4.6.2) muestra el uso básico de "hola mundo" de [.NET Framework 4.6.2](../../framework/whats-new/index.md#v462). Muestra cómo puede compilar e implementar la aplicación que se basa en la [imagen de docker de .NET Framework 4.6.2](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-4.6.2/Dockerfile).

**.NET Framework 3.5**

 El [ejemplo de dotnet-framework:3.5](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/dotnetapp-3.5) muestra el uso básico de "hola mundo" de [.NET Framework 3.5](https://github.com/Microsoft/dotnet-framework-docker-samples/blob/master/dotnetapp-3.5/dotnetapp-3.5/Dockerfile). Muestra cómo puede compilar e implementar un proyecto que se basa en .NET Framework 3.5 en Docker.

#### <a name="aspnet-core"></a>ASP.NET Core

* [En este ejemplo de Docker de ASP.NET Core](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) se muestra un patrón de prácticas recomendadas para compilar imágenes de Docker para aplicaciones de ASP.NET Core para entornos de producción. El ejemplo funciona con contenedores de Linux y Windows.

* [Imágenes de ASP.NET Core en DockerHub](https://hub.docker.com/r/microsoft/aspnetcore-build/)

* [Imágenes de ASP.NET Core en GitHub](https://github.com/aspnet/aspnet-docker)

#### <a name="aspnet-framework"></a>ASP.NET Framework

* [Imágenes de ASP.NET Framework en DockerHub](https://hub.docker.com/r/microsoft/aspnet/)

* [Aplicación de ASP.NET Web Forms en un ejemplo de .NET Framework 4.6.2](https://github.com/Microsoft/dotnet-framework-docker-samples/tree/master/aspnetapp)

#### <a name="windows-communication-framework-wcf"></a>Windows Communication Framework (WCF)

* [Imágenes de Windows Communication Framework (WCF) en DockerHub](https://hub.docker.com/r/microsoft/wcf/)

* [Imágenes de Windows Communication Framework (WCF) en GitHub](https://github.com/microsoft/wcf-docker)

* [Ejemplos de Docker de Windows Communication Framework (WCF) con .NET Framework 4.6.2](https://github.com/Microsoft/wcf-docker-samples)

#### <a name="internet-information-server-iis"></a>Internet Information Server (IIS)

* [Imágenes de Internet Information Server (IIS) en DockerHub](https://hub.docker.com/r/microsoft/iis/)

* [Imágenes de Internet Information Server (IIS) en GitHub](https://github.com/microsoft/iis-docker)

### <a name="interact-with-other-microsoft-stack-container-images"></a>Interacción con otras imágenes de contenedor de pila de Microsoft

#### <a name="microsoft-sql-server"></a>Microsoft SQL Server

* [Guía de inicio rápido para ejecutar la imagen de contenedor de Microsoft SQL Server para Linux 2017 con Docker](https://docs.microsoft.com/sql/linux/quickstart-install-connect-docker)

* [Imágenes de Microsoft SQL Server para Linux en DockerHub](https://hub.docker.com/r/microsoft/mssql-server-linux/)

* [Imágenes de Microsoft SQL Server Express Edition para contenedores de Windows en DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows-express/)

* [Imágenes de Microsoft SQL Server Developer Edition para contenedores de Windows en DockerHub](https://hub.docker.com/r/microsoft/mssql-server-windows-developer/)

#### <a name="visual-studio-team-services-vsts-agent"></a>Agente de Visual Studio Team Services (VSTS)

* [Imágenes de agente de Visual Studio Team Services (VSTS) en DockerHub](https://hub.docker.com/r/microsoft/vsts-agent/)

* [Imágenes de agente de Visual Studio Team Services (VSTS) en GitHub](https://github.com/Microsoft/vsts-agent-docker)

#### <a name="operations-management-suite-oms-linux-agent"></a>Agente de Linux de Operations Management Suite (OMS)

* [Información general de agente de Linux de Operations Management Suite (OMS)](https://github.com/Microsoft/OMS-Agent-for-Linux/blob/master/docs/Docker-Instructions.md)

* [Imágenes de Operations Management Suite (OMS) en DockerHub](https://hub.docker.com/r/microsoft/oms/)

* [Imágenes de Operations Management Suite (OMS) en GitHub](https://github.com/Microsoft/OMS-docker)

#### <a name="microsoft-azure-command-line-interface-cli"></a>Interfaz de línea de comandos (CLI) de Microsoft Azure

* [Imágenes de interfaz de línea de comandos (CLI) de Microsoft Azure en DockerHub](https://hub.docker.com/r/microsoft/azure-cli/) 

* [Imágenes de interfaz de línea de comandos (CLI) de Microsoft Azure en GitHub](https://github.com/Azure/azure-cli#Docker)

> [!NOTE]
> Si no tiene una suscripción de Azure, [regístrese hoy](https://azure.microsoft.com/free/?b=16.48) para obtener una cuenta gratuita durante 30 días y obtenga 200 dólares en créditos de Azure para probar cualquier combinación de servicios de Azure.

#### <a name="microsoft-azure-cosmos-db-emulator-windows-containers-only"></a>Emulador de Cosmos DB de Microsoft Azure (solo contenedores de Windows)

* [Imágenes del emulador de Cosmos DB de Microsoft Azure en DockerHub](https://hub.docker.com/r/microsoft/azure-cosmosdb-emulator) 

* [Uso del emulador de Cosmos DB de Azure para desarrollo y pruebas a nivel local](/azure/cosmos-db/local-emulator#developing-with-the-emulator)

## <a name="exploring-the-rich-docker-development-ecosystem"></a>Exploración del amplio ecosistema de desarrollo de Docker

Ahora que ha aprendido sobre la plataforma Docker y las diferentes imágenes de Docker, el paso siguiente consiste en explorar el amplio ecosistema de Docker. Los vínculos siguientes muestran cómo las herramientas de Microsoft complementan el desarrollo de contenedores.

* [Using .NET and Docker together](https://blogs.msdn.microsoft.com/dotnet/2017/05/25/using-net-and-docker-together/) (Uso conjunto de .NET y Docker)
* [Diseñar y desarrollar aplicaciones .NET basadas en varios contenedores y microservicios](../../standard/microservices-architecture/multi-container-microservice-net-applications/index.md)
* [Visual Studio Code Docker extension](https://code.visualstudio.com/docs/languages/dockerfile) (Extensión de Docker de Visual Studio Code)
* [Learn how to use Azure Service Fabric](/azure/service-fabric/index) (Información acerca de cómo usar Azure Service Fabric)
* [Service Fabric Getting Started Sample](https://azure.microsoft.com/resources/samples/service-fabric-dotnet-getting-started/) (Ejemplo de introducción a Service Fabric)
* [Benefits of Windows Containers](/virtualization/windowscontainers/about/index#video-overview) (Beneficios de los contenedores de Windows)
* [Working with Visual Studio Docker Tools](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Trabajo con Visual Studio Docker Tools)
* [Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/) (Implementación de imágenes de Docker desde Azure Container Registry a Azure Container Instances)
* [Depuración con Visual Studio Code](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container)
* [Getting hands on with Visual Studio for Mac, containers, and serverless code in the cloud](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments) (Información práctica sobre Visual Studio para Mac, contenedores y código sin servidor en la nube)
* [Getting Started with Docker and Visual Studio for Mac Lab](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started) (Introducción a Docker y Visual Studio para Mac Lab)

## <a name="next-steps"></a>Pasos siguientes

* [Información sobre los aspectos básicos de Docker con .NET Core](docker-basics-dotnet-core.md)
* [Creación de imágenes de Docker de .NET Core](building-net-docker-images.md)
