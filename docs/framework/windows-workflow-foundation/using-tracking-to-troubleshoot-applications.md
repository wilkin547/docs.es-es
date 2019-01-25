---
title: Usar el seguimiento para resolver problemas de las aplicaciones
ms.date: 03/30/2017
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
ms.openlocfilehash: 1ed95a26f682fcdb609b410251fdb3f8b647016a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734427"
---
# <a name="using-tracking-to-troubleshoot-applications"></a>Usar el seguimiento para resolver problemas de las aplicaciones
Windows Workflow Foundation (WF) le permite realizar un seguimiento de información relacionada con el flujo de trabajo para proporcionar detalles en la ejecución de un servicio o aplicación de Windows Workflow Foundation. Hosts de Windows Workflow Foundation pueden capturar eventos de flujo de trabajo durante la ejecución de una instancia de flujo de trabajo. Si el flujo de trabajo genera errores o excepciones, puede usar los detalles de seguimiento para solucionar problemas de procesamiento de Windows Workflow Foundation.  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a>Solucionar problemas de un WF con el seguimiento de WF  
 Para detectar errores en el procesamiento de una actividad de Windows Workflow Foundation, puede habilitar el seguimiento con un perfil de seguimiento que realiza consultas sobre un <xref:System.Activities.Tracking.ActivityStateRecord> con el estado Faulted. La consulta correspondiente se especifica en el siguiente código.  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 Si se propaga un error y este se controla en un controlador de error (como la actividad <xref:System.Activities.Statements.TryCatch>), se puede detectar mediante <xref:System.Activities.Tracking.FaultPropagationRecord>. <xref:System.Activities.Tracking.FaultPropagationRecord> indica la actividad de origen del error y el nombre del controlador de error. <xref:System.Activities.Tracking.FaultPropagationRecord> contiene detalles del error en forma de pila de excepciones para el error. La consulta para suscribirse a <xref:System.Activities.Tracking.FaultPropagationRecord> se muestra en el ejemplo siguiente.  
  
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
  
 Cuando una instancia de flujo de trabajo encuentra una excepción no controlada, un <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> objeto se genera si se ha habilitado el seguimiento de Windows Workflow Foundation.  
  
 Este registro de seguimiento contiene los detalles del error en forma de pila de excepciones-. Tiene información sobre el origen del error (por ejemplo, la actividad) que y que produjo la excepción no controlada. Para suscribirse a eventos de error de un Windows Workflow Foundation, habilite el seguimiento agregando un participante de seguimiento. Configure este participante con un perfil de seguimiento que realice consultas de `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord>y `WorkflowInstanceQuery (state="UnhandledException")`.  
  
 Si el seguimiento se habilita mediante el participante de seguimiento de ETW, los eventos de error se emiten en una sesión ETW. Los eventos pueden verse con el Visor de eventos. Esto se puede encontrar bajo el nodo **aplicaciones -> el Visor de eventos y registros de servicios -> Microsoft -> Windows -> servidor de aplicaciones-aplicaciones** en el canal analítico.  
  
## <a name="see-also"></a>Vea también
- [Supervisión de Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkId=201273)
- [Supervisión de aplicaciones con App Fabric](https://go.microsoft.com/fwlink/?LinkId=201275)
