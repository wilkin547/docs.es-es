---
title: Elección de plataformas de procesos de Azure para aplicaciones basadas en contenedores
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Seleccionar plataformas de Azure compute para las aplicaciones basadas en contenedor
ms.date: 05/04/2018
ms.openlocfilehash: 64ae542e006bf7a5d7a0be08fe1cff9770552a77
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833848"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>Elección de plataformas de procesos de Azure para aplicaciones basadas en contenedores

Como habrá observado después de leer las secciones anteriores, Azure es una nube abierta que ofrece varias opciones. Puede usar la mejor opción para sus necesidades, sin embargo, también expone preguntas acerca de qué producto o tecnología que se debe usar para las aplicaciones en contenedores.

Como un *predeterminada* recomendación, el siguiente es el criterio principal recomendado en esta guía:

- **Aplicación monolítica única:** Elija Azure App Service
- **Aplicación de N niveles:** Elegir los orquestadores como App Service o Azure Kubernetes Service (AKS) si tiene un único o algunos servicios de back-end
- **Microservicios:** Elegir AKS o Azure Web Apps para contenedores
- **Funciones sin servidor y los controladores de eventos:** Elija las funciones de Azure
- **Lote a gran escala:** Elija Azure Batch

Sin embargo, esta recomendación se debe tomar con una pizca de sal, como selección del producto dependerá de características y necesidades de la aplicación específica. No todas las aplicaciones son los mismos, incluso cuando inicialmente podría ser tipos similares.

Después de un análisis más profundo de las necesidades de la aplicación, puede variar el producto seleccionado. Pero, como punto de partida, es conveniente tener una orientación inicial desde donde puede comenzar a evaluar y probar según prioridad concreta.

En la ilustración siguiente, puede ver un desglose de los distintos tipos de aplicaciones y su escenarios de hospedaje de Azure ideal.

![](./media/image8.5.png)

> [!div class="step-by-step"]
> [Anterior](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Siguiente](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
