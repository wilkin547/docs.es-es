---
description: 'Más información acerca de cómo: implementar un proxy de detección'
title: Procedimiento para implementar un proxy de detección
ms.date: 03/30/2017
ms.assetid: 78d70e0a-f6c3-4cfb-a7ca-f66ebddadde0
ms.openlocfilehash: e7bd9833ac0d449eefd5e439b442ecb0eee121ca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793758"
---
# <a name="how-to-implement-a-discovery-proxy"></a><span data-ttu-id="36b1a-103">Procedimiento para implementar un proxy de detección</span><span class="sxs-lookup"><span data-stu-id="36b1a-103">How to: Implement a Discovery Proxy</span></span>

<span data-ttu-id="36b1a-104">En este tema se explica cómo implementar un proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="36b1a-104">This topic explains how to implement a discovery proxy.</span></span> <span data-ttu-id="36b1a-105">Para obtener más información acerca de la característica de detección en Windows Communication Foundation (WCF), consulte [información general](wcf-discovery-overview.md)sobre la detección de WCF.</span><span class="sxs-lookup"><span data-stu-id="36b1a-105">For more information about the discovery feature in Windows Communication Foundation (WCF), see [WCF Discovery Overview](wcf-discovery-overview.md).</span></span> <span data-ttu-id="36b1a-106">Puede implementarse un proxy de detección creando una clase que extienda la clase abstracta <xref:System.ServiceModel.Discovery.DiscoveryProxy>.</span><span class="sxs-lookup"><span data-stu-id="36b1a-106">A discovery proxy can be implemented by creating a class that extends the <xref:System.ServiceModel.Discovery.DiscoveryProxy> abstract class.</span></span> <span data-ttu-id="36b1a-107">Hay otras clases de compatibiildad definidas y usadas en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="36b1a-107">There are a number of other support classes defined and used in this sample.</span></span> <span data-ttu-id="36b1a-108">`OnResolveAsyncResult`, `OnFindAsyncResult`y `AsyncResult`.</span><span class="sxs-lookup"><span data-stu-id="36b1a-108">`OnResolveAsyncResult`, `OnFindAsyncResult`, and `AsyncResult`.</span></span> <span data-ttu-id="36b1a-109">Estas clases implementan la interfaz <xref:System.IAsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="36b1a-109">These classes implement the <xref:System.IAsyncResult> interface.</span></span> <span data-ttu-id="36b1a-110">Para obtener más información, <xref:System.IAsyncResult> consulte la [interfaz System. IAsyncResult](xref:System.IAsyncResult).</span><span class="sxs-lookup"><span data-stu-id="36b1a-110">For more information about <xref:System.IAsyncResult> see [System.IAsyncResult interface](xref:System.IAsyncResult).</span></span>

 <span data-ttu-id="36b1a-111">La implementación de un proxy de detección se divide en tres partes principales en este tema:</span><span class="sxs-lookup"><span data-stu-id="36b1a-111">Implementing a discovery proxy is broken down into three main parts in this topic:</span></span>

- <span data-ttu-id="36b1a-112">Defina una clase que contenga un almacén de datos y extienda la clase abstracta <xref:System.ServiceModel.Discovery.DiscoveryProxy>.</span><span class="sxs-lookup"><span data-stu-id="36b1a-112">Define a class that contains a data store and extends the abstract <xref:System.ServiceModel.Discovery.DiscoveryProxy> class.</span></span>

- <span data-ttu-id="36b1a-113">Implemente la clase `AsyncResult` del asistente.</span><span class="sxs-lookup"><span data-stu-id="36b1a-113">Implement the helper `AsyncResult` class.</span></span>

- <span data-ttu-id="36b1a-114">Hospede el proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="36b1a-114">Host the Discovery Proxy.</span></span>

### <a name="to-create-a-new-console-application-project"></a><span data-ttu-id="36b1a-115">Para crear un nuevo proyecto de aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="36b1a-115">To create a new console application project</span></span>

1. <span data-ttu-id="36b1a-116">Inicie Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="36b1a-116">Start Visual Studio 2012.</span></span>

2. <span data-ttu-id="36b1a-117">Cree un nuevo proyecto de aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="36b1a-117">Create a new console application project.</span></span> <span data-ttu-id="36b1a-118">Asigne al proyecto el nombre `DiscoveryProxy` y, a la solución, `DiscoveryProxyExample`.</span><span class="sxs-lookup"><span data-stu-id="36b1a-118">Name the project `DiscoveryProxy` and the name the solution `DiscoveryProxyExample`.</span></span>

3. <span data-ttu-id="36b1a-119">Agregue las siguientes referencias al proyecto:</span><span class="sxs-lookup"><span data-stu-id="36b1a-119">Add the following references to the project</span></span>

    1. <span data-ttu-id="36b1a-120">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="36b1a-120">System.ServiceModel.dll</span></span>

    2. <span data-ttu-id="36b1a-121">System.Servicemodel.Discovery.dll</span><span class="sxs-lookup"><span data-stu-id="36b1a-121">System.Servicemodel.Discovery.dll</span></span>

    > [!CAUTION]
    > <span data-ttu-id="36b1a-122">Asegúrese de que indica la versión 4.0 o posterior de estos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="36b1a-122">Ensure that you reference version 4.0 or greater of these assemblies.</span></span>

