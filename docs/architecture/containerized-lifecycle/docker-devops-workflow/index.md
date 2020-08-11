---
title: Flujo de trabajo de DevOps para aplicaciones de Docker con herramientas de Microsoft
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma de Microsoft y el flujo de trabajo de DevOps con herramientas de Microsoft
ms.date: 08/06/2020
ms.openlocfilehash: 30c5066fa90d8792d8eef8f760dc63c00ce32130
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915207"
---
# <a name="docker-application-devops-workflow-with-microsoft-tools"></a>Flujo de trabajo de DevOps para aplicaciones de Docker con herramientas de Microsoft

*Microsoft Visual Studio, Azure DevOps Services, Team Foundation Server y Azure Monitor proporcionan un ecosistema completo para el desarrollo y las operaciones de TI que proporcionan a su equipo las herramientas para administrar proyectos y compilar, probar e implementar rápidamente las aplicaciones en contenedor.*

Con Visual Studio y Azure DevOps Services en la nube, junto con Team Foundation Server local, los equipos de desarrollo pueden crear, probar y publicar aplicaciones en contenedor de manera productiva dirigidas a Windows o Linux.

Las herramientas de Microsoft pueden automatizar la canalización de implementaciones específicas de aplicaciones en contenedor (Docker, .NET Core o cualquier combinación con otras plataformas) desde compilaciones globales e integración continua (CI) y pruebas con Azure DevOps Services o Team Foundation Server, para realizar una implementación continua (CD) en entornos de Docker (desarrollo, almacenamiento provisional y producción) y para transmitir información de análisis sobre los servicios al equipo de desarrollo a través de Azure Monitor. Cada confirmación de código puede iniciar una compilación (CI) e implementar automáticamente los servicios en entornos en contenedores específicos (CD).

Los desarrolladores y evaluadores pueden aprovisionar con facilidad y rapidez entornos de prueba y desarrollo tipo producción basados en Docker con el uso de plantillas de Microsoft Azure.

La complejidad del desarrollo de aplicaciones en contenedores aumenta de forma constante según las necesidades empresariales de complejidad y escalabilidad. Un buen ejemplo de esta complejidad son las aplicaciones basadas en arquitecturas de microservicios. Para tener éxito en un entorno de este tipo, el proyecto debe automatizar todo el ciclo de vida, no solo la compilación y la implementación, sino que también debe administrar versiones junto con la recopilación de telemetría. Azure DevOps Services y Azure ofrecen las siguientes funcionalidades:

- Administración del código fuente de Azure DevOps Services/Team Foundation Server (basada en Git o en el Control de versiones de Team Foundation), planeación de Agile (Agile, Scrum y CMMI son compatibles), integración continua, administración de versiones y otras herramientas para equipos de Agile.

- Azure DevOps Services y Team Foundation Server incluyen un eficaz y creciente ecosistema de extensiones propias y de terceros con las que puede crear con facilidad una integración continua, así como compilar, probar, entregar y publicar la canalización de administración de microservicios.

- Ejecución de pruebas automatizadas como parte de la canalización de compilación de Azure DevOps Services.

- Azure DevOps Services puede reforzar el ciclo de vida de DevOps con la entrega a varios entornos, no solo para entornos de producción, sino también para pruebas, incluida la experimentación de A/B, [versiones de valor controlado](https://martinfowler.com/bliki/CanaryRelease.html), etc.

- Las organizaciones pueden aprovisionar fácilmente contenedores de Docker en imágenes privadas almacenadas en Azure Container Registry junto con cualquier dependencia de componentes de Azure (Data, PaaS, etc.) mediante el uso de plantillas de Azure Resource Manager con herramientas con las que se sienten cómodas al trabajar.

>[!div class="step-by-step"]
>[Anterior](../design-develop-containerized-apps/build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
>[Siguiente](docker-application-outer-loop-devops-workflow.md)
