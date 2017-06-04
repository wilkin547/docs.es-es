---
title: "Uso b&#225;sico de las actividades SendParameters y ReceiveParameters | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1b6b1681-3d41-403f-bfe2-3f600f24aa8c
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Uso b&#225;sico de las actividades SendParameters y ReceiveParameters
En este ejemplo se muestra el uso de las actividades <xref:System.ServiceModel.Activities.SendParametersContent> y <xref:System.ServiceModel.Activities.ReceiveParametersContent>.El servicio expone una operación que toma un argumento de cadena y devuelve la entrada al cliente.En el ejemplo se muestra cómo preparar los parámetros para estas actividades de mensajería.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Services\SendReceiveParameters`  
  
#### Utilizar este ejemplo  
  
1.  Cargue la solución de proyecto en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] y compile el proyecto.  
  
2.  Primero, ejecute la aplicación EchoWorkflowService generada en \[directorio base de la solución\]\\EchoWorkflowService\\bin\\debug.  
  
3.  En segundo lugar, ejecute la aplicación EchoWorkflowClient generada en \[directorio base de la solución\] \\EchoWorkflowClient\\bin\\debug.  
  
4.  El cliente llama a la operación Echo en el servicio e imprime los resultados.Cuando se haya completado, presione Entrar para salir del cliente y a continuación del servicio.  
  
## Vea también