### <a name="to-implement-the-proxydiscoveryservice-class"></a><span data-ttu-id="36b1a-123">Para implementar la clase ProxyDiscoveryService</span><span class="sxs-lookup"><span data-stu-id="36b1a-123">To implement the ProxyDiscoveryService class</span></span>

1. <span data-ttu-id="36b1a-124">Agregue un nuevo archivo de código a su proyecto y denomínelo DiscoveryProxy.cs.</span><span class="sxs-lookup"><span data-stu-id="36b1a-124">Add a new code file to your project and name it DiscoveryProxy.cs.</span></span>

2. <span data-ttu-id="36b1a-125">Agregue las siguientes instrucciones `using` a DiscoveryProxy.cs.</span><span class="sxs-lookup"><span data-stu-id="36b1a-125">Add the following `using` statements to DiscoveryProxy.cs.</span></span>

    ```csharp
    using System;
    using System.Collections.Generic;
    using System.ServiceModel;
    using System.ServiceModel.Discovery;
    using System.Xml;
    ```

3. <span data-ttu-id="36b1a-126">Derive `DiscoveryProxyService` de <xref:System.ServiceModel.Discovery.DiscoveryProxy>.</span><span class="sxs-lookup"><span data-stu-id="36b1a-126">Derive the `DiscoveryProxyService` from <xref:System.ServiceModel.Discovery.DiscoveryProxy>.</span></span> <span data-ttu-id="36b1a-127">Aplique el atributo `ServiceBehavior` a la clase, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="36b1a-127">Apply the `ServiceBehavior` attribute to the class as shown in the following example.</span></span>

    ```csharp
    // Implement DiscoveryProxy by extending the DiscoveryProxy class and overriding the abstract methods
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single, ConcurrencyMode = ConcurrencyMode.Multiple)]
    public class DiscoveryProxyService : DiscoveryProxy
    {
    }
    ```

4. <span data-ttu-id="36b1a-128">Dentro de la clase `DiscoveryProxy` defina un diccionario para retener los servicios registrados.</span><span class="sxs-lookup"><span data-stu-id="36b1a-128">Inside the `DiscoveryProxy` class define a dictionary to hold the registered services.</span></span>

    ```csharp
    // Repository to store EndpointDiscoveryMetadata.
    Dictionary<EndpointAddress, EndpointDiscoveryMetadata> onlineServices;
    ```

5. <span data-ttu-id="36b1a-129">Defina un constructor que inicializa el diccionario.</span><span class="sxs-lookup"><span data-stu-id="36b1a-129">Define a constructor that initializes the dictionary.</span></span>

    ```csharp
    public DiscoveryProxyService()
            {
                this.onlineServices = new Dictionary<EndpointAddress, EndpointDiscoveryMetadata>();
            }
    ```

### <a name="to-define-the-methods-used-to-update-the-discovery-proxy-cache"></a><span data-ttu-id="36b1a-130">Para definir los métodos usados para actualizar la memoria caché del proxy de detección</span><span class="sxs-lookup"><span data-stu-id="36b1a-130">To define the methods used to update the discovery proxy cache</span></span>

1. <span data-ttu-id="36b1a-131">Implemente el método `AddOnlineservice` para agregar servicios a la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="36b1a-131">Implement the `AddOnlineservice` method to add services to the cache.</span></span> <span data-ttu-id="36b1a-132">Se llama a este método cada vez que el proxy recibe un mensaje de anuncio.</span><span class="sxs-lookup"><span data-stu-id="36b1a-132">This is called every time the proxy receives an announcement message.</span></span>

    ```csharp
    void AddOnlineService(EndpointDiscoveryMetadata endpointDiscoveryMetadata)
    {
        lock (this.onlineServices)
        {
            this.onlineServices[endpointDiscoveryMetadata.Address] = endpointDiscoveryMetadata;
        }

        PrintDiscoveryMetadata(endpointDiscoveryMetadata, "Adding");
    }
    ```

2. <span data-ttu-id="36b1a-133">Implemente el método `RemoveOnlineService` que se utiliza para quitar servicios de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="36b1a-133">Implement the `RemoveOnlineService` method that is used to remove services from the cache.</span></span>

    ```csharp
    void RemoveOnlineService(EndpointDiscoveryMetadata endpointDiscoveryMetadata)
    {
        if (endpointDiscoveryMetadata != null)
        {
            lock (this.onlineServices)
            {
                this.onlineServices.Remove(endpointDiscoveryMetadata.Address);
            }

            PrintDiscoveryMetadata(endpointDiscoveryMetadata, "Removing");
        }
    }
    ```

3. <span data-ttu-id="36b1a-134">Implemente los métodos `MatchFromOnlineService` que intentan coincidir un servicio con un servicio en el diccionario.</span><span class="sxs-lookup"><span data-stu-id="36b1a-134">Implement the `MatchFromOnlineService` methods that attempt to match a service with a service in the dictionary.</span></span>

    ```csharp
    void MatchFromOnlineService(FindRequestContext findRequestContext)
    {
        lock (this.onlineServices)
        {
            foreach (EndpointDiscoveryMetadata endpointDiscoveryMetadata in this.onlineServices.Values)
            {
                if (findRequestContext.Criteria.IsMatch(endpointDiscoveryMetadata))
                {
                    findRequestContext.AddMatchingEndpoint(endpointDiscoveryMetadata);
                }
            }
        }
    }
    ```

    ```csharp
    EndpointDiscoveryMetadata MatchFromOnlineService(ResolveCriteria criteria)
    {
        EndpointDiscoveryMetadata matchingEndpoint = null;
        lock (this.onlineServices)
        {
            foreach (EndpointDiscoveryMetadata endpointDiscoveryMetadata in this.onlineServices.Values)
            {
                if (criteria.Address == endpointDiscoveryMetadata.Address)
                {
                    matchingEndpoint = endpointDiscoveryMetadata;
                }
            }
        }
        return matchingEndpoint;
    }
    ```

