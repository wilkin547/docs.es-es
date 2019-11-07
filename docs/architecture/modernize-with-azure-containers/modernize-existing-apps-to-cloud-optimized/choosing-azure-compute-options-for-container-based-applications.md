---
title: Elección de plataformas de procesos de Azure para aplicaciones basadas en contenedores
description: Modernización de las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | Elección de las plataformas de proceso de Azure para aplicaciones basadas en contenedores
ms.date: 05/04/2018
ms.openlocfilehash: 079c9c5ca02b6dc75214d63cb59afdead03d3190
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736999"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>Elección de plataformas de procesos de Azure para aplicaciones basadas en contenedores

Como ha observado después de leer las secciones anteriores, Azure es una nube abierta que ofrece varias opciones. Puede usar la mejor opción para sus necesidades; sin embargo, también muestra preguntas sobre el producto o la tecnología que debe usar para las aplicaciones en contenedor.

Como recomendación *predeterminada* , los criterios principales recomendados en esta guía son los siguientes:

- **Aplicación monolítica única:** Elegir Azure App Service
- **Aplicación de N niveles:** Elija orquestadores como Azure Kubernetes Service (AKS) o App Service si tiene uno o varios servicios back-end.
- **Microservicios:** Elección de AKS o Azure Web Apps para contenedores
- **Funciones sin servidor & controladores de eventos:** Elegir Azure Functions
- **Lote a gran escala:** Elegir Azure Batch

Sin embargo, esta recomendación se debe llevar a cabo con un contacto de sal, ya que la selección del producto dependerá de las necesidades y características específicas de la aplicación. No todas las aplicaciones son iguales incluso cuando inicialmente pueden ser tipos similares.

Después de un análisis más profundo de las necesidades de la aplicación, el producto seleccionado podría ser diferente. Sin embargo, como punto de partida, es conveniente tener una guía inicial desde la que puede comenzar a evaluar y probar en función de una prioridad determinada.

En la figura 1, puede ver un desglose de los diferentes tipos de aplicaciones y sus escenarios de hospedaje de Azure ideales.

![Tabla de los escenarios de hospedaje de Azure más adecuados para las diferentes aplicaciones.](./media/choosing-azure-compute-options-for-container-based-applications/azure-hosting-scenarios-for-apps.png)

> [!div class="step-by-step"]
> [Anterior](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Siguiente](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
