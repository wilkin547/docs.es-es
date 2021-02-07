---
description: 'Más información sobre: procesamiento de mensajes desordenados'
title: Procesar un mensaje sin orden
ms.date: 03/30/2017
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
ms.openlocfilehash: 4349b7d72c080dff579eda18ce51de99ab5e91fb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733611"
---
# <a name="out-of-order-message-processing"></a><span data-ttu-id="0f514-103">Procesar un mensaje sin orden</span><span class="sxs-lookup"><span data-stu-id="0f514-103">Out-of-Order Message Processing</span></span>

<span data-ttu-id="0f514-104">Los servicios del flujo de trabajo pueden depender de mensajes enviados en un orden concreto.</span><span class="sxs-lookup"><span data-stu-id="0f514-104">Workflow services may depend on messages being sent in a specific order.</span></span> <span data-ttu-id="0f514-105">Un servicio del flujo de trabajo contiene una o más actividades <xref:System.ServiceModel.Activities.Receive> y cada actividad <xref:System.ServiceModel.Activities.Receive> espera un mensaje concreto.</span><span class="sxs-lookup"><span data-stu-id="0f514-105">A workflow service contains one or more <xref:System.ServiceModel.Activities.Receive> activities and each <xref:System.ServiceModel.Activities.Receive> activity is expecting a specific message.</span></span> <span data-ttu-id="0f514-106">Sin garantías de entrega de transporte específicas, se pueden retrasar los mensajes enviados por los clientes y, por lo tanto, se pueden entregar en un orden que el servicio del flujo de trabajo no se espera.</span><span class="sxs-lookup"><span data-stu-id="0f514-106">Without particular transport delivery guarantees, messages sent by clients may be delayed and therefore delivered in an order the workflow service may not expect.</span></span> <span data-ttu-id="0f514-107">La implementación de un servicio del flujo de trabajo que no requiera que los mensajes se envíen en un orden concreto se suele llevar a cabo mediante una actividad paralela.</span><span class="sxs-lookup"><span data-stu-id="0f514-107">Implementing a workflow service that does not require messages be sent in a specific order is normally done using a Parallel activity.</span></span> <span data-ttu-id="0f514-108">Si el protocolo de aplicación es más complicado, el flujo de trabajo se volvería muy complejo con mucha rapidez.</span><span class="sxs-lookup"><span data-stu-id="0f514-108">For a more complicated application protocol, the workflow would become very complex very quickly.</span></span>  <span data-ttu-id="0f514-109">La característica de procesamiento de mensajes desordenados en Windows Communication Foundation (WCF) le permite crear este tipo de flujo de trabajo sin la complejidad de las actividades paralelas anidadas.</span><span class="sxs-lookup"><span data-stu-id="0f514-109">The out-of-order message processing feature in Windows Communication Foundation (WCF) allows you to create such a workflow without all of the complexity of nested Parallel activities.</span></span> <span data-ttu-id="0f514-110">El procesamiento de mensajes desordenados solo se admite en los canales que admiten <xref:System.ServiceModel.Channels.ReceiveContext> , como los enlaces MSMQ de WCF.</span><span class="sxs-lookup"><span data-stu-id="0f514-110">Out-of-order message processing is only supported on channels that support <xref:System.ServiceModel.Channels.ReceiveContext> such as the WCF MSMQ bindings.</span></span>  
  
## <a name="enabling-out-of-order-message-processing"></a><span data-ttu-id="0f514-111">Habilitar el procesamiento de mensajes desordenado</span><span class="sxs-lookup"><span data-stu-id="0f514-111">Enabling Out-Of-Order Message Processing</span></span>  

 <span data-ttu-id="0f514-112">El procesamiento de mensajes desordenado se habilita estableciendo la propiedad <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> en `true` en WorkflowService.</span><span class="sxs-lookup"><span data-stu-id="0f514-112">Out-of-order message processing is enabled by setting the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property to `true` on the WorkflowService.</span></span> <span data-ttu-id="0f514-113">En el siguiente ejemplo, se muestra cómo establecer la propiedad <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> en código.</span><span class="sxs-lookup"><span data-stu-id="0f514-113">The following example shows how to set the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property in code.</span></span>  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
```  
  
 <span data-ttu-id="0f514-114">También puede aplicar el atributo `AllowBufferedReceive` a un servicio del flujo de trabajo en XAML, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0f514-114">You can also apply the `AllowBufferedReceive` attribute to a workflow service in XAML as shown in the following example.</span></span>  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!--the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f514-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f514-115">See also</span></span>

- <xref:System.ServiceModel.Channels.ReceiveContext>
- [<span data-ttu-id="0f514-116">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="0f514-116">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="0f514-117">Colas y sesiones de confianza</span><span class="sxs-lookup"><span data-stu-id="0f514-117">Queues and Reliable Sessions</span></span>](queues-and-reliable-sessions.md)
