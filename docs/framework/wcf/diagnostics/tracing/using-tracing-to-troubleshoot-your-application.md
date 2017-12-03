---
title: "Uso del seguimiento para solucionar problemas de su aplicación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7676b9bb-cbd1-41fd-9a93-cc615af6e2d0
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ddb199ff1d83bef64735dd1425ec955dda83140d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="using-tracing-to-troubleshoot-your-application"></a><span data-ttu-id="4eef9-102">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="4eef9-102">Using Tracing to Troubleshoot Your Application</span></span>
<span data-ttu-id="4eef9-103">Esta sección contiene varios temas que describen cómo puede utilizar el seguimiento para solucionar los problemas de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="4eef9-103">This section contains various topics that describe how you can use tracing to troubleshoot your application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4eef9-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4eef9-104">In This Section</span></span>  
 [<span data-ttu-id="4eef9-105">Configuración recomendada para el seguimiento y registro de mensajes</span><span class="sxs-lookup"><span data-stu-id="4eef9-105">Recommended Settings for Tracing and Message Logging</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/recommended-settings-for-tracing-and-message-logging.md)  
 <span data-ttu-id="4eef9-106">Describe los valores sugeridos para los entornos de producción y depuración.</span><span class="sxs-lookup"><span data-stu-id="4eef9-106">Describes suggested settings for production and debugging environments.</span></span>  
  
 [<span data-ttu-id="4eef9-107">Uso del visor de seguimiento de servicios para ver seguimientos asociados y para la solución de problemas</span><span class="sxs-lookup"><span data-stu-id="4eef9-107">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 <span data-ttu-id="4eef9-108">Describe cómo puede utilizar la herramienta Service Trace Viewer para ver, poner en correlación y analizar los datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4eef9-108">Describes how you can use the Service Trace Viewer tool to view, correlate and analyze trace data.</span></span>  
  
 [<span data-ttu-id="4eef9-109">Seguimientos significativos</span><span class="sxs-lookup"><span data-stu-id="4eef9-109">Significant Traces</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/significant-traces.md)  
 <span data-ttu-id="4eef9-110">Una lista de seguimientos principales emitidos por [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4eef9-110">A list of major traces emitted by [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="4eef9-111">Depuración en el cliente</span><span class="sxs-lookup"><span data-stu-id="4eef9-111">Debugging on the Client</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/debugging-on-the-client.md)  
 <span data-ttu-id="4eef9-112">Permite a los clientes depurar su aplicación.</span><span class="sxs-lookup"><span data-stu-id="4eef9-112">Enables clients to debug your application.</span></span>  
  
 [<span data-ttu-id="4eef9-113">Escenarios de seguimiento de extremo a extremo</span><span class="sxs-lookup"><span data-stu-id="4eef9-113">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)  
 <span data-ttu-id="4eef9-114">Describe los seguimientos utilizados para los escenarios E2E de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], por ejemplo, solicitud-respuestas wsHttp sincrónicas y solicitudes unidireccionales de TCP asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="4eef9-114">Describes traces used for E2E [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] scenarios, for example, synchronous wsHttp request-replies, and asynchronous TCP one-way requests.</span></span>  
  
 [<span data-ttu-id="4eef9-115">Emisión de trazas del código de usuario</span><span class="sxs-lookup"><span data-stu-id="4eef9-115">Emitting User-Code Traces</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/emitting-user-code-traces.md)  
 <span data-ttu-id="4eef9-116">Describe cómo emitir seguimientos mediante programación en código de usuario, de modo que pueda crear de manera proactiva datos de instrumentación que se utilizarán más adelante para el diagnóstico, y en correlación con seguimientos de WCF.</span><span class="sxs-lookup"><span data-stu-id="4eef9-116">Describes how to emit traces programmatically in user code, so that you can proactively create instrumentation data to be used later for diagnostic purpose, and in correlation with WCF traces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eef9-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4eef9-117">See Also</span></span>  
 [<span data-ttu-id="4eef9-118">Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="4eef9-118">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)  
 [<span data-ttu-id="4eef9-119">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="4eef9-119">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="4eef9-120">Seguimiento to-End</span><span class="sxs-lookup"><span data-stu-id="4eef9-120">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
