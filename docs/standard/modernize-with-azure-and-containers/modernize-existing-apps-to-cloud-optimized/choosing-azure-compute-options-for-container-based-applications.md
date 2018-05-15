---
title: Elegir plataformas de proceso de Azure para aplicaciones basadas en el contenedor
description: Modernizar las aplicaciones .NET existentes con contenedores de Windows y de nube de Azure | Elegir plataformas de proceso de Azure para aplicaciones basadas en el contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/04/2018
ms.openlocfilehash: ebf022a52aaaf95ae335976f5e097921b0ac8006
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="7b924-103">Elegir plataformas de proceso de Azure para aplicaciones basadas en el contenedor</span><span class="sxs-lookup"><span data-stu-id="7b924-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="7b924-104">Como es posible que haya observado después de leer las secciones anteriores, Azure es una nube abierta que ofrece varias opciones.</span><span class="sxs-lookup"><span data-stu-id="7b924-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="7b924-105">Puede usar el ajuste óptimo para sus necesidades, sin embargo, también expone preguntas acerca de los productos y tecnologías que se debe usar para las aplicaciones en contenedores.</span><span class="sxs-lookup"><span data-stu-id="7b924-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="7b924-106">Como un *de forma predeterminada* recomendación, éste es el criterio principal recomendado en esta guía:</span><span class="sxs-lookup"><span data-stu-id="7b924-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

  - <span data-ttu-id="7b924-107">**Única aplicación monolítico:** elegir servicio de aplicaciones de Azure</span><span class="sxs-lookup"><span data-stu-id="7b924-107">**Single monolithic app:** Choose Azure App Service</span></span>
  - <span data-ttu-id="7b924-108">**Aplicación de N niveles:** elija orchestrators como servicio de Kubernetes de Azure (AKS), servicio tejido (SF) o servicio de aplicaciones si tiene un único o algunos servicios back-end</span><span class="sxs-lookup"><span data-stu-id="7b924-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS), Service Fabric (SF) or App Service if you have a single or few back-end services</span></span>
  - <span data-ttu-id="7b924-109">**Linux microservicios:** AKS/Kubernetes elija</span><span class="sxs-lookup"><span data-stu-id="7b924-109">**Linux microservices:** Choose AKS/Kubernetes</span></span>
  - <span data-ttu-id="7b924-110">**Windows microservicios:** elija Service Fabric</span><span class="sxs-lookup"><span data-stu-id="7b924-110">**Windows microservices:** Choose Service Fabric</span></span>
  - <span data-ttu-id="7b924-111">**Funciones sin servidor & controladores de eventos:** elegir funciones de Azure</span><span class="sxs-lookup"><span data-stu-id="7b924-111">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
  - <span data-ttu-id="7b924-112">**Proceso por lotes a gran escala:** elija Azure Batch</span><span class="sxs-lookup"><span data-stu-id="7b924-112">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="7b924-113">Sin embargo, esta recomendación debe tener cuidada con un gesto de valor "salt", como la selección del producto dependerá de las necesidades y las características de la aplicación específica.</span><span class="sxs-lookup"><span data-stu-id="7b924-113">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="7b924-114">No todas las aplicaciones son los mismos, incluso cuando inicialmente pueden parecer tipos similares.</span><span class="sxs-lookup"><span data-stu-id="7b924-114">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="7b924-115">Después de realizar un análisis más profundos de necesidades de la aplicación, puede variar el producto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="7b924-115">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="7b924-116">Pero, como punto de partida, es conveniente tener instrucciones inicial desde donde puede empezar a evaluar y probar basado en prioridad concreta.</span><span class="sxs-lookup"><span data-stu-id="7b924-116">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="7b924-117">En la ilustración siguiente, puede analizar más global mientras la tabla de decisiones detallada.</span><span class="sxs-lookup"><span data-stu-id="7b924-117">In the next figure, you can analyze a more global while detailed decision table.</span></span>

![](./media/image8.5.png)

<span data-ttu-id="7b924-118">Observe cómo el subyacente OS (frente a Windows. Linux) también puede ser un factor de decisión como algunos orchestrators son más maduro en contenedores de Linux y otros en los contenedores de Windows.</span><span class="sxs-lookup"><span data-stu-id="7b924-118">Notice how the underlying OS (Windows vs. Linux) can also be a decision factor as some orchestrators are more mature on Linux containers and other on Windows containers.</span></span> <span data-ttu-id="7b924-119">Por ejemplo, los contenedores de Linux están muy consolidados en Kubernetes (AKS en Azure) pero menos maduro en el tejido de servicio.</span><span class="sxs-lookup"><span data-stu-id="7b924-119">For instance, Linux containers are very mature in Kubernetes (AKS in Azure) but less mature on Service Fabric.</span></span> <span data-ttu-id="7b924-120">Por otro lado, los contenedores de Windows son más maduro en Service Fabric (que se publicó en mayo de 2017) y menos maduro en AKS.</span><span class="sxs-lookup"><span data-stu-id="7b924-120">On the other hand, Windows Containers are more mature in Service Fabric (released in May 2017) and less mature in AKS.</span></span>

<span data-ttu-id="7b924-121">Sin embargo, pierden esas diferencias en el nivel de madurez de sistema operativo en el futuro y varias plataformas tendrán el nivel de madurez de comparable OS y la decisión de disposición de más información sobre las preferencias en función de las características específicas que la aplicación necesite o, según el ecosistema de cada plataforma motivos.</span><span class="sxs-lookup"><span data-stu-id="7b924-121">However, those differences in OS maturity will fade in the future and multiple platforms will have comparable OS maturity and the decision will lay more on preferences based on specific features your application might need or based on each platform's ecosystem reasons.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="7b924-122">[Anterior](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Siguiente](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="7b924-122">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
