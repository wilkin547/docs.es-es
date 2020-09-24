---
title: Resistencia nativa en la nube
description: Diseño de aplicaciones .NET nativas en la nube para Azure | Resistencia nativa en la nube
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 5c4fb261515c151fd666cc33cbb020447716c814
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163562"
---
# <a name="cloud-native-resiliency"></a><span data-ttu-id="ba70f-103">Resistencia nativa en la nube</span><span class="sxs-lookup"><span data-stu-id="ba70f-103">Cloud-native resiliency</span></span>

<span data-ttu-id="ba70f-104">La resistencia es la capacidad del sistema de reaccionar ante errores y seguir siendo funcional.</span><span class="sxs-lookup"><span data-stu-id="ba70f-104">Resiliency is the ability of your system to react to failure and still remain functional.</span></span> <span data-ttu-id="ba70f-105">No se trata de evitar los errores, sino de aceptar errores y construir los servicios nativos de la nube para responder a ellos.</span><span class="sxs-lookup"><span data-stu-id="ba70f-105">It's not about avoiding failure, but accepting failure and constructing your cloud-native services to respond to it.</span></span> <span data-ttu-id="ba70f-106">Desea volver a un estado totalmente funcional lo más rápido posible.</span><span class="sxs-lookup"><span data-stu-id="ba70f-106">You want to return to a fully functioning state quickly as possible.</span></span>

<span data-ttu-id="ba70f-107">A diferencia de las aplicaciones monolíticas tradicionales, donde todo se ejecuta en un único proceso, los sistemas nativos en la nube adoptan una arquitectura distribuida, tal como se muestra en la figura 6-1:</span><span class="sxs-lookup"><span data-stu-id="ba70f-107">Unlike traditional monolithic applications, where everything runs together in a single process, cloud-native systems embrace a distributed architecture as shown in Figure 6-1:</span></span>

![Entorno distribuido nativo en la nube](./media/distributed-cloud-native-environment.png)

<span data-ttu-id="ba70f-109">**Figura 6-1.**</span><span class="sxs-lookup"><span data-stu-id="ba70f-109">**Figure 6-1.**</span></span> <span data-ttu-id="ba70f-110">Entorno distribuido nativo en la nube</span><span class="sxs-lookup"><span data-stu-id="ba70f-110">Distributed cloud-native environment</span></span>

<span data-ttu-id="ba70f-111">En la ilustración anterior, todos los microservicios y los [servicios de respaldo](https://12factor.net/backing-services) basados en la nube se ejecutan en un proceso independiente, en la infraestructura del servidor, que se comunican a través de llamadas basadas en red.</span><span class="sxs-lookup"><span data-stu-id="ba70f-111">In the previous figure, each microservice and cloud-based [backing service](https://12factor.net/backing-services) execute in a separate process, across server infrastructure, communicating via network-based calls.</span></span>

<span data-ttu-id="ba70f-112">Al funcionar en este entorno, un servicio debe ser sensible a muchos desafíos diferentes:</span><span class="sxs-lookup"><span data-stu-id="ba70f-112">Operating in this environment, a service must be sensitive to many different challenges:</span></span>

- <span data-ttu-id="ba70f-113">Latencia de red inesperada: el tiempo de una solicitud de servicio para viajar al receptor y viceversa.</span><span class="sxs-lookup"><span data-stu-id="ba70f-113">Unexpected network latency - the time for a service request to travel to the receiver and back.</span></span>

- <span data-ttu-id="ba70f-114">Errores [transitorios](/azure/architecture/best-practices/transient-faults) : errores de conectividad de red de corta duración.</span><span class="sxs-lookup"><span data-stu-id="ba70f-114">[Transient faults](/azure/architecture/best-practices/transient-faults) - short-lived network connectivity errors.</span></span>

- <span data-ttu-id="ba70f-115">Bloqueo mediante una operación sincrónica de ejecución prolongada.</span><span class="sxs-lookup"><span data-stu-id="ba70f-115">Blockage by a long-running synchronous operation.</span></span>

- <span data-ttu-id="ba70f-116">Un proceso de host que se ha bloqueado y se está reiniciando o moviendo.</span><span class="sxs-lookup"><span data-stu-id="ba70f-116">A host process that has crashed and is being restarted or moved.</span></span>

- <span data-ttu-id="ba70f-117">Microservicio sobrecargado que no puede responder durante un breve período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="ba70f-117">An overloaded microservice that can't respond for a short time.</span></span>

- <span data-ttu-id="ba70f-118">Operación de Orchestrator en curso, como una actualización gradual o el traslado de un servicio de un nodo a otro.</span><span class="sxs-lookup"><span data-stu-id="ba70f-118">An in-flight orchestrator operation such as a rolling upgrade or moving a service from one node to another.</span></span>

- <span data-ttu-id="ba70f-119">Errores de hardware.</span><span class="sxs-lookup"><span data-stu-id="ba70f-119">Hardware failures.</span></span>

<span data-ttu-id="ba70f-120">Las plataformas en la nube pueden detectar y mitigar muchos de estos problemas de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="ba70f-120">Cloud platforms can detect and mitigate many of these infrastructure issues.</span></span> <span data-ttu-id="ba70f-121">Puede reiniciar, escalar horizontalmente e incluso redistribuir el servicio a un nodo diferente.</span><span class="sxs-lookup"><span data-stu-id="ba70f-121">It may restart, scale out, and even redistribute your service to a different node.</span></span>  <span data-ttu-id="ba70f-122">Sin embargo, para sacar el máximo partido de esta protección integrada, debe diseñar los servicios para reaccionar ante ellos y prosperar en este entorno dinámico.</span><span class="sxs-lookup"><span data-stu-id="ba70f-122">However, to take full advantage of this built-in protection, you must design your services to react to it and thrive in this dynamic environment.</span></span>

<span data-ttu-id="ba70f-123">En las secciones siguientes, exploraremos técnicas defensivas que el servicio y los recursos de nube administrados pueden aprovechar para minimizar el tiempo de inactividad y la interrupción.</span><span class="sxs-lookup"><span data-stu-id="ba70f-123">In the following sections, we'll explore defensive techniques that your service and managed cloud resources can leverage to minimize downtime and disruption.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ba70f-124">[Anterior](elastic-search-in-azure.md)
>[Siguiente](application-resiliency-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="ba70f-124">[Previous](elastic-search-in-azure.md)
[Next](application-resiliency-patterns.md)</span></span>
