---
title: Modelar el comportamiento de la cancelación en los flujos de trabajo
ms.date: 03/30/2017
ms.assetid: d48f6cf3-cdde-4dd3-8265-a665acf32a03
ms.openlocfilehash: 157bff0d24b00f293fd551dd52fe693d36dfad61
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242063"
---
# <a name="modeling-cancellation-behavior-in-workflows"></a>Modelar el comportamiento de la cancelación en los flujos de trabajo

Las actividades se pueden cancelar dentro de un flujo de trabajo, por ejemplo, mediante una actividad <xref:System.Activities.Statements.Parallel> que cancele las bifurcaciones incompletas cuando su propiedad <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> se evalúe como `true` o desde fuera del flujo de trabajo, si el host llama al método <xref:System.Activities.WorkflowApplication.Cancel%2A>. Para proporcionar un control de la cancelación, los autores del flujo de trabajo pueden utilizar la actividad <xref:System.Activities.Statements.CancellationScope>, la actividad <xref:System.Activities.Statements.CompensableActivity> o crear actividades personalizadas que proporcionen lógica de cancelación. En este tema se proporciona información general sobre la cancelación en flujos de trabajo.  
  
## <a name="cancellation-compensation-and-transactions"></a>Cancelación, compensación y transacciones  

 Las transacciones ofrecen a la aplicación la posibilidad de anular (revertir) todos los cambios ejecutados dentro de la transacción si se produce algún error en cualquier momento del proceso de transacción. Sin embargo, no todos los trabajos que puede que resulte necesario cancelar o deshacer son adecuados para las transacciones, como los trabajos de ejecución prolongada o aquellos que no implican recursos transaccionales. La compensación proporciona un modelo para deshacer un trabajo no transaccional completado previamente si se produce un error en el flujo de trabajo posteriormente. La cancelación proporciona un modelo para que el flujo de trabajo y los autores de la actividad puedan controlar un trabajo no transaccional que no se ha completado. Si una actividad no ha completado su ejecución y se cancela, se invocará su lógica de la cancelación si está disponible.  
  
> [!NOTE]
> Para obtener más información sobre las transacciones y la compensación, consulte [transacciones](workflow-transactions.md) y [compensación](compensation.md).  
  
## <a name="using-cancellationscope"></a>Usar CancellationScope  

 La actividad <xref:System.Activities.Statements.CancellationScope> tiene dos secciones que pueden contener actividades secundarias: <xref:System.Activities.Statements.CancellationScope.Body%2A> y <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>. La propiedad <xref:System.Activities.Statements.CancellationScope.Body%2A> es donde se colocan las actividades que constituyen la lógica de la actividad y la propiedad <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> es donde se colocan las actividades que proporcionan la lógica de cancelación para la actividad. Una actividad solo puede cancelar si no se ha completado. En el caso de la actividad <xref:System.Activities.Statements.CancellationScope>, la finalización hace referencia a la realización de las actividades de la propiedad <xref:System.Activities.Statements.CancellationScope.Body%2A>. Si se programa una solicitud de cancelación y no se han completado las actividades de la propiedad <xref:System.Activities.Statements.CancellationScope.Body%2A>, el objeto <xref:System.Activities.Statements.CancellationScope> se marcará como <xref:System.Activities.ActivityInstanceState.Canceled> y las actividades <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> se ejecutarán.  
  
### <a name="canceling-a-workflow-from-the-host"></a>Cancelar un flujo de trabajo desde el host  

 Un host puede cancelar un flujo de trabajo llamando al método <xref:System.Activities.WorkflowApplication.Cancel%2A> de la instancia de <xref:System.Activities.WorkflowApplication> que hospeda el flujo de trabajo. En el ejemplo siguiente, se crea un flujo de trabajo con un objeto <xref:System.Activities.Statements.CancellationScope>. Se invoca el flujo de trabajo y, a continuación, el host llama al método <xref:System.Activities.WorkflowApplication.Cancel%2A>. La ejecución principal del flujo de trabajo se detiene, se invoca la propiedad <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> del objeto <xref:System.Activities.Statements.CancellationScope> y, a continuación, el flujo de trabajo se completa con el estado <xref:System.Activities.ActivityInstanceState.Canceled>.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#35](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#35)]  
  
 Cuando se invoca este flujo de trabajo, en la consola se muestra el siguiente resultado.  
  
 **Iniciando el flujo de trabajo.**  
