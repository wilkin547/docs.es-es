---
title: Usar variables con un conjunto de reglas de .NET Framework 3.5
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 27b56249-22fe-4252-840f-74c0d6c7a6b3
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 216136ba084505947b5ab3c985284d704cb5872f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="using-variables-with-a-net-framework-35-ruleset"></a>Usar variables con un conjunto de reglas de .NET Framework 3.5
En este ejemplo se muestra cómo crear un flujo de trabajo que utiliza la actividad <xref:System.Activities.Statements.Interop> para integrar una actividad personalizada escrita en [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] que utiliza directiva y reglas. El flujo de trabajo pasa datos a la actividad personalizada enlazando las variables a las propiedades de dependencia expuestas por la actividad personalizada.  
  
## <a name="sample-walkthrough"></a>Ejemplo de tutorial  
  
#### <a name="to-examine-travelrulelibrary"></a>Para examinar TravelRuleLibrary  
  
1.  Con Visual Studio, abra el archivo de solución InteropWith35RuleSet.sln.  
  
2.  Abra TravelRuleSet.cs en el diseñador de flujo de trabajo.  
  
     Se muestra una actividad secuencial personalizada que contiene una actividad <xref:System.Workflow.Activities.PolicyActivity>.  
  
3.  Haga doble clic en la actividad de directiva DiscountPolicy para examinar las reglas.  
  
     Aparece el editor de reglas para mostrar las reglas.  
  
4.  Haga clic con el `DiscountPolicy` y seleccione la **ver código** opción para examinar el código C# lateral de la actividad.  
  
     Observe el valor de propiedad de dependencia para `DiscountLevel`. Esto equivale a los argumentos en [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] argumentos, vea [Variables y argumentos](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).  
  
## <a name="interopwith35ruleset"></a>InteropWith35RuleSet  
 Es un proyecto de flujo de trabajo secuencial que utiliza la actividad <xref:System.Activities.Statements.Interop> para integrar con el conjunto de reglas personalizado creado en el proyecto `TravelRuleLibrary`. Las variables se crean en la actividad <xref:System.Activities.Statements.Sequence> de nivel superior. La actividad <xref:System.Activities.Statements.Interop> se utiliza para la integración con la actividad `TravelRuleSet`. Las variables que se declaran en <xref:System.Activities.Statements.Sequence> se utilizan para enlazar con las propiedades de dependencia.  
  
## <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución InteropWith35RuleSet.sln.  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Para ejecutar la solución, presione CTRL+F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`