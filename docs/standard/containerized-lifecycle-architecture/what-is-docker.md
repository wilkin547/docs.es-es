---
title: "¿Qué es Docker?"
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/21/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c75b2fa87e5aad93693c76c3bbd135044b36525f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="what-is-docker"></a>¿Qué es Docker?

[Docker](https://www.docker.com/) es un [proyecto de código abierto](https://github.com/docker/docker) para automatizar la implementación de aplicaciones como portátiles, autosuficientes contenedores que se pueden ejecutar en la nube o local (vea la figura 1 - 2). Docker es también un [empresa](https://www.docker.com/) que promociona y desarrolla esta tecnología, trabajar en colaboración con la nube, Linux y los proveedores de Windows, incluidos los de Microsoft.

![](./media/image2.png)

Figura 1-2: Docker implementa contenedores en todas las capas de la nube híbrida

Contenedores de imagen de docker pueden ejecutar de forma nativa en Linux y Windows. Sin embargo, las imágenes de Windows sólo pueden ejecutarse en hosts de Windows y Linux imágenes sólo pueden ejecutarse en hosts de Linux, lo que significa que un servidor de host o una máquina virtual.

Los desarrolladores pueden utilizar los entornos de desarrollo en Windows, Linux o Mac OS. En el equipo de desarrollo, el programador ejecuta en un host de Docker a qué Docker se implementan imágenes, incluida la aplicación y sus dependencias. Los desarrolladores que trabajan en Linux o en el Mac, usan un host Docker basados en Linux, y pueden crear imágenes solo para los contenedores de Linux. (Los desarrolladores que trabajan en el Mac, pueden editar código o ejecutar la interfaz de línea de comandos de Docker \[CLI\] de macOS, pero, cuando se redactó este documento, los contenedores no se ejecutan directamente en macOS.) Los desarrolladores que trabajan en Windows pueden crear imágenes de contenedores de Windows o Linux.

Para hospedar contenedores en entornos de desarrollo y proporcionan herramientas adicionales para los programadores, se distribuye Docker [Docker Community Edition (CE)](https://www.docker.com/community-edition) para Windows o Mac OS. Estos productos instalan la máquina virtual es necesaria (el host de Docker) para alojar los contenedores. Docker también pone a disposición [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition), que está diseñado para el desarrollo empresarial y es utilizado por los equipos de TI que crean, distribuir y ejecutar aplicaciones cruciales para la empresa de gran tamaño en producción.

Para ejecutar [contenedores de Windows](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview), hay dos tipos de tiempos de ejecución:

-   **Contenedor de Windows Server** este tiempo de ejecución proporciona aislamiento de aplicaciones mediante tecnología de aislamiento de proceso y espacio de nombres. Un contenedor de Windows Server comparte el kernel con el host de contenedor y todos los contenedores que se ejecutan en el host.

-   **Contenedor de Hyper-V** esta opción se expande el aislamiento que ofrecen los contenedores de Windows Server mediante la ejecución de cada contenedor en una máquina virtual altamente optimizada. En esta configuración, no se comparte el kernel del host del contenedor con los contenedores de Hyper-V, lo que proporciona un mejor aislamiento.

Las imágenes de estos contenedores se crean de la misma manera y funcionan del mismo. La diferencia radica en cómo se crea el contenedor de la imagen, la ejecución de un contenedor de Hyper-V requiere un parámetro adicional. Para obtener más información, consulte [contenedores de Hyper-V](https://msdn.microsoft.com/virtualization/windowscontainers/about/about_overview).

## <a name="comparing-docker-containers-with-vms"></a>Comparar contenedores de Docker con máquinas virtuales

Figura 1-3 muestra una comparación entre las máquinas virtuales y Docker contenedores.

Dado que los contenedores requieren mucho menos recursos (por ejemplo, que no necesitan un sistema operativo completo), son fáciles de implementar y comenzar rápidamente. Esto permite tener una mayor densidad, lo que significa que puede ejecutar más servicios en la misma unidad de hardware, lo que reduce los costos.

Como efecto secundario de la ejecución en el mismo kernel, se logra el aislamiento de menor que las máquinas virtuales.

El objetivo principal de una imagen es que lo hace el entorno (dependencias) el mismo entre las distintas implementaciones. Esto significa que puede depurar en su equipo y, a continuación, implementarlo en otro equipo con el mismo entorno garantizado.

Una imagen de contenedor es una manera para empaquetar una aplicación o servicio e implementarlo de forma confiable y reproducible. En este sentido, Docker no es solo una tecnología, también es una filosofía y un proceso.

Cuando se utiliza Docker, no podrá escuchar a los desarrolladores dice, "Funciona en mi equipo, ¿por qué no en producción?" Puede decir sencillamente, "Runs en Docker," porque la aplicación empaquetada de Docker se puede ejecutar en cualquier entorno compatible con Docker, y se ejecutará la manera en que se pretende en todos los destinos de implementación (desarrollo, control de calidad, almacenamiento provisional, producción, etcetera.).

![](./media/image3.png)

Figura 1-3: comparación de máquinas virtuales tradicionales en contenedores Docker


>[!div class="step-by-step"]
[Previous] (index.md) [Next] (docker-terminology.md)
