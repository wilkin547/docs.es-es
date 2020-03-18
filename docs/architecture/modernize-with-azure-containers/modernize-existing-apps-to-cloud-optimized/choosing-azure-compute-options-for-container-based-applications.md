---
title: Elección de plataformas de procesos de Azure para aplicaciones basadas en contenedores
description: Modernización de las aplicaciones .NET existentes con Azure Clour y contenedores Windows | Elección de las plataformas de proceso de Azure para las aplicaciones basadas en contenedores
ms.date: 02/18/2020
ms.openlocfilehash: 52e7cf1c5dd3a5850564bdb33ac7a4ac4904f432
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503893"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>Elección de plataformas de procesos de Azure para aplicaciones basadas en contenedores

Tal y como ha observado después de leer las secciones anteriores, Azure es una nube abierta que ofrece numerosas opciones. Puede usar la opción que mejor se adapte a sus necesidades; sin embargo, plantea preguntas sobre qué producto o tecnología debe usar para las aplicaciones en contenedor.

Los siguientes son los principales criterios *predeterminados* que se recomiendan en esta guía:

- **Aplicación monolítica única:** Elegir Azure App Service
- **Aplicación de N niveles:** elija orquestadores como Azure Kubernetes Service (AKS) o App Service si tiene uno o varios servicios back-end.
- **Microservicios:** elija AKS o Azure Web Apps for Containers.
- **Funciones sin servidor y controladores de eventos:** elija Azure Functions.
- **Lotes a gran escala:** elija Azure Batch.

Sin embargo, esta recomendación no se debe tomar como ley universal, porque la elección del producto dependerá de las necesidades y características específicas de la aplicación. No todas las aplicaciones son iguales aunque inicialmente puedan parecer similares.

Después de un análisis más profundo de las necesidades de la aplicación, el producto seleccionado podría ser otro. Sin embargo, como punto de partida, es conveniente tener una guía con la que poder empezar a realizar evaluaciones y pruebas en función de una prioridad determinada.

En la siguiente tabla, puede ver un desglose de los diferentes tipos de aplicaciones y sus escenarios de hospedaje de Azure posibles y recomendados.

| Arquitectura de la aplicación | VM: Azure Virtual Machines | ACI: Azure Container Instances | Azure App Service (con o sin contenedores) | AKS: Azure Kubernetes Service | Comprobación de | Azure Batch |
|:------------------------:|:--:|:--:|:--:|:--:|:--:|:--:|
| **Aplicaciones web (monolíticas)**         | ![Posible con VM](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Posible con ACI](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Recomendado con App Service](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) | ![Posible con AKS](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | | |
| **Aplicaciones de n niveles (servicios)**        | ![Posible con VM](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Posible con ACI](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Recomendado con App Service](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) | ![Posible con AKS](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Posible con Azure Fuctions](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | |
| **Nativo en la nube (microservicios)**  | | ![Posible con ACI](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | | ![Recomendado con AKS](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) <br/> (Contenedores de&nbsp;Linux)| ![Recomendado con Azure Functions](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) <br/> (Basado en eventos) | |
| **Lotes y trabajos (tareas en segundo plano)** | ![Posible con VM](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Posible con ACI](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Posible con App Service](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Posible con AKS](media/choosing-azure-compute-options-for-container-based-applications/possible.png) | ![Recomendado con Azure Functions](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) <br/> (Tareas&nbsp;en segundo plano) | ![Recomendado con Azure Batch](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) <br/> (Gran escala) |

**Leyenda**

![Icono Recomendado](media/choosing-azure-compute-options-for-container-based-applications/recommended.png) Recomendado \
![Icono Posible](media/choosing-azure-compute-options-for-container-based-applications/possible.png) Posibilidad

> [!div class="step-by-step"]
> [Anterior](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Siguiente](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
