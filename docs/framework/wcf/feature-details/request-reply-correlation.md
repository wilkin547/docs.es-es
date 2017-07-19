---
title: "Correlaci&#243;n entre solicitud y respuesta | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cf4379bf-2d08-43f3-9584-dfa30ffcb1f6
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Correlaci&#243;n entre solicitud y respuesta
La correlación de solicitud\-respuesta se utiliza con un par <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply> para implementar una operación bidireccional en un servicio de flujo de trabajo y con un par <xref:System.ServiceModel.Activities.Send>\/<xref:System.ServiceModel.Activities.ReceiveReply> que invoca una operación bidireccional en otro servicio Web.  Al invocar una operación bidireccional en un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], el servicio puede ser un servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] imperativo tradicional basado en código, o puede ser un servicio de flujo de trabajo.  Para utilizar la correlación de solicitud\-respuesta, debe usarse un enlace bidireccional, como <xref:System.ServiceModel.BasicHttpBinding>.  Ya invoque o implemente una operación bidireccional, los pasos de inicialización de la correlación son similares y se cubren en esta sección.  
  
## Utilizar correlación en una operación bidireccional con Receive\/SendReply  
 Se usa un par <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply> para implementar una operación bidireccional en un servicio de flujo de trabajo.  El tiempo de ejecución usa una correlación de solicitud\-respuesta para asegurarse de que la respuesta se envía al autor de la llamada correcto.  Cuando un flujo de trabajo se hospeda mediante <xref:System.ServiceModel.Activities.WorkflowServiceHost>, como es el caso de los servicios de flujo de trabajo, es suficiente la inicialización de correlación predeterminada.  En este escenario, se usa un par <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply> y no se requiere ninguna configuración de correlación concreta.  
  
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
  
### Inicializar explícitamente una correlación de solicitud\-respuesta  
 Si se producen otras operaciones bidireccionales en paralelo, la correlación se debería configurar de forma explícita.  Esto se puede hacer especificando <xref:System.ServiceModel.Activities.CorrelationHandle> y <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>, o colocando <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply> dentro de <xref:System.ServiceModel.Activities.CorrelationScope>.  En este ejemplo, la correlación de solicitud\-respuesta se configura en un par <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply>.  
  
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
  
 En lugar de configurar explícitamente la correlación, se puede usar una actividad <xref:System.ServiceModel.Activities.CorrelationScope>.  <xref:System.ServiceModel.Activities.CorrelationScope> proporciona un <xref:System.ServiceModel.Activities.CorrelationHandle> implícito para las actividades de mensajería que contiene.  En este ejemplo, se incluye un par <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply> dentro de <xref:System.ServiceModel.Activities.CorrelationScope>.  No se requiere ninguna configuración de correlación explícita.  
  
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
  
## Utilizar correlación en una operación bidireccional con Send\/ReceiveReply  
 Aunque la actividad <xref:System.ServiceModel.Activities.Receive> solo se puede utilizar en un servicio de flujo de trabajo hospedado por <xref:System.ServiceModel.Activities.WorkflowServiceHost>, se puede usar <xref:System.ServiceModel.Activities.Send> y el par <xref:System.ServiceModel.Activities.Send>\/<xref:System.ServiceModel.Activities.ReceiveReply> en cualquier flujo de trabajo que deba invocar un método en un servicio Web.  Si el flujo de trabajo se hospeda utilizando <xref:System.ServiceModel.Activities.WorkflowServiceHost>, se aplica la correlación predeterminada descrita en la sección anterior; si no es así, hay que configurar la correlación utilizando explícitamente las clases <xref:System.ServiceModel.Activities.CorrelationInitializer> y <xref:System.ServiceModel.Activities.CorrelationHandle> deseadas, o utilizando la administración de control implícita de <xref:System.ServiceModel.Activities.CorrelationScope>.  
  
 Al utilizar **Agregar referencia de servicio** en un servicio con operaciones bidireccionales, se generan actividades que ajustan internamente una actividad del par <xref:System.ServiceModel.Activities.Send>\/<xref:System.ServiceModel.Activities.ReceiveReply> con la correlación solicitud\-respuesta especificada explícitamente.