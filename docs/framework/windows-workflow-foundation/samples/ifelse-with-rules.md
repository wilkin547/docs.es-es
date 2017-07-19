---
title: "IfElse con reglas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c4ad9bb2-9037-413a-8b14-59ed7b927a9e
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# IfElse con reglas
En este ejemplo se muestra el uso de una condición de regla con una actividad <xref:System.Workflow.Activities.IfElseActivity>.  
  
 En el ejemplo se pasa un parámetro `OrderValue` del host.El valor del parámetro se utiliza en una condición de regla en la primera bifurcación de la actividad <xref:System.Workflow.Activities.IfElseActivity>.Si el valor es menor que 10.000, se ejecuta la primera bifurcación y la actividad <xref:System.Workflow.Activities.CodeActivity> de la primera bifurcación imprime **Get Manager Approval** en la consola.Si el valor es mayor que 10.000, se ejecuta la actividad <xref:System.Workflow.Activities.CodeActivity> de la segunda bifurcación e imprime **Get VP Approval**.  
  
### Para compilar el ejemplo  
  
1.  Abra la solución en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compile la solución presionando CTRL\+MAYÚS\+B.  
  
3.  Ejecute la solución sin depuración presionando CTRL\+F5.  
  
### Para ejecutar el ejemplo  
  
-   En la ventana del símbolo del sistema del SDK, ejecute el archivo .exe de la carpeta IfElseWithRules\\bin\\debug \(o la carpeta IfElseWithRules\\bin para la versión de Visual Basic del ejemplo\), que se encuentra debajo de la carpeta principal del ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar:  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio:  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Rules\IfElseWithRules`  
  
## Vea también  
 <xref:System.Workflow.Activities.Rules>   
 <xref:System.Workflow.Activities.IfElseActivity>   
 <xref:System.Workflow.Activities.CodeActivity>   
 <xref:System.Workflow.Activities.Rules.RuleDefinitions>