---
title: Cuándo se deben implementar contenedores de Windows en máquinas virtuales de Azure (nube IaaS)
description: Modernización de las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | Cuándo implementar contenedores de Windows en máquinas virtuales de Azure (nube IaaS)
ms.date: 04/28/2018
ms.openlocfilehash: e9a2903662306b607977a7751018e24161ab80ab
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577908"
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a>Cuándo se deben implementar contenedores de Windows en máquinas virtuales de Azure (nube IaaS)

Si su organización usa máquinas virtuales de Azure, aunque también esté usando contenedores de Windows, seguirá tratando con IaaS. Esto significa que, con las operaciones de infraestructura, las revisiones del sistema operativo de la máquina virtual y la complejidad de la infraestructura para aplicaciones altamente escalables, cuando necesite implementar en varias máquinas virtuales en una infraestructura con equilibrio de carga. Los principales escenarios para el uso de contenedores de Windows en una máquina virtual de Azure son:

- **Entorno de desarrollo y pruebas**: Una máquina virtual en la nube es perfecta para desarrollo y pruebas en la nube. Puede crear o detener el entorno rápidamente en función de sus necesidades.

- **Necesidades de escalabilidad pequeña y media**: En escenarios en los que podría necesitar un par de máquinas virtuales para el entorno de producción, la administración de un pequeño número de máquinas virtuales puede ser asequible hasta que pueda pasar a entornos PaaS más avanzados, como los orquestadores.

- **Entorno de producción con herramientas de implementación existentes**: Podría pasar de un entorno local en el que ha invertido en herramientas para realizar implementaciones complejas en máquinas virtuales o en servidores sin sistema operativo (como una posición libre o herramientas similares). Para pasar a la nube con unos cambios mínimos en los procedimientos de implementación del entorno de producción, puede seguir usando esas herramientas para implementar en máquinas virtuales de Azure. Sin embargo, querrá usar contenedores de Windows como unidad de implementación para mejorar la experiencia de implementación.

>[!div class="step-by-step"]
>[Anterior](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
>[Siguiente](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
