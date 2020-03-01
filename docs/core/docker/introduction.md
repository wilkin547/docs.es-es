---
title: Introducción a Docker
description: En este artículo se proporciona una introducción e información general para Docker en el contexto de una aplicación de .NET Core.
ms.date: 03/20/2019
ms.custom: mvc
ms.openlocfilehash: eedfd1e7c1b361beb9d4f271e739657ef5e894a6
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157796"
---
# <a name="introduction-to-net-and-docker"></a>Introducción a .NET y Docker

.NET Core puede ejecutarse con facilidad en un contenedor de Docker. Los contenedores proporcionan una manera ligera de aislar la aplicación del resto del sistema host, con tan solo compartir el kernel y usar los recursos proporcionados a la aplicación. Si no está familiarizado con Docker, se recomienda encarecidamente que lea la [documentación de introducción](https://docs.docker.com/engine/docker-overview/) a Docker.

Para más información sobre cómo instalar Docker, vea la página de descarga de [Docker Desktop: Community Edition](https://www.docker.com/products/docker-desktop).

## <a name="docker-basics"></a>Conceptos básicos de Docker

Hay algunos conceptos con los que debe estar familiarizado. El cliente de Docker tiene una CLI que puede usar para administrar imágenes y contenedores. Como se mencionó anteriormente, debe dedicar tiempo a leer la documentación de [introducción a Docker](https://docs.docker.com/engine/docker-overview/).

### <a name="images"></a>Imágenes

Una imagen es una colección ordenada de los cambios del sistema de archivos que forman la base de un contenedor. La imagen no tiene ningún estado y es de solo lectura. La mayor parte del tiempo, una imagen se basa en otra imagen, pero con alguna personalización. Por ejemplo, al crear una imagen para una aplicación, esta se basaría en una imagen existente que ya contiene .NET Core Runtime.

Dado que los contenedores se crean a partir de imágenes, estas tienen un conjunto de parámetros de ejecución (por ejemplo, un archivo ejecutable de inicio) que se ejecutan cuando se inicia el contenedor.

### <a name="containers"></a>Contenedores

Un contenedor es una instancia ejecutable de una imagen. Al crear la imagen, implementa la aplicación y sus dependencias. Después, se pueden crear instancias de varios contenedores, cada una de ellas aisladas entre sí. Cada instancia de contenedor tiene su sistema de archivos, memoria e interfaz de red propios.

### <a name="registries"></a>Registros

Los registros de contenedor son una colección de repositorios de imágenes. Puede basar sus imágenes en una imagen del registro. Puede crear contenedores directamente a partir de una imagen en un registro. La [relación entre los contenedores, las imágenes y los registros de Docker](../../architecture/microservices/container-docker-introduction/docker-containers-images-registries.md) es un concepto importante a la hora de [diseñar y compilar aplicaciones o microservicios en contenedores](../../architecture/microservices/architect-microservice-container-applications/index.md). Este enfoque reduce en gran medida el tiempo que transcurre entre el desarrollo y la implementación.

Docker tiene un registro público hospedado en [Docker Hub](https://hub.docker.com/) que puede usar. Las [imágenes relacionadas con .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) aparecen en Docker Hub.

El registro de contenedor de Microsoft (MCR) es el origen oficial de las imágenes de contenedor proporcionadas por Microsoft. El MCR se basa en Azure CDN para proporcionar imágenes replicadas globalmente. Sin embargo, el MCR no tiene un sitio web público, y la manera principal de obtener información sobre las imágenes de contenedor proporcionadas por Microsoft es en las [páginas de Microsoft Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).

### <a name="dockerfile"></a>Dockerfile

Un archivo **Dockerfile** es aquel que define un conjunto de instrucciones que crea una imagen. Cada instrucción de **Dockerfile** crea una capa en la imagen. Por lo general, cuando se recompila la imagen, solo se recompilan las capas que han cambiado. El **Dockerfile** se puede distribuir a otros usuarios, para que puedan recrear una imagen de la misma manera que usted. Aunque esto le permite distribuir las *instrucciones* sobre cómo crear la imagen, el método principal para distribuir la imagen consiste en publicarla en un registro.

## <a name="net-core-images"></a>Imágenes de .NET Core

Las imágenes oficiales de Docker en .NET Core se publican en el registro de contenedor de Microsoft (MCR) y se pueden encontrar en el [repositorio de Docker Hub para Microsoft .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/). Cada repositorio contiene imágenes para diferentes combinaciones de .NET (SDK o Runtime) y del sistema operativo que puede usar.

Microsoft ofrece imágenes que se adaptan a escenarios específicos. Por ejemplo, el [repositorio de ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) proporciona imágenes que se compilan para ejecutar aplicaciones de ASP.NET Core en producción.

## <a name="azure-services"></a>Servicios de Azure

Varios servicios de Azure admiten contenedores. Cree una imagen de Docker para la aplicación e impleméntela en alguno de los siguientes servicios:

- [Azure Kubernetes Service (AKS)](https://azure.microsoft.com/services/kubernetes-service/)\
Escale y organice contenedores de Linux mediante Kubernetes.

- [Azure App Service](https://azure.microsoft.com/services/app-service/containers/)\
Implemente aplicaciones web o API con contenedores de Linux en un entorno PaaS.

- [Azure Container Instances](https://azure.microsoft.com/services/container-instances/)\
Hospede el contenedor en la nube sin ningún servicio de administración de nivel superior.

- [Azure Batch](https://azure.microsoft.com/services/batch/)\
Ejecute trabajos de proceso repetitivos mediante contenedores.

- [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/)\
Migre las aplicaciones de .NET mediante lift-and-shift y modernícelas a microservicios mediante contenedores de Windows Server.

- [Azure Container Registry](https://azure.microsoft.com/services/container-registry/)\
Almacene y administre imágenes de contenedor en todos los tipos de implementaciones de Azure.

## <a name="next-steps"></a>Pasos siguientes

- [Obtenga información sobre cómo incluir una aplicación de .NET Core en contenedores](build-container.md).
- [Obtenga información sobre cómo incluir una aplicación ASP.NET Core en contenedores.](/aspnet/core/host-and-deploy/docker/building-net-docker-images)
- [Consulte el tutorial de ASP.NET Core para los microservicios](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro).
- [Obtenga información sobre las herramientas de contenedor en Visual Studio](/visualstudio/containers/overview)
