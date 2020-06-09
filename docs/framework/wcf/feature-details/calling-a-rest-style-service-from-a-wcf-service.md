---
title: Llamar a un servicio de estilo REST desde un servicio WCF
ms.date: 03/30/2017
ms.assetid: 77df81d8-7f53-4daf-8d2d-bf7996e94d5a
ms.openlocfilehash: eaa5d08faa335740124fcf698b22d2d324cd2c54
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576491"
---
# <a name="calling-a-rest-style-service-from-a-wcf-service"></a><span data-ttu-id="7d759-102">Llamar a un servicio de estilo REST desde un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="7d759-102">Calling a REST-style service from a WCF service</span></span>

<span data-ttu-id="7d759-103">Al llamar a un servicio de estilo REST desde un servicio WCF normal (basado en SOAP), el contexto de la operación en el método del servicio (que contiene información sobre la solicitud entrante) reemplaza el contexto que se debería usar en la solicitud saliente.</span><span class="sxs-lookup"><span data-stu-id="7d759-103">When calling a REST-style service from a regular (SOAP-based) WCF service, the operation context on the service method (which contains information about the incoming request) overrides the context which should be used by the outgoing request.</span></span> <span data-ttu-id="7d759-104">Esto da lugar a las solicitudes HTTP GET para cambiar a solicitudes HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="7d759-104">This causes HTTP GET requests to change to HTTP POST requests.</span></span> <span data-ttu-id="7d759-105">Para obligar al servicio WCF a que use el contexto idóneo para llamar al servicio de estilo REST, cree un nuevo <xref:System.ServiceModel.OperationContextScope> y llame al servicio de estilo REST desde dentro del ámbito del contexto de la operación.</span><span class="sxs-lookup"><span data-stu-id="7d759-105">To force the WCF service to use the right context for calling the REST-style service, create a new <xref:System.ServiceModel.OperationContextScope> and call the REST-style service from inside the operation context scope.</span></span> <span data-ttu-id="7d759-106">Este tema describirá cómo crear un sencillo ejemplo que muestra esta técnica.</span><span class="sxs-lookup"><span data-stu-id="7d759-106">This topic will describe how to create a simple sample that illustrates this technique.</span></span>

## <a name="define-the-rest-style-service-contract"></a><span data-ttu-id="7d759-107">Definir el contrato de servicio de estilo REST</span><span class="sxs-lookup"><span data-stu-id="7d759-107">Define the REST-style service contract</span></span>

<span data-ttu-id="7d759-108">Defina un contrato de servicio de estilo REST simple:</span><span class="sxs-lookup"><span data-stu-id="7d759-108">Define a simple  REST-style service contract:</span></span>

```csharp
[ServiceContract]
public interface IRestInterface
{
    [OperationContract, WebGet]
    int Add(int x, int y);

    [OperationContract, WebGet]
    string Echo(string input);
}
```

## <a name="implement-the-rest-style-service-contract"></a><span data-ttu-id="7d759-109">Implementar el contrato de servicio de estilo REST</span><span class="sxs-lookup"><span data-stu-id="7d759-109">Implement the REST-style service contract</span></span>

<span data-ttu-id="7d759-110">Implementar el contrato de servicio de estilo REST:</span><span class="sxs-lookup"><span data-stu-id="7d759-110">Implement the REST-style service contract:</span></span>

```csharp
public class RestService : IRestInterface
{
    public int Add(int x, int y)
    {
        return x + y;
    }

    public string Echo(string input)
    {
        return input;
    }
}
```

## <a name="define-the-wcf-service-contract"></a><span data-ttu-id="7d759-111">Definir el contrato de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="7d759-111">Define the WCF service contract</span></span>

<span data-ttu-id="7d759-112">Defina el contrato de servicio WCF que se usará para llamar al servicio de estilo REST:</span><span class="sxs-lookup"><span data-stu-id="7d759-112">Define a WCF service contract  that will be used to call the REST-style service:</span></span>

```csharp
[ServiceContract]
public interface INormalInterface
{
    [OperationContract]
    int CallAdd(int x, int y);

    [OperationContract]
    string CallEcho(string input);
}
```

## <a name="implement-the-wcf-service-contract"></a><span data-ttu-id="7d759-113">Implementar el contrato de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="7d759-113">Implement the WCF service contract</span></span>

<span data-ttu-id="7d759-114">Implementar el contrato de servicio de WCF:</span><span class="sxs-lookup"><span data-stu-id="7d759-114">Implement the WCF service contract:</span></span>

```csharp
public class NormalService : INormalInterface
{
    static MyRestClient client = new MyRestClient(RestServiceBaseAddress);
    public int CallAdd(int x, int y)
    {
        return client.Add(x, y);
    }

    public string CallEcho(string input)
    {
        return client.Echo(input);
    }
}
```

## <a name="create-the-client-proxy-for-the-rest-style-service"></a><span data-ttu-id="7d759-115">Crear un cliente proxy para el servicio de estilo REST.</span><span class="sxs-lookup"><span data-stu-id="7d759-115">Create the client proxy for the REST-style service</span></span>

<span data-ttu-id="7d759-116">Usar <xref:System.ServiceModel.ClientBase%601> para implementar el proxy de cliente.</span><span class="sxs-lookup"><span data-stu-id="7d759-116">Using <xref:System.ServiceModel.ClientBase%601> to implement the client proxy.</span></span> <span data-ttu-id="7d759-117">Para cada método llamado, se crea un nuevo <xref:System.ServiceModel.OperationContextScope> y se usa para llamar a la operación.</span><span class="sxs-lookup"><span data-stu-id="7d759-117">For each method called, a new <xref:System.ServiceModel.OperationContextScope> is created and used to call the operation.</span></span>

