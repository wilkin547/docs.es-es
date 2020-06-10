---
title: Procesar un mensaje sin orden
ms.date: 03/30/2017
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
ms.openlocfilehash: 7930f26cf5957158a16d65085267cf1bab2e4504
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598728"
---
# <a name="out-of-order-message-processing"></a>Procesar un mensaje sin orden
Los servicios del flujo de trabajo pueden depender de mensajes enviados en un orden concreto. Un servicio del flujo de trabajo contiene una o más actividades <xref:System.ServiceModel.Activities.Receive> y cada actividad <xref:System.ServiceModel.Activities.Receive> espera un mensaje concreto. Sin garantías de entrega de transporte específicas, se pueden retrasar los mensajes enviados por los clientes y, por lo tanto, se pueden entregar en un orden que el servicio del flujo de trabajo no se espera. La implementación de un servicio del flujo de trabajo que no requiera que los mensajes se envíen en un orden concreto se suele llevar a cabo mediante una actividad paralela. Si el protocolo de aplicación es más complicado, el flujo de trabajo se volvería muy complejo con mucha rapidez.  La característica de procesamiento de mensajes desordenados en Windows Communication Foundation (WCF) le permite crear este tipo de flujo de trabajo sin la complejidad de las actividades paralelas anidadas. El procesamiento de mensajes desordenados solo se admite en los canales que admiten <xref:System.ServiceModel.Channels.ReceiveContext> , como los enlaces MSMQ de WCF.  
  
## <a name="enabling-out-of-order-message-processing"></a>Habilitar el procesamiento de mensajes desordenado  
 El procesamiento de mensajes desordenado se habilita estableciendo la propiedad <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> en `true` en WorkflowService. En el siguiente ejemplo, se muestra cómo establecer la propiedad <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> en código.  
  
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
   <!--the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.ReceiveContext>
- [Servicios de flujo de trabajo](workflow-services.md)
- [Colas y sesiones de confianza](queues-and-reliable-sessions.md)
