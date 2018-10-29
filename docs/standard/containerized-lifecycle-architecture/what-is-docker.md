---
title: ¿Qué es Docker?
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.openlocfilehash: 056fb613c078cc407380060dc11890406ac8cffd
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2018
ms.locfileid: "50197683"
---
# <a name="what-is-docker"></a>¿Qué es Docker?

[Docker](https://www.docker.com/) es un [proyecto de código abierto](https://github.com/docker/docker) para automatizar la implementación de aplicaciones como contenedores portátiles y autosuficientes que se pueden ejecutar en la nube o local (consulte la figura 1 - 2). Docker es también un [empresa](https://www.docker.com/) que promueve y desarrolla esta tecnología, trabajar en colaboración con la nube, Linux y los proveedores de Windows, incluido Microsoft.

![](./media/image2.png)

Figura 1-2: Docker implementa contenedores en todas las capas de la nube híbrida

Los contenedores de imagen de Docker se pueden ejecutar de forma nativa en Linux y Windows. Sin embargo, las imágenes de Windows sólo pueden ejecutarse en hosts de Windows y las imágenes de Linux solo pueden ejecutarse en hosts de Linux, lo que significa que un servidor de host o una máquina virtual.

Los desarrolladores pueden usar entornos de desarrollo en Windows, Linux o macOS. En el equipo de desarrollo, el programador ejecuta en un host de Docker para que Docker se implementan imágenes, incluida la aplicación y sus dependencias. Los desarrolladores que trabajan en Linux o en Mac usan un host de Docker basado en Linux y pueden crear imágenes solo para contenedores de Linux. (Los desarrolladores que trabajan en el equipo Mac pueden editar código o ejecutar la interfaz de línea de comandos de Docker \[CLI\] de macOS, pero, cuando se redactó este documento, los contenedores no se ejecutan directamente en macOS.) Los desarrolladores que trabajan en Windows pueden crear imágenes para contenedores de Windows o Linux.

Para hospedar contenedores en entornos de desarrollo y proporcionar herramientas de desarrollador adicionales, Docker entrega [Docker Community Edition (CE)](https://www.docker.com/community-edition) para Windows o macOS. Estos productos instalan la máquina virtual necesaria (el host de Docker) para hospedar los contenedores. Docker también pone a disposición [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition), que está diseñado para el desarrollo empresarial y se usa en los equipos de TI que crean, envían y ejecutan aplicaciones críticas para la empresa en producción.

Para ejecutar [contenedores de Windows](/virtualization/windowscontainers/about/), hay dos tipos de tiempos de ejecución:

-   **Contenedor de Windows Server** este tiempo de ejecución proporciona aislamiento de aplicaciones mediante tecnología de aislamiento de proceso y espacio de nombres. Un contenedor de Windows Server comparte el kernel con el host de contenedor y con todos los contenedores que se ejecutan en el host.

-   **Contenedor de Hyper-V** Esto amplía el aislamiento que ofrecen los contenedores de Windows Server mediante la ejecución de cada contenedor en una máquina virtual altamente optimizada. En esta configuración, el kernel del host del contenedor no se comparte con los contenedores de Hyper-V, lo que proporciona un mejor aislamiento.

Las imágenes de estos contenedores se crean en la misma manera y funcionan del mismo. La diferencia radica en cómo se crea el contenedor de la imagen, la ejecución de un contenedor de Hyper-V requiere un parámetro adicional. Para más información, vea [Contenedores de Hyper-V](/virtualization/windowscontainers/about/).

## <a name="comparing-docker-containers-with-vms"></a>Comparar contenedores de Docker con máquinas virtuales

Figura 1-3 se muestra una comparación entre las máquinas virtuales y Docker contenedores.

Dado que los contenedores requieren muchos menos recursos (por ejemplo, que no necesitan un sistema operativo completo), son fáciles de implementar y se crean con rapidez. Esto permite tener una mayor densidad, lo que significa que puede ejecutar más servicios en la misma unidad de hardware, lo que reduce los costos.

Como efecto secundario de que se ejecutan en el mismo kernel, lograr menos aislamiento que las máquinas virtuales.

El objetivo principal de una imagen es que hace que el entorno (dependencias) sea el mismo entre las distintas implementaciones. Esto significa que puede depurarlo en su equipo y, a continuación, implementarlo en otra máquina con el mismo entorno garantizado.

Una imagen de contenedor es una manera de empaquetar una aplicación o servicio e implementarlo de forma confiable y reproducible. En este sentido, Docker no es sólo una tecnología, también es una filosofía y un proceso.

Cuando se usa Docker, no podrá escuchar a los desarrolladores dicen, "Funciona en mi equipo, ¿por qué no en producción?" Puede simplemente dicen, "Runs en Docker," porque se puede ejecutar la aplicación de Docker empaquetada en cualquier entorno compatible con Docker y ejecutará la manera en que se pretende en todos los destinos de implementación (desarrollo, control de calidad, almacenamiento provisional, producción, etcetera.).

![](./media/image3.png)

Figura 1-3: comparación de las máquinas virtuales tradicionales en contenedores de Docker


>[!div class="step-by-step"]
[Anterior](index.md)
[Siguiente](docker-terminology.md)
