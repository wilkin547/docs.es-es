---
title: Pasos del flujo de trabajo de DevOps de bucle externo para una aplicación de Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
ms.date: 08/06/2020
ms.openlocfilehash: 1a973407d59484899f99fb6e326b8d7c8e97079b
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915212"
---
# <a name="creating-cicd-pipelines-in-azure-devops-services-for-a-net-core-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a>Creación de canalizaciones de CI/CD en Azure DevOps Services para una aplicación .NET Core en contenedores e implementación en un clúster de Kubernetes

En la figura 5-12 se puede ver el escenario completo de DevOps, que comprende la administración de código, la compilación de código, la creación de imágenes de Docker, la inserción de imágenes de Docker en un registro de Docker y, por último, la implementación en un clúster de Kubernetes en Azure.

![Flujo de trabajo: Empieza en la máquina de desarrollo. La inserción en un repositorio comienza la tarea de compilación/CI con una imagen personalizada que se inserta en un registro de Docker y luego se utiliza en la tarea de implementación/CD para, finalmente, insertarse en AKS.](media/docker-workflow-ci-cd-aks.png)

**Figura 5-12**. Escenario CI/CD de creación de imágenes de Docker y su implementación en un clúster de Kubernetes en Azure

Es importante destacar que las dos canalizaciones, la de compilación/CI y la de versión/CD, se conectan a través del registro de Docker (como Docker Hub o Azure Container Registry). El registro de Docker es una de las principales diferencias con respecto a un proceso tradicional de CI/CD sin Docker.

Como se muestra en la figura 5-13, la primera fase es la canalización de compilación/CI. En Azure DevOps Services se pueden crear canalizaciones de compilación/CI que compilen el código, crear las imágenes de Docker e insertarlas en un registro de Docker como Docker Hub o Azure Container Registry.

![Vista del explorador de Azure DevOps, definición de la tarea de proceso de compilación.](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

**Figura 5-13**. Canalización de compilación/CI de Azure DevOps para crear imágenes de Docker e insertar imágenes en un registro de Docker

La segunda fase consiste en la creación de una canalización de implementación o publicación. En Azure DevOps Services se puede crear fácilmente una canalización de implementación destinada a un clúster de Kubernetes mediante tareas de Kubernetes para Azure DevOps Services, tal y como se muestra en la figura 5-14.

![Vista del explorador de Azure DevOps, definición de la tarea de implementación en Kubernetes.](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

**Figura 5-14**. Canalización de versión/CD de Azure DevOps Services para implementar en un clúster de Kubernetes

> [Tutorial] Implementación de eShopModernized en Kubernetes:
>
> Para obtener un tutorial detallado de la implementación de canalizaciones de CI/CD de Azure DevOps en Kubernetes, vea esta publicación: \
><https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

>[!div class="step-by-step"]
>[Anterior](docker-application-outer-loop-devops-workflow.md)
>[Siguiente](../run-manage-monitor-docker-environments/index.md)
