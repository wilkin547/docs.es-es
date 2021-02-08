---
description: 'Más información acerca de cómo: crear un servicio WCF que se comunique a través de WebSockets'
title: Procedimiento para crear un servicio WCF que se comunique a través de WebSockets
ms.date: 03/30/2017
ms.assetid: bafbbd89-eab8-4e9a-b4c3-b7b0178e12d8
ms.openlocfilehash: b2d755080f982c575f18269b3d103301aa7317e2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802923"
---
# <a name="how-to-create-a-wcf-service-that-communicates-over-websockets"></a><span data-ttu-id="9af68-103">Procedimiento para crear un servicio WCF que se comunique a través de WebSockets</span><span class="sxs-lookup"><span data-stu-id="9af68-103">How to: Create a WCF Service that Communicates over WebSockets</span></span>

<span data-ttu-id="9af68-104">Los servicios y los clientes de WCF pueden usar el enlace <xref:System.ServiceModel.NetHttpBinding> para comunicarse sobre WebSockets.</span><span class="sxs-lookup"><span data-stu-id="9af68-104">WCF services and clients can use the <xref:System.ServiceModel.NetHttpBinding> binding to communicate over WebSockets.</span></span>  <span data-ttu-id="9af68-105">WebSockets se usará cuando <xref:System.ServiceModel.NetHttpBinding> determine que el contrato de servicio define un contrato de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="9af68-105">WebSockets will be used when the <xref:System.ServiceModel.NetHttpBinding> determines the service contract defines a callback contract.</span></span> <span data-ttu-id="9af68-106">En este tema se describe cómo implementar un servicio de WCF y un cliente que use <xref:System.ServiceModel.NetHttpBinding> para comunicarse sobre WebSockets.</span><span class="sxs-lookup"><span data-stu-id="9af68-106">This topic describes how to implement a WCF service and client that uses the <xref:System.ServiceModel.NetHttpBinding> to communicate over WebSockets.</span></span>  
  
### <a name="define-the-service"></a><span data-ttu-id="9af68-107">Definir el servicio</span><span class="sxs-lookup"><span data-stu-id="9af68-107">Define the Service</span></span>  
  
1. <span data-ttu-id="9af68-108">Definir un contrato de devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="9af68-108">Define a callback contract</span></span>  
  
    ```csharp  
    [ServiceContract]  
        public interface IStockQuoteCallback  
        {  
            [OperationContract(IsOneWay = true)]  
            Task SendQuote(string code, double value);  
        }  
    ```  
  
     <span data-ttu-id="9af68-109">La aplicación cliente implementará este contrato para permitir que el servicio devuelva mensajes al cliente.</span><span class="sxs-lookup"><span data-stu-id="9af68-109">This contract will be implemented by the client application to allow the service to send messages back to the client.</span></span>  
  
2. <span data-ttu-id="9af68-110">Defina el contrato de servicio y especifique la interfaz `IStockQuoteCallback` como contrato de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="9af68-110">Define the service contract and specify the `IStockQuoteCallback` interface as the callback contract.</span></span>  
  
    ```csharp  
    [ServiceContract(CallbackContract = typeof(IStockQuoteCallback))]  
        public interface IStockQuoteService  
        {  
            [OperationContract(IsOneWay = true)]  
            Task StartSendingQuotes();  
        }  
    ```  
  
3. <span data-ttu-id="9af68-111">Implemente el contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="9af68-111">Implement the service contract.</span></span>  
  
    ```csharp
    public class StockQuoteService : IStockQuoteService  
    {  
        public async Task StartSendingQuotes()  
        {  
            var callback = OperationContext.Current.GetCallbackChannel<IStockQuoteCallback>();  
            var random = new Random();  
            double price = 29.00;  

            while (((IChannel)callback).State == CommunicationState.Opened)  
            {  
                await callback.SendQuote("MSFT", price);  
                price += random.NextDouble();  
                await Task.Delay(1000);  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="9af68-112">La operación de servicio `StartSendingQuotes` se implementa como una llamada asincrónica.</span><span class="sxs-lookup"><span data-stu-id="9af68-112">The service operation `StartSendingQuotes` is implemented as an asynchronous call.</span></span> <span data-ttu-id="9af68-113">Recuperamos el canal de devolución de llamada mediante `OperationContext` y si el canal está abierto, hacemos una llamada asincrónica en el canal de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="9af68-113">We retrieve the callback channel using the `OperationContext` and if the channel is open, we make an async call on the callback channel.</span></span>  
  
4. <span data-ttu-id="9af68-114">Configuración del servicio</span><span class="sxs-lookup"><span data-stu-id="9af68-114">Configure the service</span></span>  
  
    ```xml  
    <configuration>  
        <appSettings>  
          <add key="aspnet:UseTaskFriendlySynchronizationContext" value="true" />
        </appSettings>  
        <system.web>  
          <compilation debug="true" targetFramework="4.5" />
        </system.web>  
        <system.serviceModel>  
            <protocolMapping>  
              <add scheme="http" binding="netHttpBinding"/>  
              <add scheme="https" binding="netHttpsBinding"/>  
            </protocolMapping>  
            <behaviors>  
                <serviceBehaviors>  
                    <behavior name="">  
                        <serviceMetadata httpGetEnabled="true" httpsGetEnabled="true" />  
                        <serviceDebug includeExceptionDetailInFaults="false" />  
                    </behavior>  
                </serviceBehaviors>  
            </behaviors>  
            <serviceHostingEnvironment aspNetCompatibilityEnabled="true"  
                multipleSiteBindingsEnabled="true" />  
        </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="9af68-115">El archivo de configuración del servicio se basa en los puntos de conexión predeterminados de WCF.</span><span class="sxs-lookup"><span data-stu-id="9af68-115">The service’s configuration file relies on WCF’s default endpoints.</span></span> <span data-ttu-id="9af68-116">La sección `<protocolMapping>` se usa para especificar que `NetHttpBinding` se debe usar para los puntos de conexión predeterminados creados.</span><span class="sxs-lookup"><span data-stu-id="9af68-116">The `<protocolMapping>` section is used to specify that the `NetHttpBinding` should be used for the default endpoints created.</span></span>  
  
