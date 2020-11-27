---
title: Usar el seguimiento para resolver problemas de las aplicaciones
ms.date: 03/30/2017
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
ms.openlocfilehash: 62f2240831dd33bdaf78655199aad75b7e29c59c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293577"
---
# <a name="using-tracking-to-troubleshoot-applications"></a>Usar el seguimiento para resolver problemas de las aplicaciones

Windows Workflow Foundation (WF) le permite realizar un seguimiento de la información relacionada con el flujo de trabajo para proporcionar detalles sobre la ejecución de una aplicación o servicio Windows Workflow Foundation. Windows Workflow Foundation hosts pueden capturar eventos de flujo de trabajo durante la ejecución de una instancia de flujo de trabajo. Si el flujo de trabajo genera errores o excepciones, puede usar los detalles de seguimiento de Windows Workflow Foundation para solucionar el procesamiento.  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a>Solucionar problemas de un WF con el seguimiento de WF  

 Para detectar errores en el procesamiento de una actividad Windows Workflow Foundation, puede habilitar el seguimiento con un perfil de seguimiento que consulta para un <xref:System.Activities.Tracking.ActivityStateRecord> con el estado de error. La consulta correspondiente se especifica en el siguiente código.  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 Si se propaga un error y este se controla en un controlador de error (como la actividad <xref:System.Activities.Statements.TryCatch>), se puede detectar mediante <xref:System.Activities.Tracking.FaultPropagationRecord>. <xref:System.Activities.Tracking.FaultPropagationRecord> indica la actividad de origen del error y el nombre del controlador de error. <xref:System.Activities.Tracking.FaultPropagationRecord>Contiene los detalles del error en forma de pila de excepciones para el error. En el ejemplo siguiente se muestra la consulta para suscribirse a <xref:System.Activities.Tracking.FaultPropagationRecord> .  
  
```xml  
<faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
 </faultPropagationQueries>  
```  
  
 Si no se controla un error en el flujo de trabajo, se producirá una excepción no controlada en la instancia de flujo de trabajo y se anulará posteriormente. Para entender los detalles de la excepción no controlada, el perfil de seguimiento debe realizar consultas en el registro de la instancia de flujo de trabajo con un estado `state name="UnhandledException"`, tal y como se especifica en el ejemplo siguiente.  
  
```xml  
<workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="UnhandledException" />  
                </states>  
              </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
 Cuando una instancia de flujo de trabajo encuentra una excepción no controlada, <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> se emite un objeto si se ha habilitado el seguimiento de Windows Workflow Foundation.  
  
 Este registro de seguimiento contiene los detalles del error en forma de pila de excepciones-. Tiene detalles del origen del error (por ejemplo, la actividad) que generó un error y dio como resultado la excepción no controlada. Para suscribirse a eventos de error desde un Windows Workflow Foundation, habilite el seguimiento agregando un participante de seguimiento. Configure este participante con un perfil de seguimiento que realice consultas de `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>y `WorkflowInstanceQuery (state="UnhandledException")`.  
  
 Si el seguimiento se habilita mediante el participante de seguimiento de ETW, los eventos de error se emiten en una sesión ETW. Los eventos pueden verse con el Visor de eventos. Esto se puede encontrar en el nodo **visor de eventos->registros de aplicaciones y servicios->servidor de aplicaciones Microsoft >Windows->-aplicaciones** en el canal analítico.  
  
## <a name="see-also"></a>Vea también

- [Supervisión de Windows Server App fabric](/previous-versions/appfabric/ee677251(v=azure.10))
- [Supervisión de aplicaciones con App fabric](/previous-versions/appfabric/ee677276(v=azure.10))