4. <span data-ttu-id="36b1a-135">Implemente el método `PrintDiscoveryMetadata` que ofrece al usuario el resultado de texto de la consola de lo que hace el proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="36b1a-135">Implement the `PrintDiscoveryMetadata` method that provides the user with console text output of what the discovery proxy is doing.</span></span>

    ```csharp
    void PrintDiscoveryMetadata(EndpointDiscoveryMetadata endpointDiscoveryMetadata, string verb)
    {
        Console.WriteLine("\n**** " + verb + " service of the following type from cache. ");
        foreach (XmlQualifiedName contractName in endpointDiscoveryMetadata.ContractTypeNames)
        {
            Console.WriteLine("** " + contractName.ToString());
            break;
        }
        Console.WriteLine("**** Operation Completed");
    }
    ```

5. <span data-ttu-id="36b1a-136">Agregue las clases AsyncResult siguientes a DiscoveryProxyService.</span><span class="sxs-lookup"><span data-stu-id="36b1a-136">Add the following AsyncResult classes to the DiscoveryProxyService.</span></span> <span data-ttu-id="36b1a-137">Estas clases se utilizan para diferenciar entre los diferentes resultados de la operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="36b1a-137">These classes are used to differentiate between the different asynchronous operation results.</span></span>

    ```csharp
    sealed class OnOnlineAnnouncementAsyncResult : AsyncResult
    {
        public OnOnlineAnnouncementAsyncResult(AsyncCallback callback, object state)
            : base(callback, state)
        {
            this.Complete(true);
        }

        public static void End(IAsyncResult result)
        {
            AsyncResult.End<OnOnlineAnnouncementAsyncResult>(result);
        }
    }

    sealed class OnOfflineAnnouncementAsyncResult : AsyncResult
    {
        public OnOfflineAnnouncementAsyncResult(AsyncCallback callback, object state)
            : base(callback, state)
        {
            this.Complete(true);
        }

        public static void End(IAsyncResult result)
        {
            AsyncResult.End<OnOfflineAnnouncementAsyncResult>(result);
        }
    }

    sealed class OnFindAsyncResult : AsyncResult
    {
        public OnFindAsyncResult(AsyncCallback callback, object state)
            : base(callback, state)
        {
            this.Complete(true);
        }

        public static void End(IAsyncResult result)
        {
            AsyncResult.End<OnFindAsyncResult>(result);
        }
    }

    sealed class OnResolveAsyncResult : AsyncResult
    {
        EndpointDiscoveryMetadata matchingEndpoint;

        public OnResolveAsyncResult(EndpointDiscoveryMetadata matchingEndpoint, AsyncCallback callback, object state)
            : base(callback, state)
        {
            this.matchingEndpoint = matchingEndpoint;
            this.Complete(true);
        }

        public static EndpointDiscoveryMetadata End(IAsyncResult result)
        {
            OnResolveAsyncResult thisPtr = AsyncResult.End<OnResolveAsyncResult>(result);
            return thisPtr.matchingEndpoint;
        }
    }
    ```

### <a name="to-define-the-methods-that-implement-the-discovery-proxy-functionality"></a><span data-ttu-id="36b1a-138">Para definir los métodos que implementan la funcionalidad de proxy de detección</span><span class="sxs-lookup"><span data-stu-id="36b1a-138">To define the methods that implement the discovery proxy functionality</span></span>

1. <span data-ttu-id="36b1a-139">Invalide el método <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginOnlineAnnouncement%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="36b1a-139">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginOnlineAnnouncement%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="36b1a-140">Se llama a este método cuando el proxy de detección recibe un mensaje de anuncio en línea.</span><span class="sxs-lookup"><span data-stu-id="36b1a-140">This method is called when the discovery proxy receives an online announcement message.</span></span>

    ```csharp
    // OnBeginOnlineAnnouncement method is called when a Hello message is received by the Proxy
    protected override IAsyncResult OnBeginOnlineAnnouncement(DiscoveryMessageSequence messageSequence, EndpointDiscoveryMetadata endpointDiscoveryMetadata, AsyncCallback callback, object state)
    {
        this.AddOnlineService(endpointDiscoveryMetadata);
        return new OnOnlineAnnouncementAsyncResult(callback, state);
    }
    ```

2. <span data-ttu-id="36b1a-141">Invalide el método <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndOnlineAnnouncement%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="36b1a-141">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndOnlineAnnouncement%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="36b1a-142">Se llama a este método cuando el proxy de detección finaliza el procesamiento de un mensaje de anuncio.</span><span class="sxs-lookup"><span data-stu-id="36b1a-142">This method is called when the discovery proxy finishes processing an announcement message.</span></span>

    ```csharp
    protected override void OnEndOnlineAnnouncement(IAsyncResult result)
    {
        OnOnlineAnnouncementAsyncResult.End(result);
    }
    ```

