---
title: Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube
description: Modernización de las aplicaciones .NET existentes con Azure Clour y contenedores Windows | Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube
ms.date: 12/21/2018
ms.openlocfilehash: e7ad76edb659fbacfc85cb398ec0c9fe9e3c66c9
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025256"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube

Las empresas actuales deben innovar a un ritmo rápido para ser competitivas en el mercado. La entrega de aplicaciones modernas de alta calidad requiere herramientas y procesos de DevOps que son fundamentales para implementar este ciclo constante de innovación. Con las herramientas de DevOps adecuadas, los desarrolladores pueden simplificar la implementación continua y poner aplicaciones innovadoras en manos de los usuarios con más rapidez.

Aunque las prácticas de integración e implementación continuas están bien establecidas, la introducción de contenedores presenta nuevas consideraciones, sobre todo cuando se trabaja con aplicaciones en varios contenedores.

Azure DevOps Services admite la integración y la implementación continuas de aplicaciones en varios contenedores en diversos entornos mediante las tareas de implementación oficiales de Azure DevOps Services:

- [Implementación en una aplicación de Azure Web App for Containers](/azure/devops/pipelines/apps/cd/deploy-docker-webapp?tabs=dotnet-core)

- [Implementación en Azure Kubernetes Service](/azure/devops/pipelines/apps/cd/deploy-aks?tabs=dotnet-core)

Pero también puede implementar en [Docker Swarm](https://blog.jcorioland.io/archives/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services.html) o DC/OS mediante tareas de Azure DevOps Services basadas en scripts.

Para facilitar aún más la agilidad de la implementación, estas herramientas proporcionan excelentes experiencias de implementación en la secuencia desarrollo-pruebas-producción para cargas de trabajo de contenedor, con diversas soluciones de desarrollo y CI/CD.

En la figura 4-12 se muestra una canalización de implementación continua que se implementa en un clúster de Kubernetes en Azure Container Service.

![Captura de pantalla de una implementación de Azure DevOps Services en un clúster de Kubernetes.](./media/life-cycle-ci-cd-pipelines-devops-tools/deploy-mvc-app-container-kubernetes.png)

**Figura 4-12.** Canalización de implementación continua de Azure DevOps Services, implementación en un clúster de Kubernetes

>[!div class="step-by-step"]
>[Anterior](modernize-your-apps-with-monitoring-and-telemetry.md)
>[Siguiente](migrate-to-hybrid-cloud-scenarios.md)
