---
title: "¿Qué es Docker?"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | ¿Qué es Docker?"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: aa9cb379628fa91e5dc5b1b529f92db98fa59305
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="what-is-docker"></a>¿Qué es Docker?

[Docker](https://www.docker.com/) es un [proyecto de código abierto](https://github.com/docker/docker) para automatizar la implementación de aplicaciones como portátiles, autosuficientes contenedores que se pueden ejecutar en la nube o local. Docker es también un [empresa](https://www.docker.com/) que promueve y evoluciona esta tecnología. Docker funciona en colaboración con la nube, Linux y los proveedores de Windows, incluidos los de Microsoft.

![](./media/image2.png)

**Figura 2-2**. Docker implementa contenedores en todas las capas de la nube híbrida

Contenedores de imagen de docker se ejecuten de forma nativa en Windows y Linux. Imágenes de Windows solo se ejecutan en hosts de Windows y Linux imágenes solo se ejecutan en hosts de Linux. El host es un servidor o una máquina virtual.

Puede desarrollar en Windows, Linux o Mac OS. El equipo de desarrollo ejecuta un host Docker donde se implementan imágenes de Docker, incluida la aplicación y sus dependencias. En Linux o Mac OS, utilice un host Docker en función de Linux y puede crear imágenes solo para los contenedores de Linux. (En Mac OS puede editar código o ejecutar la CLI de Docker, pero en el momento de redactar este artículo, los contenedores no se ejecutan directamente en Mac OS). En Windows puede crear imágenes de contenedores de Windows o Linux.

En Windows o Mac OS, [Docker Community Edition (CE)](https://www.docker.com/community-edition) hospeda contenedores en un entorno de desarrollo y proporciona otras herramientas de desarrollador. [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition) utilizado por los equipos de TI que compilación, distribuyen y ejecutan aplicaciones cruciales para la empresa de gran tamaño. ~ Ambos productos instalan la máquina virtual es necesaria (el host de Docker) para alojar los contenedores. ~ 

[Contenedores de Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) funcionan con los dos tipos de tiempos de ejecución:

-   Contenedores de Windows Server ofrecen aislamiento de aplicaciones mediante tecnología de aislamiento de proceso y espacio de nombres. Un contenedor de Windows Server comparte el kernel con el host de contenedor y todos los contenedores que se ejecutan en el host.

-   Contenedores de Hyper-V amplían el aislamiento que ofrecen los contenedores de Windows Server mediante la ejecución de cada contenedor en una máquina virtual altamente optimizada. En esta configuración, no se comparte el kernel del host del contenedor con los contenedores de Hyper-V, lo que proporciona un mejor aislamiento. Contenedores de Hyper-V permite no son de confianza y *multiempresa hostil* aplicaciones se ejecuten en el mismo host. Contenedores de Hyper-V tienen un poco menos eficacia de tiempos de inicio y la densidad de contenedores de Windows Server.

Las imágenes de estos contenedores se crean y funcionan de la misma manera. Difieren en cómo se crea el contenedor. Para obtener más información, consulte [contenedores de Hyper-V](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview).

## <a name="comparing-docker-containers-with-virtual-machines"></a>Comparar contenedores de Docker con máquinas virtuales

Figura 2-3 muestra una comparación entre las máquinas virtuales y Docker contenedores.

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **Máquinas virtuales****contenedores de Docker** 
                                                                                                                                                                                        
  ![](./media/image3.png)                                                                                                                                ![](./media/image4.png)
                                                                                                                                                                                        
  Máquinas virtuales incluyen la aplicación, las bibliotecas necesarias o archivos binarios y un sistema operativo invitado completa. La virtualización completa requiere más recursos que la inclusión en contenedores. Los contenedores incluyen la aplicación y todas sus dependencias. No obstante, los contenedores comparten el núcleo del sistema operativo con otros contenedores. Contenedores se ejecutan como procesos aislados en el espacio de usuario en el sistema operativo host. Excepto en los contenedores de Hyper-V, donde cada contenedor se ejecuta dentro de una máquina virtual especial por contenedor.
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**Figura 2-3**. Comparación de las máquinas virtuales tradicionales en contenedores Docker

Dado que los contenedores requieren mucho menos recursos (por ejemplo, que no necesitan un sistema operativo completo), se inician rápidamente y son fáciles de implementar. Uso de pocos recursos permite una mayor densidad. Puede ejecutar más servicios en la misma unidad de hardware y reducir los costos.

Se ejecuta en el mismo kernel da como resultado menos aislamiento que proporcionan las máquinas virtuales.

El objetivo principal de una imagen es que lo hace el entorno (dependencias) el mismo entre las distintas implementaciones. Esto significa que puede depurar en su equipo y, a continuación, implementarlo en otro equipo con el mismo entorno garantizado.

Una imagen de contenedor es una manera para empaquetar una aplicación o servicio e implementarlo de forma confiable y reproducible. Podría decir que Docker no sólo es una tecnología, pero también una filosofía y un proceso.

Los desarrolladores de docker no se debe decir, "Funciona en mi equipo, ¿por qué no en producción?" Se dice, "Runs en Docker". Aplicaciones empaquetadas docker se pueden ejecutar en cualquier entorno compatible con Docker. Docker empaqueta aplicaciones que se ejecuten de forma coherente en todos los destinos de implementación (desarrollo, control de calidad, almacenamiento provisional, producción).

>[!div class="step-by-step"]
[Anterior] (index.md) [siguiente] (docker-terminology.md)
