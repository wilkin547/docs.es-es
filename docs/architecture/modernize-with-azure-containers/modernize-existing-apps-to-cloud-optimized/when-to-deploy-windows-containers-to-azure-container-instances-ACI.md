---
title: Cuándo se deben implementar contenedores Windows en Azure Container Instances (ACI)
description: Modernización de las aplicaciones .NET existentes con Azure Clour y contenedores Windows | Cuándo se deben implementar contenedores Windows en Azure Container Instances (ACI)
ms.date: 12/21/2020
ms.openlocfilehash: 556fe7cbec7d259db9ec886b777feda9eed09116
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025138"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a>Cuándo se deben implementar contenedores Windows en Azure Container Instances (ACI)

La propuesta de valor principal de Azure Container Instances es que puede implementar contenedores en él y no es necesario mantener ese entorno ni actualizar o aplicar revisiones al sistema operativo o las máquinas virtuales subyacentes; todo eso es transparente y solo se implementan contenedores en un entorno listo para usar.

Los motivos y los escenarios en los que sería conveniente usar ACI son similares a los principales escenarios en los que se usan máquinas virtuales de Azure con contenedores, por lo que, básicamente, los principales escenarios donde se usa Azure Container Instances son:

- **Escenarios de desarrollo y pruebas**
- **Automatización de tareas**
- **Agentes de CI/CD**
- **Procesamiento por lotes a pequeña o gran escala**
- **Aplicaciones web sencillas**

El escenario de aplicaciones web sencillo es apto para ACI, pero tenga en cuenta que, como en ACI solo puede haber una instancia de contenedor única por cada imagen de contenedor, no tendrá alta disponibilidad y tendrá una escalabilidad limitada.

Sin embargo, aunque ACI se considera infraestructura porque solo proporciona instancias de contenedor únicas, existe una gran ventaja en comparación con las máquinas virtuales de Azure normales con Windows Server. Con ACI, solo tiene que implementar los contenedores en un entorno autohospedado y solo paga por esos contenedores. No es necesario mantener, actualizar ni aplicar revisiones a las máquinas virtuales, por lo que es una plataforma mucho mejor para la mayoría de los escenarios en los que podría estar usando máquinas virtuales con contenedores. El uso de ACI es sencillo, solo tiene que implementar un contenedor; no es necesario crear un entorno de máquina virtual que solo implemente contenedores.

Las principales ventajas de Azure Container Instances (ACI) son:

- Ejecución de contenedores sin administrar servidores
- Aumento de la agilidad con contenedores a petición
- Implementación de contenedores en la nube con una simplicidad y una velocidad sin precedentes, con un solo comando.
- Protección de aplicaciones con aislamiento de hipervisor

En resumen, con ACI puede desarrollar aplicaciones rápidamente sin tener que administrar máquinas virtuales ni aprender nuevas herramientas. Solo necesita su aplicación, en un contenedor, ejecutándose en la nube.

> [!div class="step-by-step"]
> [Anterior](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [Siguiente](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
