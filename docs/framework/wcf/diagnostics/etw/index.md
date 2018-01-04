---
title: "Traza analítica con ETW"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a16f66ed8443749764e66d2616ae566ad788d571
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="analytic-tracing-with-etw"></a><span data-ttu-id="5997f-102">Traza analítica con ETW</span><span class="sxs-lookup"><span data-stu-id="5997f-102">Analytic Tracing with ETW</span></span>
<span data-ttu-id="5997f-103">El seguimiento analítico de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] proporciona una manera de capturar información de diagnóstico durante la ejecución de un servicio de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5997f-103">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] analytic tracing offers a way to capture diagnostic information during the execution of a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="5997f-104">Los seguimientos analíticos [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] son los eventos emitidos en los puntos clave de la pila de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] que permiten solucionar problemas de los servicios de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="5997f-104">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] analytic tracing events are emitted at key points in the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] stack to allow troubleshooting of [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services in a production environment.</span></span> <span data-ttu-id="5997f-105">Traza analítica para [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] servicios tiene un impacto mínimo en el rendimiento de un servidor del producto que hospeda [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] de servicios como estos eventos se emiten de forma muy eficaz a una sesión de seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="5997f-105">Analytic tracing for [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services has minimal impact on the performance of a product server that hosts [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services as these events are very efficiently emitted to an Event Tracing for Windows (ETW) session.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5997f-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5997f-106">In This Section</span></span>  
 [<span data-ttu-id="5997f-107">Información general de traza analítica</span><span class="sxs-lookup"><span data-stu-id="5997f-107">Analytic Tracing Overview</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 <span data-ttu-id="5997f-108">Describe cómo el seguimiento analítica [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] funciona en [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5997f-108">Discusses how [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] analytic tracing works in [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="5997f-109">Habilitación dinámica de la traza analítica</span><span class="sxs-lookup"><span data-stu-id="5997f-109">Dynamically Enabling Analytic Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 <span data-ttu-id="5997f-110">Describe cómo habilitar o deshabilitar la traza de forma dinámica mediante ETW.</span><span class="sxs-lookup"><span data-stu-id="5997f-110">Discusses how to enable or disable tracing dynamically using ETW.</span></span>  
  
 [<span data-ttu-id="5997f-111">Configuración de la traza del flujo de mensajes</span><span class="sxs-lookup"><span data-stu-id="5997f-111">Configuring Message Flow Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 <span data-ttu-id="5997f-112">Describe cómo configurar la traza de flujo de mensajes.</span><span class="sxs-lookup"><span data-stu-id="5997f-112">Describes how to configure message flow tracing.</span></span>  
  
 [<span data-ttu-id="5997f-113">Referencia de evento de traza analítica</span><span class="sxs-lookup"><span data-stu-id="5997f-113">Analytic Trace Event Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 <span data-ttu-id="5997f-114">Muestra una tabla de identificadores de eventos con sus niveles de evento, mensajes de evento y palabras clave.</span><span class="sxs-lookup"><span data-stu-id="5997f-114">Shows a table of event IDs with their event levels, event messages and keywords.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5997f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5997f-115">See Also</span></span>  
 [<span data-ttu-id="5997f-116">Servicios WCF y Seguimiento de eventos para Windows</span><span class="sxs-lookup"><span data-stu-id="5997f-116">WCF Services and Event Tracing for Windows</span></span>](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)  
 [<span data-ttu-id="5997f-117">Seguimiento de eventos en Seguimiento de eventos para Windows</span><span class="sxs-lookup"><span data-stu-id="5997f-117">Tracking Events into Event Tracing in Windows</span></span>](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