3. <span data-ttu-id="36b1a-143">Invalide el método <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginOfflineAnnouncement%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="36b1a-143">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginOfflineAnnouncement%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="36b1a-144">Se llama a este método cuando el proxy de detección recibe un mensaje de anuncio sin conexión.</span><span class="sxs-lookup"><span data-stu-id="36b1a-144">This method is called with the discovery proxy receives an offline announcement message.</span></span>

    ```csharp
    // OnBeginOfflineAnnouncement method is called when a Bye message is received by the Proxy
    protected override IAsyncResult OnBeginOfflineAnnouncement(DiscoveryMessageSequence messageSequence, EndpointDiscoveryMetadata endpointDiscoveryMetadata, AsyncCallback callback, object state)
    {
        this.RemoveOnlineService(endpointDiscoveryMetadata);
        return new OnOfflineAnnouncementAsyncResult(callback, state);
    }
    ```

4. <span data-ttu-id="36b1a-145">Invalide el método <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndOfflineAnnouncement%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="36b1a-145">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndOfflineAnnouncement%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="36b1a-146">Se llama a este método cuando el proxy de detección finaliza el procesamiento de un mensaje de anuncio sin conexión.</span><span class="sxs-lookup"><span data-stu-id="36b1a-146">This method is called when the discovery proxy finishes processing an offline announcement message.</span></span>

    ```csharp
    protected override void OnEndOfflineAnnouncement(IAsyncResult result)
    {
        OnOfflineAnnouncementAsyncResult.End(result);
    }
    ```

5. <span data-ttu-id="36b1a-147">Invalide el método <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="36b1a-147">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="36b1a-148">Se llama a este método cuando el proxy de detección recibe una solicitud de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="36b1a-148">This method is called when the discovery proxy receives a find request.</span></span>

    ```csharp
    // OnBeginFind method is called when a Probe request message is received by the Proxy
    protected override IAsyncResult OnBeginFind(FindRequestContext findRequestContext, AsyncCallback callback, object state)
    {
        this.MatchFromOnlineService(findRequestContext);
        return new OnFindAsyncResult(callback, state);
    }
    protected override IAsyncResult OnBeginFind(FindRequest findRequest, AsyncCallback callback, object state)
    {
        Collection<EndpointDiscoveryMetadata> matchingEndpoints = MatchFromCache(findRequest.Criteria);
        return new OnFindAsyncResult(
                    matchingEndpoints,
                    callback,
                    state);
    }
    ```

6. <span data-ttu-id="36b1a-149">Invalide el método <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndFind%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="36b1a-149">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndFind%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="36b1a-150">Se llama a este método cuando el proxy de detección finaliza el procesamiento de una solicitud de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="36b1a-150">This method is called when the discovery proxy finishes processing a find request.</span></span>

    ```csharp
    protected override void OnEndFind(IAsyncResult result)
    {
        OnFindAsyncResult.End(result);
    }
    ```

7. <span data-ttu-id="36b1a-151">Invalide el método <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginResolve%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="36b1a-151">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginResolve%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="36b1a-152">Se llama a este método cuando el proxy de detección recibe un mensaje de resolución.</span><span class="sxs-lookup"><span data-stu-id="36b1a-152">This method is called when the discovery proxy receives a resolve message.</span></span>

    ```csharp
    // OnBeginFind method is called when a Resolve request message is received by the Proxy
    protected override IAsyncResult OnBeginResolve(ResolveCriteria resolveCriteria, AsyncCallback callback, object state)
    {
        return new OnResolveAsyncResult(this.MatchFromOnlineService(resolveCriteria), callback, state);
    }
    protected override IAsyncResult OnBeginResolve(ResolveRequest resolveRequest, AsyncCallback callback, object state)
    {
        return new OnResolveAsyncResult(
            this.proxy.MatchFromOnlineService(resolveRequest.Criteria),
            callback,
            state);
    }
    ```

8. <span data-ttu-id="36b1a-153">Invalide el método <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndResolve%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="36b1a-153">Override the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndResolve%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="36b1a-154">Se llama a este método cuando el proxy de detección finaliza el procesamiento de un mensaje de resolución.</span><span class="sxs-lookup"><span data-stu-id="36b1a-154">This method is called when the discovery proxy finishes processing a resolve message.</span></span>

    ```csharp
    protected override EndpointDiscoveryMetadata OnEndResolve(IAsyncResult result)
    {
        return OnResolveAsyncResult.End(result);
    }
    ```

<span data-ttu-id="36b1a-155">Los métodos OnBegin.</span><span class="sxs-lookup"><span data-stu-id="36b1a-155">The OnBegin..</span></span> <span data-ttu-id="36b1a-156">/ OnEnd.</span><span class="sxs-lookup"><span data-stu-id="36b1a-156">/ OnEnd..</span></span> <span data-ttu-id="36b1a-157">métodos proporcionan la lógica para las operaciones de detección subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="36b1a-157">methods provide the logic for the subsequent discovery operations.</span></span> <span data-ttu-id="36b1a-158">Por ejemplo, los métodos <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A> y <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndFind%2A> implementan la lógica de búsqueda para el proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="36b1a-158">For example the <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A> and <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnEndFind%2A> methods implement the find logic for discovery proxy.</span></span> <span data-ttu-id="36b1a-159">Cuando el proxy de detección recibe un mensaje de sondeo, estos métodos se ejecutan para devolver una respuesta al cliente.</span><span class="sxs-lookup"><span data-stu-id="36b1a-159">When the discovery proxy receives a probe message these methods are executed to send a response back to the client.</span></span> <span data-ttu-id="36b1a-160">Puede modificar la lógica de búsqueda como desee; por ejemplo, puede incorporar una coincidencia de ámbito personalizada mediante algoritmos o un análisis de metadatos XML específico de la aplicación como parte de la operación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="36b1a-160">You may modify the find logic as you wish, for example you can incorporate custom scope matching by algorithms or application specific XML metadata parsing as part of your find operation.</span></span>

