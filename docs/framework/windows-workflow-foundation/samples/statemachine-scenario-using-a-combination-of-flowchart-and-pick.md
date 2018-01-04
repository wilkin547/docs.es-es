---
title: "Escenario StateMachine utilizando una combinación de actividades FlowChart y Pick"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88d81395-f7a3-41d8-8439-20a425c538a6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 39ae1be025e3b888fff8b46ebbc45832c218dda7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="statemachine-scenario-using-a-combination-of-flowchart-and-pick"></a>Escenario StateMachine utilizando una combinación de actividades FlowChart y Pick
En este ejemplo se muestra cómo implementar un escenario de cronómetro simple mediante una combinación de actividades <xref:System.Activities.Statements.Flowchart> y <xref:System.Activities.Statements.Pick>. Utiliza actividades Receive y Send dentro de la actividad Pick para escuchar eventos de cronómetro.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a (página de descarga) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 En la tabla siguiente se enumeran los proyectos de este ejemplo.  
  
|Nombre del proyecto|Descripción|  
|-|-|  
|StopWatchService|Este proyecto contiene la implementación de un equipo de estado para el ejemplo del cronómetro utilizando una combinación de las actividades <xref:System.Activities.Statements.Flowchart> y <xref:System.Activities.Statements.Pick>.<br /><br /> La actividad <xref:System.Activities.Statements.Pick> tiene 3 instrucciones <xref:System.Activities.Statements.PickBranch> dentro de la propiedad <xref:System.Activities.Statements.Pick.Branches%2A> que escuchan eventos de `GetStart`, `GetStop` y `GetOff`. En función del evento de entrada, se activan los desencadenadores de una de las bifurcaciones y se desencadena la propiedad <xref:System.Activities.Statements.PickBranch.Action%2A> correspondiente. En la propiedad <xref:System.Activities.Statements.PickBranch.Action%2A>, hay una instrucción <xref:System.Activities.Statements.Switch%601> que evalúa si la transición es legítima y si lo es, la propiedad `currentState` se actualiza al estado de transición y se envía al cliente.<br /><br /> La actividad <xref:System.Activities.Statements.FlowDecision> al final de <xref:System.Activities.Statements.Flowchart> evalúa la propiedad `currentState` para determinar si el estado es terminal. Si es así, el flujo de trabajo finaliza; de lo contrario, el control vuelve en bucle al inicio de la actividad <xref:System.Activities.Statements.Pick> donde el flujo de trabajo está a la espera de más eventos de cronómetro.|  
|StopWatchClient|Esta es una aplicación de consola de flujo de trabajo secuencial simple que envía varios eventos de cronómetro con combinaciones de actividades Send o Receive simples.|  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra el archivo de solución StateMachineWithPick.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Inicie StopWatchService.exe desde [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] como administrador, haga clic en el archivo .exe y seleccionando **ejecutar como administrador**.  
  
    1.  Navegue a la carpeta StateMachineWithPick\CS\StopWatchService\bin\Debug.  
  
    2.  Haga clic en el archivo StopWatchService.exe y seleccione **ejecutar como administrador**.  
  
4.  Inicie la aplicación cliente StopWatchClient desde [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    1.  En **el Explorador de soluciones**, seleccione la **StopWatchClient** del proyecto y haga clic en **establecer como proyecto de inicio**.  
  
    2.  Para ejecutar la solución, presione CTRL+F5.  
  
5.  Cambie a la ventana de consola de StopWatchService.exe para ver las transiciones de estado.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`