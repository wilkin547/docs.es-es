---
title: TransactionScope básico
ms.date: 03/30/2017
ms.assetid: 1e22b76a-76de-43b4-9be7-7a86ed3d5a44
ms.openlocfilehash: b3c673040d40ca91d8ab4a79e847d61e6f507ed1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43415428"
---
# <a name="basic-transactionscope"></a>TransactionScope básico
Este ejemplo consta de cuatro escenarios que se ejecutan para mostrar cómo se anidan instancias de <xref:System.Activities.Statements.TransactionScope>. El primer escenario muestra la anidación de una actividad de terceros de la que el autor no conoce su construcción. El segundo y tercer escenarios muestran cómo se respetan los tiempos de espera y el último escenario muestra el valor de <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A>.  
  
## <a name="nesting-of-transactionscopeactivity"></a>Anidar TransactionScopeActivity  
 El flujo de trabajo del primer escenario consta de una secuencia de dos actividades <xref:System.Activities.Statements.WriteLine> y una actividad <xref:System.Activities.Statements.TransactionScope>. El cuerpo de <xref:System.Activities.Statements.TransactionScope> es una secuencia de dos actividades <xref:System.Activities.Statements.WriteLine> más, una actividad personalizada que imprime el identificador local de la transacción y una actividad de terceros. La actividad `TransactionScopeTest` de terceros contiene una actividad <xref:System.Activities.Statements.TransactionScope> aunque el autor del flujo de trabajo no tiene manera de saberlo. Este escenario muestra que las actividades <xref:System.Activities.Statements.TransactionScope> pueden estar anidadas.  
  
## <a name="time-outs"></a>Tiempos de espera  
 El flujo de trabajo del segundo escenario es prácticamente idéntico al primero. `TransactionScopeTest` se ha reemplazado con <xref:System.Activities.Statements.TransactionScope>. El cuerpo de la actividad <xref:System.Activities.Statements.TransactionScope> es un retraso de cinco segundos y el tiempo de espera para la transacción se establece en dos segundos. El tiempo de espera de la actividad <xref:System.Activities.Statements.TransactionScope> se establece en 10 segundos. Observe que se respeta el tiempo de espera más reducido en el ámbito y que la transacción expira.  
  
 El flujo de trabajo del tercer escenario es prácticamente idéntico al escenario dos. La actividad de retraso se ha movido del cuerpo de la actividad <xref:System.Activities.Statements.TransactionScope> interior a una posición inmediatamente después de ella en la secuencia que es el cuerpo de la actividad <xref:System.Activities.Statements.TransactionScope> exterior. La transacción todavía expira, pero el tiempo de espera de dos segundos de la actividad <xref:System.Activities.Statements.TransactionScope> interior ya no se aplica. La transacción expira a los 10 segundos cuando se supera el tiempo de espera de la actividad <xref:System.Activities.Statements.TransactionScope> exterior.  
  
## <a name="aborting-on-transaction-failure"></a>Anular por error de la transacción  
 Este flujo de trabajo es similar al escenario tres excepto que los tiempos de espera se han reemplazado por la propiedad <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A>. Tenga en cuenta que las marcas de todos los elementos secundarios internos, si se establecen, deben coincidir con la actividad <xref:System.Activities.Statements.TransactionScope> exterior. En este escenario no lo hacen, por lo que se produce una excepción cuando se abre el flujo de trabajo.  
  
#### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1.  Abra la solución BasicTransactionScopeSample.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione CTRL + MAYÚS + B o seleccione **compilar solución** desde el **compilar** menú.  
  
3.  Una vez que se ha realizado correctamente la compilación, presione F5 o seleccione **Iniciar depuración** desde el **depurar** menú. También puede presionar CTRL+F5 o seleccionar **iniciar sin depurar** desde el **depurar** menú ejecutar sin depuración.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\BasicTransactionScope`