---
title: Seguimiento de traza de un extremo a otro
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f5ac7fc7-f97c-4313-b068-54e0c471b2aa
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c3f5c9f80bbf124440952e35049969c7cfa4f19c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="end-to-end-tracing"></a><span data-ttu-id="256fe-102">Seguimiento de traza de un extremo a otro</span><span class="sxs-lookup"><span data-stu-id="256fe-102">End-to-End Tracing</span></span>
<span data-ttu-id="256fe-103">El seguimiento de un extremo a otro (e2e) permite a los desarrolladores realizar el seguimiento de la ejecución del código en la infraestructura de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] para investigar por qué se ha producido un error en una ruta de acceso al código o proporcionar un seguimiento detallado para el diseño de la capacidad y el análisis del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="256fe-103">End to End (e2e) Tracing allows developers to follow the execution of code in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] infrastructure to investigate why a code path has failed, or to provide detailed tracing for capacity planning and performance analysis.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="256fe-104"> proporciona tres mecanismos de correlación para ayudar a diagnosticar la causa de un error: actividades, transferencias y propagación.</span><span class="sxs-lookup"><span data-stu-id="256fe-104"> provides three correlation mechanisms to help diagnose the cause of an error: activities, transfers, and propagation.</span></span>  
  
 <span data-ttu-id="256fe-105">Vea [escenarios de seguimiento de End-To-End](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) para obtener una lista de escenarios de seguimiento de extremo a extremo y su respectivo actividad y seguimiento de diseño.</span><span class="sxs-lookup"><span data-stu-id="256fe-105">See [End-To-End Tracing Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) for a list of end-to-end tracing scenarios, and their respective activity and tracing design.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="256fe-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="256fe-106">In This Section</span></span>  
 <span data-ttu-id="256fe-107">[Actividad](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md): describe los seguimientos de actividad en el [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] modelo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="256fe-107">[Activity](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md):  Describes activity traces in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model.</span></span>  
  
 <span data-ttu-id="256fe-108">[Transferencia](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md): describe la transferencia en el [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] modelo de seguimiento y el uso de transferencia para poner en correlación actividades dentro de los extremos.</span><span class="sxs-lookup"><span data-stu-id="256fe-108">[Transfer](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md):  Describes transfer in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model, and using transfer to correlate activities within endpoints.</span></span>  
  
 <span data-ttu-id="256fe-109">[Propagación](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md): describe la propagación de actividad en el [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] traza del modelo y utilización de la propagación para poner en correlación actividades entre los extremos.</span><span class="sxs-lookup"><span data-stu-id="256fe-109">[Propagation](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md):  Describes activity propagation in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model, and using propagation to correlate activities across endpoints.</span></span>  
  
 [<span data-ttu-id="256fe-110">Resumen de tipos de seguimiento</span><span class="sxs-lookup"><span data-stu-id="256fe-110">Trace Type Summary</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/trace-type-summary.md)  
  
 <span data-ttu-id="256fe-111">Proporciona un resumen de todos los tipos de traza de la actividad</span><span class="sxs-lookup"><span data-stu-id="256fe-111">Provides a summary of all activity trace types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="256fe-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="256fe-112">See Also</span></span>  
 [<span data-ttu-id="256fe-113">Configuración del seguimiento</span><span class="sxs-lookup"><span data-stu-id="256fe-113">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
 [<span data-ttu-id="256fe-114">Uso del visor de seguimiento de servicios para ver seguimientos asociados y para la solución de problemas</span><span class="sxs-lookup"><span data-stu-id="256fe-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 [<span data-ttu-id="256fe-115">Escenarios de seguimiento de extremo a extremo</span><span class="sxs-lookup"><span data-stu-id="256fe-115">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)  
 [<span data-ttu-id="256fe-116">Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="256fe-116">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
