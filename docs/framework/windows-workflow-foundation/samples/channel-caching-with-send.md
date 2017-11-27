---
title: "Almacenamiento en caché de canales con envío"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e69a2502-25cb-43bf-b8d2-95fbdecb41cb
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3f78b22d1481e260535e4aeb9764d8ee349a7a2c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="channel-caching-with-send"></a>Almacenamiento en caché de canales con envío
<xref:System.ServiceModel.Activities.SendMessageChannelCache> permite a los usuarios tener niveles diferentes de almacenamiento en caché de canales con actividades <xref:System.ServiceModel.Activities.Send> y <xref:System.ServiceModel.Activities.SendParametersContent>. El almacenamiento en caché en el nivel de instancia se habilita de forma predeterminada y en este ejemplo se muestran las siguientes características:  
  
1.  Comparta un <xref:System.ServiceModel.Activities.SendMessageChannelCache> en un dominio de aplicación.  
  
2.  Deshabilite el almacenamiento en caché de canales.  
  
3.  Comparta <xref:System.ServiceModel.Activities.SendMessageChannelCache> entre distintas instancias de flujo de trabajo en <xref:System.ServiceModel.Activities.WorkflowServiceHost>.  
  
## <a name="demonstrates"></a>Demostraciones  
 Extensión de <xref:System.ServiceModel.Activities.SendMessageChannelCache> y actividades <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.ReceiveContent> y <xref:System.ServiceModel.Activities.SendReply>.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Cargue la solución de proyecto en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] y compile el proyecto.  
  
2.  Ejecute la aplicación EchoWorkflowService generada en \EchoWorkflowService\bin\debug.  
  
3.  Ejecute la aplicación EchoWorkflowClient generada en .\EchoWorkflowClient\bin\debug.  
  
4.  El cliente llama a la operación Echo en el servicio e imprime los resultados. Cuando se impriman los resultados, presione ENTRAR para salir del cliente y del servicio.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ChannelCache`
