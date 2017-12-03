---
title: Usar el seguimiento para resolver problemas de las aplicaciones
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 52a599d9cba2e68fdb74d364dad562d2547ca020
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="using-tracking-to-troubleshoot-applications"></a><span data-ttu-id="81b69-102">Usar el seguimiento para resolver problemas de las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="81b69-102">Using Tracking to Troubleshoot Applications</span></span>
[!INCLUDE[wf](../../../includes/wf-md.md)]<span data-ttu-id="81b69-103"> permite realizar el seguimiento de la información relacionada con el flujo de trabajo para proporcionar detalles en la ejecución de una aplicación o servicio [!INCLUDE[wf2](../../../includes/wf2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81b69-103"> enables you to track workflow-related information to give details into the execution of a [!INCLUDE[wf2](../../../includes/wf2-md.md)] application or service.</span></span> <span data-ttu-id="81b69-104">Los hosts de [!INCLUDE[wf2](../../../includes/wf2-md.md)] pueden capturar eventos del flujo de trabajo durante la ejecución de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="81b69-104">[!INCLUDE[wf2](../../../includes/wf2-md.md)] hosts are able to capture workflow events during the execution of a workflow instance.</span></span> <span data-ttu-id="81b69-105">Si su flujo de trabajo genera errores o excepciones, puede usar los detalles de seguimiento de [!INCLUDE[wf2](../../../includes/wf2-md.md)] para solucionar problemas de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="81b69-105">If your workflow generates faults or exceptions, you can use the [!INCLUDE[wf2](../../../includes/wf2-md.md)] tracking details to troubleshooting its processing.</span></span>  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a><span data-ttu-id="81b69-106">Solucionar problemas de un WF con el seguimiento de WF</span><span class="sxs-lookup"><span data-stu-id="81b69-106">Troubleshooting a WF using WF Tracking</span></span>  
 <span data-ttu-id="81b69-107">Para detectar errores en el procesamiento de una actividad [!INCLUDE[wf2](../../../includes/wf2-md.md)], puede habilitar el seguimiento con un perfil de seguimiento que realiza consultas sobre una clase <xref:System.Activities.Tracking.ActivityStateRecord> con el estado Faulted.</span><span class="sxs-lookup"><span data-stu-id="81b69-107">To detect faults within the processing of a [!INCLUDE[wf2](../../../includes/wf2-md.md)] activity, you can enable tracking with a tracking profile that queries for an <xref:System.Activities.Tracking.ActivityStateRecord> with the state of Faulted.</span></span> <span data-ttu-id="81b69-108">La consulta correspondiente se especifica en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="81b69-108">The corresponding query is specified in the following code.</span></span>  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 <span data-ttu-id="81b69-109">Si se propaga un error y este se controla en un controlador de error (como la actividad <xref:System.Activities.Statements.TryCatch>), se puede detectar mediante <xref:System.Activities.Tracking.FaultPropagationRecord>.</span><span class="sxs-lookup"><span data-stu-id="81b69-109">If a fault is propagated and handled within a fault handler (such as a <xref:System.Activities.Statements.TryCatch> activity) this can be detected using a <xref:System.Activities.Tracking.FaultPropagationRecord>.</span></span> <span data-ttu-id="81b69-110"><xref:System.Activities.Tracking.FaultPropagationRecord> indica la actividad de origen del error y el nombre del controlador de error.</span><span class="sxs-lookup"><span data-stu-id="81b69-110">The <xref:System.Activities.Tracking.FaultPropagationRecord> indicates the source activity of the fault and the name of the fault handler.</span></span> <span data-ttu-id="81b69-111"><xref:System.Activities.Tracking.FaultPropagationRecord> contiene detalles del error en forma de pila de excepciones para el error. La consulta para suscribirse a <xref:System.Activities.Tracking.FaultPropagationRecord> se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="81b69-111">The <xref:System.Activities.Tracking.FaultPropagationRecord> contains fault details in form of the exception stack for the fault.The query to subscribe for a <xref:System.Activities.Tracking.FaultPropagationRecord> is shown in the following example.</span></span>  
  
```xml  
<faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
 </faultPropagationQueries>  
```  
  
 <span data-ttu-id="81b69-112">Si no se controla un error en el flujo de trabajo, se producirá una excepción no controlada en la instancia de flujo de trabajo y se anulará posteriormente.</span><span class="sxs-lookup"><span data-stu-id="81b69-112">If a fault is not handled within the workflow it results in an unhandled exception at the workflow instance and the workflow instance is aborted.</span></span> <span data-ttu-id="81b69-113">Para entender los detalles de la excepción no controlada, el perfil de seguimiento debe realizar consultas en el registro de la instancia de flujo de trabajo con un estado `state name="UnhandledException"`, tal y como se especifica en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="81b69-113">To understand the details of the unhandled exception, the tracking profile must query the workflow instance record with `state name="UnhandledException"` as specified in the following example.</span></span>  
  
```xml  
<workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="UnhandledException" />  
                </states>  
              </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
 <span data-ttu-id="81b69-114">Cuando una instancia de flujo de trabajo encuentra una excepción no controlada, se emite un objeto <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> si se ha habilitado el seguimiento de [!INCLUDE[wf2](../../../includes/wf2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81b69-114">When a workflow instance encounters an unhandled exception, a <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> object is emitted if [!INCLUDE[wf2](../../../includes/wf2-md.md)] tracking has been enabled.</span></span>  
  
 <span data-ttu-id="81b69-115">Este registro de seguimiento contiene los detalles del error en forma de pila de excepciones-.</span><span class="sxs-lookup"><span data-stu-id="81b69-115">This tracking record contains the fault details in the form of the exception stack.</span></span> <span data-ttu-id="81b69-116">Tiene información sobre el origen del error (por ejemplo, la actividad) que lo provocó y que produjo la excepción no controlada. Para suscribirse a eventos de error de [!INCLUDE[wf2](../../../includes/wf2-md.md)], habilite el seguimiento agregando un participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="81b69-116">It has details of the source of the fault (for example, the activity) that faulted and resulted in the unhandled exception.To subscribe to fault events from a [!INCLUDE[wf2](../../../includes/wf2-md.md)], enable tracking by adding a tracking participant.</span></span> <span data-ttu-id="81b69-117">Configure este participante con un perfil de seguimiento que realice consultas de `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>y `WorkflowInstanceQuery (state="UnhandledException")`.</span><span class="sxs-lookup"><span data-stu-id="81b69-117">Configure this participant with a tracking profile that queries for `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>, and `WorkflowInstanceQuery (state="UnhandledException")`.</span></span>  
  
 <span data-ttu-id="81b69-118">Si el seguimiento se habilita mediante el participante de seguimiento de ETW, los eventos de error se emiten en una sesión ETW.</span><span class="sxs-lookup"><span data-stu-id="81b69-118">If tracking is enabled using the ETW tracking participant, the fault events are emitted to an ETW session.</span></span> <span data-ttu-id="81b69-119">Los eventos pueden verse con el Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="81b69-119">The events can be viewed using the Event Viewer event viewer.</span></span> <span data-ttu-id="81b69-120">Se puede encontrar bajo el nodo **aplicaciones -> el Visor de eventos y registros de servicios -> Microsoft -> Windows -> servidor de aplicaciones** en el canal analítico.</span><span class="sxs-lookup"><span data-stu-id="81b69-120">This can be found under the node **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications** in the analytic channel.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81b69-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="81b69-121">See Also</span></span>  
 [<span data-ttu-id="81b69-122">Supervisión de Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="81b69-122">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="81b69-123">Supervisión de aplicaciones con App Fabric</span><span class="sxs-lookup"><span data-stu-id="81b69-123">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)
