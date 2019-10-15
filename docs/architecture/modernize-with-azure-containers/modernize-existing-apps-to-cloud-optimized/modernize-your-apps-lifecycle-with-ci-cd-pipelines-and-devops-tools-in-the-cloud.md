---
title: Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube
description: Modernización de las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube
ms.date: 04/30/2018
ms.openlocfilehash: 75ac3fa06f442570a0a5043a88409b3fdebb5810
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318569"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube

Las empresas de hoy en día deben innovar a un ritmo rápido para ser competitivos en Marketplace. La entrega de aplicaciones modernas de alta calidad requiere herramientas y procesos de DevOps que son fundamentales para implementar este ciclo constante de innovación. Con las herramientas de DevOps adecuadas, los desarrolladores pueden simplificar la implementación continua y obtener aplicaciones innovadoras a las manos de los usuarios con más rapidez.

Aunque las prácticas de integración e implementación continuas están bien establecidas, la introducción de contenedores presenta nuevas consideraciones, sobre todo cuando se trabaja con aplicaciones de varios contenedores.

Azure DevOps Services admite la integración y la implementación continuas de aplicaciones de varios contenedores en una gran variedad de entornos a través de las tareas de implementación de Azure DevOps Services oficiales:

- [Implementación en una Web App for Containers de Azure](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?tabs=dotnet-core)

- [Implementación en Azure Kubernetes Service](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-aks?tabs=dotnet-core)

Pero también puede implementar en [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) o DC/os mediante el uso de Azure DevOps Services tareas basadas en scripts.

Para seguir facilitando la agilidad de la implementación, estas herramientas proporcionan excelentes experiencias de implementación de desarrollo a prueba en producción para cargas de trabajo de contenedor, con una elección de soluciones de desarrollo y de CI/CD.

En la figura 4-12 se muestra una canalización de implementación continua que se implementa en un clúster de Kubernetes en Azure Container Service.

![Captura de pantalla de Azure DevOps Services implementación en un clúster de Kubernetes.](./media/modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud/deploy-mvc-app-container-kubernetes.png)

**Figura 4-12.** Azure DevOps Services canalización de implementación continua, implementar en un clúster de Kubernetes

>[!div class="step-by-step"]
>[Anterior](modernize-your-apps-with-monitoring-and-telemetry.md)
>[Siguiente](migrate-to-hybrid-cloud-scenarios.md)
