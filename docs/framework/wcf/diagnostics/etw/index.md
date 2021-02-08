---
description: 'Más información sobre: traza analítica con ETW'
title: Traza analítica con ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: fd40d40de2508fd251c793e4455c1e656a1cbbf6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798802"
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="487c5-103">Traza analítica con ETW</span><span class="sxs-lookup"><span data-stu-id="487c5-103">Analytic Tracing with ETW</span></span>

<span data-ttu-id="487c5-104">La traza analítica de Windows Communication Foundation (WCF) ofrece una manera de capturar información de diagnóstico durante la ejecución de un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="487c5-104">Windows Communication Foundation (WCF) analytic tracing offers a way to capture diagnostic information during the execution of a WCF service.</span></span> <span data-ttu-id="487c5-105">Los eventos de seguimiento analítico de WCF se emiten en puntos clave de la pila de WCF para permitir la solución de problemas de los servicios WCF en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="487c5-105">WCF analytic tracing events are emitted at key points in the WCF stack to allow troubleshooting of WCF services in a production environment.</span></span> <span data-ttu-id="487c5-106">La traza analítica de los servicios WCF tiene un impacto mínimo en el rendimiento de un servidor de producto que hospeda los [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] servicios WCF, ya que estos eventos se emiten de forma muy eficaz a una sesión de seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="487c5-106">Analytic tracing for WCF services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="487c5-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="487c5-107">In This Section</span></span>  

 [<span data-ttu-id="487c5-108">Información general de traza analítica</span><span class="sxs-lookup"><span data-stu-id="487c5-108">Analytic Tracing Overview</span></span>](analytic-tracing-overview.md)  
 <span data-ttu-id="487c5-109">Describe cómo funciona el seguimiento analítico de WCF en [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="487c5-109">Discusses how WCF analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="487c5-110">Habilitar dinámicamente la traza analítica</span><span class="sxs-lookup"><span data-stu-id="487c5-110">Dynamically Enabling Analytic Tracing</span></span>](dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="487c5-111">Describe cómo habilitar o deshabilitar la traza de forma dinámica mediante ETW.</span><span class="sxs-lookup"><span data-stu-id="487c5-111">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="487c5-112">Configurar la traza de flujo de mensajes</span><span class="sxs-lookup"><span data-stu-id="487c5-112">Configuring Message Flow Tracing</span></span>](configuring-message-flow-tracing.md)  
 <span data-ttu-id="487c5-113">Describe cómo configurar la traza de flujo de mensajes.</span><span class="sxs-lookup"><span data-stu-id="487c5-113">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="487c5-114">Referencia de evento de traza analítica</span><span class="sxs-lookup"><span data-stu-id="487c5-114">Analytic Trace Event Reference</span></span>](analytic-trace-event-reference.md)  
 <span data-ttu-id="487c5-115">Muestra una tabla de identificadores de eventos con sus niveles de evento, mensajes de evento y palabras clave.</span><span class="sxs-lookup"><span data-stu-id="487c5-115">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="487c5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="487c5-116">See also</span></span>

- [<span data-ttu-id="487c5-117">Servicios de WCF y seguimiento de eventos para Windows</span><span class="sxs-lookup"><span data-stu-id="487c5-117">WCF Services and Event Tracing for Windows</span></span>](../../samples/wcf-services-and-event-tracing-for-windows.md)
- [<span data-ttu-id="487c5-118">Seguimiento de eventos en Seguimiento de eventos para Windows</span><span class="sxs-lookup"><span data-stu-id="487c5-118">Tracking Events into Event Tracing in Windows</span></span>](../../../windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
