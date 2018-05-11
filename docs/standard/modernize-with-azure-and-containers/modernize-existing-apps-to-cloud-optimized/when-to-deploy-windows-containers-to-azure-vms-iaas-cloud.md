---
title: Cuándo se debe implementar contenedores de Windows en máquinas virtuales de Azure (IaaS nube)
description: Modernizar las aplicaciones .NET existentes con contenedores de Windows y de nube de Azure | Cuándo se debe implementar contenedores de Windows en máquinas virtuales de Azure (IaaS nube)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 7472745577f414062b460fd71ab45bae85d7a62e
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a>Cuándo se debe implementar contenedores de Windows en máquinas virtuales de Azure (IaaS nube)

Si su organización está usando máquinas virtuales de Azure, incluso si también usa contenedores de Windows, siguen siendo ocuparse de IaaS. Esto significa que tratar con las operaciones de infraestructura, revisiones del sistema operativo de la máquina virtual y complejidad de la infraestructura para aplicaciones muy escalables cuando necesite implementar en varias máquinas virtuales en una infraestructura con equilibrio de carga. Los escenarios principales para usar los contenedores de Windows en una máquina virtual de Azure son:

-   **Entorno de desarrollo/pruebas**: una VM en la nube es ideal para desarrollo y pruebas en la nube. Puede crear rápidamente o detener el entorno según sus necesidades.

-   **Escalabilidad pequeña y mediana necesita**: en escenarios donde podría necesitar un par de máquinas virtuales para su entorno de producción, administra un pequeño número de máquinas virtuales podría estar asequible hasta que puede mover a los entornos de PaaS más avanzados, como orchestrators.

-   **Entorno de producción con las herramientas de implementación existentes**: pueden mover desde un entorno local en el que se ha invertido en herramientas para realizar las implementaciones complejas en las máquinas virtuales o servidores de reconstrucción completa (por ejemplo, Puppet o herramientas similares). Para mover a la nube con unos cambios mínimos en los procedimientos de implementación del entorno de producción, puede continuar usar estas herramientas para implementar en máquinas virtuales de Azure. Sin embargo, conviene utilizar contenedores de Windows como la unidad de implementación para mejorar la experiencia de implementación.

>[!div class="step-by-step"]
[Anterior](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[Siguiente](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
