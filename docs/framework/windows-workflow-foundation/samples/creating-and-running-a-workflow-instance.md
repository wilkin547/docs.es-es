---
title: "Crear y ejecutar una instancia de flujo de trabajo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Crear y ejecutar una instancia de flujo de trabajo
En este ejemplo se muestra cómo ejecutar una instancia de flujo de trabajo.Muestra cómo ejecutarla sincrónicamente y de forma asincrónica.  
  
## Demostraciones  
 <xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.  
  
## Análisis  
 La primera parte del ejemplo utiliza <xref:System.Activities.WorkflowInvoker.Invoke%2A>.Esta es la manera más básica de ejecutar un flujo de trabajo.Los flujos de trabajo ejecutados con <xref:System.Activities.WorkflowInvoker.Invoke%2A> se ejecutan de forma sincrónica.  
  
 La segunda parte del ejemplo usa la clase <xref:System.Activities.WorkflowApplication>.<xref:System.Activities.WorkflowApplication> permite tener más control sobre cada instancia, incluida la capacidad de interactuar con el flujo de trabajo en ejecución y ejecutar el flujo de trabajo de forma asincrónica.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## Vea también  
 [Usar WorkflowInvoker y WorkflowApplication](../../../../docs/framework/windows-workflow-foundation//using-workflowinvoker-and-workflowapplication.md)