---
title: Cuándo se deben implementar contenedores de Windows en Azure Container Service (es decir, Kubernetes)
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Cuándo se deben implementar contenedores de Windows en Azure Container Service (es decir, Kubernetes)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 0b803b104f905fddac7939d7b070c206aabffeda
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144798"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Cuándo se deben implementar contenedores de Windows en Azure Container Service (es decir, Kubernetes)

Azure Container Service optimiza la configuración de tecnologías y herramientas populares de código abierto específicamente para Azure. Obtenga una solución abierta que ofrece la portabilidad para sus contenedores tanto para la configuración de la aplicación. Seleccione el tamaño, el número de hosts y las herramientas de orchestrator. Azure Container Service controla la infraestructura para usted.

Si ya está trabajando con orquestadores de código abierto como Kubernetes, Docker Swarm o DC/OS, no es necesario cambiar sus prácticas de administración existente para mover las cargas de trabajo de contenedor a la nube. Usar las herramientas de administración de la aplicación que ya está familiarizado y conéctese a través de los puntos de conexión de API estándares para el orquestador de su elección.

Todos estos orquestadores son entornos maduros si usa contenedores de Linux Docker, pero sólo puede estar en estado de vista previa para los contenedores de Windows.

Por ejemplo, en Kubernetes, compatibilidad para contenedores es nativo (ciudadano de primera clase), mediante contenedores de Windows en Kubernetes también es efectivo (en versión preliminar de ACS a partir de principios de 2018).

Nota importante: El evolucionadas y "PaaS más" versión de ACS (Azure Container Service) para Kubernetes es AKS (Azure Kubernetes Service), sin embargo, los contenedores de Windows aún no se admiten a partir del 2 º trimestre de 2018, pero se admitirá pronto.

>[!div class="step-by-step"]
>[Anterior](when-to-deploy-windows-containers-to-service-fabric.md)
>[Siguiente](choosing-azure-compute-options-for-container-based-applications.md)