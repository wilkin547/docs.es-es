---
title: Correlación dúplex duradera
ms.date: 03/30/2017
ms.assetid: 8eb0e49a-6d3b-4f7e-a054-0d4febee2ffb
ms.openlocfilehash: eb879c583b4454cd0062396d86e157a90db4652f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254238"
---
# <a name="durable-duplex-correlation"></a>Correlación dúplex duradera

La correlación dúplex duradera, también conocida como correlación de devolución de llamada, es útil cuando un servicio de flujo de trabajo tiene un requisito para enviar una devolución de llamada al autor de la llamada inicial. A diferencia del dúplex de WCF, la devolución de llamada puede producirse en cualquier momento en el futuro y no está vinculada a un mismo canal o a la duración del canal; el único requisito es que el autor de la llamada tenga un extremo activo que realice escuchas para el mensaje de devolución de llamada. Esto permite a dos servicios de flujo de trabajo comunicarse en una conversación de ejecución prolongada. En este tema, se proporciona información general sobre la correlación dúplex duradera.  
  
## <a name="using-durable-duplex-correlation"></a>Usar la correlación dúplex duradera  

 Para usar la correlación dúplex duradera, los dos servicios deben usar un enlace habilitado para el contexto que admita operaciones bidireccionales, como <xref:System.ServiceModel.NetTcpContextBinding> o <xref:System.ServiceModel.WSHttpContextBinding>. El servicio de llamada registra <xref:System.ServiceModel.WSHttpContextBinding.ClientCallbackAddress%2A> con el enlace deseado en <xref:System.ServiceModel.Endpoint> del cliente. El servicio de recepción recibe estos datos en la llamada inicial y, a continuación, los usa en su propia <xref:System.ServiceModel.Endpoint>, en la actividad <xref:System.ServiceModel.Activities.Send> que realiza la devolución de llamada al servicio de llamada. En este ejemplo, dos servicios se comunican entre sí. El primer servicio invoca un método en el segundo servicio y, a continuación, espera una respuesta. El segundo servicio conoce el nombre del método de devolución de llamada, pero no conoce el punto de conexión del servicio que implementa este método en tiempo de diseño.  
  
> [!NOTE]
> El dúplex duradero solo se puede usar cuando el objeto <xref:System.ServiceModel.Channels.AddressingVersion> del extremo se configura con la propiedad <xref:System.ServiceModel.Channels.AddressingVersion.WSAddressing10%2A>. Si no es así, <xref:System.InvalidOperationException> se produce una excepción con el siguiente mensaje: "el mensaje contiene un encabezado de contexto de devolución de llamada con una referencia de punto de conexión para [AddressingVersion](http://schemas.xmlsoap.org/ws/2004/08/addressing). El contexto de devolución de llamada solo se puede transmitir cuando AddressingVersion está configurado con ' WSAddressing10 '.
  
 En el siguiente ejemplo, se hospeda un servicio de flujo de trabajo que crea una <xref:System.ServiceModel.Endpoint> de devolución de llamada mediante <xref:System.ServiceModel.WSHttpContextBinding>.  
  
```csharp  
// Host WF Service 1.  
string baseAddress1 = "http://localhost:8080/Service1";  
WorkflowServiceHost host1 = new WorkflowServiceHost(GetWF1(), new Uri(baseAddress1));  
  
// Add the callback endpoint.  
WSHttpContextBinding Binding1 = new WSHttpContextBinding();  
host1.AddServiceEndpoint("ICallbackItemsReady", Binding1, "ItemsReady");  
  
// Add the service endpoint.  
host1.AddServiceEndpoint("IService1", Binding1, baseAddress1);  
  
// Open the first workflow service.  
host1.Open();  
Console.WriteLine("Service1 waiting at: {0}", baseAddress1);  
```  
  
 El flujo de trabajo que implementa este servicio de flujo de trabajo inicializa la correlación de devolución de llamada con su actividad <xref:System.ServiceModel.Activities.Send> y hace referencia a este punto de conexión de devolución de llamada de la actividad <xref:System.ServiceModel.Activities.Receive> que se relaciona con <xref:System.ServiceModel.Activities.Send>. En el siguiente ejemplo, se representa el flujo de trabajo que se devuelve del método `GetWF1`.  
  
