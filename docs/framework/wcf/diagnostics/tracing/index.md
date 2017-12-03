---
title: Traza
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2649eae2-dbf8-421c-9cfb-cfa9e01de87f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3d57517daaf78e737ea4417d5d46cf33400ff97a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="tracing"></a><span data-ttu-id="d6878-102">Traza</span><span class="sxs-lookup"><span data-stu-id="d6878-102">Tracing</span></span>
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="d6878-103"> proporciona instrumental de la aplicación y datos de diagnóstico para la supervisión y el análisis de errores.</span><span class="sxs-lookup"><span data-stu-id="d6878-103"> provides application instrumentation and diagnostic data for fault monitoring and analysis.</span></span> <span data-ttu-id="d6878-104">Puede utilizar el seguimiento en lugar de un depurador para entender cómo se está comportando una aplicación o por qué genera errores.</span><span class="sxs-lookup"><span data-stu-id="d6878-104">You can use tracing instead of a debugger to understand how an application is behaving, or why it faults.</span></span> <span data-ttu-id="d6878-105">También puede correlacionar los errores y el procesamiento en los componentes para proporcionar una experiencia de extremo a extremo.</span><span class="sxs-lookup"><span data-stu-id="d6878-105">You can also correlate faults and processing across components to provide an end-to-end experience.</span></span>  
  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]<span data-ttu-id="d6878-106"> genera los datos siguientes para el seguimiento de diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="d6878-106"> outputs the following data for diagnostic tracing:</span></span>  
  
-   <span data-ttu-id="d6878-107">Trazas para los hitos del proceso en todos los componentes de las aplicaciones, como llamadas de la operación, excepciones de código, advertencias y otros eventos de procesamiento significativos.”</span><span class="sxs-lookup"><span data-stu-id="d6878-107">Traces for process milestones across all components of the applications, such as operation calls, code exceptions, warnings and other significant processing events."</span></span>  
  
-   <span data-ttu-id="d6878-108">Eventos de error de Windows cuando la característica de seguimiento no funciona bien.</span><span class="sxs-lookup"><span data-stu-id="d6878-108">Windows error events when the tracing feature malfunctions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d6878-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d6878-109">In This Section</span></span>  
 [<span data-ttu-id="d6878-110">Configuración del seguimiento</span><span class="sxs-lookup"><span data-stu-id="d6878-110">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
  
 <span data-ttu-id="d6878-111">En este tema se describe cómo puede configurar el seguimiento en diferentes niveles para satisfacer sus necesidades concretas.</span><span class="sxs-lookup"><span data-stu-id="d6878-111">This topic describes how you can configure tracing at different levels to suit your specific need.</span></span>  
  
 [<span data-ttu-id="d6878-112">Seguimiento to-End</span><span class="sxs-lookup"><span data-stu-id="d6878-112">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)  
  
 <span data-ttu-id="d6878-113">En esta sección se describe cómo puede utilizar la propagación y el seguimiento de las actividades para ofrecer una correlación de extremo a extremo que ayude a la depuración.</span><span class="sxs-lookup"><span data-stu-id="d6878-113">This section describes how you can use Activity Tracing and Propagation for end-to-end correlation to assist debugging.</span></span>  
  
 [<span data-ttu-id="d6878-114">Uso del seguimiento para solucionar problemas de la aplicación</span><span class="sxs-lookup"><span data-stu-id="d6878-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
  
 <span data-ttu-id="d6878-115">En esta sección se describe cómo puede utilizar el seguimiento para depurar su aplicación.</span><span class="sxs-lookup"><span data-stu-id="d6878-115">This section describes how you can use tracing to debug your application.</span></span>  
  
 [<span data-ttu-id="d6878-116">Cuestiones de seguridad y sugerencias útiles para el seguimiento</span><span class="sxs-lookup"><span data-stu-id="d6878-116">Security Concerns and Useful Tips for Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/security-concerns-and-useful-tips-for-tracing.md)  
  
 <span data-ttu-id="d6878-117">Este tema describe cómo puede proteger información confidencial de ser expuesta, así como sugerencias útiles al utilizar WebHost.</span><span class="sxs-lookup"><span data-stu-id="d6878-117">This topic describes how you can protect sensitive information from being exposed, as well as useful tips when using WebHost.</span></span>  
  
 [<span data-ttu-id="d6878-118">Referencia de seguimientos</span><span class="sxs-lookup"><span data-stu-id="d6878-118">Traces Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/traces-reference.md)  
  
 <span data-ttu-id="d6878-119">En este tema se detallan todos los seguimientos generados por [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6878-119">This topic lists all the traces generated by [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6878-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6878-120">See Also</span></span>  
 [<span data-ttu-id="d6878-121">Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="d6878-121">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
