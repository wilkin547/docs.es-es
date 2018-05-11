---
title: Cuándo se debe implementar contenedores de Windows en el servicio de contenedor de Azure (es decir, Kubernetes)
description: Modernizar las aplicaciones .NET existentes con contenedores de Windows y de nube de Azure | Cuándo se debe implementar contenedores de Windows en el servicio de contenedor de Azure (es decir, Kubernetes)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: b7f106e2b79a2c6bb24733debf7f4828505d66a6
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Cuándo se debe implementar contenedores de Windows en el servicio de contenedor de Azure (es decir, Kubernetes)

Servicio de contenedor de Azure optimiza la configuración de tecnologías y herramientas de código abierto populares específicamente para Azure. Obtener una solución abierta que ofrece la portabilidad de los contenedores y para la configuración de la aplicación. Seleccione el tamaño, el número de hosts y las herramientas de orchestrator. Servicio de contenedor de Azure controla la infraestructura de.

Si ya está trabajando con orchestrators de código abierto como Kubernetes, Docker Swarm o DC/OS, no es necesario cambiar sus prácticas de administración existente para mover cargas de trabajo de contenedor en la nube. Usar las herramientas de administración de aplicación que ya está familiarizado con y se conecte a través de los extremos de API estándar por el orquestador de su elección.

Todas estas orchestrators son entornos consolidados si utiliza contenedores de Linux Docker, pero sólo puede estar en estado de vista previa para los contenedores de Windows.

Por ejemplo, en Kubernetes, la compatibilidad con contenedores es nativo (ciudadano de primera clase), por lo que usar contenedores de Windows en Kubernetes también es efectivo (en versión preliminar en ACS a partir de 2018 anticipado).

Nota importante: la evolved y "PaaS más" versión de ACS (servicio de contenedor de Azure) para Kubernetes es AKS (servicio de Kubernetes de Azure), sin embargo, los contenedores de Windows aún no se admiten a partir de Q2 2018, pero se admitirá pronto.

>[!div class="step-by-step"]
[Anterior](when-to-deploy-windows-containers-to-service-fabric.md)
[Siguiente](choosing-azure-compute-options-for-container-based-applications.md)
