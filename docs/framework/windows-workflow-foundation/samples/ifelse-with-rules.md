---
title: IfElse con reglas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4ad9bb2-9037-413a-8b14-59ed7b927a9e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bec818ca5492e9a49a602a4f7baef4b45cb073c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ifelse-with-rules"></a>IfElse con reglas
En este ejemplo se muestra el uso de una condición de regla con una actividad <xref:System.Workflow.Activities.IfElseActivity>.  
  
 En el ejemplo se pasa un parámetro `OrderValue` del host. El valor del parámetro se utiliza en una condición de regla en la primera bifurcación de la actividad <xref:System.Workflow.Activities.IfElseActivity>. Si el valor es menor que 10.000, se ejecuta la primera bifurcación y la <xref:System.Workflow.Activities.CodeActivity> actividad en la primera bifurcación imprime **obtener la aprobación del administrador** en la consola. Si el valor es mayor que 10.000, el <xref:System.Workflow.Activities.CodeActivity> actividad en la segunda bifurcación ejecuta e imprime **obtener la aprobación de VP**.  
  
### <a name="to-build-the-sample"></a>Para compilar el ejemplo  
  
1.  Abra la solución en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compile la solución presionando CTRL+MAYÚS+B.  
  
3.  Ejecute la solución sin depuración presionando CTRL+F5.  
  
### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
-   En la ventana del símbolo del sistema del SDK, ejecute el archivo .exe de la carpeta IfElseWithRules\bin\debug (o la carpeta IfElseWithRules\bin para la versión de Visual Basic del ejemplo), que se encuentra debajo de la carpeta principal del ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar:  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\IfElseWithRules`  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Workflow.Activities.Rules>  
 <xref:System.Workflow.Activities.IfElseActivity>  
 <xref:System.Workflow.Activities.CodeActivity>  
 <xref:System.Workflow.Activities.Rules.RuleDefinitions>