```csharp
public class MyRestClient : ClientBase<IRestInterface>, IRestInterface
{
    public MyRestClient(string address)
        : base(new WebHttpBinding(), new EndpointAddress(address))
    {
        this.Endpoint.Behaviors.Add(new WebHttpBehavior());
    }

    public int Add(int x, int y)
    {
        using (new OperationContextScope(this.InnerChannel))
        {
            return base.Channel.Add(x, y);
        }
    }

    public string Echo(string input)
    {
        using (new OperationContextScope(this.InnerChannel))
        {
            return base.Channel.Echo(input);
        }
    }
}
```

## <a name="host-and-call-the-services"></a><span data-ttu-id="7d759-118">Hospedar y llamar a los servicios</span><span class="sxs-lookup"><span data-stu-id="7d759-118">Host and call the services</span></span>

<span data-ttu-id="7d759-119">Hospede a ambos servicios en una aplicación de consola, agregando los extremos y los comportamientos necesarios.</span><span class="sxs-lookup"><span data-stu-id="7d759-119">Host both services in a console app, adding the needed endpoints and behaviors.</span></span> <span data-ttu-id="7d759-120">A continuación llama al servicio WCF normal:</span><span class="sxs-lookup"><span data-stu-id="7d759-120">And then call the regular WCF service:</span></span>

```csharp
public static void Main()
{
    ServiceHost restHost = new ServiceHost(typeof(RestService), new Uri(RestServiceBaseAddress));
    restHost.AddServiceEndpoint(typeof(IRestInterface), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());
    restHost.Open();

    ServiceHost normalHost = new ServiceHost(typeof(NormalService), new Uri(NormalServiceBaseAddress));
    normalHost.AddServiceEndpoint(typeof(INormalInterface), new BasicHttpBinding(), "");
    normalHost.Open();

    Console.WriteLine("Hosts opened");

    ChannelFactory<INormalInterface> factory = new ChannelFactory<INormalInterface>(new BasicHttpBinding(), new EndpointAddress(NormalServiceBaseAddress));
    INormalInterface proxy = factory.CreateChannel();

    Console.WriteLine(proxy.CallAdd(123, 456));
    Console.WriteLine(proxy.CallEcho("Hello world"));
}
```

## <a name="complete-code-listing"></a><span data-ttu-id="7d759-121">Completar la lista de códigos</span><span class="sxs-lookup"><span data-stu-id="7d759-121">Complete code listing</span></span>

<span data-ttu-id="7d759-122">A continuación, se muestra la lista completa del ejemplo implementado en este tema:</span><span class="sxs-lookup"><span data-stu-id="7d759-122">The following is a complete listing of the sample implemented in this topic:</span></span>

```csharp
public class CallingRESTSample
{
    static readonly string RestServiceBaseAddress = "http://" + Environment.MachineName + ":8008/Service";
    static readonly string NormalServiceBaseAddress = "http://" + Environment.MachineName + ":8000/Service";

    [ServiceContract]
    public interface IRestInterface
    {
        [OperationContract, WebGet]
        int Add(int x, int y);
        [OperationContract, WebGet]
        string Echo(string input);
    }

    [ServiceContract]
    public interface INormalInterface
    {
        [OperationContract]
        int CallAdd(int x, int y);
        [OperationContract]
        string CallEcho(string input);
    }

    public class RestService : IRestInterface
    {
        public int Add(int x, int y)
        {
            return x + y;
        }

        public string Echo(string input)
        {
            return input;
        }
    }

    public class MyRestClient : ClientBase<IRestInterface>, IRestInterface
    {
        public MyRestClient(string address)
            : base(new WebHttpBinding(), new EndpointAddress(address))
        {
            this.Endpoint.Behaviors.Add(new WebHttpBehavior());
        }

        public int Add(int x, int y)
        {
            using (new OperationContextScope(this.InnerChannel))
            {
                return base.Channel.Add(x, y);
            }
        }

        public string Echo(string input)
        {
            using (new OperationContextScope(this.InnerChannel))
            {
                return base.Channel.Echo(input);
            }
        }
    }

    public class NormalService : INormalInterface
    {
        static MyRestClient client = new MyRestClient(RestServiceBaseAddress);
        public int CallAdd(int x, int y)
        {
            return client.Add(x, y);
        }

        public string CallEcho(string input)
        {
            return client.Echo(input);
        }
    }

    public static void Main()
    {
        ServiceHost restHost = new ServiceHost(typeof(RestService), new Uri(RestServiceBaseAddress));
        restHost.AddServiceEndpoint(typeof(IRestInterface), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());
        restHost.Open();

        ServiceHost normalHost = new ServiceHost(typeof(NormalService), new Uri(NormalServiceBaseAddress));
        normalHost.AddServiceEndpoint(typeof(INormalInterface), new BasicHttpBinding(), "");
        normalHost.Open();

        Console.WriteLine("Hosts opened");

        ChannelFactory<INormalInterface> factory = new ChannelFactory<INormalInterface>(new BasicHttpBinding(), new EndpointAddress(NormalServiceBaseAddress));
        INormalInterface proxy = factory.CreateChannel();

        Console.WriteLine(proxy.CallAdd(123, 456));
        Console.WriteLine(proxy.CallEcho("Hello world"));
    }
}
```

## <a name="see-also"></a><span data-ttu-id="7d759-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d759-123">See also</span></span>

- [<span data-ttu-id="7d759-124">Procedimiento para crear un servicio básico web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="7d759-124">How to: Create a Basic WCF Web HTTP Service</span></span>](how-to-create-a-basic-wcf-web-http-service.md)
- [<span data-ttu-id="7d759-125">Modelo de objetos de programación web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="7d759-125">WCF Web HTTP Programming Object Model</span></span>](wcf-web-http-programming-object-model.md)