```csharp  
Variable<CorrelationHandle> CallbackHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = "IService1",  
    OperationName = "StartOrder"  
};  
  
Send GetItems = new Send  
{  
    CorrelationInitializers =
    {  
        new CallbackCorrelationInitializer  
        {  
            CorrelationHandle = CallbackHandle  
        }  
    },  
    ServiceContractName = "IService2",  
    OperationName = "StartItems",  
    Endpoint = new Endpoint  
    {  
        AddressUri = new Uri("http://localhost:8081/Service2"),  
        Binding = new WSHttpContextBinding  
        {  
            ClientCallbackAddress = new Uri("http://localhost:8080/Service1/ItemsReady")
        }  
    }  
};  
  
Receive ItemsReady = new Receive  
{  
    ServiceContractName = "ICallbackItemsReady",  
    OperationName = "ItemsReady",  
    CorrelatesWith = CallbackHandle,  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        CallbackHandle  
    },  
    Activities =  
    {  
        StartOrder,  
        new WriteLine  
        {  
            Text = "WF1 - Started"  
        },  
        GetItems,  
        new WriteLine  
        {  
            Text = "WF1 - Request Submitted"  
        },  
        ItemsReady,  
        new WriteLine  
        {  
            Text = "WF1 - Items Received"  
        }  
     }  
};  
```  
  
 El segundo servicio de flujo de trabajo se hospeda mediante un enlace proporcionado por sistema, con un enlace basado en el contexto.  
  
```csharp  
// Host WF Service 2.  
string baseAddress2 = "http://localhost:8081/Service2";  
WorkflowServiceHost host2 = new WorkflowServiceHost(GetWF2(), new Uri(baseAddress2));  
  
// Add the service endpoint.  
WSHttpContextBinding Binding2 = new WSHttpContextBinding();  
host2.AddServiceEndpoint("IService2", Binding2, baseAddress2);  
  
// Open the second workflow service.  
host2.Open();  
Console.WriteLine("Service2 waiting at: {0}", baseAddress2);  
```  
  
 El flujo de trabajo que implementa este servicio de flujo de trabajo comienza con una actividad <xref:System.ServiceModel.Activities.Receive>. Esta actividad de recepción inicializa la correlación de devolución de llamada para este servicio, se retrasa durante un período de tiempo para simular un trabajo de ejecución prolongada y, a continuación, vuelve a llamar al primer servicio mediante el contexto de devolución de llamada que se pasó en la primera llamada al servicio. En el siguiente ejemplo, se representa el flujo de trabajo que se devuelve de una llamada a `GetWF2`. Tenga en cuenta que la actividad <xref:System.ServiceModel.Activities.Send> tiene una dirección de marcador de posición `http://www.contoso.com`; la dirección real usada en el tiempo de ejecución es la dirección de devolución de llamada proporcionada.  
  
```csharp  
Variable<CorrelationHandle> ItemsCallbackHandle = new Variable<CorrelationHandle>();  
  
Receive StartItems = new Receive  
{  
    CorrelationInitializers =
    {  
        new CallbackCorrelationInitializer  
        {  
            CorrelationHandle = ItemsCallbackHandle  
        }  
    },  
    CanCreateInstance = true,  
    ServiceContractName = "IService2",  
    OperationName = "StartItems"  
};  
  
Send ItemsReady = new Send  
{  
    CorrelatesWith = ItemsCallbackHandle,  
    Endpoint = new Endpoint  
    {  
        // The callback address on the binding is used  
        // instead of this placeholder address.  
        AddressUri = new Uri("http://www.contoso.com"),  
  
        Binding = new WSHttpContextBinding()  
    },  
    OperationName = "ItemsReady",  
    ServiceContractName = "ICallbackItemsReady"  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        ItemsCallbackHandle  
    },  
    Activities =  
    {  
        StartItems,  
        new WriteLine  
        {  
            Text = "WF2 - Request Received"  
        },  
        new Delay  
        {  
            Duration = TimeSpan.FromMinutes(90)  
        },  
        new WriteLine  
        {  
            Text = "WF2 - Sending items"  
        },  
        ItemsReady,  
        new WriteLine  
        {  
            Text = "WF2 - Items sent"  
        }  
     }  
};  
```  
  
 Cuando se invoca el método `StartOrder` en el primer flujo de trabajo, se muestra el siguiente resultado, que muestra el flujo de ejecución a través de los dos flujos de trabajo.  
  
```output  
Service1 waiting at: http://localhost:8080/Service1  
Service2 waiting at: http://localhost:8081/Service2  
Press enter to exit.
WF1 - Started  
WF2 - Request Received  
WF1 - Request Submitted  
WF2 - Sending items  
WF2 - Items sent  
WF1 - Items Received  
```  
  
 En este ejemplo, ambos flujos de trabajo administran explícitamente la correlación mediante una clase <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer>. Dado que solo hubo una correlación única en los flujos de trabajo de este ejemplo, la administración <xref:System.ServiceModel.Activities.CorrelationHandle> predeterminada habría sido suficiente.
