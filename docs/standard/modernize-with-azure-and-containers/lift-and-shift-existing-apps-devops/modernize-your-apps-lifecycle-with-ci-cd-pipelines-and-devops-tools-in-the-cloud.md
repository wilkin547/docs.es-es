---
title: "Modernizar del ciclo de vida de la aplicación con las canalizaciones de CI/CD y las herramientas de DevOps en la nube"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Modernizar del ciclo de vida de la aplicación con las canalizaciones de CI/CD y las herramientas de DevOps en la nube"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c0b87d01c1305695dacaf3ba112b387de2ee0cc1
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>Modernizar del ciclo de vida de la aplicación con las canalizaciones de CI/CD y las herramientas de DevOps en la nube

Las empresas de hoy en día necesitan innovar a un ritmo rápido para ser competitivos en el mercado. Entrega de alta calidad, las aplicaciones modernas requiere las herramientas de DevOps y procesos que son fundamentales para implementar este ciclo constante de innovación. Con las herramientas adecuadas de DevOps, los desarrolladores pueden simplificar la implementación continua y obtención más rápida de aplicaciones innovadoras en manos de los usuarios.

Aunque los procedimientos de integración e implementación continuados están bien consolidados, la introducción de contenedores presenta nuevas consideraciones, especialmente cuando se trabaja con aplicaciones de contenedor de varios.

Visual Studio Team Services admite la integración continua y la implementación de aplicaciones de contenedor de varios a una variedad de entornos a través de las tareas de implementación de Team Services oficiales:

-   [Implementar en la máquina virtual del Host de Docker independiente](https://docs.microsoft.com/vsts/build-release/apps/cd/deploy-docker-windowsvm) (Linux o Windows Server 2016 o posterior)

-   [Implementar en Service Fabric.](https://docs.microsoft.com/azure/service-fabric/service-fabric-tutorial-deploy-app-with-cicd-vsts)

-   [Implementar en el servicio de contenedor de Azure: Kubernetes](https://docs.microsoft.com/vsts/build-release/apps/cd/azure/deploy-container-kubernetes)

Pero también puede implementar en [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) o DC/OS mediante el uso de las tareas basadas en secuencias de comandos de Team Services.

Para continuar facilitar la agilidad de la implementación, estas herramientas proporcionan experiencias de implementación excelente de desarrollo a prueba a producción para cargas de trabajo de contenedor, con una opción de desarrollo y las soluciones de integración continua/CD.

Figura 4-12 se muestra una canalización de implementación continua que se implementa en un clúster de Kubernetes en el servicio de contenedor de Azure.

![Canalización de implementación continua de Visual Studio Team Services, implementar en un clúster de Kubernetes](./media/image12.png)

> **Figura 4-12.** Canalización de implementación continua de Visual Studio Team Services, implementar en un clúster de Kubernetes

>[!div class="step-by-step"]
[Anterior](modernize-your-apps-with-monitoring-and-telemetry.md)
[Siguiente](migrate-to-hybrid-cloud-scenarios.md)
