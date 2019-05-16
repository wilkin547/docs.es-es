---
title: Elección de plataformas de procesos de Azure para aplicaciones basadas en contenedores
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Seleccionar plataformas de Azure compute para las aplicaciones basadas en contenedor
ms.date: 05/04/2018
ms.openlocfilehash: 28e103c67f47d63582384c9ab468a5f631b5ce9e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638980"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a>Elección de plataformas de procesos de Azure para aplicaciones basadas en contenedores

Como habrá observado después de leer las secciones anteriores, Azure es una nube abierta que ofrece varias opciones. Puede usar la mejor opción para sus necesidades, sin embargo, también expone preguntas acerca de qué producto o tecnología que se debe usar para las aplicaciones en contenedores.

Como un *predeterminada* recomendación, el siguiente es el criterio principal recomendado en esta guía:

- **Aplicación monolítica única:** Elija Azure App Service
- **Aplicación de N niveles:** Elegir los orquestadores como App Service, Service Fabric (SF) o Azure Kubernetes Service (AKS) si tiene un único o algunos servicios de back-end
- **Microservicios de Linux:** Elija AKS/Kubernetes
- **Microservicios de Windows:** Elija Service Fabric
- **Funciones sin servidor y los controladores de eventos:** Elija las funciones de Azure
- **Lote a gran escala:** Elija Azure Batch

Sin embargo, esta recomendación se debe tomar con una pizca de sal, como selección del producto dependerá de características y necesidades de la aplicación específica. No todas las aplicaciones son los mismos, incluso cuando inicialmente podría ser tipos similares.

Después de un análisis más profundo de las necesidades de la aplicación, puede variar el producto seleccionado. Pero, como punto de partida, es conveniente tener una orientación inicial desde donde puede comenzar a evaluar y probar según prioridad concreta.

En la ilustración siguiente, puede analizar un más global mientras la tabla de decisiones detalladas.

![](./media/image8.5.png)

Tenga en cuenta el modo subyacente del sistema operativo (Windows vs. Linux) también puede ser un factor de decisión, ya que algunos orquestadores son más maduro en contenedores de Linux y otras en los contenedores de Windows. Por ejemplo, los contenedores de Linux son muy consistente en Kubernetes (AKS en Azure), pero menos maduro en Service Fabric. Por otro lado, los contenedores de Windows son más maduro en Service Fabric (publicado en mayo de 2017) y menos maduro en AKS.

Sin embargo, estas diferencias en el nivel de madurez del sistema operativo quedará en el futuro y varias plataformas tienen comparable madurez del sistema operativo y la decisión está más en las preferencias según características específicas, la aplicación podría necesitar o según el ecosistema de la plataforma motivos.

> [!div class="step-by-step"]
> [Anterior](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Siguiente](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
