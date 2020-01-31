---
title: Resistencia nativa en la nube
description: Diseño de aplicaciones .NET nativas en la nube para Azure | Resistencia nativa en la nube
ms.date: 06/30/2019
ms.openlocfilehash: 427405d95534c4467ab519c2188fe88e2f18e2b2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781086"
---
# <a name="cloud-native-resiliency"></a><span data-ttu-id="94f6d-103">Resistencia nativa en la nube</span><span class="sxs-lookup"><span data-stu-id="94f6d-103">Cloud-native resiliency</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="94f6d-104">La resistencia es la capacidad del sistema de reaccionar ante errores y seguir siendo funcional.</span><span class="sxs-lookup"><span data-stu-id="94f6d-104">Resiliency is the ability of your system to react to failure and still remain functional.</span></span> <span data-ttu-id="94f6d-105">No se trata de evitar los errores.</span><span class="sxs-lookup"><span data-stu-id="94f6d-105">It isn't about avoiding failure.</span></span> <span data-ttu-id="94f6d-106">Pero se trata de aceptar que el error es inevitable en los sistemas basados en la nube y compilar la aplicación para responder a ella.</span><span class="sxs-lookup"><span data-stu-id="94f6d-106">But it's about accepting that failure is inevitable in cloud-based systems and building your application to respond to it.</span></span> <span data-ttu-id="94f6d-107">El objetivo final de la resistencia es devolver la aplicación a un estado totalmente funcional después de un error.</span><span class="sxs-lookup"><span data-stu-id="94f6d-107">The end-goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="94f6d-108">A diferencia de las aplicaciones monolíticas tradicionales, donde todo se ejecuta en un único proceso, los sistemas nativos en la nube adoptan una arquitectura distribuida como se muestra en la figura 6-1:</span><span class="sxs-lookup"><span data-stu-id="94f6d-108">Unlike traditional monolithic applications, where everything runs together in a single process, cloud-native systems embrace distributed architecture as shown in Figure 6-1:</span></span>

![Entorno distribuido nativo en la nube](./media/distributed-cloud-native-environment.png)

<span data-ttu-id="94f6d-110">**Figura 6-1.**</span><span class="sxs-lookup"><span data-stu-id="94f6d-110">**Figure 6-1.**</span></span> <span data-ttu-id="94f6d-111">Entorno distribuido nativo en la nube</span><span class="sxs-lookup"><span data-stu-id="94f6d-111">Distributed cloud-native environment</span></span>

<span data-ttu-id="94f6d-112">En la ilustración anterior, observe cómo cada cliente, microservicio y [servicio de respaldo](https://12factor.net/backing-services) basado en la nube se ejecutan como un proceso independiente que se ejecuta en distintos servidores y se comunican a través de llamadas basadas en red.</span><span class="sxs-lookup"><span data-stu-id="94f6d-112">In the previous figure, note how each client, microservice, and cloud-based [backing service](https://12factor.net/backing-services) executes as a separate process, running across different servers, all communicating via network-based calls.</span></span>

<span data-ttu-id="94f6d-113">¿Qué podría ir mal?</span><span class="sxs-lookup"><span data-stu-id="94f6d-113">So, what could go wrong?</span></span>

- <span data-ttu-id="94f6d-114">[Latencia de red](https://www.techopedia.com/definition/8553/network-latency)inesperada.</span><span class="sxs-lookup"><span data-stu-id="94f6d-114">Unexpected [network latency](https://www.techopedia.com/definition/8553/network-latency).</span></span>
- <span data-ttu-id="94f6d-115">Errores [transitorios](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) (errores de conectividad de red temporales).</span><span class="sxs-lookup"><span data-stu-id="94f6d-115">[Transient faults](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) (temporary network connectivity errors).</span></span>
- <span data-ttu-id="94f6d-116">Bloqueo mediante una operación sincrónica de ejecución prolongada.</span><span class="sxs-lookup"><span data-stu-id="94f6d-116">Blocking by a long-running synchronous operation.</span></span>
- <span data-ttu-id="94f6d-117">Un proceso de host que se ha bloqueado y se está reiniciando o moviendo.</span><span class="sxs-lookup"><span data-stu-id="94f6d-117">A host process that has crashed and is being restarted or moved.</span></span>
- <span data-ttu-id="94f6d-118">Microservicio sobrecargado que no puede responder durante un breve período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="94f6d-118">An overloaded microservice that can't respond for a short time.</span></span>
- <span data-ttu-id="94f6d-119">Operación DevOps en curso, como una operación de actualización o escalado.</span><span class="sxs-lookup"><span data-stu-id="94f6d-119">An in-flight DevOps operation such as an update or scaling operation.</span></span>
- <span data-ttu-id="94f6d-120">Operación de orquestador, como mover un servicio de un nodo a otro.</span><span class="sxs-lookup"><span data-stu-id="94f6d-120">An Orchestrator operation such as moving a service from one node to another.</span></span>
- <span data-ttu-id="94f6d-121">Errores de hardware de hardware estándar.</span><span class="sxs-lookup"><span data-stu-id="94f6d-121">Hardware failures from commodity hardware.</span></span>

<span data-ttu-id="94f6d-122">Al implementar servicios distribuidos en una infraestructura basada en la nube, los factores de la lista anterior se vuelven muy reales y debe diseñarlos y desarrollarlos de forma defensiva para abordarlos.</span><span class="sxs-lookup"><span data-stu-id="94f6d-122">When deploying distributed services into cloud-based infrastructure, the factors from the previous list become very real and you must architect and develop defensively to deal with them.</span></span>

<span data-ttu-id="94f6d-123">En un sistema distribuido a pequeña escala, el error será menos frecuente, pero a medida que un sistema se escale verticalmente y horizontalmente, puede esperar experimentar más de estos problemas hasta un punto en el que el error parcial se convierte en un funcionamiento normal.</span><span class="sxs-lookup"><span data-stu-id="94f6d-123">In a small-scale distributed system, failure will be less frequent, but as a system scales up and out, you can expect to experience more of these issues to a point where partial failure becomes normal operation.</span></span>

<span data-ttu-id="94f6d-124">Por lo tanto, la aplicación y la infraestructura deben ser resistentes.</span><span class="sxs-lookup"><span data-stu-id="94f6d-124">Therefore, your application and infrastructure must be resilient.</span></span> <span data-ttu-id="94f6d-125">En las secciones siguientes, exploraremos técnicas defensivas que puede Agregar a su aplicación y características integradas en la nube que puede aprovechar para ayudar a revisar la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="94f6d-125">In the following sections, we'll explore defensive techniques that you can add to your application and built-in cloud features that you can leverage to help bullet-proof your user's experience.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="94f6d-126">[Anterior](elastic-search-in-azure.md)
>[Siguiente](application-resiliency-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="94f6d-126">[Previous](elastic-search-in-azure.md)
[Next](application-resiliency-patterns.md)</span></span>
