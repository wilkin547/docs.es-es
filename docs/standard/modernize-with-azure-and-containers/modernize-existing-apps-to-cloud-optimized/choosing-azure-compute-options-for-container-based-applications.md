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
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="91b36-103">Elección de plataformas de procesos de Azure para aplicaciones basadas en contenedores</span><span class="sxs-lookup"><span data-stu-id="91b36-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="91b36-104">Como habrá observado después de leer las secciones anteriores, Azure es una nube abierta que ofrece varias opciones.</span><span class="sxs-lookup"><span data-stu-id="91b36-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="91b36-105">Puede usar la mejor opción para sus necesidades, sin embargo, también expone preguntas acerca de qué producto o tecnología que se debe usar para las aplicaciones en contenedores.</span><span class="sxs-lookup"><span data-stu-id="91b36-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="91b36-106">Como un *predeterminada* recomendación, el siguiente es el criterio principal recomendado en esta guía:</span><span class="sxs-lookup"><span data-stu-id="91b36-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="91b36-107">**Aplicación monolítica única:** Elija Azure App Service</span><span class="sxs-lookup"><span data-stu-id="91b36-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="91b36-108">**Aplicación de N niveles:** Elegir los orquestadores como App Service o Azure Kubernetes Service (AKS) si tiene un único o algunos servicios de back-end</span><span class="sxs-lookup"><span data-stu-id="91b36-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS)or App Service if you have a single or few back-end services</span></span>
- <span data-ttu-id="91b36-109">**Microservicios:** Elegir AKS o Azure Web Apps para contenedores</span><span class="sxs-lookup"><span data-stu-id="91b36-109">**Microservices:** Choose AKS or Azure Web Apps for Containers</span></span>
- <span data-ttu-id="91b36-110">**Funciones sin servidor y los controladores de eventos:** Elija las funciones de Azure</span><span class="sxs-lookup"><span data-stu-id="91b36-110">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="91b36-111">**Lote a gran escala:** Elija Azure Batch</span><span class="sxs-lookup"><span data-stu-id="91b36-111">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="91b36-112">Sin embargo, esta recomendación se debe tomar con una pizca de sal, como selección del producto dependerá de características y necesidades de la aplicación específica.</span><span class="sxs-lookup"><span data-stu-id="91b36-112">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="91b36-113">No todas las aplicaciones son los mismos, incluso cuando inicialmente podría ser tipos similares.</span><span class="sxs-lookup"><span data-stu-id="91b36-113">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="91b36-114">Después de un análisis más profundo de las necesidades de la aplicación, puede variar el producto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="91b36-114">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="91b36-115">Pero, como punto de partida, es conveniente tener una orientación inicial desde donde puede comenzar a evaluar y probar según prioridad concreta.</span><span class="sxs-lookup"><span data-stu-id="91b36-115">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="91b36-116">En la ilustración siguiente, puede ver un desglose de los distintos tipos de aplicaciones y su escenarios de hospedaje de Azure ideal.</span><span class="sxs-lookup"><span data-stu-id="91b36-116">In the next figure, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![](./media/image8.5.png)

> [!div class="step-by-step"]
> <span data-ttu-id="91b36-117">[Anterior](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Siguiente](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="91b36-117">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