### <a name="define-the-client"></a><span data-ttu-id="9af68-117">Definir el cliente</span><span class="sxs-lookup"><span data-stu-id="9af68-117">Define the Client</span></span>  
  
1. <span data-ttu-id="9af68-118">Implemente el contrato de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="9af68-118">Implement the callback contract.</span></span>  
  
    ```csharp  
    private class CallbackHandler : StockQuoteServiceReference.IStockQuoteServiceCallback  
            {  
                public async Task SendQuoteAsync(string code, double value)  
                {  
                    Console.WriteLine("{0}: {1:f2}", code, value);  
                }  
            }  
    ```  
  
     <span data-ttu-id="9af68-119">La operación de contrato de devolución de llamada se implementa como un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="9af68-119">The callback contract operation is implemented as an asynchronous method.</span></span>  
  
    1. <span data-ttu-id="9af68-120">Implemente el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="9af68-120">Implement the client code.</span></span>  
  
        ```csharp  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                var context = new InstanceContext(new CallbackHandler());  
                var client = new StockQuoteServiceReference.StockQuoteServiceClient(context);  
                client.StartSendingQuotes();
                Console.ReadLine();  
            }  
  
            private class CallbackHandler : StockQuoteServiceReference.IStockQuoteServiceCallback  
            {  
                public async Task SendQuoteAsync(string code, double value)  
                {  
                    Console.WriteLine("{0}: {1:f2}", code, value);  
                }  
            }  
        }  
        ```  
  
         <span data-ttu-id="9af68-121">El CallbackHandler se repite aquí para mayor claridad.</span><span class="sxs-lookup"><span data-stu-id="9af68-121">The CallbackHandler is repeated here for clarity.</span></span> <span data-ttu-id="9af68-122">La aplicación cliente crea un nuevo InstanceContext y especifica la implementación de la interfaz de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="9af68-122">The client application creates a new InstanceContext and specifies the implementation of the callback interface.</span></span> <span data-ttu-id="9af68-123">Después crea una instancia de la clase de proxy que envía una referencia al InstanceContext recién creado.</span><span class="sxs-lookup"><span data-stu-id="9af68-123">Next it creates an instance of the proxy class sending a reference to the newly created InstanceContext.</span></span> <span data-ttu-id="9af68-124">Cuando el cliente llama al servicio, el servicio llamará al cliente usando el contrato de devolución de llamada especificado.</span><span class="sxs-lookup"><span data-stu-id="9af68-124">When the client calls the service, the service will call the client using the callback contract specified.</span></span>  
  
    2. <span data-ttu-id="9af68-125">Configurar el cliente</span><span class="sxs-lookup"><span data-stu-id="9af68-125">Configure the client</span></span>  
  
        ```xml  
        <?xml version="1.0" encoding="utf-8" ?>  
        <configuration>  
            <startup>
                <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />  
            </startup>  
            <system.serviceModel>  
                <bindings>  
                    <netHttpBinding>  
                        <binding name="NetHttpBinding_IStockQuoteService">  
                            <webSocketSettings transportUsage="Always" />  
                        </binding>  
                    </netHttpBinding>  
                </bindings>  
                <client>  
                    <endpoint address="ws://localhost/NetHttpSampleServer/StockQuoteService.svc"  
                        binding="netHttpBinding" bindingConfiguration="NetHttpBinding_IStockQuoteService"  
                        contract="StockQuoteServiceReference.IStockQuoteService" name="NetHttpBinding_IStockQuoteService" />  
                </client>  
            </system.serviceModel>  
        </configuration>  
        ```  
  
         <span data-ttu-id="9af68-126">No es necesario hacer nada especial en la configuración de cliente, simplemente especificar el extremo del lado cliente mediante `NetHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="9af68-126">There is nothing special you need to do in the client configuration, just specify the client side endpoint using the `NetHttpBinding`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9af68-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9af68-127">Example</span></span>  

 <span data-ttu-id="9af68-128">A continuación, se muestra el código completo que se emplea en este tema.</span><span class="sxs-lookup"><span data-stu-id="9af68-128">The following is the complete code used in this topic.</span></span>  
  
```csharp  
// IStockQuoteService.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
using System.Threading.Tasks;  
  
