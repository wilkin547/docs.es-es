---
title: Procesar un mensaje sin orden
ms.date: 03/30/2017
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
ms.openlocfilehash: 3beca8d73788d177d07868d7169d8aea3ecd8e80
ms.sourcegitcommit: 3b9b7ae6771712337d40374d2fef6b25b0d53df6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/04/2019
ms.locfileid: "54029953"
---
# <a name="out-of-order-message-processing"></a><span data-ttu-id="3c727-102">Procesar un mensaje sin orden</span><span class="sxs-lookup"><span data-stu-id="3c727-102">Out-of-Order Message Processing</span></span>
<span data-ttu-id="3c727-103">Los servicios del flujo de trabajo pueden depender de mensajes enviados en un orden concreto.</span><span class="sxs-lookup"><span data-stu-id="3c727-103">Workflow services may depend on messages being sent in a specific order.</span></span> <span data-ttu-id="3c727-104">Un servicio del flujo de trabajo contiene una o más actividades <xref:System.ServiceModel.Activities.Receive> y cada actividad <xref:System.ServiceModel.Activities.Receive> espera un mensaje concreto.</span><span class="sxs-lookup"><span data-stu-id="3c727-104">A workflow service contains one or more <xref:System.ServiceModel.Activities.Receive> activities and each <xref:System.ServiceModel.Activities.Receive> activity is expecting a specific message.</span></span> <span data-ttu-id="3c727-105">Sin garantías de entrega de transporte específicas, se pueden retrasar los mensajes enviados por los clientes y, por lo tanto, se pueden entregar en un orden que el servicio del flujo de trabajo no se espera.</span><span class="sxs-lookup"><span data-stu-id="3c727-105">Without particular transport delivery guarantees, messages sent by clients may be delayed and therefore delivered in an order the workflow service may not expect.</span></span> <span data-ttu-id="3c727-106">La implementación de un servicio del flujo de trabajo que no requiera que los mensajes se envíen en un orden concreto se suele llevar a cabo mediante una actividad paralela.</span><span class="sxs-lookup"><span data-stu-id="3c727-106">Implementing a workflow service that does not require messages be sent in a specific order is normally done using a Parallel activity.</span></span> <span data-ttu-id="3c727-107">Si el protocolo de aplicación es más complicado, el flujo de trabajo se volvería muy complejo con mucha rapidez.</span><span class="sxs-lookup"><span data-stu-id="3c727-107">For a more complicated application protocol, the workflow would become very complex very quickly.</span></span>  <span data-ttu-id="3c727-108">El mensaje desordenado de procesamiento de la característica de Windows Communication Foundation (WCF) le permite crear este flujo de trabajo sin toda la complejidad de las actividades paralelas anidadas.</span><span class="sxs-lookup"><span data-stu-id="3c727-108">The out-of-order message processing feature in Windows Communication Foundation (WCF) allows you to create such a workflow without all of the complexity of nested Parallel activities.</span></span> <span data-ttu-id="3c727-109">Procesamiento de mensajes de desordenado solo se admite en los canales que admiten <xref:System.ServiceModel.Channels.ReceiveContext> como los enlaces de MSMQ de WCF.</span><span class="sxs-lookup"><span data-stu-id="3c727-109">Out-of-order message processing is only supported on channels that support <xref:System.ServiceModel.Channels.ReceiveContext> such as the WCF MSMQ bindings.</span></span>  
  
## <a name="enabling-out-of-order-message-processing"></a><span data-ttu-id="3c727-110">Habilitar el procesamiento de mensajes desordenado</span><span class="sxs-lookup"><span data-stu-id="3c727-110">Enabling Out-Of-Order Message Processing</span></span>  
 <span data-ttu-id="3c727-111">El procesamiento de mensajes desordenado se habilita estableciendo la propiedad <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> en `true` en WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="3c727-111">Out-of-order message processing is enabled by setting the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property to `true` on the WorkflowService.</span></span> <span data-ttu-id="3c727-112">En el siguiente ejemplo, se muestra cómo establecer la propiedad <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> en código.</span><span class="sxs-lookup"><span data-stu-id="3c727-112">The following example shows how to set the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property in code.</span></span>  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
```  
  
 <span data-ttu-id="3c727-113">También puede aplicar el atributo `AllowBufferedReceive` a un servicio del flujo de trabajo en XAML, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3c727-113">You can also apply the `AllowBufferedReceive` attribute to a workflow service in XAML as shown in the following example.</span></span>  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!--the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c727-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c727-114">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ReceiveContext>  
 [<span data-ttu-id="3c727-115">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="3c727-115">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="3c727-116">Colas y sesiones de confianza</span><span class="sxs-lookup"><span data-stu-id="3c727-116">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
