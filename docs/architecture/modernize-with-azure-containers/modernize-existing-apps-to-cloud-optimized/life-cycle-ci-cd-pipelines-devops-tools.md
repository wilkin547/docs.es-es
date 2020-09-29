---
title: Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube
description: Modernización de las aplicaciones .NET existentes con Azure Clour y contenedores Windows | Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube
ms.date: 04/30/2018
ms.openlocfilehash: 98ebd29b8ab81c8fff6da546942825133f06f4de
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172058"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube

Las empresas actuales deben innovar a un ritmo rápido para ser competitivas en el mercado. La entrega de aplicaciones modernas de alta calidad requiere herramientas y procesos de DevOps que son fundamentales para implementar este ciclo constante de innovación. Con las herramientas de DevOps adecuadas, los desarrolladores pueden simplificar la implementación continua y poner aplicaciones innovadoras en manos de los usuarios con más rapidez.

Aunque las prácticas de integración e implementación continuas están bien establecidas, la introducción de contenedores presenta nuevas consideraciones, sobre todo cuando se trabaja con aplicaciones en varios contenedores.

Azure DevOps Services admite la integración y la implementación continuas de aplicaciones en varios contenedores en una gran variedad de entornos mediante las tareas de implementación oficiales de Azure DevOps Services:

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
