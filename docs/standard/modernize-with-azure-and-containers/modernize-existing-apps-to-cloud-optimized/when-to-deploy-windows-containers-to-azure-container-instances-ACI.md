---
title: Cuándo se debe implementar contenedores de Windows para instancias de contenedor de Azure (ACI)
description: Modernizar las aplicaciones .NET existentes con contenedores de Windows y de nube de Azure | Cuándo se debe implementar contenedores de Windows para instancias de contenedor de Azure (ACI)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/29/2018
ms.openlocfilehash: 3dc23c96543d9611763b571105f52b150dfec06f
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957955"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a>Cuándo se debe implementar contenedores de Windows para instancias de contenedor de Azure (ACI)

Instancias de contenedor propuesta de valor principal es que inmediatamente puede implementar contenedores en él y no es necesario mantener ese entorno de Azure, no necesita actualización/revisión en el sistema de operativo subyacentes o máquinas virtuales, todo lo que es transparente y acaba de implementar contenedores en un entorno de listos para usar.

Las razones y escenarios de cuándo es conveniente usar ACI son similares a los principales escenarios que, cuando se usa máquinas virtuales de Azure con los contenedores, por lo que básicamente, son los escenarios principales para usar instancias de contenedor de Azure:

-   **Escenarios de desarrollo/pruebas**
-   **Automatización de tareas**
-   **Agentes de CI/CD**
-   **Procesamiento por lotes pequeños y la escala**
-   **Aplicaciones web simples**

El escenario de aplicaciones web simple es un escenario razonable para ACI pero tenga en cuenta que, puesto que en ACI sólo puede tener una instancia del contenedor único por cada imagen de contenedor, no tiene una alta disponibilidad y solo se escalabilidad limitada.

Sin embargo, incluso cuando ACI se considera infraestructura porque solo proporciona instancias de contenedor único, hay una gran ventaja en comparación con regular máquinas virtuales de Azure con Windows Server. Con ACI, simplemente implementa los contenedores en un entorno mantiene automáticamente y solo paga por los contenedores. No es necesario para mantener / / revisión de actualización de las máquinas virtuales, por lo que es una mejor plataforma para la mayoría de los escenarios donde puede que esté usando máquinas virtuales con contenedores. Usar ACI es sencillo, simplemente implementar un contenedor, no es necesario para crear un entorno de máquinas virtuales solo implementar contenedores.

Las ventajas principales de instancias de contenedor de Azure (ACI) son:

-   Contenedores de ejecución sin tener que administrar servidores
-   Aumentar la agilidad con contenedores a petición
-   Implementar contenedores en la nube con sin precedentes simplicidad y velocidad, con un solo comando. 
-   Proteger aplicaciones con aislamiento de hipervisor

En resumen, con ACI puede desarrollar aplicaciones rápidamente sin administrar máquinas virtuales ni tener que aprender nuevas herramientas. Es simplemente la aplicación, en un contenedor, que se ejecuta en la nube.

>[!div class="step-by-step"]
[Anterior](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Siguiente](when-to-deploy-windows-containers-to-service-fabric.md)
