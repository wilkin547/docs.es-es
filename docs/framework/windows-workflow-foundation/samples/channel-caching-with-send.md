---
title: "Almacenamiento en cach&#233; de canales con env&#237;o | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e69a2502-25cb-43bf-b8d2-95fbdecb41cb
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Almacenamiento en cach&#233; de canales con env&#237;o
<xref:System.ServiceModel.Activities.SendMessageChannelCache> permite a los usuarios tener niveles diferentes de almacenamiento en caché de canales con actividades <xref:System.ServiceModel.Activities.SendParametersContent> y <xref:System.ServiceModel.Activities.Send>.El almacenamiento en caché en el nivel de instancia se habilita de forma predeterminada y en este ejemplo se muestran las siguientes características:  
  
1.  Comparta un <xref:System.ServiceModel.Activities.SendMessageChannelCache> en un dominio de aplicación.  
  
2.  Deshabilite el almacenamiento en caché de canales.  
  
3.  Comparta <xref:System.ServiceModel.Activities.SendMessageChannelCache> entre distintas instancias de flujo de trabajo en <xref:System.ServiceModel.Activities.WorkflowServiceHost>.  
  
## Demostraciones  
 Extensión de <xref:System.ServiceModel.Activities.SendMessageChannelCache> y actividades <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply> y <xref:System.ServiceModel.Activities.ReceiveContent>.  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Cargue la solución de proyecto en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] y compile el proyecto.  
  
2.  Ejecute la aplicación EchoWorkflowService generada en \\EchoWorkflowService\\bin\\debug.  
  
3.  Ejecute la aplicación EchoWorkflowClient generada.\\EchoWorkflowClient\\bin\\debug.  
  
4.  El cliente llama a la operación Echo en el servicio e imprime los resultados.Cuando se impriman los resultados, presione ENTRAR para salir del cliente y del servicio.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Services\ChannelCache`