### <a name="to-implement-the-asyncresult-class"></a><span data-ttu-id="36b1a-161">Para implementar la clase AsyncResult</span><span class="sxs-lookup"><span data-stu-id="36b1a-161">To implement the AsyncResult class</span></span>

1. <span data-ttu-id="36b1a-162">Defina la clase base abstracta AsyncResult que se utiliza para derivar las diversas clases Result asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="36b1a-162">Define the abstract base class AsyncResult which is used to derive the various async result classes.</span></span>

2. <span data-ttu-id="36b1a-163">Cree un nuevo archivo de código denominado AsyncResult.cs.</span><span class="sxs-lookup"><span data-stu-id="36b1a-163">Create a new code file called AsyncResult.cs.</span></span>

3. <span data-ttu-id="36b1a-164">Agregue las instrucciones `using` siguientes a AsyncResult.cs.</span><span class="sxs-lookup"><span data-stu-id="36b1a-164">Add the following `using` statements to AsyncResult.cs.</span></span>

    ```csharp
    using System;
    using System.Threading;
    ```

4. <span data-ttu-id="36b1a-165">Agregue la siguiente clase AsyncResult.</span><span class="sxs-lookup"><span data-stu-id="36b1a-165">Add the following AsyncResult class.</span></span>

    ```csharp
    abstract class AsyncResult : IAsyncResult
    {
        AsyncCallback callback;
        bool completedSynchronously;
        bool endCalled;
        Exception exception;
        bool isCompleted;
        ManualResetEvent manualResetEvent;
        object state;
        object thisLock;

        protected AsyncResult(AsyncCallback callback, object state)
        {
            this.callback = callback;
            this.state = state;
            this.thisLock = new object();
        }

        public object AsyncState
        {
            get
            {
                return state;
            }
        }

        public WaitHandle AsyncWaitHandle
        {
            get
            {
                if (manualResetEvent != null)
                {
                    return manualResetEvent;
                }
                lock (ThisLock)
                {
                    manualResetEvent ??= new ManualResetEvent(isCompleted);
                }
                return manualResetEvent;
            }
        }

        public bool CompletedSynchronously
        {
            get
            {
                return completedSynchronously;
            }
        }

        public bool IsCompleted
        {
            get
            {
                return isCompleted;
            }
        }

        object ThisLock
        {
            get
            {
                return this.thisLock;
            }
        }

        protected static TAsyncResult End<TAsyncResult>(IAsyncResult result)
            where TAsyncResult : AsyncResult
        {
            if (result == null)
            {
                throw new ArgumentNullException("result");
            }

            TAsyncResult asyncResult = result as TAsyncResult;

            if (asyncResult == null)
            {
                throw new ArgumentException("Invalid async result.", "result");
            }

            if (asyncResult.endCalled)
            {
                throw new InvalidOperationException("Async object already ended.");
            }

            asyncResult.endCalled = true;

            if (!asyncResult.isCompleted)
            {
                asyncResult.AsyncWaitHandle.WaitOne();
            }

            if (asyncResult.manualResetEvent != null)
            {
                asyncResult.manualResetEvent.Close();
            }

            if (asyncResult.exception != null)
            {
                throw asyncResult.exception;
            }

            return asyncResult;
        }

        protected void Complete(bool completedSynchronously)
        {
            if (isCompleted)
            {
                throw new InvalidOperationException("This async result is already completed.");
            }

            this.completedSynchronously = completedSynchronously;

            if (completedSynchronously)
            {
                this.isCompleted = true;
            }
            else
            {
                lock (ThisLock)
                {
                    this.isCompleted = true;
                    if (this.manualResetEvent != null)
                    {
                        this.manualResetEvent.Set();
                    }
                }
            }

            if (callback != null)
            {
                callback(this);
            }
        }

        protected void Complete(bool completedSynchronously, Exception exception)
        {
            this.exception = exception;
            Complete(completedSynchronously);
        }
    }
    ```

### <a name="to-host-the-discoveryproxy"></a><span data-ttu-id="36b1a-166">Para hospedar DiscoveryProxy</span><span class="sxs-lookup"><span data-stu-id="36b1a-166">To host the DiscoveryProxy</span></span>

1. <span data-ttu-id="36b1a-167">Abra el archivo Program.cs en el proyecto DiscoveryProxyExample.</span><span class="sxs-lookup"><span data-stu-id="36b1a-167">Open the Program.cs file in the DiscoveryProxyExample project.</span></span>

2. <span data-ttu-id="36b1a-168">Agregue las siguientes instrucciones `using`.</span><span class="sxs-lookup"><span data-stu-id="36b1a-168">Add the following `using` statements.</span></span>

    ```csharp
    using System;
    using System.ServiceModel;
    using System.ServiceModel.Discovery;
    ```

