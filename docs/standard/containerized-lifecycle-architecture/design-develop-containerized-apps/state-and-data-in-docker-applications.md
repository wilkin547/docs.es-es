---
title: Estado y los datos en aplicaciones de Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d4b75faffd76a85f9ca1c779ed58bfa37625cff3
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="state-and-data-in-docker-applications"></a>Estado y los datos en aplicaciones de Docker

Un tipo primitivo de contenedores es inmutabilidad. En comparación con una máquina virtual, los contenedores no desaparecen como un hecho frecuente. Una máquina virtual podría producir errores en diversas formas de procesos muertos, sobrecarga de la CPU o un disco completo o con error. Pero, esperamos que la máquina virtual esté disponible y las unidades RAID son comunes para asegurarse de mantienen los datos de errores de disco.

Sin embargo, los contenedores se consideran que son instancias de procesos. Un proceso no mantiene el estado duradero. Aunque puede escribir un contenedor para su almacenamiento local, suponiendo que esa instancia serán indefinidamente alrededor sería equivalente al suponiendo que una única copia de memoria será duradero. Se debe suponer que se duplican contenedores, como procesos, terminar, o cuando se administran con un orquestador del contenedor, se pueden mover.

Docker utiliza una característica que se conoce como un *superposición de sistema de archivos* implementar un proceso de copia en escritura que almacena cualquier información actualizada en el sistema de archivos de la raíz de un contenedor, en comparación con la imagen original en el que se basa. Estos cambios se perderán si posteriormente elimina el contenedor del sistema. Un contenedor, por lo tanto, no tiene almacenamiento persistente de forma predeterminada. Aunque es posible guardar el estado de un contenedor, diseñar un sistema de resolver este problema sería en conflicto con el principio de arquitectura de contenedor.

Para administrar los datos persistentes en aplicaciones de Docker, hay soluciones comunes:

-   [**Volúmenes de datos**](https://docs.docker.com/engine/tutorials/dockervolumes/) estos montaje en el host, como se indicó solo.

-   [**Contenedores de volúmenes de datos**](https://docs.docker.com/engine/tutorials/dockervolumes/#/creating-and-mounting-a-data-volume-container) proporcionan almacenamiento compartido entre todos los contenedores, usando un contenedor externo que puede desplazarse.

-   [**Complementos de volumen**](https://docs.docker.com/engine/tutorials/dockervolumes/#/mount-a-shared-storage-volume-as-a-data-volume) estos montan volúmenes en ubicaciones remotas, proporcionando la persistencia a largo plazo.

-   **Orígenes de datos remotos** los ejemplos incluyen bases de datos SQL y NO SQL o almacenar en caché servicios como Redis.

-   [**Almacenamiento de Azure**](https://docs.microsoft.com/azure/storage/) Esto proporciona plataforma distribuible geográfica como almacenamiento de servicio (PaaS), lo mejor de los contenedores de persistencia como a largo plazo.

Volúmenes de datos se designan especialmente directorios dentro de uno o varios contenedores que omiten el [filesystem unión](https://docs.docker.com/v1.8/reference/glossary#union-file-system). Volúmenes de datos están diseñados para mantener los datos, independientemente del ciclo de vida del contenedor. Docker, por tanto, nunca elimina automáticamente los volúmenes al quitar un contenedor, ni le volúmenes "recopilar de elementos no utilizados" que ya no hace referencia a un contenedor. El sistema operativo host puede examinar y modificar los datos en cualquier volumen libremente, que es simplemente otra razón para usar los volúmenes de datos con moderación.

A [contenedor de volúmenes de datos](https://docs.docker.com/v1.8/userguide/dockervolumes/) es una mejora respecto de los volúmenes de datos normal. Es básicamente un contenedor inactivo que tiene uno o más volúmenes de datos creados dentro del mismo (como se describió anteriormente). El contenedor de volúmenes de datos proporciona acceso a los contenedores desde un punto de montaje central. La ventaja de este método de acceso es que abstrae la ubicación de los datos originales, hacer que el contenedor de datos de un punto de montaje lógico. También permite obtener acceso a los volúmenes del contenedor de datos para crear y destruir manteniendo los datos persistentes en un contenedor dedicado de contenedores de "aplicación".

Figura 4-5 muestra que regular volúmenes de Docker pueden colocarse en un almacenamiento fuera de los propios contenedores pero dentro de los límites físicos de VM/server host. *Volúmenes de docker no tienen la capacidad para usar un volumen de servidor de un host o máquina virtual a otro*.

![](./media/image5.png)

Figura 4-5: volúmenes de datos y orígenes de datos externos para contenedores o aplicaciones de contenedores

Debido a la incapacidad para administrar los datos que se comparten entre contenedores que se ejecutan en hosts físicos independientes, se recomienda que no utilice volúmenes de datos empresariales a menos que el host Docker es una host o VM fija, porque al utilizar contenedores de Docker en Organizador, los contenedores se espera para moverse de uno a otro host, dependiendo de las optimizaciones que debe realizar el clúster.

Por lo tanto, los volúmenes de datos normales son un buen mecanismo para trabajar con archivos de seguimiento, archivos temporales o ningún concepto similar que no afectan a la coherencia de datos de negocio si o cuando se mueven los contenedores en varios hosts.

Complementos de volumen como [Flocker](https://clusterhq.com/flocker/) proporcionar datos a través de todos los hosts en un clúster. Aunque no todos los complementos de volumen se crean por igual, volumen complementos suelen proporcionan externalizado almacenamiento persistente de confianza de los contenedores inmutable.

Orígenes de datos remotos y las memorias caché como base de datos SQL, documentos o una memoria caché remota como Redis podría ser el mismo que desarrollar sin contenedores. Esta es una de las formas preferidas y comprobadas para almacenar datos de aplicaciones de negocios.


>[!div class="step-by-step"]
[Previous] (monolithic-applications.md) [Next] (soa-applications.md)
