---
title: Flujo de trabajo de DevOps para aplicaciones de Docker con herramientas de Microsoft
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma de Microsoft y flujo de trabajo de DevOps de aplicaciones con las herramientas de Microsoft
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8539e8c0a6d0c6c9d558b91e062184e7ef135856
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="docker-application-devops-workflow-with-microsoft-tools"></a>Flujo de trabajo de DevOps para aplicaciones de Docker con herramientas de Microsoft

Microsoft Visual Studio, Visual Studio Team Services, Team Foundation Server y Application Insights proporcionan un ecosistema completo para el desarrollo y las operaciones de TI que proporcionan a su equipo las herramientas para administrar proyectos y compilar, probar e implementar rápidamente las aplicaciones en contenedor.

Con Visual Studio y Visual Studio Team Services en la nube, junto con Team Foundation Server local, los equipos de desarrollo puede crear, probar y publicar aplicaciones en contenedor de manera productiva dirigidas a cualquier plataforma (Windows o Linux).

Las herramientas de Microsoft puede automatizar la canalización de implementaciones específicas de aplicaciones en contenedor (Docker, .NET Core o cualquier combinación con otras plataformas) desde compilaciones globales e integración continua y pruebas con Visual Studio Team Services o Team Foundation Server, a fin de realizar una implementación continua en entornos de Docker (desarrollo, almacenamiento provisional y producción) y para transmitir información de análisis sobre los servicios al equipo de desarrollo a través de Application Insights. Cada confirmación de código puede iniciar una compilación (CI) e implementar automáticamente los servicios en entornos en contenedores específicos (CD).

Los desarrolladores y evaluadores pueden aprovisionar con facilidad y rapidez entornos de prueba y desarrollo tipo producción basados en Docker con el uso de plantillas de Microsoft Azure.

La complejidad del desarrollo de aplicaciones en contenedores aumenta de forma constante según las necesidades empresariales de complejidad y escalabilidad. Un buen ejemplo de esto son las aplicaciones basadas en arquitecturas de microservicios. Para tener éxito en un entorno de este tipo, el proyecto debe automatizar todo el ciclo de vida, no solo la compilación y el desarrollo, sino que también debe administrar versiones junto con la colección de telemetría. Visual Studio Team Services y Azure ofrecen las siguientes funcionalidades:

-   Administración del código fuente de Visual Studio Team Services/Team Foundation Server (basada en Git o en el Control de versiones de Team Foundation), planeación de Agile (Agile, Scrum y CMMI son compatibles), integración continua, administración de versiones y otras herramientas para equipos de Agile.

-   Visual Studio Team Services/Team Foundation Server incluyen un eficaz y creciente ecosistema de extensiones propias y de terceros con las que puede crear con facilidad una integración continua, así como compilar, probar, entregar y publicar la canalización de administración de microservicios.

-   Ejecutar pruebas automatizadas como parte de la canalización de compilación de Visual Studio Team Services.

-   Visual Studio Team Services puede reforzar el ciclo de vida de DevOps con la entrega a varios entornos, no solo para entornos de producción, sino también para pruebas, incluida la experimentación de A/B, [versiones de valor controlado](http://martinfowler.com/bliki/CanaryRelease.html), etc.

-   Las organizaciones pueden aprovisionar fácilmente contenedores de Docker en imágenes privadas almacenadas en Azure Container Registry junto con cualquier dependencia de componentes de Azure (Data, PaaS, etc.) mediante el uso de plantillas de Azure Resource Manager con herramientas con las que se sienten cómodas para trabajar.


>[!div class="step-by-step"]
[Anterior] (../design-develop-containerized-apps/set-up-windows-containers-with-powershell.md) [Siguiente] (docker-application-outer-loop-devops-workflow.md)
