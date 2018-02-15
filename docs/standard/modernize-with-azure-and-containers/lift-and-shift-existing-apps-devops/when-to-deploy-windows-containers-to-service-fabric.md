---
title: "Cuándo se debe implementar contenedores de Windows en Service Fabric"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Cuándo se debe implementar contenedores de Windows en Service Fabric"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f848c61fe49f9c2e883b422b574758ffac931229
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="when-to-deploy-windows-containers-to-service-fabric"></a>Cuándo se debe implementar contenedores de Windows en Service Fabric

Las aplicaciones que se basan en los contenedores de Windows rápidamente deberán usan las plataformas que se mueven aún más alejada de las máquinas virtuales IaaS. Esto para mejorar la escalabilidad automatizada y de alta escalabilidad, y obtener mejoras significativas en una experiencia de administración completa para las implementaciones, actualizaciones, control de versiones, reversiones y la supervisión del estado. Puede lograr estos objetivos con el orchestrator Azure Service Fabric, disponible en la nube de Microsoft Azure, sino también en local, o incluso en otra nube.

Muchas organizaciones están levantar y desplazar las aplicaciones monolíticas existentes a los contenedores por dos motivos:

-   Reducción de costos, ya sea debido a la consolidación y eliminación de hardware existente, o mediante la ejecución de aplicaciones en una mayor densidad.

-   Un contrato de implementación coherente entre el desarrollo y las operaciones.

Intentando obtener reducciones de costos es comprensible, y es probable que todas las organizaciones persiguen ese objetivo. Es más difícil de implementación coherente evaluar, pero es igualmente como importantes. Un contrato de implementación coherente dice que los desarrolladores pueden optar por usar la tecnología que se adapte a ellos, y el equipo de operaciones obtiene una única manera de implementar y administrar aplicaciones. Este contrato alivia el problema de tener las operaciones de tratar la complejidad de las muchas tecnologías diferentes, o forzar a los programadores trabajar solo con determinadas tecnologías. Básicamente, cada aplicación está en contenedores en una imagen de implementación independiente.

Algunas organizaciones continuará modernizado agregando microservicios (aplicaciones optimizada para la nube y en la nube nativo). Muchas organizaciones se detendrá aquí (DevOps preparada para la nube). Como se muestra en la figura 4-8, estas organizaciones no mover a las arquitecturas de microservicios porque no es posible que deba. En cualquier caso, ya Obtenga las ventajas que usar contenedores suma Service Fabric experiencia de administración proporciona una completa que incluye la implementación, actualiza, control de versiones, reversiones y supervisión de estado.

> ![Levantar y mover una aplicación a Service Fabric](./media/image8.png)
>
> **Figura 4-8.** Levantar y mover una aplicación a Service Fabric

Un método clave para Service Fabric es reutilizar código existente y simplemente levantar y mover. Por lo tanto, puede migrar las aplicaciones de .NET Framework actuales, mediante el uso de contenedores de Windows e implementarlas en Service Fabric. Le resultará más fácil mantener va modernizado, finalmente, agregando nuevos microservicios.

Cuando se comparan a Service Fabric a otros orchestrators, es importante resaltar que Service Fabric es muy consistente en ejecutar los servicios y aplicaciones basadas en Windows. Se ha estado ejecutando Service Fabric servicios basados en Windows y aplicaciones, incluidos los productos de nivel 1, críticas de Microsoft, para años. Es el primer orchestrator tener disponibilidad general para los contenedores de Windows (mayo de 2017). Otros contenedores, como Kubernetes, DC/OS y Docker Swarm, son más maduros en Linux, pero menos maduro que el de tejido de servicio para Windows-based applications y contenedores de Windows.

El objetivo final de Service Fabric es reducir las complejidades de la creación de aplicaciones mediante un enfoque de microservicios. Esto es que finalmente se desea que sean para determinados tipos de aplicaciones, para evitar volver a diseñar costosa. Puede empezar siendo pequeños, escalar cuando sea necesario, dejar de utilizar servicios, agregar nuevos servicios y desarrollar su aplicación con el uso de los clientes. Sabemos que existen muchos otros problemas que todavía hay que resolver para hacer que microservicios sea más accesible para la mayoría de los desarrolladores. Si actualmente se acaba levantar y desplazamiento de una aplicación con contenedores de Windows, pero está pensando en Agregar microservicios basándose en los contenedores en el futuro, es la zona de acción de Service Fabric.

>[!div class="step-by-step"]
[Anterior](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Siguiente](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
