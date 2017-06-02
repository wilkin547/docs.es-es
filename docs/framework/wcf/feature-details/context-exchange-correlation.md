---
title: "Correlaci&#243;n de intercambio de contexto | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1e2852be-3601-45ae-b507-ccc465d45c60
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Correlaci&#243;n de intercambio de contexto
La correlación del contexto está basada en el mecanismo de intercambio de contexto descrito en la [especificación del protocolo de intercambio de contexto de .NET](http://go.microsoft.com/fwlink/?LinkId=166059).La correlación del contexto utiliza una cookie o un encabezado de contexto conocidos para relacionar los mensajes con la instancia correcta.Para utilizar la correlación del contexto, debe usarse un enlace basado en contexto como <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> o <xref:System.ServiceModel.NetTcpContextBinding> en el extremo de <xref:System.ServiceModel.Activities.WorkflowServiceHost>.En este tema, se explica cómo utilizar la correlación del contexto con actividades de mensajería en un servicio del flujo de trabajo.  
  
## Usar correlación del contexto  
 Se utiliza la correlación del contexto cuando un cliente debe realizar llamadas repetidas en un servicio del flujo de trabajo y el servicio se hospeda mediante uno de los enlaces del contexto.Este tipo de correlación se inicializa mediante un par <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply> en el servicio del flujo de trabajo.El contexto se devuelve al cliente junto con la respuesta y, a continuación, el cliente adjunta dicho contexto en las llamadas al servicio posteriores.  
  
### Configurar la correlación del contexto en un servicio del flujo de trabajo  
 La correlación del contexto se inicializa mediante una clase <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>, que está asociada a la actividad <xref:System.ServiceModel.Activities.SendReply> que responde al mensaje entrante inicial.En el siguiente ejemplo, la clase <xref:System.ServiceModel.Activities.SendReply> se configura para inicializar una correlación del contexto.  
  
```csharp  
Variable<string> Item = new Variable<string>();  
Variable<CorrelationHandle> OrderHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = "IOrderService",  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    CorrelationInitializers =  
    {  
        new ContextCorrelationInitializer  
        {  
            CorrelationHandle = OrderHandle  
        }  
    }  
};  
```  
  
> [!NOTE]
>  En este ejemplo se usan realmente dos tipos de correlación: la de contexto y la de solicitud\-respuesta.La correlación de contexto se usa para que las llamadas de los clientes se enruten a la instancia correcta.La correlación de solicitud\-respuesta se usa en las actividades de <xref:System.ServiceModel.Activities.Receive> y de <xref:System.ServiceModel.Activities.SendReply> conjuntamente para implementar la operación bidireccional modelada por estas actividades.En este ejemplo, solo la correlación de contexto se configura de modo explícito y el par <xref:System.ServiceModel.Activities.Receive>\/<xref:System.ServiceModel.Activities.SendReply> usa la correlación de solicitud\-respuesta predeterminada ofrecida por la administración <xref:System.ServiceModel.Activities.CorrelationHandle> implícita de <xref:System.ServiceModel.Activities.WorkflowServiceHost>.Cuando se usa la plantilla de actividad **ReceiveAndSendReply** en el diseñador de flujo de trabajo, la correlación de solicitud\-respuesta se configura explícitamente.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] la correlación de solicitud\-respuesta y la administración implícita del identificador de correlación, vea [Solicitud\-respuesta](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md) y [Información general de correlación](../../../../docs/framework/wcf/feature-details/correlation-overview.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] la plantilla de actividad **ReceiveAndSendReply**, vea [ReceiveAndSendReply](../Topic/ReceiveAndSendReply%20Template%20Designer.md).  
  
 Las actividades de <xref:System.ServiceModel.Activities.Receive> subsiguientes en el servicio del flujo de trabajo pueden hacer referencia a la clase <xref:System.ServiceModel.Activities.CorrelationHandle> inicializada por <xref:System.ServiceModel.Activities.SendReply> en el ejemplo anterior.  
  
```csharp  
Receive AddItem = new Receive  
{  
    ServiceContractName = "IOrderService",  
    OperationName = "AddItem",  
    CorrelatesWith = OrderHandle  
};  
```  
  
 A continuación, el extremo se configura en <xref:System.ServiceModel.Activities.WorkflowServiceHost> para utilizar un enlace basado en el contexto, como <xref:System.ServiceModel.BasicHttpContextBinding>.  
  
```xml  
<endpoint  
  contract=”IOrderContract”  
  binding = “basicHttpContextBinding”  
  address=”http://localhost:8080/OrderService” />  
```  
  
### Configurar la correlación del contexto en un cliente del flujo de trabajo  
 Cuando el cliente es otro flujo de trabajo, la correlación del contexto también se debe configurar en el cliente.En el flujo de trabajo del cliente, la clase <xref:System.ServiceModel.Activities.ReceiveReply> del par <xref:System.ServiceModel.Activities.Send>\/<xref:System.ServiceModel.Activities.ReceiveReply> que realiza la llamada inicial al servicio del flujo de trabajo se debe configurar con una clase <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>.  
  
```csharp  
Variable<CorrelationHandle> cchandle = new Variable<CorrelationHandle>();  
Send request = new Send  
{  
    // Activity configuration omitted.  
};  
  
ReceiveReply reply = new ReceiveReply  
{  
    Request = request,  
    CorrelationInitializers =   
    {  
        new ContextCorrelationInitializer  
        {  
            CorrelationHandle = cchandle  
        }  
    }  
};  
```  
  
 Una vez inicializada la correlación, las actividades <xref:System.ServiceModel.Activities.Send> subsiguientes pueden utilizar <xref:System.ServiceModel.Activities.CorrelationHandle> para invocar métodos en la misma instancia de servicio.  
  
```csharp  
Send request2 = new Send  
{  
    CorrelatesWith = cchandle,  
    // Remaining activity configuration omitted.  
};  
```  
  
 Tenga en cuenta que, en estos ejemplos, la correlación del contexto se ha configurado explícitamente.Si el flujo de trabajo del cliente no se hospeda también en <xref:System.ServiceModel.Activities.WorkflowServiceHost>, se debe configurar la correlación explícitamente, a menos que las actividades se incluyan en una actividad <xref:System.ServiceModel.Activities.CorrelationScope>.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] la correlación de contexto, vea el ejemplo de [NetContextExchangeCorrelation](http://msdn.microsoft.com/es-es/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf).  
  
 Si el cliente que está realizando las llamadas al servicio del flujo de trabajo no es un flujo de trabajo, seguirá pudiendo realizar las llamadas repetidas, siempre y cuando pase explícitamente el contexto devuelto de la primera llamada al servicio del flujo de trabajo.Los servidores proxy generados mediante la adición de una referencia del servicio en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] almacenan y pasan este contexto de forma predeterminada.