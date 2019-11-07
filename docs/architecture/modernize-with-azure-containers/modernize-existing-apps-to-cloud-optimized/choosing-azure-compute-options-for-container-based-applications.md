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
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="1cbb7-103">Elección de plataformas de procesos de Azure para aplicaciones basadas en contenedores</span><span class="sxs-lookup"><span data-stu-id="1cbb7-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="1cbb7-104">Como ha observado después de leer las secciones anteriores, Azure es una nube abierta que ofrece varias opciones.</span><span class="sxs-lookup"><span data-stu-id="1cbb7-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="1cbb7-105">Puede usar la mejor opción para sus necesidades; sin embargo, también muestra preguntas sobre el producto o la tecnología que debe usar para las aplicaciones en contenedor.</span><span class="sxs-lookup"><span data-stu-id="1cbb7-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="1cbb7-106">Como recomendación *predeterminada* , los criterios principales recomendados en esta guía son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1cbb7-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="1cbb7-107">**Aplicación monolítica única:** Elegir Azure App Service</span><span class="sxs-lookup"><span data-stu-id="1cbb7-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="1cbb7-108">**Aplicación de N niveles:** Elija orquestadores como Azure Kubernetes Service (AKS) o App Service si tiene uno o varios servicios back-end.</span><span class="sxs-lookup"><span data-stu-id="1cbb7-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS) or App Service if you have a single or a few back-end services</span></span>
- <span data-ttu-id="1cbb7-109">**Microservicios:** Elección de AKS o Azure Web Apps para contenedores</span><span class="sxs-lookup"><span data-stu-id="1cbb7-109">**Microservices:** Choose AKS or Azure Web Apps for Containers</span></span>
- <span data-ttu-id="1cbb7-110">**Funciones sin servidor & controladores de eventos:** Elegir Azure Functions</span><span class="sxs-lookup"><span data-stu-id="1cbb7-110">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="1cbb7-111">**Lote a gran escala:** Elegir Azure Batch</span><span class="sxs-lookup"><span data-stu-id="1cbb7-111">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="1cbb7-112">Sin embargo, esta recomendación se debe llevar a cabo con un contacto de sal, ya que la selección del producto dependerá de las necesidades y características específicas de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1cbb7-112">However, this recommendation should be taken with a pinch of salt, as the product's selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="1cbb7-113">No todas las aplicaciones son iguales incluso cuando inicialmente pueden ser tipos similares.</span><span class="sxs-lookup"><span data-stu-id="1cbb7-113">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="1cbb7-114">Después de un análisis más profundo de las necesidades de la aplicación, el producto seleccionado podría ser diferente.</span><span class="sxs-lookup"><span data-stu-id="1cbb7-114">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="1cbb7-115">Sin embargo, como punto de partida, es conveniente tener una guía inicial desde la que puede comenzar a evaluar y probar en función de una prioridad determinada.</span><span class="sxs-lookup"><span data-stu-id="1cbb7-115">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="1cbb7-116">En la figura 1, puede ver un desglose de los diferentes tipos de aplicaciones y sus escenarios de hospedaje de Azure ideales.</span><span class="sxs-lookup"><span data-stu-id="1cbb7-116">In Figure 1, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![Tabla de los escenarios de hospedaje de Azure más adecuados para las diferentes aplicaciones.](./media/choosing-azure-compute-options-for-container-based-applications/azure-hosting-scenarios-for-apps.png)

> [!div class="step-by-step"]
> <span data-ttu-id="1cbb7-118">[Anterior](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [Siguiente](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="1cbb7-118">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
