---
title: Estado y datos en aplicaciones de Docker
description: Administración de estado y datos en aplicaciones de Docker. Las instancias de microservicios son prescindibles, pero LOS DATOS NO, aquí se explica cómo controlarlos con microservicios.
ms.date: 09/20/2018
ms.openlocfilehash: 10271d41dcd0574cd212663c2ee22ae06c2c1269
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91152629"
---
# <a name="state-and-data-in-docker-applications"></a>Estado y datos en aplicaciones de Docker

En la mayoría de los casos, un contenedor se puede considerar como una instancia de un proceso. Un proceso no mantiene un estado persistente. Si bien un contenedor puede escribir en su almacenamiento local, suponer que una instancia permanecerá indefinidamente sería como suponer que una sola ubicación en memoria será duradera. Debe suponer que las imágenes de contenedor, como los procesos, tienen varias instancias o finalmente se terminarán. Si se administran con un orquestador de contenedores, debe suponer que podrían desplazarse de un nodo o máquina virtual a otro.

Las soluciones siguientes se usan para administrar datos en aplicaciones de Docker:

Desde el host de Docker, como [volúmenes de Docker](https://docs.docker.com/engine/admin/volumes/):

- Los **volúmenes** se almacenan en un área del sistema de archivos de host administrado por Docker.

- Los **montajes de enlace** pueden asignar cualquier carpeta en el sistema de archivos de host, por lo que el acceso no se puede controlar desde el proceso de Docker y puede suponer un riesgo de seguridad ya que un contenedor podría acceder a carpetas del sistema operativo confidenciales.

- Los **montajes tmpfs** son como carpetas virtuales que solo existen en la memoria del host y nunca se escriben en el sistema de archivos.

Desde el almacenamiento remoto:

- [Azure Storage](https://azure.microsoft.com/documentation/services/storage/), que proporciona almacenamiento con distribución geográfica y representa una buena solución de persistencia a largo plazo para los contenedores.

- Bases de datos relacionales remotas como [Azure SQL Database](https://azure.microsoft.com/services/sql-database/), bases de datos NoSQL como [Azure Cosmos DB](/azure/cosmos-db/introduction) o servicios de caché como [Redis](https://redis.io/).

Desde el contenedor de Docker:

- **Superposición del sistema de archivos**. Esta característica de Docker implementa una tarea de copia en escritura que almacena información actualizada en el sistema de archivos raíz del contenedor. Esa información se coloca "encima" de la imagen original en la que se basa el contenedor. Si se elimina el contenedor del sistema, estos cambios se pierden. Por tanto, si bien es posible guardar el estado de un contenedor dentro de su almacenamiento local, diseñar un sistema sobre esta base entraría en conflicto con la idea del diseño del contenedor, que de manera predeterminada es sin estado.

Sin embargo, el uso de los volúmenes de Docker es ahora la mejor manera de controlar datos locales en Docker. Si necesita obtener más información sobre el almacenamiento en contenedores, consulte [Docker storage drivers](https://docs.docker.com/storage/storagedriver/select-storage-driver/) (Controladores de almacenamiento de Docker) y [About storage drivers](https://docs.docker.com/storage/storagedriver/) (Sobre los controladores de almacenamiento).

Los siguientes puntos proporcionan más información sobre estas opciones:

Los **volúmenes** son directorios asignados desde el sistema operativo del host a directorios en contenedores. Cuando el código en el contenedor tiene acceso al directorio, ese acceso es realmente a un directorio en el sistema operativo del host. Este directorio no está asociado a la duración del contenedor y Docker lo administra y aísla de la funcionalidad básica de la máquina host. Por tanto, los volúmenes de datos están diseñados para conservar los datos independientemente de la vida del contenedor. Si elimina un contenedor o una imagen del host de Docker, los datos que se conservan en el volumen de datos no se eliminan.

Los volúmenes pueden tener nombre o ser anónimos (predeterminado). Los volúmenes con nombre son la evolución de los **Contenedores de volúmenes de datos** y facilitan el uso compartido de datos entre contenedores. Los volúmenes también admiten controladores de volumen, que le permiten almacenar datos en hosts remotos, entre otras opciones.

Los **montajes de enlace** están disponibles desde hace mucho tiempo y permiten la asignación de cualquier carpeta a un punto de montaje en un contenedor. Los montajes de enlace tienen más limitaciones que los volúmenes y algunos problemas de seguridad importantes, por lo que los volúmenes son la opción recomendada.

Los **montajes tmpfs** son básicamente carpetas virtuales que solo existen en la memoria del host y nunca se escriben en el sistema de archivos. Son rápidos y seguros, pero usan memoria y solo están diseñados para datos temporales y no persistentes.

Tal como se muestra en la figura 4-5, los volúmenes de Docker normales pueden almacenarse fuera de los propios contenedores, pero dentro de los límites físicos del servidor de host o de la máquina virtual. Pero los contenedores de Docker no pueden acceder a un volumen desde un servidor de host o máquina virtual a otro. En otras palabras, con estos volúmenes, no es posible administrar los datos que se comparten entre contenedores que se ejecutan en otros hosts de Docker, aunque se podría lograr con un controlador de volumen que sea compatible con los hosts remotos.

![Diagrama que muestra volúmenes de datos y orígenes de datos externos para aplicaciones basadas en contenedor.](./media/docker-application-state-data/volumes-external-data-sources.png)

**Figura 4-5**. Volúmenes y orígenes de datos externos para aplicaciones basadas en contenedor

Los volúmenes se pueden compartir entre contenedores, pero solo en el mismo host, a menos que use un controlador remoto compatible con hosts remotos. Además, cuando un orquestador administra los contenedores de Docker, estos podrían "moverse" entre hosts, según las optimizaciones que el clúster realice. Por tanto, no se recomienda usar volúmenes de datos para los datos empresariales. Pero son un buen mecanismo para trabajar con archivos de seguimiento, archivos temporales o similares que no afectarán a la coherencia de los datos empresariales.

Las herramientas de **orígenes de datos remotos y caché** como Azure SQL Database, Azure Cosmos DB o una caché remota como Redis pueden usarse en aplicaciones en contenedores del mismo modo que se usan al desarrollar sin contenedores. Se trata de una manera comprobada para almacenar datos de aplicaciones empresariales.

**Azure Storage.** Normalmente, los datos empresariales deben colocarse en recursos o bases de datos externos, como Azure Storage. Azure Storage, en concreto, proporciona los siguientes servicios en la nube:

- El almacenamiento de blobs almacena datos de objetos no estructurados. Un blob puede ser cualquier tipo de texto o datos binarios, como documentos o archivos multimedia (archivos de imagen, audio y vídeo). El almacenamiento de blobs también se conoce como "almacenamiento de objetos".

- El almacenamiento de archivos ofrece almacenamiento compartido para aplicaciones heredadas mediante el protocolo SMB estándar. Las máquinas virtuales de Azure y los servicios en la nube pueden compartir datos de archivos en los componentes de la aplicación a través de recursos compartidos montados. Las aplicaciones locales pueden tener acceso a datos de archivos en un recurso compartido a través de la API de REST de servicio de archivos.

- El almacenamiento de tabla almacena conjuntos de datos estructurados. El almacenamiento de tabla es un almacén de datos del atributo de clave NoSQL, lo que permite desarrollar y acceder rápidamente a grandes cantidades de datos.

**Bases de datos relacionales y bases de datos NoSQL.** Existen muchas opciones de bases de datos externas, desde las bases de datos relacionales como SQL Server, PostgreSQL u Oracle, o las bases de datos NoSQL como Azure Cosmos DB, MongoDB, etc. En esta guía no se explicarán estas bases de datos puesto que eso se hace en un tema completamente diferente.

>[!div class="step-by-step"]
>[Anterior](containerize-monolithic-applications.md)
>[Siguiente](service-oriented-architecture.md)
