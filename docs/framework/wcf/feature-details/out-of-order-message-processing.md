---
title: Procesar un mensaje sin orden
ms.date: 03/30/2017
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
ms.openlocfilehash: 4e1864b25a4dbe8192cd5c692c75645bebbb92d2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141406"
---
# <a name="out-of-order-message-processing"></a>Procesar un mensaje sin orden
Los servicios del flujo de trabajo pueden depender de mensajes enviados en un orden concreto. Un servicio del flujo de trabajo contiene una o más actividades <xref:System.ServiceModel.Activities.Receive> y cada actividad <xref:System.ServiceModel.Activities.Receive> espera un mensaje concreto. Sin garantías de entrega de transporte específicas, se pueden retrasar los mensajes enviados por los clientes y, por lo tanto, se pueden entregar en un orden que el servicio del flujo de trabajo no se espera. La implementación de un servicio del flujo de trabajo que no requiera que los mensajes se envíen en un orden concreto se suele llevar a cabo mediante una actividad paralela. Si el protocolo de aplicación es más complicado, el flujo de trabajo se volvería muy complejo con mucha rapidez.  El mensaje desordenado de procesamiento de la característica de Windows Communication Foundation (WCF) le permite crear este flujo de trabajo sin toda la complejidad de las actividades paralelas anidadas. Procesamiento de mensajes de desordenado solo se admite en los canales que admiten <xref:System.ServiceModel.Channels.ReceiveContext> como los enlaces de MSMQ de WCF.  
  
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
- [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Colas y sesiones de confianza](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
