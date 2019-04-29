---
title: Pasos del flujo de trabajo de DevOps de bucle externo para una aplicación de Docker
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 2cd769ce9013a8521c53f36b44ea260ceccd48b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795380"
---
# <a name="creating-cicd-pipelines-in-azure-devops-services-for-a-net-core-20-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a>Creación de canalizaciones de CI/CD en Azure DevOps Services para una aplicación .NET Core 2.0 en contenedores e implementación en un clúster de Kubernetes

En la figura 5-12 puede ver el escenario de DevOps-to-end, que abarcan la administración de código, compilación de código, compilación de imágenes de Docker, inserción de imágenes de Docker en un registro de Docker y, finalmente, la implementación en un clúster de Kubernetes en Azure.

![Flujo de trabajo: Se inicia en el equipo de desarrollo. Inserción en un repositorio comienza la tarea de compilación/integración continua mediante una imagen personalizada que se inserta en un registro de Docker y, a continuación, se utiliza la tarea de CD o implementar, por último, insertar en AKS.](media/docker-workflow-ci-cd-aks.png)

**Figura 5-12**. Escenario de CI/CD, crear imágenes de Docker e implementar en un clúster de Kubernetes en Azure

Es importante destacar que los dos canalizaciones y compilación, CI/CD de la versión, están conectados a través del registro de Docker (como Docker Hub o Azure Container Registry). El registro de Docker es una de las principales diferencias en comparación con un proceso de CI/CD tradicionales sin Docker.

Como se muestra en la figura 5-13, la primera fase es la canalización de compilación o CI. En los servicios de DevOps de Azure puede crear canalizaciones de compilación/CD que se compile el código, crear las imágenes de Docker y los inserta en un registro de Docker como Docker Hub o Azure Container Registry.

![Vista del explorador de Azure DevOps, definición de tarea de proceso de compilación.](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

**Figura 5-13**. Canalización de compilación/integración continua en Azure DevOps compilar imágenes de Docker e inserción de imágenes en un registro de Docker

La segunda fase consiste en crear una canalización de implementación y lanzamiento. En los servicios de Azure DevOps, puede crear fácilmente una canalización de implementación destinadas a un clúster de Kubernetes mediante el uso de las tareas de Kubernetes para los servicios de Azure DevOps, como se muestra en la figura 5-14.

![Vista del explorador de Azure DevOps, implemente en la definición de tarea de Kubernetes.](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

**Figura 5-14**. Canalización de versión/CD en la implementación de servicios de Azure DevOps a un clúster de Kubernetes

> [! Tutorial] implementación eShopModernized en Kubernetes:
>
> Para obtener un tutorial detallado de las canalizaciones de Azure DevOps CI/CD de implementación en Kubernetes, consulte esta publicación: \
><https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

>[!div class="step-by-step"]
>[Anterior](docker-application-outer-loop-devops-workflow.md)
>[Siguiente](../run-manage-monitor-docker-environments/index.md)
