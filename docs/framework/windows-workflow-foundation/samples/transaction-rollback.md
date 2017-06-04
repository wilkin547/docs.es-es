---
title: "Revertir una transacci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7f377147-7529-4689-a588-608cee87fdf8
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Revertir una transacci&#243;n
En este ejemplo se muestra cómo crear un objeto <xref:System.Activities.NativeActivity> personalizado que tenga acceso al ambiente <xref:System.Activities.RuntimeTransactionHandle> para obtener la transacción ambiente y revertirla explícitamente.  
  
## Detalles del ejemplo  
 En el flujo de trabajo, una transacción se completa automáticamente cuando se completa la actividad <xref:System.Activities.Statements.TransactionScope> o <xref:System.ServiceModel.Activities.TransactedReceiveScope> más extrema.Una transacción se revierte implícitamente cuando se propaga una excepción no controlada en el límite del ámbito.Sin embargo, puede haber ocasiones en que convenga revertir explícitamente una transacción sin necesidad de que se produzca una excepción.En este caso, puede usar la actividad de reversión personalizada como la de este ejemplo para anular explícitamente la transacción ambiente y proporcionar un motivo opcional para la excepción.  
  
 La actividad `RollbackActivity` es una actividad <xref:System.Activities.NativeActivity>, ya que requiere acceso a las propiedades de ejecución para obtener la clase <xref:System.Activities.RuntimeTransactionHandle> ambiente.En el método `Execute`, obtiene la clase <xref:System.Activities.RuntimeTransactionHandle> y comprueba si es `null`, lo que indica que la actividad se utilizó sin una transacción en tiempo de ejecución ambiente.A continuación, obtiene la transacción y comprueba de nuevo si `null` está presente.Es posible contar con una clase <xref:System.Activities.RuntimeTransactionHandle> ambiente sin inicializar nunca una transacción en tiempo de ejecución.Por último, anula la transacción mediante una llamada al método <xref:System.Transactions.Transaction.Rollback%2A> y la especificación de una excepción proporcionada por el usuario o de una excepción genérica que indica que la actividad revirtió la transacción.  
  
 El flujo de trabajo que se ha mostrado consta de una actividad <xref:System.Activities.Statements.TransactionScope> cuyo cuerpo imprime el estado de la transacción antes y después de que se ejecute la actividad `RollbackActivity`.Tenga en cuenta que aunque se haya revertido la transacción, <xref:System.Activities.Statements.TransactionScope> se ejecuta hasta completarse y no anula el flujo de trabajo hasta que se completa el cuerpo.El flujo de trabajo se anula porque la propiedad <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A> tiene como valor predeterminado `true`.  
  
#### Para utilizar este ejemplo  
  
1.  Cargue la solución TransactionRollback.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Presione Ctrl\+MAYÚS\+B para compilar la solución.  
  
3.  Presione CTRL\+F5 para ejecutar la aplicación.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactionRollback`  
  
## Vea también  
 [Transacciones](../../../../docs/framework/windows-workflow-foundation//workflow-transactions.md)