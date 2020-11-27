---
title: Excepciones
ms.date: 03/30/2017
ms.assetid: 065205cc-52dd-4f30-9578-b17d8d113136
ms.openlocfilehash: 53cc8e3e27e131c5c2a9f8271851a0d8d7e0cbd7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280213"
---
# <a name="exceptions"></a>Excepciones

Los flujos de trabajo pueden usar la actividad <xref:System.Activities.Statements.TryCatch> para controlar excepciones que se producen durante la ejecución de un flujo de trabajo. Se pueden controlar estas excepciones o se pueden volver a producir usando la actividad <xref:System.Activities.Statements.Rethrow>. Las actividades de la sección <xref:System.Activities.Statements.TryCatch.Finally%2A> se ejecutan cuando la sección <xref:System.Activities.Statements.TryCatch.Try%2A> o la sección <xref:System.Activities.Statements.TryCatch.Catches%2A> se hayan completado. Los flujos de trabajo hospedados por una <xref:System.Activities.WorkflowApplication> instancia de también pueden usar el <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> controlador de eventos para controlar las excepciones que no se controlan mediante una <xref:System.Activities.Statements.TryCatch> actividad.  
  
## <a name="causes-of-exceptions"></a>Causas de excepciones  

 En un flujo de trabajo, las excepciones se pueden generar de las maneras siguientes:  
  
- Un tiempo de espera de transacciones en <xref:System.Activities.Statements.TransactionScope>.  
  
- Una excepción explícita iniciada por el flujo de trabajo mediante la actividad <xref:System.Activities.Statements.Throw>.  
  
- Una excepción [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] iniciada desde una actividad.  
  
- Una excepción iniciada desde el código externo, como bibliotecas, componentes o servicios que se usan en el flujo de trabajo.  
  
## <a name="handling-exceptions"></a>Controlar las excepciones  

 Si la actividad inicia una excepción y no está controlada, el comportamiento predeterminado es terminar la instancia de flujo de trabajo. Si un controlador <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> personalizado está presente, puede invalidar este comportamiento predeterminado. Este controlador da al autor de host de flujo de trabajo la oportunidad de proporcionar el control adecuado, como el registro personalizado o la anulación, cancelación o finalización del flujo de trabajo.  Si un flujo de trabajo produce una excepción no administrada, se invoca el controlador <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>. Se devuelven tres posibles acciones de <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> que determinan el resultado final del flujo de trabajo.  
  
- **Cancelar** : una instancia de flujo de trabajo cancelada es una salida correcta de una ejecución de la rama. Puede modelar el comportamiento de cancelación (por ejemplo, con una actividad CancellationScope). Se invoca el controlador Completed cuando el proceso de cancelación se completa. Un flujo de trabajo cancelado está en estado Cancelled.  
  
- **Terminate** : no se puede reanudar o reiniciar una instancia de flujo de trabajo terminada.  Esto desencadena el evento Completed en el que puede proporcionar una excepción como razón por la que finalizó. Se invoca el controlador Terminated cuando el proceso de finalización se completa. Un flujo de trabajo finalizado está en el estado Faulted.  
  
- **Abort** : las instancias de flujo de trabajo anuladas se pueden reanudar solo si se ha configurado para ser persistentes.  Sin persistencia, un flujo de trabajo no se puede reanudar.  En el punto en que se anula un flujo de trabajo, se perderá todo el trabajo realizado (en memoria) desde el último punto de persistencia. Para un flujo de trabajo anulado, se invoca el controlador Aborted usando la excepción como motivo cuando se completa el proceso de anulación. Sin embargo, a diferencia de Cancelled y Terminated, no se invoca el controlador Completed. Un flujo de trabajo anulado está en un estado Aborted.  
  
 En el ejemplo siguiente se invoca un flujo de trabajo que produce una excepción. El flujo de trabajo no controla la excepción y se invoca el controlador de la propiedad <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>. El objeto <xref:System.Activities.WorkflowApplicationUnhandledExceptionEventArgs> se inspecciona para proporcionar información acerca de la excepción y se termina el flujo de trabajo.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#1)]  
  
