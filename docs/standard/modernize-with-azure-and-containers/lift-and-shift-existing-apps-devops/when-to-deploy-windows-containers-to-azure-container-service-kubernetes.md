---
title: "Cuándo se debe implementar contenedores de Windows en el servicio de contenedor de Azure (es decir, Kubernetes)"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Cuándo se debe implementar contenedores de Windows en el servicio de contenedor de Azure (es decir, Kubernetes)"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2f7ed0c9ebf1c80ae6cae4311b2682d3cc161623
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Cuándo se debe implementar contenedores de Windows en el servicio de contenedor de Azure (es decir, Kubernetes)

Servicio de contenedor de Azure optimiza la configuración de tecnologías y herramientas de código abierto populares específicamente para Azure. Obtener una solución abierta que ofrece la portabilidad de los contenedores y para la configuración de la aplicación. Seleccione el tamaño, el número de hosts y las herramientas de orchestrator. Servicio de contenedor de Azure controla la infraestructura de.

Si ya está trabajando con orchestrators de código abierto como Kubernetes, Docker Swarm o DC/OS, no es necesario cambiar sus prácticas de administración existente para mover cargas de trabajo de contenedor en la nube. Use las herramientas de administración de la aplicación que ya está familiarizado con y conectarse a través de los extremos de API estándar para el orquestador de su elección.

Todas estas orchestrators son entornos consolidados si utilizas contenedores de Linux Docker, pero también compatibilidad con contenedores de Windows como de 2017 (algunos anteriormente, algunos más recientemente, según el orchestrator).

Por ejemplo, en Kubernetes, la compatibilidad con contenedores es nativo (ciudadano de primera clase), por lo que usar contenedores de Windows en Kubernetes también es muy eficaz y confiable (en vista previa hasta una fase temprana quedan 2017).

>[!div class="step-by-step"]
[Anterior](when-to-deploy-windows-containers-to-service-fabric.md)
[Siguiente](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
