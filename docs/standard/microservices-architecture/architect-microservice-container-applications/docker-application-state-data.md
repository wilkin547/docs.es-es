---
title: Estado y datos en aplicaciones de Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Estado y datos en aplicaciones de Docker
keywords: Docker, microservicios, ASP.NET, contenedor, SQL, CosmosDB, Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ef11d89c39ee02d52dab29f949d1ac6be981d87f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="state-and-data-in-docker-applications"></a>Estado y datos en aplicaciones de Docker

En la mayoría de los casos, un contenedor se puede considerar como una instancia de un proceso. Un proceso no mantiene un estado persistente. Si bien un contenedor puede escribir en su almacenamiento local, suponer que una instancia permanecerá indefinidamente sería como suponer que una sola ubicación en memoria será duradera. Debe suponerse que las imágenes del contenedor, como los procesos, tienen varias instancias o que finalmente desaparecerán; si se administran con un orquestador de contenedores, se debe suponer que podrían desplazarse de un nodo o máquina virtual a otro.

Docker ofrece una característica denominada el *sistema de archivos de superposición*. Esto implementa una tarea de copia en escritura que almacena información actualizada en el sistema de archivos raíz del contenedor. Esa información se combina con la imagen original en la que se basa el contenedor. Si se elimina el contenedor del sistema, estos cambios se pierden. Por tanto, si bien es posible guardar el estado de un contenedor dentro de su almacenamiento local, diseñar un sistema sobre esta base entraría en conflicto con la idea del diseño del contenedor, que de manera predeterminada es sin estado.

Las soluciones siguientes se usan para administrar datos persistentes en aplicaciones de Docker:

-   [Volúmenes de datos](https://docs.docker.com/engine/tutorials/dockervolumes/) que se montan en el host.

-   [Contenedores de volúmenes de datos](https://docs.docker.com/engine/tutorials/dockervolumes/#creating-and-mounting-a-data-volume-container) que proporcionan almacenamiento compartido entre los contenedores mediante un contenedor externo.

-   [Complementos de volumen](https://docs.docker.com/engine/tutorials/dockervolumes/) que montan volúmenes en los servicios remotos y proporcionan persistencia a largo plazo.

-   [Azure Storage](https://docs.microsoft.com/azure/storage/), que proporciona almacenamiento con distribución geográfica y representa una buena solución de persistencia a largo plazo para los contenedores.

-   Bases de datos relacionales remotas como [Azure SQL Database](https://azure.microsoft.com/services/sql-database/), bases de datos NoSQL como [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction) o servicios de caché como [Redis](https://redis.io/).

Los puntos siguientes proporcionan más información sobre estas opciones.

Los **volúmenes de datos** son directorios asignados desde el sistema operativo del host a directorios en contenedores. Cuando el código en el contenedor tiene acceso al directorio, ese acceso es realmente a un directorio en el sistema operativo del host. Este directorio no está asociado a la duración del contenedor y se puede acceder a él con el código que se ejecuta directamente en el sistema operativo del host o mediante otro contenedor que asigna el mismo directorio del host a sí mismo. Por tanto, los volúmenes de datos están diseñados para conservar los datos independientemente de la vida del contenedor. Si elimina un contenedor o una imagen del host de Docker, los datos que se conservan en el volumen de datos no se eliminan. También se puede acceder a los datos de un volumen desde el sistema operativo del host.

Los **contenedores de volúmenes de datos** son una evolución de los volúmenes de datos normales. Un contenedor de volúmenes de datos es un contenedor simple que contiene uno o más volúmenes de datos. El contenedor de volúmenes de datos proporciona acceso a los contenedores desde un punto de montaje central. Este método de acceso a datos es conveniente porque resume la ubicación de los datos originales. Aparte de eso, su comportamiento es similar al de un volumen de datos normal, por lo que los datos se guardan en este contenedor dedicado independientemente del ciclo de vida de los contenedores de la aplicación.

Tal como se muestra en la figura 4-5, los volúmenes de Docker normales pueden almacenarse fuera de los propios contenedores, pero dentro de los límites físicos del servidor de host o de la máquina virtual. Sin embargo, los contenedores de Docker no pueden tener acceso a un volumen desde un servidor de host o máquina virtual a otro. En otras palabras, con estos volúmenes, no es posible administrar los datos que se comparten entre contenedores que se ejecutan en diferentes hosts de Docker

![](./media/image5.png)

**Figura 4-5**. Volúmenes de datos y orígenes de datos externos para aplicaciones basadas en contenedor

Además, cuando un orquestador administra los contenedores de Docker, estos podrían "moverse" entre hosts, según las optimizaciones que el clúster realice. Por tanto, no se recomienda usar volúmenes de datos para los datos empresariales. Pero son un buen mecanismo para trabajar con archivos de seguimiento, archivos temporales o similares que no afectarán a la coherencia de los datos empresariales.

Los **complementos de volumen** como [Flocker](https://clusterhq.com/flocker/) proporcionan acceso a datos a través de todos los hosts de un clúster. Aunque no todos los complementos de volumen se crean por igual, normalmente proporcionan almacenamiento confiable persistente externalizado a partir de contenedores inmutables.

Las herramientas de **orígenes de datos remotos y caché** como Azure SQL Database, Azure Cosmos DB o una caché remota como Redis pueden usarse en aplicaciones en contenedores del mismo modo que se usan al desarrollar sin contenedores. Se trata de una manera comprobada para almacenar datos de aplicaciones empresariales.

**Azure Storage.** Normalmente, los datos empresariales deben colocarse en recursos o bases de datos externos, como Azure Storage. Azure Storage, en concreto, proporciona los siguientes servicios en la nube:

-   El almacenamiento de blobs almacena datos de objetos no estructurados. Un blob puede ser cualquier tipo de texto o datos binarios, como documentos o archivos multimedia (archivos de imagen, audio y vídeo). El almacenamiento de blobs también se conoce como "almacenamiento de objetos".

-   El almacenamiento de archivos ofrece almacenamiento compartido para aplicaciones heredadas mediante el protocolo SMB estándar. Las máquinas virtuales de Azure y los servicios en la nube pueden compartir datos de archivos en los componentes de la aplicación a través de recursos compartidos montados. Las aplicaciones locales pueden tener acceso a datos de archivos en un recurso compartido a través de la API de REST de servicio de archivos.

-   El almacenamiento de tabla almacena conjuntos de datos estructurados. El almacenamiento de tabla es un almacén de datos del atributo de clave NoSQL, lo que permite desarrollar y acceder rápidamente a grandes cantidades de datos.

**Bases de datos relacionales y bases de datos NoSQL.** Existen muchas opciones de bases de datos externas, desde las bases de datos relacionales como SQL Server, PostgreSQL u Oracle, o las bases de datos NoSQL como Azure Cosmos DB, MongoDB, etc. En esta guía no se explicarán estas bases de datos puesto que eso se hace en un tema completamente diferente.


>[!div class="step-by-step"]
[Previous] (containerize-monolithic-applications.md) [Next] (service-oriented-architecture.md)
