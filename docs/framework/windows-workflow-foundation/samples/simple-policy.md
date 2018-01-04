---
title: Directiva simple
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a94c834-2e32-4bed-9f47-ae5845eef6ff
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 884a099c1334b53c904173987d2f1ccfe6dd741a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="simple-policy"></a>Directiva simple
En este ejemplo se muestra cómo utilizar una actividad <xref:System.Workflow.Activities.PolicyActivity> en un flujo de trabajo.  
  
 El flujo de trabajo secuencial de este ejemplo se crea utilizando una actividad <xref:System.Workflow.Activities.PolicyActivity>. El flujo de trabajo define campos `orderValue`, `customerType`  y `discount` que se utilizan para definir un flujo de trabajo de descuento de productos. Las reglas definidas en los archivos de reglas establecen un valor de descuento basado en los campos `orderValue` y `customerType`. `orderValue` y `customerType` se establecen en la definición de clase `SimplePolicyWorkflow` y se pueden cambiar para modificar el comportamiento. El descuento resultante se escribe en la consola el controlador de eventos <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> que se define en la clase `SimplePolicyWorkflow`.  
  
### <a name="to-build-the-sample"></a>Para compilar el ejemplo  
  
1.  Abra la solución en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compile la solución presionando CTRL+MAYÚS+B.  
  
3.  Ejecute la solución sin depuración presionando CTRL+F5.  
  
### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
-   En la ventana del símbolo del sistema del SDK, ejecute el archivo .exe de la carpeta SimplePolicy\bin\debug (o la carpeta SimplePolicy\bin para la versión de Visual Basic del ejemplo), que se encuentra debajo de la carpeta principal del ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar:  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\SimplePolicy`  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [Directiva avanzada](../../../../docs/framework/windows-workflow-foundation/samples/advanced-policy.md)