3. <span data-ttu-id="36b1a-169">Agregue el código siguiente en el método `Main()`.</span><span class="sxs-lookup"><span data-stu-id="36b1a-169">Within the `Main()` method, add the following code.</span></span> <span data-ttu-id="36b1a-170">De esta forma se crea una instancia de la clase `DiscoveryProxy`.</span><span class="sxs-lookup"><span data-stu-id="36b1a-170">This creates an instance of the `DiscoveryProxy` class.</span></span>

    ```csharp
    Uri probeEndpointAddress = new Uri("net.tcp://localhost:8001/Probe");
    Uri announcementEndpointAddress = new Uri("net.tcp://localhost:9021/Announcement");

    // Host the DiscoveryProxy service
    ServiceHost proxyServiceHost = new ServiceHost(new DiscoveryProxyService());
    ```

4. <span data-ttu-id="36b1a-171">Luego, agregue el siguiente código para agregar un extremo de detección y un extremo de anuncio.</span><span class="sxs-lookup"><span data-stu-id="36b1a-171">Next add the following code to add a discovery endpoint and an announcement endpoint.</span></span>

    ```csharp
    try
    {
        // Add DiscoveryEndpoint to receive Probe and Resolve messages
        DiscoveryEndpoint discoveryEndpoint = new DiscoveryEndpoint(new NetTcpBinding(), new EndpointAddress(probeEndpointAddress));
        discoveryEndpoint.IsSystemEndpoint = false;

        // Add AnnouncementEndpoint to receive Hello and Bye announcement messages
        AnnouncementEndpoint announcementEndpoint = new AnnouncementEndpoint(new NetTcpBinding(), new EndpointAddress(announcementEndpointAddress));

        proxyServiceHost.AddServiceEndpoint(discoveryEndpoint);
        proxyServiceHost.AddServiceEndpoint(announcementEndpoint);

        proxyServiceHost.Open();

        Console.WriteLine("Proxy Service started.");
        Console.WriteLine();
        Console.WriteLine("Press <ENTER> to terminate the service.");
        Console.WriteLine();
        Console.ReadLine();

        proxyServiceHost.Close();
    }
    catch (CommunicationException e)
    {
        Console.WriteLine(e.Message);
    }
    catch (TimeoutException e)
    {
        Console.WriteLine(e.Message);
    }

    if (proxyServiceHost.State != CommunicationState.Closed)
    {
        Console.WriteLine("Aborting the service...");
        proxyServiceHost.Abort();
    }
    ```

