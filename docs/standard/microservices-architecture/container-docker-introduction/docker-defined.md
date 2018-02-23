---
title: "¿Qué es Docker?"
description: "Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | ¿Qué es Docker?"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a079a3303d1e1fed9a8df2dca2c5627beb0c672d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="what-is-docker"></a>¿Qué es Docker?

[Docker](https://www.docker.com/) es un [proyecto de código abierto](https://github.com/docker/docker) para automatizar la implementación de aplicaciones como contenedores portátiles y autosuficientes que se pueden ejecutar en la nube o localmente. Docker es también una [empresa](https://www.docker.com/) que promueve esta tecnología y la hace evolucionar. Docker funciona en colaboración con la nube, Linux y los proveedores de Windows, incluido Microsoft.

![](./media/image2.png)

**Figura 2-2**. Docker implementa contenedores en todas las capas de la nube híbrida

Los contenedores de imagen de Docker se ejecutan de forma nativa en Linux y Windows. Las imágenes de Windows solo se ejecutan en hosts de Windows y las imágenes de Linux solo se ejecutan en hosts de Linux. El host es un servidor o una máquina virtual.

Puede desarrollar en Windows, Linux o macOS. El equipo de desarrollo ejecuta un host de Docker en que se implementan imágenes de Docker, incluidas la aplicación y sus dependencias. En Linux o macOS, debe usar un host de Docker basado en Linux y puede crear imágenes solo para los contenedores de Linux. (En macOS puede editar código o ejecutar la CLI de Docker, pero en el momento de redactar este artículo los contenedores no se ejecutan directamente en macOS). En Windows, puede crear imágenes para contenedores de Windows o Linux.

En Windows o macOS, [Docker Community Edition (CE)](https://www.docker.com/community-edition) aloja contenedores en un entorno de desarrollo y proporciona herramientas de desarrollador adicionales. [Docker Enterprise Edition (EE)](https://www.docker.com/enterprise-edition) es usado por los equipos de TI que compilan, distribuyen y ejecutan aplicaciones fundamentales para la empresa de gran tamaño. ~Ambos productos instalan la máquina virtual necesaria (el host de Docker) para alojar los contenedores.~ 

Los [contenedores de Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) funcionan con dos tipos de tiempos de ejecución:

-   Los contenedores de Windows Server ofrecen aislamiento de aplicaciones a través de tecnología de aislamiento de proceso y de espacio de nombres. Un contenedor de Windows Server comparte el kernel con el host de contenedor y con todos los contenedores que se ejecutan en el host.

-   Los contenedores de Hyper-V amplían el aislamiento que ofrecen los contenedores de Windows Server mediante la ejecución de cada contenedor en una máquina virtual altamente optimizada. En esta configuración, el kernel del host del contenedor no se comparte con los contenedores de Hyper-V, lo que proporciona un mejor aislamiento. Los contenedores de Hyper-V permiten que las aplicaciones que no sean de confianza y las *multiinquilino hostiles* se ejecuten en el mismo host. Los contenedores de Hyper-V son un poco menos eficaces en cuanto a tiempo de inicio y densidad que los contenedores de Windows Server.

Las imágenes de estos contenedores se crean y funcionan de la misma manera. Difieren en cómo se crea el contenedor. Para más información, vea [Contenedores de Hyper-V](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview).

## <a name="comparing-docker-containers-with-virtual-machines"></a>Comparación de los contenedores de Docker con las máquinas virtuales

En la figura 2-3 se muestra una comparación entre las máquinas virtuales y los contenedores de Docker.

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **Máquinas virtuales**                                                                                                                                                                  **Contenedores de Docker**
                                                                                                                                                                                        
  ![](./media/image3.png)                                                                                                                                ![](./media/image4.png)
                                                                                                                                                                                        
  Las máquinas virtuales incluyen la aplicación, las bibliotecas o los archivos binarios necesarios y un sistema operativo invitado completo. La virtualización completa requiere más recursos que la inclusión en contenedores. Los contenedores incluyen la aplicación y todas sus dependencias. No obstante, los contenedores comparten el kernel del sistema operativo con otros contenedores. Los contenedores se ejecutan como procesos aislados en el espacio de usuario del sistema operativo host. Excepto en los contenedores de Hyper-V, en que cada contenedor se ejecuta dentro de una máquina virtual especial por contenedor.
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**Figura 2-3**. Comparación de las máquinas virtuales tradicionales con los contenedores de Docker

Dado que los contenedores requieren muchos menos recursos (por ejemplo, no necesitan un sistema operativo completo), se inician rápidamente y son fáciles de implementar. El uso de pocos recursos permite una mayor densidad. Puede ejecutar más servicios en la misma unidad de hardware y reducir los costos.

La ejecución en el mismo kernel produce menos aislamiento que el que proporcionan las máquinas virtuales.

El objetivo principal de una imagen es que hace que el entorno (dependencias) sea el mismo entre las distintas implementaciones. Esto significa que puede depurarlo en su equipo y, a continuación, implementarlo en otra máquina con el mismo entorno garantizado.

Una imagen de contenedor es una manera de empaquetar una aplicación o un servicio e implementarlo de forma confiable y reproducible. Podría decir que Docker no solo es una tecnología, sino también una filosofía y un proceso.

Los desarrolladores de Docker no dicen, "Si funciona en mi máquina, ¿por qué no en producción?" Dicen, "Se ejecuta en Docker". Las aplicaciones empaquetadas en Docker se pueden ejecutar en cualquier entorno compatible con Docker. Las aplicaciones empaquetadas en Docker se ejecutan de forma coherente en todos los destinos de implementación (desarrollo, control de calidad, almacenamiento provisional, producción).

>[!div class="step-by-step"]
[Previous] (index.md) [Next] (docker-terminology.md)