**CancellationHandler invocado.** 
 **Flujo de trabajo B30ebb30-df46-4d90-A211-e31c38d8db3c cancelado.**
> [!NOTE]
> Cuando una actividad <xref:System.Activities.Statements.CancellationScope> se cancela y se invoca la propiedad <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>, es responsabilidad del autor del flujo de trabajo determinar el progreso de la actividad antes de cancelarse para proporcionar la lógica de cancelación adecuada. La propiedad <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> no proporciona ninguna información sobre el progreso de la actividad cancelada.  
  
 Un flujo de trabajo también se puede cancelar desde el host si una excepción no controlada traspasa la raíz del flujo de trabajo y el controlador de la propiedad <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> devuelve <xref:System.Activities.UnhandledExceptionAction.Cancel>. En este ejemplo el flujo de trabajo se inicia y, a continuación, genera una <xref:System.ApplicationException>. El flujo de trabajo no controla la excepción y, en consecuencia, se invoca al controlador de la propiedad <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>. El controlador indica al tiempo de ejecución que cancele el flujo de trabajo y se invoca la propiedad <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> de la actividad <xref:System.Activities.Statements.CancellationScope> actualmente en ejecución.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#36](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#36)]  
  
 Cuando se invoca este flujo de trabajo, en la consola se muestra el siguiente resultado.  
  
 **Iniciando el flujo de trabajo.**  
**OnUnhandledException en flujo de trabajo 6bb2d5d6-f49a-4c6d-a988-478afb86dbe9** 
 **Se ha producido una excepción ApplicationException.** 
 **CancellationHandler invocado.** 
 **Flujo de trabajo 6Bb2d5d6-f49a-4c6d-a988-478afb86dbe9 cancelado.**

### <a name="canceling-an-activity-from-inside-a-workflow"></a>Cancelar una actividad desde dentro de un flujo de trabajo  

 Una actividad también puede cancelarse mediante su elemento primario. Por ejemplo, si una actividad <xref:System.Activities.Statements.Parallel> tiene varias bifurcaciones en ejecución y su propiedad <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> se evalúa como `true`, se cancelarán sus bifurcaciones incompletas. En este ejemplo, se crea una actividad <xref:System.Activities.Statements.Parallel> con dos bifurcaciones. Su propiedad <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> está establecida como `true`, por lo que la actividad <xref:System.Activities.Statements.Parallel> se completa cuando lo hace una de sus bifurcaciones. En este ejemplo, la bifurcación 2 se completa, por lo que se cancela la bifurcación 1.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#37](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#37)]  
  
 Cuando se invoca este flujo de trabajo, en la consola se muestra el siguiente resultado.  
  
 **Iniciando rama 1.**  
**Rama 2 completa.** 
 **Rama 1 cancelada.** 
 **E0685e24-18ef-4a47-acf3-5c638732f3be de flujo de trabajo completado.**  Las actividades también se cancelan si una excepción traspasa la raíz de la actividad, pero se controla en un nivel más alto del flujo de trabajo. En este ejemplo, la lógica principal del flujo de trabajo consta de una actividad <xref:System.Activities.Statements.Sequence>. El objeto <xref:System.Activities.Statements.Sequence> se especifica como la propiedad <xref:System.Activities.Statements.CancellationScope.Body%2A> de una actividad <xref:System.Activities.Statements.CancellationScope> que está incluida en una actividad <xref:System.Activities.Statements.TryCatch>. El cuerpo del objeto <xref:System.Activities.Statements.Sequence> produce una excepción, que es controlada por el elemento principal de la actividad <xref:System.Activities.Statements.TryCatch> y el objeto <xref:System.Activities.Statements.Sequence> se cancela.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#39](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#39)]  
  
 Cuando se invoca este flujo de trabajo, en la consola se muestra el siguiente resultado.  
  
 **Iniciando secuencia.**  
