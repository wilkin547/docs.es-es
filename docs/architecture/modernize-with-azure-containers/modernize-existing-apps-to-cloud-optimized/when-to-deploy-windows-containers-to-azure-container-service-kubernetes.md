---
title: Cuándo implementar contenedores de Windows en Azure Container Service (es decir, Kubernetes)
description: Modernización de las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | Cuándo implementar contenedores de Windows en Azure Container Service (es decir, Kubernetes)
ms.date: 04/30/2018
ms.openlocfilehash: 903082deba635dd0dfc22d0186fbc589f8d05b92
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577948"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Cuándo implementar contenedores de Windows en Azure Container Service (es decir, Kubernetes)

Azure Container Service optimiza la configuración de las conocidas herramientas y tecnologías de código abierto específicamente para Azure. Obtiene una solución abierta que ofrece portabilidad tanto para los contenedores como para la configuración de la aplicación. Seleccione el tamaño, el número de hosts y las herramientas de Orchestrator. Azure Container Service controla la infraestructura.

Si ya está trabajando con orquestadores de código abierto, como Kubernetes, Docker Swarm o DC/OS, no es necesario cambiar las prácticas de administración existentes para trasladar las cargas de trabajo de los contenedores a la nube. Use las herramientas de administración de aplicaciones con las que ya está familiarizado y conéctese a través de los puntos de conexión de API estándar para el Orchestrator de su elección.

Todos estos orquestadores son entornos maduros si usa contenedores de Docker de Linux, pero solo pueden estar en estado de versión preliminar para contenedores de Windows.

Por ejemplo, en Kubernetes, la compatibilidad con contenedores es nativa (ciudadano de primera clase), por lo que el uso de contenedores de Windows en Kubernetes también es eficaz (en la versión preliminar en ACS a partir de las 2018 primeras).

Nota importante: La versión de ACS y "más PaaS" de ACS (Azure Container Service) para Kubernetes es AKS (Azure Kubernetes Service). sin embargo, los contenedores de Windows todavía no se admiten a partir del 2 Trim 2018, pero pronto se admitirán.

>[!div class="step-by-step"]
>[Anterior](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[Siguiente](choosing-azure-compute-options-for-container-based-applications.md)
