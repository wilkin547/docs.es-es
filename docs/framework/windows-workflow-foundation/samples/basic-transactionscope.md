---
title: "TransactionScope b&#225;sico | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1e22b76a-76de-43b4-9be7-7a86ed3d5a44
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# TransactionScope b&#225;sico
Este ejemplo consta de cuatro escenarios que se ejecutan para mostrar cómo se anidan instancias de <xref:System.Activities.Statements.TransactionScope>.El primer escenario muestra la anidación de una actividad de terceros de la que el autor no conoce su construcción.El segundo y tercer escenarios muestran cómo se respetan los tiempos de espera y el último escenario muestra el valor de <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A>.  
  
## Anidar TransactionScopeActivity  
 El flujo de trabajo del primer escenario consta de una secuencia de dos actividades <xref:System.Activities.Statements.WriteLine> y una actividad <xref:System.Activities.Statements.TransactionScope>.El cuerpo de <xref:System.Activities.Statements.TransactionScope> es una secuencia de dos actividades <xref:System.Activities.Statements.WriteLine> más, una actividad personalizada que imprime el identificador local de la transacción y una actividad de terceros.La actividad `TransactionScopeTest` de terceros contiene una actividad <xref:System.Activities.Statements.TransactionScope> aunque el autor del flujo de trabajo no tiene manera de saberlo.Este escenario muestra que las actividades <xref:System.Activities.Statements.TransactionScope> pueden estar anidadas.  
  
## Tiempos de espera  
 El flujo de trabajo del segundo escenario es prácticamente idéntico al primero.`TransactionScopeTest` se ha reemplazado con <xref:System.Activities.Statements.TransactionScope>.El cuerpo de la actividad <xref:System.Activities.Statements.TransactionScope> es un retraso de cinco segundos y el tiempo de espera para la transacción se establece en dos segundos.El tiempo de espera de la actividad <xref:System.Activities.Statements.TransactionScope> se establece en 10 segundos.Observe que se respeta el tiempo de espera más reducido en el ámbito y que la transacción expira.  
  
 El flujo de trabajo del tercer escenario es prácticamente idéntico al escenario dos.La actividad de retraso se ha movido del cuerpo de la actividad <xref:System.Activities.Statements.TransactionScope> interior a una posición inmediatamente después de ella en la secuencia que es el cuerpo de la actividad <xref:System.Activities.Statements.TransactionScope> exterior.La transacción todavía expira, pero el tiempo de espera de dos segundos de la actividad <xref:System.Activities.Statements.TransactionScope> interior ya no se aplica.La transacción expira a los 10 segundos cuando se supera el tiempo de espera de la actividad <xref:System.Activities.Statements.TransactionScope> exterior.  
  
## Anular por error de la transacción  
 Este flujo de trabajo es similar al escenario tres excepto que los tiempos de espera se han reemplazado por la propiedad <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A>.Tenga en cuenta que las marcas de todos los elementos secundarios internos, si se establecen, deben coincidir con la actividad <xref:System.Activities.Statements.TransactionScope> exterior.En este escenario no lo hacen, por lo que se produce una excepción cuando se abre el flujo de trabajo.  
  
#### Para ejecutar el ejemplo  
  
1.  Abra la solución BasicTransactionScopeSample.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione CTRL\+MAYÚS\+B o seleccione **Compilar solución** en el menú **Compilar**.  
  
3.  Cuando la compilación finalice correctamente, presione F5 o seleccione **Iniciar depuración** en el menú **Depurar**.También puede presionar CTRL\+F5 o seleccionar **Iniciar sin depurar** en el menú **Depurar** para realizar la ejecución sin depuración.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Transactions\BasicTransactionScope`  
  
## Vea también