namespace Server  
{  
    [ServiceContract(CallbackContract = typeof(IStockQuoteCallback))]  
    public interface IStockQuoteService  
    {  
        [OperationContract(IsOneWay = true)]  
        Task StartSendingQuotes();  
    }  
  
    [ServiceContract]  
    public interface IStockQuoteCallback  
    {  
        [OperationContract(IsOneWay = true)]  
        Task SendQuote(string code, double value);  
    }  
}  
```  
  
```csharp
// StockQuoteService.svc.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
using System.Text;  
using System.Threading.Tasks;  
  
namespace Server  
{  
    public class StockQuoteService : IStockQuoteService  
    {  
        public async Task StartSendingQuotes()  
        {  
            var callback = OperationContext.Current.GetCallbackChannel<IStockQuoteCallback>();  
            var random = new Random();  
            double price = 29.00;  
  
            while (((IChannel)callback).State == CommunicationState.Opened)  
            {  
                await callback.SendQuote("MSFT", price);  
                price += random.NextDouble();  
                await Task.Delay(1000);  
            }  
        }  
    }  
}  
```  
  
```xml  
<?xml version="1.0"?>  
  
<!--  
  For more information on how to configure your ASP.NET application, please visit  
  https://go.microsoft.com/fwlink/?LinkId=169433  
  -->  
  
<configuration>  
    <appSettings>  
      <add key="aspnet:UseTaskFriendlySynchronizationContext" value="true" />
    </appSettings>  
    <system.web>  
      <compilation debug="true" targetFramework="4.5" />
    </system.web>  
    <system.serviceModel>  
        <protocolMapping>  
          <add scheme="http" binding="netHttpBinding"/>  
          <add scheme="https" binding="netHttpsBinding"/>  
        </protocolMapping>  
        <behaviors>  
            <serviceBehaviors>  
                <behavior name="">  
                    <serviceMetadata httpGetEnabled="true" httpsGetEnabled="true" />  
                    <serviceDebug includeExceptionDetailInFaults="false" />  
                </behavior>  
            </serviceBehaviors>  
        </behaviors>  
        <serviceHostingEnvironment aspNetCompatibilityEnabled="true"  
            multipleSiteBindingsEnabled="true" />  
    </system.serviceModel>  
</configuration>  
```  
  
```aspx-csharp
<!-- StockQuoteService.svc -->  
<%@ ServiceHost Language="C#" Debug="true" Service="Server.StockQuoteService" CodeBehind="StockQuoteService.svc.cs" %>  
```  
  
```csharp  
// Client.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.ServiceModel;  
using System.Text;  
using System.Threading.Tasks;  
  
namespace Client  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            var context = new InstanceContext(new CallbackHandler());  
            var client = new StockQuoteServiceReference.StockQuoteServiceClient(context);  
            client.StartSendingQuotes();
            Console.ReadLine();  
        }  
  
        private class CallbackHandler : StockQuoteServiceReference.IStockQuoteServiceCallback  
        {  
            public async Task SendQuoteAsync(string code, double value)  
            {  
                Console.WriteLine("{0}: {1:f2}", code, value);  
            }  
        }  
    }  
}  
```  
  
```xml  
<!--App.config -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <startup>
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />  
    </startup>  
    <system.serviceModel>  
        <bindings>  
            <netHttpBinding>  
                <binding name="NetHttpBinding_IStockQuoteService">  
                    <webSocketSettings transportUsage="Always" />  
                </binding>  
            </netHttpBinding>  
        </bindings>  
        <client>  
            <endpoint address="ws://localhost/NetHttpSampleServer/StockQuoteService.svc"  
                binding="netHttpBinding" bindingConfiguration="NetHttpBinding_IStockQuoteService"  
                contract="StockQuoteServiceReference.IStockQuoteService" name="NetHttpBinding_IStockQuoteService" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9af68-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="9af68-129">See also</span></span>

- [<span data-ttu-id="9af68-130">Operaciones sincrónicas y asincrónicas</span><span class="sxs-lookup"><span data-stu-id="9af68-130">Synchronous and Asynchronous Operations</span></span>](../synchronous-and-asynchronous-operations.md)
- [<span data-ttu-id="9af68-131">Usar NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="9af68-131">Using the NetHttpBinding</span></span>](using-the-nethttpbinding.md)
