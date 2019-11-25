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
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="706ec-103">Elección de plataformas de procesos de Azure para aplicaciones basadas en contenedores</span><span class="sxs-lookup"><span data-stu-id="706ec-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="706ec-104">Tal y como ha observado después de leer las secciones anteriores, Azure es una nube abierta que ofrece numerosas opciones.</span><span class="sxs-lookup"><span data-stu-id="706ec-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="706ec-105">Puede usar la opción que mejor se adapte a sus necesidades; sin embargo, plantea preguntas sobre qué producto o tecnología debe usar para las aplicaciones en contenedor.</span><span class="sxs-lookup"><span data-stu-id="706ec-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="706ec-106">Los siguientes son los principales criterios *predeterminados* que se recomiendan en esta guía:</span><span class="sxs-lookup"><span data-stu-id="706ec-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="706ec-107">**Aplicación monolítica única:** Elegir Azure App Service</span><span class="sxs-lookup"><span data-stu-id="706ec-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="706ec-108">**Aplicación de N niveles:** elija orquestadores como Azure Kubernetes Service (AKS) o App Service si tiene uno o varios servicios back-end.</span><span class="sxs-lookup"><span data-stu-id="706ec-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS) or App Service if you have a single or a few back-end services</span></span>
- <span data-ttu-id="706ec-109">**Microservicios:** elija AKS o Azure Web Apps for Containers.</span><span class="sxs-lookup"><span data-stu-id="706ec-109">**Microservices:** Choose AKS or Azure Web Apps for Containers</span></span>
- <span data-ttu-id="706ec-110">**Funciones sin servidor y controladores de eventos:** elija Azure Functions.</span><span class="sxs-lookup"><span data-stu-id="706ec-110">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="706ec-111">**Lotes a gran escala:** elija Azure Batch.</span><span class="sxs-lookup"><span data-stu-id="706ec-111">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="706ec-112">Sin embargo, esta recomendación no se debe tomar como ley universal, porque la elección del producto dependerá de las necesidades y características específicas de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="706ec-112">However, this recommendation should be taken with a pinch of salt, as the product's selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="706ec-113">No todas las aplicaciones son iguales aunque inicialmente puedan parecer similares.</span><span class="sxs-lookup"><span data-stu-id="706ec-113">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="706ec-114">Después de un análisis más profundo de las necesidades de la aplicación, el producto seleccionado podría ser otro.</span><span class="sxs-lookup"><span data-stu-id="706ec-114">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="706ec-115">Sin embargo, como punto de partida, es conveniente tener una guía con la que poder empezar a realizar evaluaciones y pruebas en función de una prioridad determinada.</span><span class="sxs-lookup"><span data-stu-id="706ec-115">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="706ec-116">En la figura 1, puede ver un desglose de los diferentes tipos de aplicaciones y sus escenarios de hospedaje de Azure ideales.</span><span class="sxs-lookup"><span data-stu-id="706ec-116">In Figure 1, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![Tabla de los escenarios de hospedaje de Azure más adecuados para las diferentes aplicaciones.](./media/choosing-azure-compute-options-for-container-based-applications/azure-hosting-scenarios-for-apps.png)

> [!div class="step-by-step"]
> <span data-ttu-id="706ec-118">[Anterior](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Siguiente](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="706ec-118">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
