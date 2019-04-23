---
title: Traza analítica con ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: cff13439995d8a90da15b7afa15723f21574e35e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59193731"
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="3272c-102">Traza analítica con ETW</span><span class="sxs-lookup"><span data-stu-id="3272c-102">Analytic Tracing with ETW</span></span>
<span data-ttu-id="3272c-103">Traza analítica de Windows Communication Foundation (WCF) ofrece una manera de capturar información de diagnóstico durante la ejecución de un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="3272c-103">Windows Communication Foundation (WCF) analytic tracing offers a way to capture diagnostic information during the execution of a WCF service.</span></span> <span data-ttu-id="3272c-104">Eventos de traza analítica de WCF se emiten en puntos clave de la pila de WCF para permitir que la solución de problemas de servicios WCF en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="3272c-104">WCF analytic tracing events are emitted at key points in the WCF stack to allow troubleshooting of WCF services in a production environment.</span></span> <span data-ttu-id="3272c-105">Traza analítica de WCF services tiene un impacto mínimo en el rendimiento de un producto de servidor que hospeda [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] servicios WCF como estos eventos se emiten de forma muy eficaz a una sesión de seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="3272c-105">Analytic tracing for WCF services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] WCF services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3272c-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3272c-106">In This Section</span></span>  
 [<span data-ttu-id="3272c-107">Información general de traza analítica</span><span class="sxs-lookup"><span data-stu-id="3272c-107">Analytic Tracing Overview</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 <span data-ttu-id="3272c-108">Describe cómo funciona la traza analítica de WCF en [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3272c-108">Discusses how WCF analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="3272c-109">Habilitación dinámica de la traza analítica</span><span class="sxs-lookup"><span data-stu-id="3272c-109">Dynamically Enabling Analytic Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="3272c-110">Describe cómo habilitar o deshabilitar la traza de forma dinámica mediante ETW.</span><span class="sxs-lookup"><span data-stu-id="3272c-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="3272c-111">Configuración de la traza del flujo de mensajes</span><span class="sxs-lookup"><span data-stu-id="3272c-111">Configuring Message Flow Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 <span data-ttu-id="3272c-112">Describe cómo configurar la traza de flujo de mensajes.</span><span class="sxs-lookup"><span data-stu-id="3272c-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="3272c-113">Referencia de evento de traza analítica</span><span class="sxs-lookup"><span data-stu-id="3272c-113">Analytic Trace Event Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 <span data-ttu-id="3272c-114">Muestra una tabla de identificadores de eventos con sus niveles de evento, mensajes de evento y palabras clave.</span><span class="sxs-lookup"><span data-stu-id="3272c-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3272c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3272c-115">See also</span></span>

- [<span data-ttu-id="3272c-116">Servicios WCF y Seguimiento de eventos para Windows</span><span class="sxs-lookup"><span data-stu-id="3272c-116">WCF Services and Event Tracing for Windows</span></span>](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)
- [<span data-ttu-id="3272c-117">Seguimiento de eventos en Seguimiento de eventos para Windows</span><span class="sxs-lookup"><span data-stu-id="3272c-117">Tracking Events into Event Tracing in Windows</span></span>](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