### <a name="handling-exceptions-with-the-trycatch-activity"></a>Administrar excepciones con la actividad TryCatch  

 La administración de excepciones dentro de un flujo de trabajo se realiza mediante la actividad <xref:System.Activities.Statements.TryCatch>. La actividad <xref:System.Activities.Statements.TryCatch> tiene una colección de <xref:System.Activities.Statements.TryCatch.Catches%2A> de las actividades de <xref:System.Activities.Statements.Catch> que se asocian con un tipo <xref:System.Exception> concreto. Si la excepción producida por una actividad incluida en la sección <xref:System.Activities.Statements.TryCatch.Try%2A> de una actividad <xref:System.Activities.Statements.TryCatch> coincide con la excepción de una actividad <xref:System.Activities.Statements.Catch%601> en la colección de <xref:System.Activities.Statements.TryCatch.Catches%2A>, se administrará la excepción. Si se vuelve a producir explícitamente la excepción o se produce una nueva, esta excepción se pasa a la actividad principal. El siguiente ejemplo de código muestra una actividad <xref:System.Activities.Statements.TryCatch> que administra un objeto <xref:System.ApplicationException> que se produce en la sección <xref:System.Activities.Statements.TryCatch.Try%2A> mediante una actividad <xref:System.Activities.Statements.Throw>. El mensaje de la excepción se escribe en la consola mediante la actividad <xref:System.Activities.Statements.Catch%601> y, a continuación, se escribe un mensaje en la consola de la sección <xref:System.Activities.Statements.TryCatch.Finally%2A>.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#33](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#33)]  
  
 Se ejecutarán las actividades en la sección <xref:System.Activities.Statements.TryCatch.Finally%2A> cuando la sección <xref:System.Activities.Statements.TryCatch.Try%2A> o la sección <xref:System.Activities.Statements.TryCatch.Catches%2A> se hayan completado. La sección <xref:System.Activities.Statements.TryCatch.Try%2A> se completa correctamente si no se produce ninguna excepción de ella, y la sección <xref:System.Activities.Statements.TryCatch.Catches%2A> se completa correctamente si no se produce o se vuelve a producir ninguna excepción desde ella. Si se produce una excepción en la sección <xref:System.Activities.Statements.TryCatch.Try%2A> de <xref:System.Activities.Statements.TryCatch> y no está controlada por <xref:System.Activities.Statements.Catch%601> en la sección <xref:System.Activities.Statements.TryCatch.Catches%2A> o si se vuelve a producir desde <xref:System.Activities.Statements.TryCatch.Catches%2A>, las actividades de <xref:System.Activities.Statements.TryCatch.Finally%2A> no se ejecutarán a menos que ocurra algo de lo siguiente.  
  
- La excepción es detectada por una actividad <xref:System.Activities.Statements.TryCatch> de mayor nivel en el flujo de trabajo, independientemente de si se vuelven a producir desde <xref:System.Activities.Statements.TryCatch> de mayor nivel.  
  
- La excepción no la controla un <xref:System.Activities.Statements.TryCatch> de mayor nivel, se escapa la raíz del flujo de trabajo, y el flujo de trabajo se configura para cancelarse en lugar de finalizarse o anularse. Los flujos de trabajo hospedados mediante <xref:System.Activities.WorkflowApplication> pueden configurar esto controlando <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> y devolviendo <xref:System.Activities.UnhandledExceptionAction.Cancel>. Un ejemplo de cómo administrar <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> se proporciona anteriormente en este tema. Los servicios de flujo de trabajo pueden configurar esto mediante <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> y especificando <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction.Cancel>. Para obtener un ejemplo de configuración <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> , consulte [extensibilidad de host de servicio de flujo de trabajo](../wcf/feature-details/workflow-service-host-extensibility.md).  
  
## <a name="exception-handling-versus-compensation"></a>Control de excepciones contra compensación  

 La diferencia entre el control de excepciones y la compensación es que el primero se produce durante la ejecución de una actividad. La compensación, sin embargo, se produce después de que una actividad se haya completado correctamente. El control de excepciones proporciona una oportunidad para limpiar después de que la actividad produzca la excepción, mientras la compensación proporciona un mecanismo por el que se puede deshacer el trabajo terminado correctamente de una actividad completada previamente. Para obtener más información, consulte [compensación](compensation.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Activities.Statements.TryCatch>
- <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>
- <xref:System.Activities.Statements.CompensableActivity>
