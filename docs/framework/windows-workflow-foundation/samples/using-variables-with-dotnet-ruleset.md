---
title: "Usar variables con un conjunto de reglas de .NET Framework 3.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 27b56249-22fe-4252-840f-74c0d6c7a6b3
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Usar variables con un conjunto de reglas de .NET Framework 3.5
En este ejemplo se muestra cómo crear un flujo de trabajo que utiliza la actividad <xref:System.Activities.Statements.Interop> para integrar una actividad personalizada escrita en [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] que utiliza directiva y reglas.El flujo de trabajo pasa datos a la actividad personalizada enlazando las variables a las propiedades de dependencia expuestas por la actividad personalizada.  
  
## Ejemplo de tutorial  
  
#### Para examinar TravelRuleLibrary  
  
1.  Con [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], abra el archivo de solución InteropWith35RuleSet.sln.  
  
2.  Abra TravelRuleSet.cs en el diseñador de flujo de trabajo.  
  
     Se muestra una actividad secuencial personalizada que contiene una actividad <xref:System.Workflow.Activities.PolicyActivity>.  
  
3.  Haga doble clic en la actividad de directiva DiscountPolicy para examinar las reglas.  
  
     Aparece el editor de reglas para mostrar las reglas.  
  
4.  Haga clic con el botón secundario en `DiscountPolicy` y seleccione la opción **Ver código** para examinar el código C\# lateral de la actividad.  
  
     Observe el valor de propiedad de dependencia para `DiscountLevel`.Esto equivale a los argumentos en [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].[!INCLUDE[crabout](../../../../includes/crabout-md.md)] los argumentos, vea [Variables y argumentos](../../../../docs/framework/windows-workflow-foundation//variables-and-arguments.md).  
  
## InteropWith35RuleSet  
 Es un proyecto de flujo de trabajo secuencial que utiliza la actividad <xref:System.Activities.Statements.Interop> para integrar con el conjunto de reglas personalizado creado en el proyecto `TravelRuleLibrary`.Las variables se crean en la actividad <xref:System.Activities.Statements.Sequence> de nivel superior.La actividad <xref:System.Activities.Statements.Interop> se utiliza para la integración con la actividad `TravelRuleSet`.Las variables que se declaran en <xref:System.Activities.Statements.Sequence> se utilizan para enlazar con las propiedades de dependencia.  
  
## Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución InteropWith35RuleSet.sln.  
  
2.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
3.  Para ejecutar la solución, presione CTRL\+F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`  
  
## Vea también