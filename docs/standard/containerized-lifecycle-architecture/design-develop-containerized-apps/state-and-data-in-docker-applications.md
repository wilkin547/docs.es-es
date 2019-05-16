---
title: Estado y datos en aplicaciones de Docker
description: Obtenga información sobre la opción disponible para guardar el estado en las aplicaciones en contenedores.
ms.date: 02/15/2019
ms.openlocfilehash: bc171a419632f2ac61c7c9bf6b201b84e0691c3a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641271"
---
# <a name="state-and-data-in-docker-applications"></a>Estado y datos en aplicaciones de Docker

En la mayoría de los casos, un contenedor se puede considerar como una instancia de un proceso. Un proceso no mantiene un estado persistente. Aunque puede escribir un contenedor para su almacenamiento local, suponiendo que una instancia permanecerá indefinidamente es como suponer que una sola ubicación en la memoria será duradera. Imágenes de contenedor, como los procesos, deben suponerse que tiene varias instancias y que finalmente terminarán; Si se administran con un orquestador de contenedores, se debe suponer que podrían desplazarse de un nodo o máquina virtual a otro.

Las soluciones siguientes se usan para administrar datos persistentes en aplicaciones de Docker:

Desde el host de Docker, como [volúmenes de Docker](https://docs.docker.com/engine/admin/volumes/):

- Los **volúmenes** se almacenan en un área del sistema de archivos de host administrado por Docker.

- **Enlazar montajes** puede asignar a cualquier carpeta en el sistema de archivos de host, por lo que no se puede controlar desde un proceso de Docker de acceso y puede suponer un riesgo de seguridad como un contenedor podría tener acceso a carpetas confidenciales de sistema operativo.

- Los **montajes tmpfs** son como carpetas virtuales que solo existen en la memoria del host y nunca se escriben en el sistema de archivos.

Desde el almacenamiento remoto:

- [Almacenamiento de Azure](https://azure.microsoft.com/documentation/services/storage/) proporciona almacenamiento geográfica distribuible, que proporciona una buena solución de persistencia a largo plazo para los contenedores.

- Bases de datos relacionales remotas como [Azure SQL Database](https://azure.microsoft.com/services/sql-database/), como bases de datos NoSQL [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction), o servicios de caché como [Redis](https://redis.io/).

Desde el contenedor de Docker:

- Docker ofrece una característica denominada el *sistema de archivos de superposición*. Esta característica implementa una tarea de copia en escritura que almacena información actualizada en el sistema de archivos raíz del contenedor. Esa información "pone en la parte superior de" la imagen original en el que se basa el contenedor. Si se elimina el contenedor del sistema, estos cambios se pierden. Por lo tanto, aunque es posible guardar el estado de un contenedor dentro de su almacenamiento local, diseñar un sistema basado en esta característica entraría en conflicto con la premisa de diseño del contenedor, cuyo valor predeterminado es sin estado.

- Sin embargo, los volúmenes de Docker ahora es la mejor manera de controlar los datos locales en Docker. Si necesita obtener más información acerca del almacenamiento en contenedores, consulte en [controladores de almacenamiento de Docker](https://docs.docker.com/engine/userguide/storagedriver/) y [acerca de los controladores de almacenamiento, contenedores y las imágenes](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/).

A continuación proporciona información adicional sobre estas opciones.

Los **volúmenes** son directorios asignados desde el sistema operativo del host a directorios en contenedores. Cuando el código en el contenedor tiene acceso al directorio, ese acceso es realmente a un directorio en el sistema operativo del host. Este directorio no está asociado a la duración del contenedor y Docker lo administra y aísla de la funcionalidad básica de la máquina host. Por tanto, los volúmenes de datos están diseñados para conservar los datos independientemente de la vida del contenedor. Si elimina un contenedor o una imagen del host de Docker, los datos que se conservan en el volumen de datos no se eliminan.

Los volúmenes pueden tener nombre o ser anónimos (predeterminado). Los volúmenes con nombre son la evolución de los **Contenedores de volúmenes de datos** y facilitan el uso compartido de datos entre contenedores. Los volúmenes también admiten controladores de volumen que le permiten almacenar datos en los hosts remotos, entre otras opciones.

**Enlazar montajes** han estado disponibles durante mucho tiempo y permitir la asignación de las carpetas en un punto de montaje en un contenedor. Los montajes de enlace tienen más limitaciones que los volúmenes y algunos problemas de seguridad importantes, por lo que los volúmenes son la opción recomendada.

**`tmpfs` monta** son carpetas virtuales que residen únicamente en memoria del host y nunca se escriben en el sistema de archivos. Son rápidos y seguros, pero usan memoria y solo están diseñados para datos no persistentes.

Tal como se muestra en la figura 4-5, los volúmenes de Docker normales pueden almacenarse fuera de los propios contenedores, pero dentro de los límites físicos del servidor de host o de la máquina virtual. Sin embargo, los contenedores de Docker no pueden tener acceso a un volumen desde un servidor de host o máquina virtual a otro. En otras palabras, con estos volúmenes, no es posible administrar los datos que se comparten entre contenedores que se ejecutan en otros hosts de Docker, aunque se podría lograr con un controlador de volumen que sea compatible con los hosts remotos.

![Los volúmenes se pueden compartir entre contenedores, pero solo en el mismo host, a menos que use un controlador remoto compatible con hosts remotos. ](./media/image5.png)

**Figura 4-5**. Volúmenes y orígenes de datos externos para aplicaciones basadas en contenedor

Además, cuando un orquestador administra los contenedores de Docker, estos podrían "moverse" entre hosts, según las optimizaciones que el clúster realice. Por tanto, no se recomienda usar volúmenes de datos para los datos empresariales. Pero son un buen mecanismo para trabajar con archivos de seguimiento, archivos temporales o similares, no afectará a coherencia de los datos empresariales.

Las herramientas de **orígenes de datos remotos y caché** como Azure SQL Database, Azure Cosmos DB o una caché remota como Redis pueden usarse en aplicaciones en contenedores del mismo modo que se usan al desarrollar sin contenedores. Se trata de una manera comprobada para almacenar datos de aplicaciones empresariales.

**Azure Storage.** Datos económicos normalmente deben colocarse en los recursos externos o bases de datos, como el almacenamiento de Azure. Azure Storage proporciona los siguientes servicios en la nube:

- El almacenamiento de blobs almacena datos de objetos no estructurados. Un blob puede ser cualquier tipo de texto o datos binarios, como documentos o archivos multimedia (archivos de imagen, audio y vídeo). El almacenamiento de blobs también se conoce como "almacenamiento de objetos".

- Almacenamiento de archivos ofrece almacenamiento compartido para aplicaciones heredadas que usan el protocolo SMB estándar. Las máquinas virtuales de Azure y los servicios en la nube pueden compartir datos de archivos en los componentes de la aplicación a través de recursos compartidos montados. Aplicaciones locales pueden tener acceso a datos de archivos en un recurso compartido a través de la API de REST del servicio de archivos.

- El almacenamiento de tabla almacena conjuntos de datos estructurados. El almacenamiento de tabla es un almacén de datos del atributo de clave NoSQL, lo que permite desarrollar y acceder rápidamente a grandes cantidades de datos.

**Bases de datos relacionales y bases de datos NoSQL.** Existen muchas opciones de bases de datos externas, desde las bases de datos relacionales como SQL Server, PostgreSQL u Oracle, o las bases de datos NoSQL como Azure Cosmos DB, MongoDB, etc. Estas bases de datos no va a explicar como parte de esta guía, ya que son un tema diferente por completo.

>[!div class="step-by-step"]
>[Anterior](monolithic-applications.md)
>[Siguiente](soa-applications.md)