<span data-ttu-id="36b1a-172">Ha completado la implementación del proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="36b1a-172">You have completed implementing the discovery proxy.</span></span> <span data-ttu-id="36b1a-173">Continúe con [el procedimiento para implementar un servicio reconocible que se registra con el proxy de detección](discoverable-service-that-registers-with-the-discovery-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="36b1a-173">Continue on to [How to: Implement a Discoverable Service that Registers with the Discovery Proxy](discoverable-service-that-registers-with-the-discovery-proxy.md).</span></span>

## <a name="example"></a><span data-ttu-id="36b1a-174">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="36b1a-174">Example</span></span>

<span data-ttu-id="36b1a-175">Esta es la lista completa del código empleado en este tema.</span><span class="sxs-lookup"><span data-stu-id="36b1a-175">This is the full listing of the code used in this topic.</span></span>

```csharp
// DiscoveryProxy.cs
//----------------------------------------------------------------
// Copyright (c) Microsoft Corporation.  All rights reserved.
//----------------------------------------------------------------

using System;
using System.Collections.Generic;
using System.ServiceModel;
using System.ServiceModel.Discovery;
using System.Xml;

namespace Microsoft.Samples.Discovery
{
    // Implement DiscoveryProxy by extending the DiscoveryProxy class and overriding the abstract methods
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single, ConcurrencyMode = ConcurrencyMode.Multiple)]
    public class DiscoveryProxyService : DiscoveryProxy
    {
        // Repository to store EndpointDiscoveryMetadata. A database or a flat file could also be used instead.
        Dictionary<EndpointAddress, EndpointDiscoveryMetadata> onlineServices;

        public DiscoveryProxyService()
        {
            this.onlineServices = new Dictionary<EndpointAddress, EndpointDiscoveryMetadata>();
        }

        // OnBeginOnlineAnnouncement method is called when a Hello message is received by the Proxy
        protected override IAsyncResult OnBeginOnlineAnnouncement(DiscoveryMessageSequence messageSequence, EndpointDiscoveryMetadata endpointDiscoveryMetadata, AsyncCallback callback, object state)
        {
            this.AddOnlineService(endpointDiscoveryMetadata);
            return new OnOnlineAnnouncementAsyncResult(callback, state);
        }

        protected override void OnEndOnlineAnnouncement(IAsyncResult result)
        {
            OnOnlineAnnouncementAsyncResult.End(result);
        }

        // OnBeginOfflineAnnouncement method is called when a Bye message is received by the Proxy
        protected override IAsyncResult OnBeginOfflineAnnouncement(DiscoveryMessageSequence messageSequence, EndpointDiscoveryMetadata endpointDiscoveryMetadata, AsyncCallback callback, object state)
        {
            this.RemoveOnlineService(endpointDiscoveryMetadata);
            return new OnOfflineAnnouncementAsyncResult(callback, state);
        }

        protected override void OnEndOfflineAnnouncement(IAsyncResult result)
        {
            OnOfflineAnnouncementAsyncResult.End(result);
        }

        // OnBeginFind method is called when a Probe request message is received by the Proxy
        protected override IAsyncResult OnBeginFind(FindRequestContext findRequestContext, AsyncCallback callback, object state)
        {
            this.MatchFromOnlineService(findRequestContext);
            return new OnFindAsyncResult(callback, state);
        }

        protected override void OnEndFind(IAsyncResult result)
        {
            OnFindAsyncResult.End(result);
        }

        // OnBeginFind method is called when a Resolve request message is received by the Proxy
        protected override IAsyncResult OnBeginResolve(ResolveCriteria resolveCriteria, AsyncCallback callback, object state)
        {
            return new OnResolveAsyncResult(this.MatchFromOnlineService(resolveCriteria), callback, state);
        }

        protected override EndpointDiscoveryMetadata OnEndResolve(IAsyncResult result)
        {
            return OnResolveAsyncResult.End(result);
        }

        // The following are helper methods required by the Proxy implementation
        void AddOnlineService(EndpointDiscoveryMetadata endpointDiscoveryMetadata)
        {
            lock (this.onlineServices)
            {
                this.onlineServices[endpointDiscoveryMetadata.Address] = endpointDiscoveryMetadata;
            }

            PrintDiscoveryMetadata(endpointDiscoveryMetadata, "Adding");
        }

        void RemoveOnlineService(EndpointDiscoveryMetadata endpointDiscoveryMetadata)
        {
            if (endpointDiscoveryMetadata != null)
            {
                lock (this.onlineServices)
                {
                    this.onlineServices.Remove(endpointDiscoveryMetadata.Address);
                }

                PrintDiscoveryMetadata(endpointDiscoveryMetadata, "Removing");
            }
        }

        void MatchFromOnlineService(FindRequestContext findRequestContext)
        {
            lock (this.onlineServices)
            {
                foreach (EndpointDiscoveryMetadata endpointDiscoveryMetadata in this.onlineServices.Values)
                {
                    if (findRequestContext.Criteria.IsMatch(endpointDiscoveryMetadata))
                    {
                        findRequestContext.AddMatchingEndpoint(endpointDiscoveryMetadata);
                    }
                }
            }
        }

        EndpointDiscoveryMetadata MatchFromOnlineService(ResolveCriteria criteria)
        {
            EndpointDiscoveryMetadata matchingEndpoint = null;
            lock (this.onlineServices)
            {
                foreach (EndpointDiscoveryMetadata endpointDiscoveryMetadata in this.onlineServices.Values)
                {
                    if (criteria.Address == endpointDiscoveryMetadata.Address)
                    {
                        matchingEndpoint = endpointDiscoveryMetadata;
                    }
                }
            }
            return matchingEndpoint;
        }

        void PrintDiscoveryMetadata(EndpointDiscoveryMetadata endpointDiscoveryMetadata, string verb)
        {
            Console.WriteLine("\n**** " + verb + " service of the following type from cache. ");
            foreach (XmlQualifiedName contractName in endpointDiscoveryMetadata.ContractTypeNames)
            {
                Console.WriteLine("** " + contractName.ToString());
                break;
            }
            Console.WriteLine("**** Operation Completed");
        }

        sealed class OnOnlineAnnouncementAsyncResult : AsyncResult
        {
            public OnOnlineAnnouncementAsyncResult(AsyncCallback callback, object state)
                : base(callback, state)
            {
                this.Complete(true);
            }

            public static void End(IAsyncResult result)
            {
                AsyncResult.End<OnOnlineAnnouncementAsyncResult>(result);
            }
        }

        sealed class OnOfflineAnnouncementAsyncResult : AsyncResult
        {
            public OnOfflineAnnouncementAsyncResult(AsyncCallback callback, object state)
                : base(callback, state)
            {
                this.Complete(true);
            }

            public static void End(IAsyncResult result)
            {
                AsyncResult.End<OnOfflineAnnouncementAsyncResult>(result);
            }
        }

        sealed class OnFindAsyncResult : AsyncResult
        {
            public OnFindAsyncResult(AsyncCallback callback, object state)
                : base(callback, state)
            {
                this.Complete(true);
            }

            public static void End(IAsyncResult result)
            {
                AsyncResult.End<OnFindAsyncResult>(result);
            }
        }

        sealed class OnResolveAsyncResult : AsyncResult
        {
            EndpointDiscoveryMetadata matchingEndpoint;

            public OnResolveAsyncResult(EndpointDiscoveryMetadata matchingEndpoint, AsyncCallback callback, object state)
                : base(callback, state)
            {
                this.matchingEndpoint = matchingEndpoint;
                this.Complete(true);
            }

            public static EndpointDiscoveryMetadata End(IAsyncResult result)
            {
                OnResolveAsyncResult thisPtr = AsyncResult.End<OnResolveAsyncResult>(result);
                return thisPtr.matchingEndpoint;
            }
        }
    }
}
```

```csharp
// AsyncResult.cs
//----------------------------------------------------------------
// Copyright (c) Microsoft Corporation.  All rights reserved.
//----------------------------------------------------------------

using System;
using System.Threading;

namespace Microsoft.Samples.Discovery
{
    abstract class AsyncResult : IAsyncResult
    {
        AsyncCallback callback;
        bool completedSynchronously;
        bool endCalled;
        Exception exception;
        bool isCompleted;
        ManualResetEvent manualResetEvent;
        object state;
        object thisLock;

        protected AsyncResult(AsyncCallback callback, object state)
        {
            this.callback = callback;
            this.state = state;
            this.thisLock = new object();
        }

        public object AsyncState
        {
            get
            {
                return state;
            }
        }

        public WaitHandle AsyncWaitHandle
        {
            get
            {
                if (manualResetEvent != null)
                {
                    return manualResetEvent;
                }
                lock (ThisLock)
                {
                    manualResetEvent ??= new ManualResetEvent(isCompleted);
                }
                return manualResetEvent;
            }
        }

        public bool CompletedSynchronously
        {
            get
            {
                return completedSynchronously;
            }
        }

        public bool IsCompleted
        {
            get
            {
                return isCompleted;
            }
        }

        object ThisLock
        {
            get
            {
                return this.thisLock;
            }
        }

        protected static TAsyncResult End<TAsyncResult>(IAsyncResult result)
            where TAsyncResult : AsyncResult
        {
            if (result == null)
            {
                throw new ArgumentNullException("result");
            }

            TAsyncResult asyncResult = result as TAsyncResult;

            if (asyncResult == null)
            {
                throw new ArgumentException("Invalid async result.", "result");
            }

            if (asyncResult.endCalled)
            {
                throw new InvalidOperationException("Async object already ended.");
            }

            asyncResult.endCalled = true;

            if (!asyncResult.isCompleted)
            {
                asyncResult.AsyncWaitHandle.WaitOne();
            }

            if (asyncResult.manualResetEvent != null)
            {
                asyncResult.manualResetEvent.Close();
            }

            if (asyncResult.exception != null)
            {
                throw asyncResult.exception;
            }

            return asyncResult;
        }

        protected void Complete(bool completedSynchronously)
        {
            if (isCompleted)
            {
                throw new InvalidOperationException("This async result is already completed.");
            }

            this.completedSynchronously = completedSynchronously;

            if (completedSynchronously)
            {
                this.isCompleted = true;
            }
            else
            {
                lock (ThisLock)
                {
                    this.isCompleted = true;
                    if (this.manualResetEvent != null)
                    {
                        this.manualResetEvent.Set();
                    }
                }
            }

            if (callback != null)
            {
                callback(this);
            }
        }

        protected void Complete(bool completedSynchronously, Exception exception)
        {
            this.exception = exception;
            Complete(completedSynchronously);
        }
    }
}
```

```csharp
// program.cs
//----------------------------------------------------------------
// Copyright (c) Microsoft Corporation.  All rights reserved.
//----------------------------------------------------------------

using System;
using System.ServiceModel;
using System.ServiceModel.Discovery;

namespace Microsoft.Samples.Discovery
{
    class Program
    {
        public static void Main()
        {
            Uri probeEndpointAddress = new Uri("net.tcp://localhost:8001/Probe");
            Uri announcementEndpointAddress = new Uri("net.tcp://localhost:9021/Announcement");

            // Host the DiscoveryProxy service
            ServiceHost proxyServiceHost = new ServiceHost(new DiscoveryProxyService());

            try
            {
                // Add DiscoveryEndpoint to receive Probe and Resolve messages
                DiscoveryEndpoint discoveryEndpoint = new DiscoveryEndpoint(new NetTcpBinding(), new EndpointAddress(probeEndpointAddress));
                discoveryEndpoint.IsSystemEndpoint = false;

                // Add AnnouncementEndpoint to receive Hello and Bye announcement messages
                AnnouncementEndpoint announcementEndpoint = new AnnouncementEndpoint(new NetTcpBinding(), new EndpointAddress(announcementEndpointAddress));

                proxyServiceHost.AddServiceEndpoint(discoveryEndpoint);
                proxyServiceHost.AddServiceEndpoint(announcementEndpoint);

                proxyServiceHost.Open();

                Console.WriteLine("Proxy Service started.");
                Console.WriteLine();
                Console.WriteLine("Press <ENTER> to terminate the service.");
                Console.WriteLine();
                Console.ReadLine();

                proxyServiceHost.Close();
            }
            catch (CommunicationException e)
            {
                Console.WriteLine(e.Message);
            }
            catch (TimeoutException e)
            {
                Console.WriteLine(e.Message);
            }

            if (proxyServiceHost.State != CommunicationState.Closed)
            {
                Console.WriteLine("Aborting the service...");
                proxyServiceHost.Abort();
            }
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="36b1a-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="36b1a-176">See also</span></span>

- [<span data-ttu-id="36b1a-177">Información general de Detección de WCF</span><span class="sxs-lookup"><span data-stu-id="36b1a-177">WCF Discovery Overview</span></span>](wcf-discovery-overview.md)
- [<span data-ttu-id="36b1a-178">Procedimiento para implementar un servicio reconocible que se registra con el proxy de detección</span><span class="sxs-lookup"><span data-stu-id="36b1a-178">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](discoverable-service-that-registers-with-the-discovery-proxy.md)
- [<span data-ttu-id="36b1a-179">Procedimiento para implementar una aplicación cliente que usa el proxy de detección para buscar un servicio</span><span class="sxs-lookup"><span data-stu-id="36b1a-179">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](client-app-discovery-proxy-to-find-a-service.md)
- [<span data-ttu-id="36b1a-180">Procedimiento para probar el proxy de detección</span><span class="sxs-lookup"><span data-stu-id="36b1a-180">How to: Test the Discovery Proxy</span></span>](how-to-test-the-discovery-proxy.md)
