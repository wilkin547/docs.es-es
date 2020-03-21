---
title: Correlación entre solicitud y respuesta
ms.date: 03/30/2017
ms.assetid: cf4379bf-2d08-43f3-9584-dfa30ffcb1f6
ms.openlocfilehash: 34a41a149e740faf0f3816bba2c9bd9b47d4996e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184546"
---
# <a name="request-reply-correlation"></a>Correlación entre solicitud y respuesta
La correlación solicitud-respuesta <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> se usa con un par para implementar <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> una operación bidireccional en un servicio de flujo de trabajo y con un par que invoca una operación bidireccional en otro servicio web. Al invocar una operación bidireccional en un servicio WCF, el servicio puede ser un servicio tradicional de Windows Communication Foundation (WCF) basado en código imperativo o puede ser un servicio de flujo de trabajo. Para utilizar la correlación de solicitud-respuesta, debe usarse un enlace bidireccional, como <xref:System.ServiceModel.BasicHttpBinding>. Ya invoque o implemente una operación bidireccional, los pasos de inicialización de la correlación son similares y se cubren en esta sección.  
  
## <a name="using-correlation-in-a-two-way-operation-with-receivesendreply"></a>Utilizar correlación en una operación bidireccional con Receive/SendReply  
 <xref:System.ServiceModel.Activities.Receive> / Un <xref:System.ServiceModel.Activities.SendReply> par se usa para implementar una operación bidireccional en un servicio de flujo de trabajo. El tiempo de ejecución usa una correlación de solicitud-respuesta para asegurarse de que la respuesta se envía al autor de la llamada correcto. Cuando un flujo de trabajo se hospeda mediante <xref:System.ServiceModel.Activities.WorkflowServiceHost>, como es el caso de los servicios de flujo de trabajo, es suficiente la inicialización de correlación predeterminada. En este escenario, un flujo de trabajo utiliza un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par y no se requiere ninguna configuración de correlación específica.  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
### <a name="explicitly-initializing-request-reply-correlation"></a>Inicializar explícitamente una correlación de solicitud-respuesta  
 Si se producen otras operaciones bidireccionales en paralelo, la correlación se debería configurar de forma explícita. Esto se puede hacer <xref:System.ServiceModel.Activities.CorrelationHandle> especificando <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>a y <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> , <xref:System.ServiceModel.Activities.CorrelationScope>o colocando el interior de un archivo . En este ejemplo, la correlación <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> solicitud-respuesta se configura en un par.  
  
```csharp  
Variable<CorrelationHandle> RRHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder",  
    CorrelationInitializers =  
    {  
        new RequestReplyCorrelationInitializer  
        {  
            CorrelationHandle = RRHandle  
        }  
    }  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
 En lugar de configurar explícitamente la correlación, se puede usar una actividad <xref:System.ServiceModel.Activities.CorrelationScope>. <xref:System.ServiceModel.Activities.CorrelationScope> proporciona un <xref:System.ServiceModel.Activities.CorrelationHandle> implícito para las actividades de mensajería que contiene. En este ejemplo, un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par <xref:System.ServiceModel.Activities.CorrelationScope>se encuentra dentro de un archivo . No se requiere ninguna configuración de correlación explícita.  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
CorrelationScope s = new CorrelationScope  
{  
    Body = new Sequence  
    {  
        Activities =
        {  
            StartOrder,  
            // Activities that create the reply.  
            ReplyToStartOrder  
        }  
    }  
};  
  
// Construct a workflow using the CorrelationScope.  
```  
  
 Si se requieren correlaciones adicionales, se pueden configurar mediante la propiedad <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> de las actividades de mensajería respectivas utilizando los tipos `CorrelationInitializer` deseados.  
  
## <a name="using-correlation-in-a-two-way-operation-with-sendreceivereply"></a>Utilizar correlación en una operación bidireccional con Send/ReceiveReply  
 Aunque <xref:System.ServiceModel.Activities.Receive> la actividad solo se puede usar <xref:System.ServiceModel.Activities.WorkflowServiceHost> <xref:System.ServiceModel.Activities.Send> en <xref:System.ServiceModel.Activities.Send> / un servicio de flujo de trabajo hospedado por , y el <xref:System.ServiceModel.Activities.ReceiveReply> par se puede usar en cualquier flujo de trabajo que debe invocar un método en un servicio web. Si el flujo de trabajo se hospeda utilizando <xref:System.ServiceModel.Activities.WorkflowServiceHost>, se aplica la correlación predeterminada descrita en la sección anterior; si no es así, hay que configurar la correlación utilizando explícitamente las clases <xref:System.ServiceModel.Activities.CorrelationInitializer> y <xref:System.ServiceModel.Activities.CorrelationHandle> deseadas, o utilizando la administración de control implícita de <xref:System.ServiceModel.Activities.CorrelationScope>.  
  
 Cuando se usa **Agregar referencia** de servicio en un servicio con <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> operaciones bidireccionales, se generan actividades que ajustan una actividad de par internamente con la correlación Solicitud/Respuesta especificada explícitamente.
