---
title: Cuándo se deben implementar contenedores de Windows en Service Fabric
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Cuándo se deben implementar contenedores de Windows en Service Fabric
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 01d76f325480c7cf09fef36b02589a602e3ee11e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973651"
---
# <a name="when-to-deploy-windows-containers-to-service-fabric"></a>Cuándo se deben implementar contenedores de Windows en Service Fabric

Las aplicaciones que se basan en los contenedores de Windows rápidamente deba usar las plataformas que mueven aún más lejos de máquinas virtuales de IaaS. Esto es para una mejor escalabilidad automatizada y de alta escalabilidad, y obtener mejoras significativas en una experiencia de administración completa para las implementaciones, actualiza, control de versiones, reversiones y la supervisión de estado. Puede lograr estos objetivos con el orquestador de Azure Service Fabric, disponible en la nube de Microsoft Azure, sino también de forma local, o incluso en otra nube.

Muchas organizaciones están levantando y moviendo las aplicaciones monolíticas existentes a contenedores por dos motivos:

- Reducción de costos, ya sea debido a la consolidación y la eliminación del hardware existente, o mediante la ejecución de aplicaciones en una mayor densidad.

- Un contrato de la implementación coherente entre el desarrollo y operaciones.

Intentando obtener reducciones de costos es comprensible, y es probable que todas las organizaciones persiguen ese objetivo. Una implementación coherente es más difícil de evaluar, pero es igualmente importante. Un contrato de la implementación coherente dice que los desarrolladores tienen libertad para optar por usar la tecnología que les convenga, y el equipo de operaciones obtiene una única manera de implementar y administrar aplicaciones. Este contrato alivia la dificultad de tener las operaciones de tratar la complejidad de las muchas tecnologías diferentes, o forzar a los desarrolladores trabajar sólo con determinadas tecnologías. Básicamente, cada aplicación está en contenedores en una imagen de implementación independiente.

Algunas organizaciones seguirán Modernización mediante la adición de microservicios (aplicaciones nativas de nube), pero muchas otras organizaciones detienen aquí (aplicaciones optimizadas para la nube). Como se muestra en la figura 4-8, estas organizaciones no se moverá a las arquitecturas de microservicios porque es posible que no necesitan. En cualquier caso, ya obtener ventajas que mediante contenedores además de Service Fabric experiencia de administración proporciona una completa que incluye la implementación, se actualizan, control de versiones, reversiones y la supervisión de estado.

> ![Levantar y mover una aplicación en Service Fabric](./media/image8.png)
>
> **Figura 4-8.** Levantar y mover una aplicación en Service Fabric

Un enfoque clave en Service Fabric es reutilizar código existente y levantar y mover. Por lo tanto, puede migrar las aplicaciones de .NET Framework actuales, mediante contenedores de Windows e implementarlas en Service Fabric. Le resultará más fácil mantener va modernización, finalmente, mediante la adición de nuevos microservicios.

Cuando Service Fabric en comparación con otros orquestadores, es importante destacar que Service Fabric está más desarrollado en la ejecución de servicios y aplicaciones basadas en Windows. Service Fabric se ha estado ejecutando servicios basados en Windows y aplicaciones, incluidos los productos de misión crítica, de nivel 1 de Microsoft durante años. Fue la primera orchestrator tener disponibilidad general para contenedores de Windows. Otros contenedores, como Kubernetes, DC/OS y Docker Swarm, son más maduros en Linux, pero menos maduro que Service Fabric para Windows-based applications y contenedores de Windows.

El objetivo de Service Fabric es reducir las complejidades de la creación de aplicaciones mediante el uso de un enfoque de microservicios. Finalmente, desea un microservicios para ciertos tipos de aplicaciones para evitar el costoso volver. Puede empiece poco a poco, escale cuando sea necesario, dejar de utilizar los servicios, agregar nuevos servicios y evolucionar la aplicación con el uso del cliente. Hay muchos otros problemas que aún deben resolverse para que los microservicios sean más accesibles para la mayoría de los desarrolladores. Si actualmente está simplemente levantando y moviendo una aplicación con contenedores de Windows, pero piensa agregar microservicios que se basa en contenedores en el futuro, es el uso más idóneo Service Fabric.

>[!div class="step-by-step"]
>[Anterior](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
>[Siguiente](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)