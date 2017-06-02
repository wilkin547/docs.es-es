---
title: "Escenario StateMachine utilizando una combinaci&#243;n de actividades FlowChart y Pick | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 88d81395-f7a3-41d8-8439-20a425c538a6
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Escenario StateMachine utilizando una combinaci&#243;n de actividades FlowChart y Pick
En este ejemplo se muestra cómo implementar un escenario de cronómetro simple mediante una combinación de actividades <xref:System.Activities.Statements.Flowchart> y <xref:System.Activities.Statements.Pick>.Utiliza actividades Receive y Send dentro de la actividad Pick para escuchar eventos de cronómetro.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a \(página de descarga\) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>: \WF_WCF_Samples\WF\Scenario\StateMachineWithPick`  
  
## Detalles del ejemplo  
 En la tabla siguiente se enumeran los proyectos de este ejemplo.  
  
|||  
|-|-|  
|Nombre del proyecto|Descripción|  
|StopWatchService|Este proyecto contiene la implementación de un equipo de estado para el ejemplo del cronómetro utilizando una combinación de las actividades <xref:System.Activities.Statements.Flowchart> y <xref:System.Activities.Statements.Pick>.<br /><br /> La actividad <xref:System.Activities.Statements.Pick> tiene 3 instrucciones <xref:System.Activities.Statements.PickBranch> dentro de la propiedad <xref:System.Activities.Statements.Pick.Branches%2A> que escuchan eventos de `GetStart`, `GetOff` y `GetStop`.En función del evento de entrada, se activan los desencadenadores de una de las bifurcaciones y se desencadena la propiedad <xref:System.Activities.Statements.PickBranch.Action%2A> correspondiente.En la propiedad <xref:System.Activities.Statements.PickBranch.Action%2A>, hay una instrucción <xref:System.Activities.Statements.Switch%601> que evalúa si la transición es legítima y si lo es, la propiedad `currentState` se actualiza al estado de transición y se envía al cliente.<br /><br /> La actividad <xref:System.Activities.Statements.FlowDecision> al final de <xref:System.Activities.Statements.Flowchart> evalúa la propiedad `currentState` para determinar si el estado es terminal.Si es así, el flujo de trabajo finaliza; de lo contrario, el control vuelve en bucle al inicio de la actividad <xref:System.Activities.Statements.Pick> donde el flujo de trabajo está a la espera de más eventos de cronómetro.|  
|StopWatchClient|Esta es una aplicación de consola de flujo de trabajo secuencial simple que envía varios eventos de cronómetro con combinaciones de actividades Send o Receive simples.|  
  
#### Para utilizar este ejemplo  
  
1.  Abra el archivo de solución StateMachineWithPick.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
3.  Inicie StopWatchService.exe desde el [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] como administrador haciendo clic con el botón secundario en el archivo .exe y seleccionando **Ejecutar como administrador**.  
  
    1.  Navegue a la carpeta StateMachineWithPick\\CS\\StopWatchService\\bin\\Debug.  
  
    2.  Haga clic con el botón secundario en el archivo StopWatchService.exe y seleccione **Ejecutar como administrador**.  
  
4.  Inicie la aplicación cliente StopWatchClient desde [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    1.  En el **Explorador de soluciones**, seleccione el proyecto **StopWatchClient** y haga clic con el botón secundario en **Establecer como proyecto de inicio**.  
  
    2.  Presione CTRL\+F5 para ejecutar la solución.  
  
5.  Cambie a la ventana de consola de StopWatchService.exe para ver las transiciones de estado.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>: \WF_WCF_Samples\WF\Scenario\StateMachineWithPick`  
  
## Vea también