**Secuencia cancelada.** 
 **Excepción detectada.** 
 **E3c18939-121E-4c43-af1c-ba1ce977ce55 de flujo de trabajo completado.**

### <a name="throwing-exceptions-from-a-cancellationhandler"></a>Producir excepciones en CancellationHandler  

 Cualquier excepción producida por la propiedad <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> de un objeto <xref:System.Activities.Statements.CancellationScope> resulta grave para el flujo de trabajo. Si existe alguna posibilidad de que se escapen excepciones de un objeto <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>, utilice un objeto <xref:System.Activities.Statements.TryCatch> en la propiedad <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> para detectar y controlar estas excepciones.  
  
### <a name="cancellation-using-compensableactivity"></a>Cancelación mediante CompensableActivity  

 Al igual que la actividad <xref:System.Activities.Statements.CancellationScope>, <xref:System.Activities.Statements.CompensableActivity> tiene una propiedad <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>. Si se cancela un objeto <xref:System.Activities.Statements.CompensableActivity>, se invoca cualquier actividad presente en su propiedad <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>. Esto puede ser útil para deshacer un trabajo compensable completado parcialmente. Para obtener información sobre cómo usar <xref:System.Activities.Statements.CompensableActivity> para la compensación y la cancelación, consulte [compensación](compensation.md).  
  
## <a name="cancellation-using-custom-activities"></a>Cancelación mediante actividades personalizadas  

 Los autores de actividades personalizadas pueden implementar la lógica de cancelación en sus actividades personalizadas de varias maneras diferentes. Las actividades personalizadas que derivan de <xref:System.Activities.Activity> pueden implementar la lógica de cancelación colocando <xref:System.Activities.Statements.CancellationScope> u otra actividad personalizada que contiene lógica de cancelación en el cuerpo de la actividad. Las actividades derivadas <xref:System.Activities.AsyncCodeActivity> y <xref:System.Activities.NativeActivity> pueden invalidar su método <xref:System.Activities.NativeActivity.Cancel%2A> respectivo y proporcionar lógica de cancelación allí. Las actividades derivadas de <xref:System.Activities.CodeActivity> no proporcionan ninguna disposición para cancelación porque todo el trabajo se realiza en una sola ráfaga de ejecución cuando el tiempo de ejecución llama al método <xref:System.Activities.CodeActivity.Execute%2A>. Si no se ha llamado todavía al método de ejecución y se cancela una actividad basada en <xref:System.Activities.CodeActivity>, la actividad se cierra con el estado <xref:System.Activities.ActivityInstanceState.Canceled> y no se llama al método <xref:System.Activities.CodeActivity.Execute%2A>.  
  
