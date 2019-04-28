---
title: Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Modernice el ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: c4eeb5606d3ea93b76efee58ddfecae0abbbd743
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012175"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a>Modernización del ciclo de vida de la aplicación con canalizaciones de CI/CD y herramientas de DevOps en la nube

Las empresas de hoy en día necesitan innovar con rapidez para ser competitivos en marketplace. Entrega de alta calidad, las aplicaciones modernas requiere herramientas de DevOps y procesos que son fundamentales para implementar este ciclo constante de innovación. Con las herramientas adecuadas de DevOps, los desarrolladores pueden simplificar la implementación continua y obtener aplicaciones innovadoras en manos de usuarios más rápidamente.

Aunque las prácticas de integración e implementación continua están bien consolidadas, la introducción de los contenedores de introduce nuevas consideraciones, especialmente cuando se trabaja con aplicaciones de varios contenedores.

Servicios de Azure DevOps es compatible con la integración continua e implementación de aplicaciones de varios contenedores a una variedad de entornos a través de las tareas de implementación de servicios de Azure DevOps oficiales:

- [Implementar en la máquina virtual del Host de Docker independiente](https://docs.microsoft.com/azure/devops/build-release/apps/cd/deploy-docker-windowsvm) (Linux o Windows Server 2016 o posterior)

- [Implementación en Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-tutorial-deploy-app-with-cicd-vsts)

- [Implementar en Azure Container Service: Kubernetes](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

Pero también puede implementar en [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) o DC/OS mediante el uso de las tareas basadas en scripts de servicios de Azure DevOps.

Para continuar facilita la agilidad de implementación, estas herramientas ofrecen experiencias de implementación de desarrollo a prueba a producción excelente para cargas de trabajo de contenedor, con las opciones de desarrollo y las soluciones de CI/CD.

Figura 4-12 se muestra una canalización de implementación continua que se implementa en un clúster de Kubernetes en Azure Container Service.

![Canalización de implementación continua de Azure DevOps servicios, la implementación en un clúster de Kubernetes](./media/image12.png)

> **Figura 4-12.** Canalización de implementación continua de Azure DevOps servicios, la implementación en un clúster de Kubernetes

>[!div class="step-by-step"]
>[Anterior](modernize-your-apps-with-monitoring-and-telemetry.md)
>[Siguiente](migrate-to-hybrid-cloud-scenarios.md)