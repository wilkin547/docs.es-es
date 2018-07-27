---
title: Implementar aplicaciones resistentes
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Implementar aplicaciones resistentes
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/08/2018
ms.openlocfilehash: dc0db8f0cdfa77bcca467c3c632b3d93de8851d8
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2018
ms.locfileid: "37875130"
---
# <a name="implementing-resilient-applications"></a><span data-ttu-id="b9674-103">Implementar aplicaciones resistentes</span><span class="sxs-lookup"><span data-stu-id="b9674-103">Implementing Resilient Applications</span></span>

<span data-ttu-id="b9674-104">*Sus aplicaciones basadas en microservicios y en la nube deben estar preparadas para los errores parciales que seguramente se acabarán produciendo en algún momento. Debe diseñar su aplicación de modo que sea resistente a estos errores parciales.*</span><span class="sxs-lookup"><span data-stu-id="b9674-104">*Your microservice and cloud-based applications must embrace the partial failures that will certainly occur eventually. You need to design your application so it will be resilient to those partial failures.*</span></span>

<span data-ttu-id="b9674-105">La resistencia es la capacidad de recuperarse de errores y seguir funcionando.</span><span class="sxs-lookup"><span data-stu-id="b9674-105">Resiliency is the ability to recover from failures and continue to function.</span></span> <span data-ttu-id="b9674-106">No se trata de evitar los errores, sino de aceptar el hecho de que se producirán errores y responder a ellos para evitar el tiempo de inactividad o la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="b9674-106">It is not about avoiding failures but accepting the fact that failures will happen and responding to them in a way that avoids downtime or data loss.</span></span> <span data-ttu-id="b9674-107">El objetivo de la resistencia consiste en que la aplicación vuelva a un estado totalmente operativo después de un error.</span><span class="sxs-lookup"><span data-stu-id="b9674-107">The goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="b9674-108">Es todo un desafío diseñar e implementar una aplicación basada en microservicios.</span><span class="sxs-lookup"><span data-stu-id="b9674-108">It is challenging enough to design and deploy a microservices-based application.</span></span> <span data-ttu-id="b9674-109">Pero también necesita mantener la aplicación en ejecución en un entorno en el que con seguridad se producirá algún tipo de error.</span><span class="sxs-lookup"><span data-stu-id="b9674-109">But you also need to keep your application running in an environment where some sort of failure is certain.</span></span> <span data-ttu-id="b9674-110">Por lo tanto, la aplicación debe ser resistente.</span><span class="sxs-lookup"><span data-stu-id="b9674-110">Therefore, your application should be resilient.</span></span> <span data-ttu-id="b9674-111">Debe estar diseñada para hacer frente a errores parciales, como las interrupciones de red o el bloqueo de nodos o máquinas virtuales en la nube.</span><span class="sxs-lookup"><span data-stu-id="b9674-111">It should be designed to cope with partial failures, like network outages or nodes or VMs crashing in the cloud.</span></span> <span data-ttu-id="b9674-112">Incluso los microservicios (contenedores) que se mueven a otro nodo dentro de un clúster pueden causar breves errores intermitentes dentro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b9674-112">Even microservices (containers) being moved to a different node within a cluster can cause intermittent short failures within the application.</span></span>

<span data-ttu-id="b9674-113">Los numerosos componentes individuales de la aplicación también deberían incorporar características de seguimiento de estado.</span><span class="sxs-lookup"><span data-stu-id="b9674-113">The many individual components of your application should also incorporate health monitoring features.</span></span> <span data-ttu-id="b9674-114">Mediante las directrices descritas en este capítulo, podrá crear una aplicación que funcione sin problemas aunque se produzcan tiempos de inactividad transitorios o las interrupciones típicas de las implementaciones complejas y basadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="b9674-114">By following the guidelines in this chapter, you can create an application that can work smoothly in spite of transient downtime or the normal hiccups that occur in complex and cloud-based deployments.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="b9674-115">[Anterior](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
[Siguiente](handle-partial-failure.md)</span><span class="sxs-lookup"><span data-stu-id="b9674-115">[Previous](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
[Next](handle-partial-failure.md)</span></span>
