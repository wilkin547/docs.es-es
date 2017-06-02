---
title: "Procesar un mensaje sin orden | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Procesar un mensaje sin orden
Los servicios del flujo de trabajo pueden depender de mensajes enviados en un orden concreto.Un servicio del flujo de trabajo contiene una o más actividades <xref:System.ServiceModel.Activities.Receive> y cada actividad <xref:System.ServiceModel.Activities.Receive> espera un mensaje concreto.Sin garantías de entrega de transporte específicas, se pueden retrasar los mensajes enviados por los clientes y, por lo tanto, se pueden entregar en un orden que el servicio del flujo de trabajo no se espera.La implementación de un servicio del flujo de trabajo que no requiera que los mensajes se envíen en un orden concreto se suele llevar a cabo mediante una actividad paralela.Si el protocolo de aplicación es más complicado, el flujo de trabajo se volvería muy complejo con mucha rapidez.La característica de procesamiento de mensajes desordenado en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] le permite crear este tipo de flujo de trabajo sin toda la complejidad de las actividades paralelas anidadas.El procesamiento de mensajes desordenado solo se admite en canales que admitan <xref:System.ServiceModel.Channele.ReceiveContext>, como los enlaces de MSMQ de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## Habilitar el procesamiento de mensajes desordenado  
 El procesamiento de mensajes desordenado se habilita estableciendo la propiedad <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> en `true` en WorkflowService.En el siguiente ejemplo, se muestra cómo establecer la propiedad <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> en código.  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
  
```  
  
 También puede aplicar el atributo `AllowBufferedReceive` a un servicio del flujo de trabajo en XAML, tal y como se muestra en el siguiente ejemplo.  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!—the actual children activities -->  
</Sequence>  
```  
  
## Vea también  
 <xref:System.ServiceModel.Channels.ReceiveContext>   
 [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)   
 [Colas y sesiones de confianza](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)