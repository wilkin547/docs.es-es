---
title: Usar CancellationScope
ms.date: 03/30/2017
ms.assetid: 39c5c338-b316-43d6-b7fe-a543281dd1ec
ms.openlocfilehash: 62b798b29149e30a2fae680b507f62ef0a2e23d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="using-cancellationscope"></a>Usar CancellationScope
En este ejemplo se muestra cómo utilizar la actividad <xref:System.Activities.Statements.CancellationScope> para cancelar el trabajo en una aplicación.  
  
 Muchos componentes y servicios de nivel intermedio confían en la conocida construcción de programación de transacciones para administrar su cancelación.  Sin embargo, hay muchas casos en los que el trabajo que no se puede realizar en una transacción se debe cancelar.  El uso de la cancelación es más difícil que el uso de transacciones, porque antes de cancelar un trabajo se debe realizar su seguimiento. [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] ayuda con esto proporcionando una actividad <xref:System.Activities.Statements.CancellationScope>.  
  
 La cancelación se puede activar desde una actividad o desde el elemento primario de la actividad.  La actividad primaria (como una actividad <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Parallel>, <xref:System.Activities.Statements.Flowchart> o una actividad compuesta personalizada) programa sus actividades secundarias.  La actividad primaria puede cancelar las actividades secundarias por cualquier motivo.  Por ejemplo, una actividad <xref:System.Activities.Statements.Parallel> con tres bifurcaciones secundarias cancelará las bifurcaciones secundarias restantes siempre que complete una bifurcación y la expresión <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> se evalúe como `true`. La aplicación host también puede cancelar externamente el flujo de trabajo llamando a <xref:System.Activities.WorkflowApplication.Cancel%2A>.  
  
 Para utilizar la actividad <xref:System.Activities.Statements.CancellationScope>, coloque el trabajo que se debe cancelar en la propiedad <xref:System.Activities.Statements.CancellationScope.Body%2A> y el trabajo que se realiza después de la cancelación en la propiedad <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>.  
  
 En este ejemplo se muestra la cancelación de una actividad desde la propia actividad.  
  
 El escenario que el ejemplo utiliza para mostrar la actividad <xref:System.Activities.Statements.CancellationScope> es un cliente que desea comprar un billete a Miami lo antes posible. Hay dos agencias de viaje que desean el negocio. En el ejemplo se utilizan dos actividades <xref:System.Activities.Statements.CancellationScope> dentro de una actividad <xref:System.Activities.Statements.Parallel> para modelar esta lógica comercial. La propiedad <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> de la actividad <xref:System.Activities.Statements.Parallel> está establecida en `true`; puesto que la propiedad <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> se comprueba una vez que se completa una bifurcación, esto hará que la bifurcación restante se cancele cuando se complete la primera. La aplicación cliente pide a ambas agencias que compren el billete y, cuando la primera confirma que lo ha comprado, la aplicación cancela el pedido en la otra agencia.  
  
## <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución CancelationScopeXAML.sln.  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Para ejecutar la solución, presione CTRL+F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\CancellationScope`