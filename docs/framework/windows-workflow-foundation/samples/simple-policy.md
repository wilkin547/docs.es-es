---
title: Directiva simple
ms.date: 03/30/2017
ms.assetid: 6a94c834-2e32-4bed-9f47-ae5845eef6ff
ms.openlocfilehash: 7f189e4d1811cb0b7dd9138b944bfd0552481690
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43561269"
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
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\SimplePolicy`  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [Directiva avanzada](../../../../docs/framework/windows-workflow-foundation/samples/advanced-policy.md)
