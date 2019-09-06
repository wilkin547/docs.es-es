---
title: Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube
description: Modernización de las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube
ms.date: 04/30/2018
ms.openlocfilehash: 62b6c541780ed3bf82c55e576fa485f811b55b17
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2019
ms.locfileid: "70374137"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube

Las empresas de hoy en día deben innovar a un ritmo rápido para ser competitivos en Marketplace. La entrega de aplicaciones modernas de alta calidad requiere herramientas y procesos de DevOps que son fundamentales para implementar este ciclo constante de innovación. Con las herramientas de DevOps adecuadas, los desarrolladores pueden simplificar la implementación continua y obtener aplicaciones innovadoras a las manos de los usuarios con más rapidez.

Aunque las prácticas de integración e implementación continuas están bien establecidas, la introducción de contenedores presenta nuevas consideraciones, sobre todo cuando se trabaja con aplicaciones de varios contenedores.

Azure DevOps Services admite la integración y la implementación continuas de aplicaciones de varios contenedores en una gran variedad de entornos a través de las tareas de implementación de Azure DevOps Services oficiales:

- [Implementación en una Web App for Containers de Azure](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?view=azure-devops)

- [Implementar en Azure Container Service: Kubernetes](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

Pero también puede implementar en [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) o DC/os mediante el uso de Azure DevOps Services tareas basadas en scripts.

Para seguir facilitando la agilidad de la implementación, estas herramientas proporcionan excelentes experiencias de implementación de desarrollo a prueba en producción para cargas de trabajo de contenedor, con una elección de soluciones de desarrollo y de CI/CD.

En la figura 4-12 se muestra una canalización de implementación continua que se implementa en un clúster de Kubernetes en Azure Container Service.

![Azure DevOps Services canalización de implementación continua, implementar en un clúster de Kubernetes](./media/image12.png)

**Figura 4-12.** Azure DevOps Services canalización de implementación continua, implementar en un clúster de Kubernetes

>[!div class="step-by-step"]
>[Anterior](modernize-your-apps-with-monitoring-and-telemetry.md)
>[Siguiente](migrate-to-hybrid-cloud-scenarios.md)
