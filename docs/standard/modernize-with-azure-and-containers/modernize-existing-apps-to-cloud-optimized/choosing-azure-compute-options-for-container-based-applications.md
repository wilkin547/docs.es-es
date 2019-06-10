---
title: Elección de plataformas de procesos de Azure para aplicaciones basadas en contenedores
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Seleccionar plataformas de Azure compute para las aplicaciones basadas en contenedor
ms.date: 05/04/2018
ms.openlocfilehash: d91cd279402dc24beb5f766c06cb85ac8d74f482
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758807"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="9a823-103">Elección de plataformas de procesos de Azure para aplicaciones basadas en contenedores</span><span class="sxs-lookup"><span data-stu-id="9a823-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="9a823-104">Como habrá observado después de leer las secciones anteriores, Azure es una nube abierta que ofrece varias opciones.</span><span class="sxs-lookup"><span data-stu-id="9a823-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="9a823-105">Puede usar la mejor opción para sus necesidades, sin embargo, también expone preguntas acerca de qué producto o tecnología que se debe usar para las aplicaciones en contenedores.</span><span class="sxs-lookup"><span data-stu-id="9a823-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="9a823-106">Como un *predeterminada* recomendación, el siguiente es el criterio principal recomendado en esta guía:</span><span class="sxs-lookup"><span data-stu-id="9a823-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="9a823-107">**Aplicación monolítica única:** Elija Azure App Service</span><span class="sxs-lookup"><span data-stu-id="9a823-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="9a823-108">**Aplicación de N niveles:** Elegir los orquestadores como App Service o Azure Kubernetes Service (AKS) si tiene un único o algunos servicios de back-end</span><span class="sxs-lookup"><span data-stu-id="9a823-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS)or App Service if you have a single or few back-end services</span></span>
- <span data-ttu-id="9a823-109">**Microservicios de Linux:** Elija AKS/Kubernetes</span><span class="sxs-lookup"><span data-stu-id="9a823-109">**Linux microservices:** Choose AKS/Kubernetes</span></span>
- <span data-ttu-id="9a823-110">**Microservicios de Windows:** Elegir aplicaciones Web de Azure para contenedores</span><span class="sxs-lookup"><span data-stu-id="9a823-110">**Windows microservices:** Choose Azure Web Apps for Containers</span></span>
- <span data-ttu-id="9a823-111">**Funciones sin servidor y los controladores de eventos:** Elija las funciones de Azure</span><span class="sxs-lookup"><span data-stu-id="9a823-111">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="9a823-112">**Lote a gran escala:** Elija Azure Batch</span><span class="sxs-lookup"><span data-stu-id="9a823-112">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="9a823-113">Sin embargo, esta recomendación se debe tomar con una pizca de sal, como selección del producto dependerá de características y necesidades de la aplicación específica.</span><span class="sxs-lookup"><span data-stu-id="9a823-113">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="9a823-114">No todas las aplicaciones son los mismos, incluso cuando inicialmente podría ser tipos similares.</span><span class="sxs-lookup"><span data-stu-id="9a823-114">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="9a823-115">Después de un análisis más profundo de las necesidades de la aplicación, puede variar el producto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9a823-115">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="9a823-116">Pero, como punto de partida, es conveniente tener una orientación inicial desde donde puede comenzar a evaluar y probar según prioridad concreta.</span><span class="sxs-lookup"><span data-stu-id="9a823-116">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="9a823-117">En la ilustración siguiente, puede ver un desglose de los distintos tipos de aplicaciones y su escenarios de hospedaje de Azure ideal.</span><span class="sxs-lookup"><span data-stu-id="9a823-117">In the next figure, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![](./media/image8.5.png)

> [!div class="step-by-step"]
> <span data-ttu-id="9a823-118">[Anterior](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Siguiente](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="9a823-118">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
