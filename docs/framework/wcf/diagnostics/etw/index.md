---
title: Traza analítica con ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: 4bb31eeac7c5d3c8c30f66090b07de9f8af4d5a4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274626"
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="274e7-102">Traza analítica con ETW</span><span class="sxs-lookup"><span data-stu-id="274e7-102">Analytic Tracing with ETW</span></span>

<span data-ttu-id="274e7-103">La traza analítica de Windows Communication Foundation (WCF) ofrece una manera de capturar información de diagnóstico durante la ejecución de un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="274e7-103">Windows Communication Foundation (WCF) analytic tracing offers a way to capture diagnostic information during the execution of a WCF service.</span></span> <span data-ttu-id="274e7-104">Los eventos de seguimiento analítico de WCF se emiten en puntos clave de la pila de WCF para permitir la solución de problemas de los servicios WCF en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="274e7-104">WCF analytic tracing events are emitted at key points in the WCF stack to allow troubleshooting of WCF services in a production environment.</span></span> <span data-ttu-id="274e7-105">La traza analítica de los servicios WCF tiene un impacto mínimo en el rendimiento de un servidor de producto que hospeda los [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] servicios WCF, ya que estos eventos se emiten de forma muy eficaz a una sesión de seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="274e7-105">Analytic tracing for WCF services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="274e7-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="274e7-106">In This Section</span></span>  

 [<span data-ttu-id="274e7-107">Información general de traza analítica</span><span class="sxs-lookup"><span data-stu-id="274e7-107">Analytic Tracing Overview</span></span>](analytic-tracing-overview.md)  
 <span data-ttu-id="274e7-108">Describe cómo funciona el seguimiento analítico de WCF en [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="274e7-108">Discusses how WCF analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="274e7-109">Habilitar dinámicamente la traza analítica</span><span class="sxs-lookup"><span data-stu-id="274e7-109">Dynamically Enabling Analytic Tracing</span></span>](dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="274e7-110">Describe cómo habilitar o deshabilitar la traza de forma dinámica mediante ETW.</span><span class="sxs-lookup"><span data-stu-id="274e7-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="274e7-111">Configurar la traza de flujo de mensajes</span><span class="sxs-lookup"><span data-stu-id="274e7-111">Configuring Message Flow Tracing</span></span>](configuring-message-flow-tracing.md)  
 <span data-ttu-id="274e7-112">Describe cómo configurar la traza de flujo de mensajes.</span><span class="sxs-lookup"><span data-stu-id="274e7-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="274e7-113">Referencia de evento de traza analítica</span><span class="sxs-lookup"><span data-stu-id="274e7-113">Analytic Trace Event Reference</span></span>](analytic-trace-event-reference.md)  
 <span data-ttu-id="274e7-114">Muestra una tabla de identificadores de eventos con sus niveles de evento, mensajes de evento y palabras clave.</span><span class="sxs-lookup"><span data-stu-id="274e7-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="274e7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="274e7-115">See also</span></span>

- [<span data-ttu-id="274e7-116">Servicios de WCF y seguimiento de eventos para Windows</span><span class="sxs-lookup"><span data-stu-id="274e7-116">WCF Services and Event Tracing for Windows</span></span>](../../samples/wcf-services-and-event-tracing-for-windows.md)
- [<span data-ttu-id="274e7-117">Seguimiento de eventos en Seguimiento de eventos para Windows</span><span class="sxs-lookup"><span data-stu-id="274e7-117">Tracking Events into Event Tracing in Windows</span></span>](../../../windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
