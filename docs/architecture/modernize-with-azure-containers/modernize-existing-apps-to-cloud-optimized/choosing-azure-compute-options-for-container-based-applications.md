---
title: Elección de plataformas de procesos de Azure para aplicaciones basadas en contenedores
description: Modernización de las aplicaciones .NET existentes con Azure Clour y contenedores Windows | Elección de las plataformas de proceso de Azure para las aplicaciones basadas en contenedores
ms.date: 05/04/2018
ms.openlocfilehash: 079c9c5ca02b6dc75214d63cb59afdead03d3190
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2019
ms.locfileid: "73736999"
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

En la figura 1, puede ver un desglose de los diferentes tipos de aplicaciones y sus escenarios de hospedaje de Azure ideales.

![Tabla de los escenarios de hospedaje de Azure más adecuados para las diferentes aplicaciones.](./media/choosing-azure-compute-options-for-container-based-applications/azure-hosting-scenarios-for-apps.png)

> [!div class="step-by-step"]
> [Anterior](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Siguiente](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
