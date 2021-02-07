---
description: 'Más información sobre: uso del seguimiento para solucionar problemas de aplicaciones'
title: Usar el seguimiento para resolver problemas de las aplicaciones
ms.date: 03/30/2017
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
ms.openlocfilehash: 9ff2c1b9a4a35a75a9f4d2229b5b43d6607e7557
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754997"
---
# <a name="using-tracking-to-troubleshoot-applications"></a><span data-ttu-id="e2db5-103">Usar el seguimiento para resolver problemas de las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e2db5-103">Using Tracking to Troubleshoot Applications</span></span>

<span data-ttu-id="e2db5-104">Windows Workflow Foundation (WF) le permite realizar un seguimiento de la información relacionada con el flujo de trabajo para proporcionar detalles sobre la ejecución de una aplicación o servicio Windows Workflow Foundation.</span><span class="sxs-lookup"><span data-stu-id="e2db5-104">Windows Workflow Foundation (WF) enables you to track workflow-related information to give details into the execution of a Windows Workflow Foundation application or service.</span></span> <span data-ttu-id="e2db5-105">Windows Workflow Foundation hosts pueden capturar eventos de flujo de trabajo durante la ejecución de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e2db5-105">Windows Workflow Foundation hosts are able to capture workflow events during the execution of a workflow instance.</span></span> <span data-ttu-id="e2db5-106">Si el flujo de trabajo genera errores o excepciones, puede usar los detalles de seguimiento de Windows Workflow Foundation para solucionar el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e2db5-106">If your workflow generates faults or exceptions, you can use the Windows Workflow Foundation tracking details to troubleshooting its processing.</span></span>  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a><span data-ttu-id="e2db5-107">Solucionar problemas de un WF con el seguimiento de WF</span><span class="sxs-lookup"><span data-stu-id="e2db5-107">Troubleshooting a WF using WF Tracking</span></span>  

 <span data-ttu-id="e2db5-108">Para detectar errores en el procesamiento de una actividad Windows Workflow Foundation, puede habilitar el seguimiento con un perfil de seguimiento que consulta para un <xref:System.Activities.Tracking.ActivityStateRecord> con el estado de error.</span><span class="sxs-lookup"><span data-stu-id="e2db5-108">To detect faults within the processing of a Windows Workflow Foundation activity, you can enable tracking with a tracking profile that queries for an <xref:System.Activities.Tracking.ActivityStateRecord> with the state of Faulted.</span></span> <span data-ttu-id="e2db5-109">La consulta correspondiente se especifica en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="e2db5-109">The corresponding query is specified in the following code.</span></span>  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 <span data-ttu-id="e2db5-110">Si se propaga un error y este se controla en un controlador de error (como la actividad <xref:System.Activities.Statements.TryCatch>), se puede detectar mediante <xref:System.Activities.Tracking.FaultPropagationRecord>.</span><span class="sxs-lookup"><span data-stu-id="e2db5-110">If a fault is propagated and handled within a fault handler (such as a <xref:System.Activities.Statements.TryCatch> activity) this can be detected using a <xref:System.Activities.Tracking.FaultPropagationRecord>.</span></span> <span data-ttu-id="e2db5-111"><xref:System.Activities.Tracking.FaultPropagationRecord> indica la actividad de origen del error y el nombre del controlador de error.</span><span class="sxs-lookup"><span data-stu-id="e2db5-111">The <xref:System.Activities.Tracking.FaultPropagationRecord> indicates the source activity of the fault and the name of the fault handler.</span></span> <span data-ttu-id="e2db5-112"><xref:System.Activities.Tracking.FaultPropagationRecord>Contiene los detalles del error en forma de pila de excepciones para el error.</span><span class="sxs-lookup"><span data-stu-id="e2db5-112">The <xref:System.Activities.Tracking.FaultPropagationRecord> contains fault details in form of the exception stack for the fault.</span></span> <span data-ttu-id="e2db5-113">En el ejemplo siguiente se muestra la consulta para suscribirse a <xref:System.Activities.Tracking.FaultPropagationRecord> .</span><span class="sxs-lookup"><span data-stu-id="e2db5-113">The query to subscribe for a <xref:System.Activities.Tracking.FaultPropagationRecord> is shown in the following example.</span></span>  
  