### <a name="cancellation-using-nativeactivity"></a>Cancelación utilizando NativeActivity  

 Las actividades derivadas <xref:System.Activities.NativeActivity> pueden invalidar el método <xref:System.Activities.NativeActivity.Cancel%2A> para proporcionar lógica de cancelación personalizada. Si no se invalida este método, se aplica la lógica de cancelación de flujo de trabajo predeterminada. La cancelación predeterminada es el proceso que se produce para un <xref:System.Activities.NativeActivity> que no invalida el <xref:System.Activities.NativeActivity.Cancel%2A> método o cuyo <xref:System.Activities.NativeActivity.Cancel%2A> método llama al <xref:System.Activities.NativeActivity> <xref:System.Activities.NativeActivity.Cancel%2A> método base. Cuando se cancela una actividad, el tiempo de ejecución marca la actividad para cancelarla y controla automáticamente determinadas tareas de limpieza. Si la actividad solo tiene marcadores pendientes, estos se quitarán y la actividad se marcará como <xref:System.Activities.ActivityInstanceState.Canceled>. Cualquier actividad secundaria pendiente de la actividad cancelada se cancelará a su vez. Cualquier intento de programación de actividades secundarias adicionales se ignorará y la actividad se marcará como <xref:System.Activities.ActivityInstanceState.Canceled>. Si alguna de las actividades secundarias pendientes se completa con el estado <xref:System.Activities.ActivityInstanceState.Canceled> o <xref:System.Activities.ActivityInstanceState.Faulted>, la actividad se marcará como <xref:System.Activities.ActivityInstanceState.Canceled>. Tenga en cuenta que se puede omitir una solicitud de cancelación. Si una actividad no tiene marcadores pendientes ni actividades secundarias en ejecución y no programa ningún elemento de trabajo adicional tras haber sido marcada para cancelarse, se completará correctamente. Esta cancelación predeterminada resulta suficiente para muchos escenarios, pero si se necesita lógica de cancelación adicional, se pueden utilizar actividades de cancelación integradas o personalizadas.  
  
 En el siguiente ejemplo, se define la invalidación <xref:System.Activities.NativeActivity.Cancel%2A> de una actividad <xref:System.Activities.NativeActivity> personalizada basada en `ParallelForEach`. Cuando se cancela la actividad, esta invalidación controla la lógica de cancelación de la actividad. Este ejemplo forma parte del ejemplo [ParallelForEach no genérico](./samples/non-generic-parallelforeach.md) .  
  
```csharp  
protected override void Cancel(NativeActivityContext context)  
{  
    // If we do not have a completion condition then we can just  
    // use default logic.  
    if (this.CompletionCondition == null)  
    {  
        base.Cancel(context);  
    }  
    else  
    {  
        context.CancelChildren();  
    }  
}  
```  
  
 Las actividades derivadas <xref:System.Activities.NativeActivity> pueden determinar si la propiedad <xref:System.Activities.NativeActivityContext.IsCancellationRequested%2A> ha solicitado la cancelación y marcarse a sí mismas como canceladas llamando al método <xref:System.Activities.NativeActivityContext.MarkCanceled%2A>. La llamada al método <xref:System.Activities.NativeActivityContext.MarkCanceled%2A> no completa la actividad de forma inmediata. Como es habitual, el tiempo de ejecución completará la actividad cuando no tenga ningún trabajo pendiente, pero si se llama al método <xref:System.Activities.NativeActivityContext.MarkCanceled%2A>, el estado final será <xref:System.Activities.ActivityInstanceState.Canceled> en lugar de <xref:System.Activities.ActivityInstanceState.Closed>.  
  
### <a name="cancellation-using-asynccodeactivity"></a>Cancelación utilizando AsyncCodeActivity  

 Las actividades basadas en <xref:System.Activities.AsyncCodeActivity> también pueden proporcionar lógica de cancelación personalizada invalidando el método <xref:System.Activities.AsyncCodeActivity.Cancel%2A>. Si no se invalida este método, no se realizará ningún control de la cancelación si la actividad se cancela. En el siguiente ejemplo, se define la invalidación <xref:System.Activities.AsyncCodeActivity.Cancel%2A> de una actividad <xref:System.Activities.AsyncCodeActivity> personalizada basada en `ExecutePowerShell`. Cuando la actividad se cancela, pone en práctica el comportamiento de cancelación deseado.
  
 [!code-csharp[CFX_WorkflowApplicationExample#1020](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#1020)]  
  
 Las actividades derivadas <xref:System.Activities.AsyncCodeActivity> pueden determinar si la propiedad <xref:System.Activities.AsyncCodeActivityContext.IsCancellationRequested%2A> ha solicitado la cancelación y marcarse a sí mismas como canceladas llamando al método <xref:System.Activities.AsyncCodeActivityContext.MarkCanceled%2A>.
