---
title: Cuándo implementar contenedores de Windows en Azure Container Instances (ACI)
description: Modernización de las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | Cuándo implementar contenedores de Windows en Azure Container Instances (ACI)
ms.date: 04/29/2018
ms.openlocfilehash: 3b6ae1ced9c4e01f5ab400e2575947a396064ebd
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577938"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a>Cuándo implementar contenedores de Windows en Azure Container Instances (ACI)

Azure Container Instances propuesta de valor principal es que puede implementar contenedores en él de forma inmediata y no es necesario mantener ese entorno, no es necesario actualizar o aplicar revisiones al sistema operativo o las máquinas virtuales subyacentes, todo eso es transparente y solo se implementa. contenedores en un entorno listo para usar.

Los motivos y los escenarios en los que sería conveniente usar ACI son similares a los principales escenarios cuando se usan máquinas virtuales de Azure con contenedores, por lo que básicamente, los principales escenarios para usar Azure Container Instances son:

- **Escenarios de desarrollo y pruebas**
- **Automatización de tareas**
- **Agentes de CI/CD**
- **Procesamiento por lotes de pequeña o escala**
- **Aplicaciones web sencillas**

El escenario de Web Apps sencillo es un escenario justo para ACI, pero tenga en cuenta que, puesto que en ACI solo puede tener una instancia de contenedor única por cada imagen de contenedor, no tendrá alta disponibilidad y solo tendrá una escalabilidad limitada.

Sin embargo, incluso cuando ACI se considera infraestructura porque solo proporciona instancias de contenedor único, existe una gran ventaja en comparación con las máquinas virtuales de Azure normales con Windows Server. Con ACI, solo tiene que implementar los contenedores en un entorno autohospedado y solo paga por esos contenedores. No es necesario mantener, actualizar o aplicar revisiones a las máquinas virtuales, por lo que es una plataforma mucho mejor para la mayoría de los escenarios en los que podría estar usando máquinas virtuales con contenedores. El uso de ACI es sencillo, solo tiene que implementar un contenedor, no es necesario crear un entorno de máquina virtual que solo implemente contenedores.

Las principales ventajas de Azure Container Instances (ACI) son:

- Ejecutar contenedores sin administrar servidores
- Aumento de la agilidad con contenedores a petición
- Implemente contenedores en la nube con una simplicidad y una velocidad sin precedentes, con un solo comando.
- Protección de aplicaciones con aislamiento de hipervisor

En Resumen, con ACI puede desarrollar aplicaciones rápidamente sin administrar máquinas virtuales ni tener que aprender nuevas herramientas. Es simplemente su aplicación, en un contenedor, que se ejecuta en la nube.

> [!div class="step-by-step"]
> [Anterior](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [Siguiente](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
