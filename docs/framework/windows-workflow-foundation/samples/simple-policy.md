---
title: "Directiva simple | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6a94c834-2e32-4bed-9f47-ae5845eef6ff
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Directiva simple
En este ejemplo se muestra cómo utilizar una actividad <xref:System.Workflow.Activities.PolicyActivity> en un flujo de trabajo.  
  
 El flujo de trabajo secuencial de este ejemplo se crea utilizando una actividad <xref:System.Workflow.Activities.PolicyActivity>.El flujo de trabajo define campos `orderValue`, `customerType` y `discount` que se utilizan para definir un flujo de trabajo de descuento de productos.Las reglas definidas en los archivos de reglas establecen un valor de descuento basado en los campos `orderValue` y `customerType`.`orderValue` y `customerType` se establecen en la definición de clase `SimplePolicyWorkflow` y se pueden cambiar para modificar el comportamiento.El descuento resultante se escribe en la consola el controlador de eventos <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> que se define en la clase `SimplePolicyWorkflow`.  
  
### Para compilar el ejemplo  
  
1.  Abra la solución en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compile la solución presionando CTRL\+MAYÚS\+B.  
  
3.  Ejecute la solución sin depuración presionando CTRL\+F5.  
  
### Para ejecutar el ejemplo  
  
-   En la ventana del símbolo del sistema del SDK, ejecute el archivo .exe de la carpeta SimplePolicy\\bin\\debug \(o la carpeta SimplePolicy\\bin para la versión de Visual Basic del ejemplo\), que se encuentra debajo de la carpeta principal del ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar:  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio:  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Rules\Policy\SimplePolicy`  
  
## Vea también  
 <xref:System.Workflow.Activities.Rules.RuleSet>   
 <xref:System.Workflow.Activities.PolicyActivity>   
 [Directiva avanzada](../../../../docs/framework/windows-workflow-foundation/samples/advanced-policy.md)