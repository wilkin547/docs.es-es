---
title: Ejecutar un flujo de trabajo en un objeto TransactionScope imperativo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd0e8686-c1d0-4400-a541-da94ed03afc7
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 40a9e00659cad1dd2ab22b85f3ed15d958fd107b
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="execute-a-workflow-in-an-imperative-transactionscope"></a>Ejecutar un flujo de trabajo en un objeto TransactionScope imperativo
En este ejemplo se muestra cómo ejecutar un flujo de trabajo utilizando <xref:System.Activities.WorkflowInvoker> en un objeto <xref:System.Transactions.Transaction> con código C# imperativo.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 En el código C# imperativo, el objeto <xref:System.Transactions.TransactionScope> se utiliza para encapsular un conjunto de trabajo que se ejecuta en la misma transacción. <xref:System.Transactions.TransactionScope> funciona creando una transacción ambiente e inicializando la propiedad <xref:System.Transactions.Transaction.Current%2A> a la que puede tener acceso cualquier trabajo que se esté ejecutando en ese subproceso.  
  
 Para obtener el comportamiento equivalente en el flujo de trabajo, el tiempo de ejecución tiene que realizar el trabajo extraordinario de inicializar <xref:System.Transactions.Transaction.Current%2A> antes de ejecutar cada actividad porque un flujo de trabajo no mantiene la afinidad del subproceso entre actividades. Con esta compatibilidad con el motor en tiempo de ejecución, el comportamiento resultante es que al ejecutar un flujo de trabajo con <xref:System.Activities.WorkflowInvoker> dentro de <xref:System.Transactions.TransactionScope>, se garantiza que todas las actividades se ejecutarán en el contexto de la transacción ambiente creado por <xref:System.Transactions.TransactionScope>.  
  
 Un flujo de trabajo puede tener solo una transacción ambiente única para cada instancia de flujo de trabajo; las transacciones anidadas no están disponibles. Aunque el flujo de trabajo contenga una actividad <xref:System.Activities.Statements.TransactionScope>, no se crea una transacción interna. En su lugar, se reutiliza la transacción ambiente que se creó fuera del flujo de trabajo.  
  
 El ejemplo comienza un nuevo <xref:System.Transactions.TransactionScope>, imprime el identificador de la transacción y comienza un flujo de trabajo mediante <xref:System.Activities.WorkflowInvoker>. El flujo de trabajo imprime de nuevo el identificador de la transacción, mostrando que es la misma transacción; a continuación, ejecuta <xref:System.Activities.Statements.TransactionScope> y, después, se completa. La llamada de <xref:System.Activities.WorkflowInvoker.Invoke%2A> en <xref:System.Activities.WorkflowInvoker> es sincrónica para que el subproceso original se bloquee hasta que el flujo de trabajo se complete. Cuando el flujo de trabajo finaliza, la transacción se completa y los recursos se eliminan.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra el archivo de solución ImperativeTransactionSample.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Presione F5 para ejecutar la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\ImperativeTransaction`