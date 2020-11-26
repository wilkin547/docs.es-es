---
title: Seguimiento de traza de un extremo a otro
ms.date: 03/30/2017
ms.assetid: f5ac7fc7-f97c-4313-b068-54e0c471b2aa
ms.openlocfilehash: a8c06b9e4f70321e6ef3756863390dc62c659557
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243955"
---
# <a name="end-to-end-tracing"></a><span data-ttu-id="ca7fe-102">Seguimiento de traza de un extremo a otro</span><span class="sxs-lookup"><span data-stu-id="ca7fe-102">End-to-End Tracing</span></span>

<span data-ttu-id="ca7fe-103">El seguimiento de un extremo a otro (E2E) permite a los desarrolladores seguir la ejecución de código en la infraestructura de Windows Communication Foundation (WCF) para investigar por qué se ha producido un error en una ruta de acceso del código o para proporcionar un seguimiento detallado de la planificación de la capacidad y el análisis del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ca7fe-103">End to End (e2e) Tracing allows developers to follow the execution of code in the Windows Communication Foundation (WCF) infrastructure to investigate why a code path has failed, or to provide detailed tracing for capacity planning and performance analysis.</span></span> <span data-ttu-id="ca7fe-104">Windows Communication Foundation (WCF) proporciona tres mecanismos de correlación para ayudar a diagnosticar la causa de un error: actividades, transferencias y propagación.</span><span class="sxs-lookup"><span data-stu-id="ca7fe-104">Windows Communication Foundation (WCF) provides three correlation mechanisms to help diagnose the cause of an error: activities, transfers, and propagation.</span></span>  
  
 <span data-ttu-id="ca7fe-105">Vea [escenarios de seguimiento de un extremo a otro](end-to-end-tracing-scenarios.md) para obtener una lista de escenarios de seguimiento de un extremo a otro, así como su actividad y diseño de seguimiento respectivos.</span><span class="sxs-lookup"><span data-stu-id="ca7fe-105">See [End-To-End Tracing Scenarios](end-to-end-tracing-scenarios.md) for a list of end-to-end tracing scenarios, and their respective activity and tracing design.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ca7fe-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ca7fe-106">In This Section</span></span>  

 <span data-ttu-id="ca7fe-107">[Actividad](activity.md): describe los seguimientos de actividad en el modelo de seguimiento de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ca7fe-107">[Activity](activity.md):  Describes activity traces in the Windows Communication Foundation (WCF) tracing model.</span></span>  
  
 <span data-ttu-id="ca7fe-108">[Transfer](transfer.md): describe la transferencia en el modelo de seguimiento de Windows Communication Foundation (WCF) y el uso de la transferencia para poner en correlación las actividades dentro de los extremos.</span><span class="sxs-lookup"><span data-stu-id="ca7fe-108">[Transfer](transfer.md):  Describes transfer in the Windows Communication Foundation (WCF) tracing model, and using transfer to correlate activities within endpoints.</span></span>  
  
 <span data-ttu-id="ca7fe-109">[Propagación](propagation.md): describe la propagación de actividades en el modelo de seguimiento de Windows Communication Foundation (WCF) y el uso de la propagación para poner en correlación las actividades a través de los extremos.</span><span class="sxs-lookup"><span data-stu-id="ca7fe-109">[Propagation](propagation.md):  Describes activity propagation in the Windows Communication Foundation (WCF) tracing model, and using propagation to correlate activities across endpoints.</span></span>  
  
 [<span data-ttu-id="ca7fe-110">Resumen del tipo de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ca7fe-110">Trace Type Summary</span></span>](trace-type-summary.md)  
  
 <span data-ttu-id="ca7fe-111">Proporciona un resumen de todos los tipos de traza de la actividad</span><span class="sxs-lookup"><span data-stu-id="ca7fe-111">Provides a summary of all activity trace types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca7fe-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca7fe-112">See also</span></span>

- [<span data-ttu-id="ca7fe-113">Configurar seguimiento</span><span class="sxs-lookup"><span data-stu-id="ca7fe-113">Configuring Tracing</span></span>](configuring-tracing.md)
- [<span data-ttu-id="ca7fe-114">Uso del visor de seguimiento de servicios para ver seguimientos asociados y para la solución de problemas</span><span class="sxs-lookup"><span data-stu-id="ca7fe-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="ca7fe-115">Escenarios de seguimiento de traza de un extremo a otro</span><span class="sxs-lookup"><span data-stu-id="ca7fe-115">End-To-End Tracing Scenarios</span></span>](end-to-end-tracing-scenarios.md)
- [<span data-ttu-id="ca7fe-116">Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="ca7fe-116">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../service-trace-viewer-tool-svctraceviewer-exe.md)
