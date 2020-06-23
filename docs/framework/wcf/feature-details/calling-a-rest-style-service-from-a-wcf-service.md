---
title: Llamar a un servicio de estilo REST desde un servicio WCF
description: Obtenga información sobre cómo hacer que un servicio WCF use el contexto correcto con un servicio de estilo REST mediante la creación de un ámbito y la llamada al servicio de estilo REST desde ese ámbito.
ms.date: 03/30/2017
ms.assetid: 77df81d8-7f53-4daf-8d2d-bf7996e94d5a
ms.openlocfilehash: 15f468923cf55feb85e7aeca1a2cc5e38050d665
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245302"
---
# <a name="calling-a-rest-style-service-from-a-wcf-service"></a><span data-ttu-id="471e8-103">Llamar a un servicio de estilo REST desde un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="471e8-103">Calling a REST-style service from a WCF service</span></span>

<span data-ttu-id="471e8-104">Al llamar a un servicio de estilo REST desde un servicio WCF normal (basado en SOAP), el contexto de la operación en el método del servicio (que contiene información sobre la solicitud entrante) reemplaza el contexto que se debería usar en la solicitud saliente.</span><span class="sxs-lookup"><span data-stu-id="471e8-104">When calling a REST-style service from a regular (SOAP-based) WCF service, the operation context on the service method (which contains information about the incoming request) overrides the context which should be used by the outgoing request.</span></span> <span data-ttu-id="471e8-105">Esto da lugar a las solicitudes HTTP GET para cambiar a solicitudes HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="471e8-105">This causes HTTP GET requests to change to HTTP POST requests.</span></span> <span data-ttu-id="471e8-106">Para obligar al servicio WCF a que use el contexto idóneo para llamar al servicio de estilo REST, cree un nuevo <xref:System.ServiceModel.OperationContextScope> y llame al servicio de estilo REST desde dentro del ámbito del contexto de la operación.</span><span class="sxs-lookup"><span data-stu-id="471e8-106">To force the WCF service to use the right context for calling the REST-style service, create a new <xref:System.ServiceModel.OperationContextScope> and call the REST-style service from inside the operation context scope.</span></span> <span data-ttu-id="471e8-107">Este tema describirá cómo crear un sencillo ejemplo que muestra esta técnica.</span><span class="sxs-lookup"><span data-stu-id="471e8-107">This topic will describe how to create a simple sample that illustrates this technique.</span></span>

## <a name="define-the-rest-style-service-contract"></a><span data-ttu-id="471e8-108">Definir el contrato de servicio de estilo REST</span><span class="sxs-lookup"><span data-stu-id="471e8-108">Define the REST-style service contract</span></span>

<span data-ttu-id="471e8-109">Defina un contrato de servicio de estilo REST simple:</span><span class="sxs-lookup"><span data-stu-id="471e8-109">Define a simple  REST-style service contract:</span></span>

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

## <a name="implement-the-rest-style-service-contract"></a><span data-ttu-id="471e8-110">Implementar el contrato de servicio de estilo REST</span><span class="sxs-lookup"><span data-stu-id="471e8-110">Implement the REST-style service contract</span></span>

<span data-ttu-id="471e8-111">Implementar el contrato de servicio de estilo REST:</span><span class="sxs-lookup"><span data-stu-id="471e8-111">Implement the REST-style service contract:</span></span>

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

## <a name="define-the-wcf-service-contract"></a><span data-ttu-id="471e8-112">Definir el contrato de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="471e8-112">Define the WCF service contract</span></span>

<span data-ttu-id="471e8-113">Defina el contrato de servicio WCF que se usará para llamar al servicio de estilo REST:</span><span class="sxs-lookup"><span data-stu-id="471e8-113">Define a WCF service contract  that will be used to call the REST-style service:</span></span>

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

## <a name="implement-the-wcf-service-contract"></a><span data-ttu-id="471e8-114">Implementar el contrato de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="471e8-114">Implement the WCF service contract</span></span>

<span data-ttu-id="471e8-115">Implementar el contrato de servicio de WCF:</span><span class="sxs-lookup"><span data-stu-id="471e8-115">Implement the WCF service contract:</span></span>

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

## <a name="create-the-client-proxy-for-the-rest-style-service"></a><span data-ttu-id="471e8-116">Crear un cliente proxy para el servicio de estilo REST.</span><span class="sxs-lookup"><span data-stu-id="471e8-116">Create the client proxy for the REST-style service</span></span>

<span data-ttu-id="471e8-117">Usar <xref:System.ServiceModel.ClientBase%601> para implementar el proxy de cliente.</span><span class="sxs-lookup"><span data-stu-id="471e8-117">Using <xref:System.ServiceModel.ClientBase%601> to implement the client proxy.</span></span> <span data-ttu-id="471e8-118">Para cada método llamado, se crea un nuevo <xref:System.ServiceModel.OperationContextScope> y se usa para llamar a la operación.</span><span class="sxs-lookup"><span data-stu-id="471e8-118">For each method called, a new <xref:System.ServiceModel.OperationContextScope> is created and used to call the operation.</span></span>

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

## <a name="host-and-call-the-services"></a><span data-ttu-id="471e8-119">Hospedar y llamar a los servicios</span><span class="sxs-lookup"><span data-stu-id="471e8-119">Host and call the services</span></span>

<span data-ttu-id="471e8-120">Hospede a ambos servicios en una aplicación de consola, agregando los extremos y los comportamientos necesarios.</span><span class="sxs-lookup"><span data-stu-id="471e8-120">Host both services in a console app, adding the needed endpoints and behaviors.</span></span> <span data-ttu-id="471e8-121">A continuación llama al servicio WCF normal:</span><span class="sxs-lookup"><span data-stu-id="471e8-121">And then call the regular WCF service:</span></span>

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

## <a name="complete-code-listing"></a><span data-ttu-id="471e8-122">Completar la lista de códigos</span><span class="sxs-lookup"><span data-stu-id="471e8-122">Complete code listing</span></span>

<span data-ttu-id="471e8-123">A continuación, se muestra la lista completa del ejemplo implementado en este tema:</span><span class="sxs-lookup"><span data-stu-id="471e8-123">The following is a complete listing of the sample implemented in this topic:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="471e8-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="471e8-124">See also</span></span>

- [<span data-ttu-id="471e8-125">Procedimiento para crear un servicio básico web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="471e8-125">How to: Create a Basic WCF Web HTTP Service</span></span>](how-to-create-a-basic-wcf-web-http-service.md)
- [<span data-ttu-id="471e8-126">Modelo de objetos de programación web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="471e8-126">WCF Web HTTP Programming Object Model</span></span>](wcf-web-http-programming-object-model.md)
