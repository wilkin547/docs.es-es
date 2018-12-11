---
title: Seleccionar plataformas de Azure compute para las aplicaciones basadas en contenedor
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Seleccionar plataformas de Azure compute para las aplicaciones basadas en contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/04/2018
ms.openlocfilehash: 20d8899d404ec72e3b1b9c2471524133a6428c44
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53125501"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="73246-103">Seleccionar plataformas de Azure compute para las aplicaciones basadas en contenedor</span><span class="sxs-lookup"><span data-stu-id="73246-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="73246-104">Como habrá observado después de leer las secciones anteriores, Azure es una nube abierta que ofrece varias opciones.</span><span class="sxs-lookup"><span data-stu-id="73246-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="73246-105">Puede usar la mejor opción para sus necesidades, sin embargo, también expone preguntas acerca de qué producto o tecnología que se debe usar para las aplicaciones en contenedores.</span><span class="sxs-lookup"><span data-stu-id="73246-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="73246-106">Como un *predeterminada* recomendación, el siguiente es el criterio principal recomendado en esta guía:</span><span class="sxs-lookup"><span data-stu-id="73246-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

  - <span data-ttu-id="73246-107">**Aplicación monolítica única:** Elija Azure App Service</span><span class="sxs-lookup"><span data-stu-id="73246-107">**Single monolithic app:** Choose Azure App Service</span></span>
  - <span data-ttu-id="73246-108">**Aplicación de N niveles:** Elegir los orquestadores como App Service, Service Fabric (SF) o Azure Kubernetes Service (AKS) si tiene un único o algunos servicios de back-end</span><span class="sxs-lookup"><span data-stu-id="73246-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS), Service Fabric (SF) or App Service if you have a single or few back-end services</span></span>
  - <span data-ttu-id="73246-109">**Microservicios de Linux:** Elija AKS/Kubernetes</span><span class="sxs-lookup"><span data-stu-id="73246-109">**Linux microservices:** Choose AKS/Kubernetes</span></span>
  - <span data-ttu-id="73246-110">**Microservicios de Windows:** Elija Service Fabric</span><span class="sxs-lookup"><span data-stu-id="73246-110">**Windows microservices:** Choose Service Fabric</span></span>
  - <span data-ttu-id="73246-111">**Funciones sin servidor y los controladores de eventos:** Elija las funciones de Azure</span><span class="sxs-lookup"><span data-stu-id="73246-111">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
  - <span data-ttu-id="73246-112">**Lote a gran escala:** Elija Azure Batch</span><span class="sxs-lookup"><span data-stu-id="73246-112">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="73246-113">Sin embargo, esta recomendación se debe tomar con una pizca de sal, como selección del producto dependerá de características y necesidades de la aplicación específica.</span><span class="sxs-lookup"><span data-stu-id="73246-113">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="73246-114">No todas las aplicaciones son los mismos, incluso cuando inicialmente podría ser tipos similares.</span><span class="sxs-lookup"><span data-stu-id="73246-114">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="73246-115">Después de un análisis más profundo de las necesidades de la aplicación, puede variar el producto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="73246-115">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="73246-116">Pero, como punto de partida, es conveniente tener una orientación inicial desde donde puede comenzar a evaluar y probar según prioridad concreta.</span><span class="sxs-lookup"><span data-stu-id="73246-116">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="73246-117">En la ilustración siguiente, puede analizar un más global mientras la tabla de decisiones detalladas.</span><span class="sxs-lookup"><span data-stu-id="73246-117">In the next figure, you can analyze a more global while detailed decision table.</span></span>

![](./media/image8.5.png)

<span data-ttu-id="73246-118">Tenga en cuenta el modo subyacente del sistema operativo (Windows vs. Linux) también puede ser un factor de decisión, ya que algunos orquestadores son más maduro en contenedores de Linux y otras en los contenedores de Windows.</span><span class="sxs-lookup"><span data-stu-id="73246-118">Notice how the underlying OS (Windows vs. Linux) can also be a decision factor as some orchestrators are more mature on Linux containers and other on Windows containers.</span></span> <span data-ttu-id="73246-119">Por ejemplo, los contenedores de Linux son muy consistente en Kubernetes (AKS en Azure), pero menos maduro en Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="73246-119">For instance, Linux containers are very mature in Kubernetes (AKS in Azure) but less mature on Service Fabric.</span></span> <span data-ttu-id="73246-120">Por otro lado, los contenedores de Windows son más maduro en Service Fabric (publicado en mayo de 2017) y menos maduro en AKS.</span><span class="sxs-lookup"><span data-stu-id="73246-120">On the other hand, Windows Containers are more mature in Service Fabric (released in May 2017) and less mature in AKS.</span></span>

<span data-ttu-id="73246-121">Sin embargo, estas diferencias en el nivel de madurez del sistema operativo quedará en el futuro y varias plataformas tienen comparable madurez del sistema operativo y la decisión está más en las preferencias según características específicas, la aplicación podría necesitar o según el ecosistema de la plataforma motivos.</span><span class="sxs-lookup"><span data-stu-id="73246-121">However, those differences in OS maturity will fade in the future and multiple platforms will have comparable OS maturity and the decision will lay more on preferences based on specific features your application might need or based on each platform's ecosystem reasons.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="73246-122">[Anterior](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
>[Siguiente](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="73246-122">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>