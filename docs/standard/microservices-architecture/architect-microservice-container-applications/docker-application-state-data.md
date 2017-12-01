---
title: Estado y los datos en aplicaciones de Docker
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Estado y los datos en aplicaciones de Docker
keywords: Docker, Microservicios, ASP.NET, contenedor, SQL, CosmosDB, Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 36d0fb9f27ef56b36c380e2fc972c79cff77003e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="state-and-data-in-docker-applications"></a>Estado y los datos en aplicaciones de Docker

En la mayoría de los casos, se puede considerar un contenedor como una instancia de un proceso. Un proceso no mantiene el estado persistente. Aunque puede escribir un contenedor para su almacenamiento local, suponiendo que una instancia será indefinidamente alrededor sería como suponiendo que una sola ubicación en memoria será duradera. Imágenes del contenedor, como procesos, deben suponer tener varias instancias o que finalmente se terminará; Si administra que se encuentra con un orquestador del contenedor, se debe suponer que se podría obtener mover desde un nodo o la máquina virtual a otro.

Docker ofrece una característica denominada la *superposición de sistema de archivos*. Esto implementa una tarea de copia en escritura que almacena información actualizada en el sistema de archivos de la raíz del contenedor. Esta información es además la imagen original en el que se basa el contenedor. Si se elimina el contenedor del sistema, estos cambios se perderán. Por lo tanto, si es posible guardar el estado de un contenedor dentro de su almacenamiento local, diseñar un sistema de resolver este problema entrarían en conflicto con la idea de diseño de contenedor, cuyo valor predeterminado es sin estado.

Las soluciones siguientes se usan para administrar datos persistentes en aplicaciones de Docker:

-   [Volúmenes de datos](https://docs.docker.com/engine/tutorials/dockervolumes/) que montar en el host.

-   [Contenedores de volúmenes de datos](https://docs.docker.com/engine/tutorials/dockervolumes/#creating-and-mounting-a-data-volume-container) que proporcionan almacenamiento compartido entre todos los contenedores mediante un contenedor externo.

-   [Complementos de volumen](https://docs.docker.com/engine/tutorials/dockervolumes/) que montar los volúmenes a los servicios remotos, proporcionar persistencia a largo plazo.

-   [Almacenamiento de Azure](https://docs.microsoft.com/azure/storage/), que proporciona almacenamiento geográfica distribuible, proporcionar una buena solución de persistencia a largo plazo para los contenedores.

-   Bases de datos relacionales remotos como [base de datos de SQL Azure](https://azure.microsoft.com/services/sql-database/) o bases de datos NoSQL, como [base de datos de Azure Cosmos](https://docs.microsoft.com/azure/cosmos-db/introduction), o almacenar en caché servicios como [Redis](https://redis.io/).

A continuación proporciona más información sobre estas opciones.

**Volúmenes de datos** directorios asignado desde el sistema operativo del host en los directorios en contenedores. Cuando el código en el contenedor tiene acceso al directorio, que acceso es realmente un directorio en el sistema operativo del host. Este directorio no está asociado a la duración del contenedor y el directorio puede tener acceso desde el código que se ejecuta directamente en el sistema operativo del host o por otro contenedor que asigna el mismo directorio de host a sí mismo. Por lo tanto, los volúmenes de datos están diseñados para conservar los datos independientemente de la vida del contenedor. Si elimina un contenedor o una imagen desde el host Docker, los datos se conserva en el volumen de datos no se elimina. Pueden tener acceso a los datos en un volumen desde el sistema operativo de host también.

**Contenedores de volúmenes de datos** son una evolución de los volúmenes de datos normal. Un contenedor de volúmenes de datos es un contenedor simple que tiene uno o más volúmenes de datos dentro de él. El contenedor de volúmenes de datos proporciona acceso a los contenedores desde un punto de montaje central. Este método de acceso a datos es conveniente porque resume la ubicación de los datos originales. Aparte de eso, su comportamiento es similar de un volumen de datos normal, por lo que los datos se guardan en este contenedor dedicado independientemente del ciclo de vida de los contenedores de la aplicación.

Tal como se muestra en la figura 4-5, volúmenes de Docker normales pueden almacenarse fuera de los propios contenedores, pero dentro de los límites físicos del servidor de host o máquina virtual. Sin embargo, contenedores de Docker no pueden tener acceso a un volumen de servidor de un host o máquina virtual a otro. En otras palabras, con estos volúmenes, no es posible administrar los datos que se comparten entre contenedores que se ejecutan en diferentes hosts de Docker

![](./media/image5.png)

**Figura 4-5**. Volúmenes de datos y orígenes de datos externos para aplicaciones basadas en el contenedor

Además, cuando un orchestrator administra contenedores de Docker, contenedores podrían "mover" entre los hosts, dependiendo de las optimizaciones realizadas por el clúster. Por lo tanto, no se recomienda utilizar volúmenes de datos para los datos empresariales. Pero son un buen mecanismo para trabajar con archivos de seguimiento, archivos temporales, o similar no afectará a coherencia de los datos empresariales.

**Complementos de volumen** como [Flocker](https://clusterhq.com/flocker/) proporcionan acceso a datos a través de todos los hosts en un clúster. Aunque no todos los complementos de volumen se crean por igual, volumen complementos normalmente proporcionar externalizado almacenamiento confiable persistente de contenedores inmutable.

**Orígenes de datos remotos y caché** herramientas como base de datos de SQL Azure, base de datos de Azure Cosmos o una caché remota como Redis pueden utilizarse en contenedores aplicaciones del mismo modo que se utilizan cuando se desarrolla sin contenedores. Se trata de una manera comprobada para almacenar datos de aplicaciones de negocios.

**Almacenamiento de Azure.** Datos económicos normalmente deberá colocarse en recursos externos o las bases de datos, como el almacenamiento de Azure. Almacenamiento de Azure, en concreto, proporciona los siguientes servicios en la nube:

-   Almacenamiento de blobs almacena datos de objetos no estructurados. Un blob puede ser cualquier tipo de datos de texto o binarios, como documentos o medios de archivos (imágenes, audio y vídeo). Almacenamiento de blobs también se conoce como almacenamiento de objetos.

-   Almacenamiento de archivos ofrece almacenamiento compartido para aplicaciones heredadas mediante el protocolo SMB estándar. Máquinas virtuales de Azure y servicios en la nube pueden compartir datos de archivos a través de los componentes de la aplicación a través de recursos compartidos montados. Aplicaciones locales pueden tener acceso a datos de archivos en un recurso compartido a través de la API de REST de servicio de archivo.

-   Almacenamiento de tabla almacena conjuntos de datos estructurados. Almacenamiento de tabla es un almacén de datos del atributo de clave NoSQL, lo que permite el desarrollo rápido y un acceso rápido a grandes cantidades de datos.

**Bases de datos relacionales y bases de datos NoSQL.** Existen muchas opciones para bases de datos externas, desde bases de datos relacionales como bases de datos NoSQL, PostgreSQL, Oracle o SQL Server como base de datos de Azure Cosmos, MongoDB, etcetera. Estas bases de datos no se van a explicarse como parte de esta guía puesto que están en un asunto completamente diferente.


>[!div class="step-by-step"]
[Anterior] (incluya-monolítico-applications.md) [siguiente] (service-oriented-architecture.md)
