---
title: Traza
ms.date: 03/30/2017
ms.assetid: 2649eae2-dbf8-421c-9cfb-cfa9e01de87f
ms.openlocfilehash: 6f427425b1bbf19ecd8b30fb1498634a7a3d5fa9
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809321"
---
# <a name="tracing"></a><span data-ttu-id="ac7da-102">Traza</span><span class="sxs-lookup"><span data-stu-id="ac7da-102">Tracing</span></span>
<span data-ttu-id="ac7da-103">Windows Communication Foundation (WCF) proporciona instrumentación de aplicaciones y datos de diagnóstico para la supervisión de los errores y el análisis.</span><span class="sxs-lookup"><span data-stu-id="ac7da-103">Windows Communication Foundation (WCF) provides application instrumentation and diagnostic data for fault monitoring and analysis.</span></span> <span data-ttu-id="ac7da-104">Puede utilizar el seguimiento en lugar de un depurador para entender cómo se está comportando una aplicación o por qué genera errores.</span><span class="sxs-lookup"><span data-stu-id="ac7da-104">You can use tracing instead of a debugger to understand how an application is behaving, or why it faults.</span></span> <span data-ttu-id="ac7da-105">También puede correlacionar los errores y el procesamiento en los componentes para proporcionar una experiencia de extremo a extremo.</span><span class="sxs-lookup"><span data-stu-id="ac7da-105">You can also correlate faults and processing across components to provide an end-to-end experience.</span></span>  
  
 <span data-ttu-id="ac7da-106">WCF genera los datos siguientes para el seguimiento de diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="ac7da-106">WCF outputs the following data for diagnostic tracing:</span></span>  
  
-   <span data-ttu-id="ac7da-107">Trazas para los hitos del proceso en todos los componentes de las aplicaciones, como llamadas de la operación, excepciones de código, advertencias y otros eventos de procesamiento significativos.”</span><span class="sxs-lookup"><span data-stu-id="ac7da-107">Traces for process milestones across all components of the applications, such as operation calls, code exceptions, warnings and other significant processing events."</span></span>  
  
-   <span data-ttu-id="ac7da-108">Eventos de error de Windows cuando la característica de seguimiento no funciona bien.</span><span class="sxs-lookup"><span data-stu-id="ac7da-108">Windows error events when the tracing feature malfunctions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ac7da-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ac7da-109">In This Section</span></span>  
 [<span data-ttu-id="ac7da-110">Configuración de la traza</span><span class="sxs-lookup"><span data-stu-id="ac7da-110">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
  
 <span data-ttu-id="ac7da-111">En este tema se describe cómo puede configurar el seguimiento en diferentes niveles para satisfacer sus necesidades concretas.</span><span class="sxs-lookup"><span data-stu-id="ac7da-111">This topic describes how you can configure tracing at different levels to suit your specific need.</span></span>  
  
 [<span data-ttu-id="ac7da-112">Traza de un extremo a otro</span><span class="sxs-lookup"><span data-stu-id="ac7da-112">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)  
  
 <span data-ttu-id="ac7da-113">En esta sección se describe cómo puede utilizar la propagación y el seguimiento de las actividades para ofrecer una correlación de extremo a extremo que ayude a la depuración.</span><span class="sxs-lookup"><span data-stu-id="ac7da-113">This section describes how you can use Activity Tracing and Propagation for end-to-end correlation to assist debugging.</span></span>  
  
 [<span data-ttu-id="ac7da-114">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="ac7da-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
  
 <span data-ttu-id="ac7da-115">En esta sección se describe cómo puede utilizar el seguimiento para depurar su aplicación.</span><span class="sxs-lookup"><span data-stu-id="ac7da-115">This section describes how you can use tracing to debug your application.</span></span>  
  
 [<span data-ttu-id="ac7da-116">Riesgos de seguridad y sugerencias útiles para el seguimiento</span><span class="sxs-lookup"><span data-stu-id="ac7da-116">Security Concerns and Useful Tips for Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/security-concerns-and-useful-tips-for-tracing.md)  
  
 <span data-ttu-id="ac7da-117">Este tema describe cómo puede proteger información confidencial de ser expuesta, así como sugerencias útiles al utilizar WebHost.</span><span class="sxs-lookup"><span data-stu-id="ac7da-117">This topic describes how you can protect sensitive information from being exposed, as well as useful tips when using WebHost.</span></span>  
  
 [<span data-ttu-id="ac7da-118">Referencias del seguimiento</span><span class="sxs-lookup"><span data-stu-id="ac7da-118">Traces Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/traces-reference.md)  
  
 <span data-ttu-id="ac7da-119">Este tema enumeran todos los rastros generados por WCF.</span><span class="sxs-lookup"><span data-stu-id="ac7da-119">This topic lists all the traces generated by WCF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac7da-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac7da-120">See Also</span></span>  
 [<span data-ttu-id="ac7da-121">Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="ac7da-121">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
