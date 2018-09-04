---
title: Correlación de intercambio de contexto
ms.date: 03/30/2017
ms.assetid: 1e2852be-3601-45ae-b507-ccc465d45c60
ms.openlocfilehash: d9de111fa08b4a398bba52bc903ea1fec8c7f298
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43519737"
---
# <a name="context-exchange-correlation"></a>Correlación de intercambio de contexto
Correlación de contexto se basa en el mecanismo de intercambio de contexto descrito en la [especificación de protocolo de intercambio de contexto de .NET](https://go.microsoft.com/fwlink/?LinkId=166059). La correlación del contexto utiliza una cookie o un encabezado de contexto conocidos para relacionar los mensajes con la instancia correcta. Para utilizar la correlación del contexto, debe usarse un enlace basado en contexto como <xref:System.ServiceModel.BasicHttpContextBinding>, <xref:System.ServiceModel.WSHttpContextBinding> o <xref:System.ServiceModel.NetTcpContextBinding> en el extremo de <xref:System.ServiceModel.Activities.WorkflowServiceHost>. En este tema, se explica cómo utilizar la correlación del contexto con actividades de mensajería en un servicio del flujo de trabajo.  
  
## <a name="using-context-correlation"></a>Usar correlación del contexto  
 Se utiliza la correlación del contexto cuando un cliente debe realizar llamadas repetidas en un servicio del flujo de trabajo y el servicio se hospeda mediante uno de los enlaces del contexto. Este tipo de correlación se inicializa mediante un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par en el servicio de flujo de trabajo. El contexto se devuelve al cliente junto con la respuesta y, a continuación, el cliente adjunta dicho contexto en las llamadas al servicio posteriores.  
  
### <a name="configuring-context-correlation-in-a-workflow-service"></a>Configurar la correlación del contexto en un servicio del flujo de trabajo  
 La correlación del contexto se inicializa mediante una clase <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>, que está asociada a la actividad <xref:System.ServiceModel.Activities.SendReply> que responde al mensaje entrante inicial. En el siguiente ejemplo, la clase <xref:System.ServiceModel.Activities.SendReply> se configura para inicializar una correlación del contexto.  
  
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
>  En este ejemplo se usan realmente dos tipos de correlación: la de contexto y la de solicitud-respuesta. La correlación de contexto se usa para que las llamadas de los clientes se enruten a la instancia correcta. La correlación de solicitud-respuesta se usa en las actividades de <xref:System.ServiceModel.Activities.Receive> y de <xref:System.ServiceModel.Activities.SendReply> conjuntamente para implementar la operación bidireccional modelada por estas actividades. En este ejemplo, solo la correlación del contexto se configura explícitamente y el <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par es mediante la correlación de solicitud-respuesta predeterminada proporcionada por implícito <xref:System.ServiceModel.Activities.CorrelationHandle> administración de <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Cuando se usa el **ReceiveAndSendReply** plantilla de actividad en el diseñador, la correlación de solicitud-respuesta flujo de trabajo se configura explícitamente. Para obtener más información sobre la correlación de solicitud-respuesta y administración de identificador de correlación implícita, vea [solicitud-respuesta](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md) y [información general de correlación](../../../../docs/framework/wcf/feature-details/correlation-overview.md). Para obtener más información sobre la **ReceiveAndSendReply** plantilla de actividad, consulte [ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer).  
  
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
  contract="IOrderContract"  
  binding = "basicHttpContextBinding"  
  address="http://localhost:8080/OrderService" />  
```  
  
### <a name="configuring-context-correlation-in-a-workflow-client"></a>Configurar la correlación del contexto en un cliente del flujo de trabajo  
 Cuando el cliente es otro flujo de trabajo, la correlación del contexto también se debe configurar en el cliente. En el flujo de trabajo cliente, el <xref:System.ServiceModel.Activities.ReceiveReply> de la <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> par que realiza la llamada inicial al servicio de flujo de trabajo debe configurarse con un <xref:System.ServiceModel.Activities.ContextCorrelationInitializer>.  
  
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
  
 Tenga en cuenta que, en estos ejemplos, la correlación del contexto se ha configurado explícitamente. Si el flujo de trabajo del cliente no se hospeda también en <xref:System.ServiceModel.Activities.WorkflowServiceHost>, se debe configurar la correlación explícitamente, a menos que las actividades se incluyan en una actividad <xref:System.ServiceModel.Activities.CorrelationScope>. Para obtener más información sobre la correlación de contexto, vea el [NetContextExchangeCorrelation](https://msdn.microsoft.com/library/93c74a1a-b9e2-46c6-95c0-c9b0e9472caf) ejemplo.  
  
 Si el cliente que está realizando las llamadas al servicio del flujo de trabajo no es un flujo de trabajo, seguirá pudiendo realizar las llamadas repetidas, siempre y cuando pase explícitamente el contexto devuelto de la primera llamada al servicio del flujo de trabajo. Los servidores proxy generados mediante la adición de una referencia del servicio en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] almacenan y pasan este contexto de forma predeterminada.