```xml  
<faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
 </faultPropagationQueries>  
```  
  
 <span data-ttu-id="e2db5-114">Si no se controla un error en el flujo de trabajo, se producirá una excepción no controlada en la instancia de flujo de trabajo y se anulará posteriormente.</span><span class="sxs-lookup"><span data-stu-id="e2db5-114">If a fault is not handled within the workflow it results in an unhandled exception at the workflow instance and the workflow instance is aborted.</span></span> <span data-ttu-id="e2db5-115">Para entender los detalles de la excepción no controlada, el perfil de seguimiento debe realizar consultas en el registro de la instancia de flujo de trabajo con un estado `state name="UnhandledException"`, tal y como se especifica en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e2db5-115">To understand the details of the unhandled exception, the tracking profile must query the workflow instance record with `state name="UnhandledException"` as specified in the following example.</span></span>  
  
```xml  
<workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="UnhandledException" />  
                </states>  
              </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
 <span data-ttu-id="e2db5-116">Cuando una instancia de flujo de trabajo encuentra una excepción no controlada, <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> se emite un objeto si se ha habilitado el seguimiento de Windows Workflow Foundation.</span><span class="sxs-lookup"><span data-stu-id="e2db5-116">When a workflow instance encounters an unhandled exception, a <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> object is emitted if Windows Workflow Foundation tracking has been enabled.</span></span>  
  
 <span data-ttu-id="e2db5-117">Este registro de seguimiento contiene los detalles del error en forma de pila de excepciones-.</span><span class="sxs-lookup"><span data-stu-id="e2db5-117">This tracking record contains the fault details in the form of the exception stack.</span></span> <span data-ttu-id="e2db5-118">Tiene detalles del origen del error (por ejemplo, la actividad) que generó un error y dio como resultado la excepción no controlada. Para suscribirse a eventos de error desde un Windows Workflow Foundation, habilite el seguimiento agregando un participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="e2db5-118">It has details of the source of the fault (for example, the activity) that faulted and resulted in the unhandled exception.To subscribe to fault events from a Windows Workflow Foundation, enable tracking by adding a tracking participant.</span></span> <span data-ttu-id="e2db5-119">Configure este participante con un perfil de seguimiento que realice consultas de `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>y `WorkflowInstanceQuery (state="UnhandledException")`.</span><span class="sxs-lookup"><span data-stu-id="e2db5-119">Configure this participant with a tracking profile that queries for `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>, and `WorkflowInstanceQuery (state="UnhandledException")`.</span></span>  
  
 <span data-ttu-id="e2db5-120">Si el seguimiento se habilita mediante el participante de seguimiento de ETW, los eventos de error se emiten en una sesión ETW.</span><span class="sxs-lookup"><span data-stu-id="e2db5-120">If tracking is enabled using the ETW tracking participant, the fault events are emitted to an ETW session.</span></span> <span data-ttu-id="e2db5-121">Los eventos pueden verse con el Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="e2db5-121">The events can be viewed using the Event Viewer event viewer.</span></span> <span data-ttu-id="e2db5-122">Esto se puede encontrar en el nodo **visor de eventos->registros de aplicaciones y servicios->servidor de aplicaciones Microsoft >Windows->-aplicaciones** en el canal analítico.</span><span class="sxs-lookup"><span data-stu-id="e2db5-122">This can be found under the node **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications** in the analytic channel.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2db5-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2db5-123">See also</span></span>

- <span data-ttu-id="e2db5-124">[Supervisión de Windows Server App fabric](/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e2db5-124">[Windows Server App Fabric Monitoring](/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="e2db5-125">[Supervisión de aplicaciones con App fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e2db5-125">[Monitoring Applications with App Fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
