---
title: Estado y datos en aplicaciones de Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 78db191bdec4c25c11728d819d89eaaaff4bd7da
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44137270"
---
# <a name="state-and-data-in-docker-applications"></a>Estado y datos en aplicaciones de Docker

Un tipo primitivo de contenedores es la inmutabilidad. En comparación con una máquina virtual, no desaparecen contenedores como un hecho frecuente. Una máquina virtual puede producir un error en diversas formas de procesos caducos, sobrecarga de la CPU o un disco completo o con errores. Sin embargo, esperamos que la máquina virtual esté disponible y unidades RAID son típicos para asegurarse de mantienen los datos de errores de disco.

Sin embargo, los contenedores se consideran las instancias de procesos. Un proceso no mantiene el estado duradero. Aunque puede escribir un contenedor para su almacenamiento local, suponiendo que esa instancia permanecerá indefinidamente sería equivalente a suponiendo que una copia única de memoria será duradera. Debe suponer que los contenedores, como procesos, están duplicados, elimina, o cuando se administran con un orquestador de contenedores, se puede mover.

Docker usa una característica conocida como una *sistema de archivos de superposición* implementar un proceso de copia en escritura que almacena cualquier información actualizada en el sistema de archivos raíz de un contenedor, en comparación con la imagen original en el que se basa. Estos cambios se perderán si posteriormente se elimina el contenedor del sistema. Un contenedor, por lo tanto, no tiene almacenamiento persistente de forma predeterminada. Aunque es posible guardar el estado de un contenedor, diseñar un sistema de solucionar este problema sería en conflicto con el principio de arquitectura de contenedor.

Para administrar datos persistentes en aplicaciones de Docker, hay soluciones comunes:

-   [**Los volúmenes de datos**](https://docs.docker.com/engine/tutorials/dockervolumes/) estos se montan en el host, como se indicó simplemente.

-   [**Contenedores de volúmenes de datos**](https://docs.docker.com/engine/tutorials/dockervolumes/#/creating-and-mounting-a-data-volume-container) proporcionan almacenamiento compartido entre todos los contenedores, mediante un contenedor externo que puede realizar un recorrido.

-   [**Complementos de volumen**](https://docs.docker.com/engine/tutorials/dockervolumes/#/mount-a-shared-storage-volume-as-a-data-volume) estos montan volúmenes en ubicaciones remotas, que proporciona persistencia a largo plazo.

-   **Orígenes de datos remotos** los ejemplos incluyen bases de datos SQL y NO SQL o servicios de caché como Redis.

-   [**Almacenamiento de Azure**](https://docs.microsoft.com/azure/storage/) Esto proporciona la plataforma de distribución geográfica como almacenamiento de servicio (PaaS), que ofrece la mejor de los contenedores de persistencia a largo plazo como.

Los volúmenes de datos especialmente designados directorios dentro de uno o varios contenedores que omiten el [unión del sistema de archivos](https://docs.docker.com/glossary/?term=Union%20file%20system). Los volúmenes de datos están diseñados para mantener los datos, independientemente del ciclo de vida del contenedor. Docker, por tanto, nunca elimina automáticamente los volúmenes cuando se quita un contenedor, ni tampoco lo volúmenes "recopilación de elementos no utilizados" que ya no se hace referencia a un contenedor. El sistema operativo host puede examinar y editar los datos en cualquier volumen libremente, que es simplemente otra razón para usar los volúmenes de datos con moderación.

Un [contenedor de volúmenes de datos](https://docs.docker.com/glossary/?term=volume) es una mejora de los volúmenes de datos normales. Es básicamente un contenedor inactivo que tiene uno o más volúmenes de datos creados dentro de él (como se describió anteriormente). El contenedor de volúmenes de datos proporciona acceso a los contenedores desde un punto de montaje central. La ventaja de este método de acceso es que abstrae la ubicación de los datos originales, hacer que el contenedor de datos de un punto de montaje lógico. También permite obtener acceso a los volúmenes del contenedor de datos para crear y destruir manteniendo los datos persistentes en un contenedor dedicado de contenedores de "aplicación".

Figura 4-5 se muestra que los volúmenes de Docker normales pueden colocarse en almacenamiento fuera de los propios contenedores, pero dentro de los límites físicos del servidor o máquina virtual host. *Volúmenes de docker no tienen la capacidad para usar un volumen de servidor en un host o máquina virtual a otro*.

![](./media/image5.png)

Figura 4-5: volúmenes de datos y orígenes de datos externos para aplicaciones de contenedores, contenedores

Debido a la incapacidad para administrar los datos que se comparten entre contenedores que se ejecutan en hosts físicos independientes, se recomienda que no utilice volúmenes de datos empresariales a menos que el host de Docker es una host o VM fija, porque cuando se usa contenedores de Docker en un orquestador, los contenedores se esperan que se ha movido de uno a otro host, según las optimizaciones que debe realizar el clúster.

Por lo tanto, los volúmenes de datos regulares son un buen mecanismo para trabajar con archivos de seguimiento, archivos temporales o ningún concepto similar que no afectan a la coherencia de datos de negocio si o cuando se mueven los contenedores en varios hosts.

[Los complementos de volumen](https://docs.docker.com/engine/extend/plugins_volume/) proporcionar datos a través de todos los hosts en un clúster. Aunque no todos los complementos de volumen se crean por igual, los complementos de volumen normalmente proporcionan almacenamiento confiable persistente externalizado desde los contenedores inmutables.

Orígenes de datos remotos y las memorias caché, como SQL Database, DocumentDB o una caché remota como Redis sería igual a desarrollar sin contenedores. Esta es una de las formas preferidas y probadas para almacenar datos de aplicaciones empresariales.


>[!div class="step-by-step"]
[Anterior](monolithic-applications.md)
[Siguiente](soa-applications.md)
