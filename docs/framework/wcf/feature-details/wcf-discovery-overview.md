---
title: Información general de Detección de WCF
ms.date: 03/30/2017
ms.assetid: 84fad0e4-23b1-45b5-a2d4-c9cdf90bbb22
ms.openlocfilehash: 5876605f5096bfb75c18680faaef4ba0cd15c082
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281422"
---
# <a name="wcf-discovery-overview"></a><span data-ttu-id="1376c-102">Información general de Detección de WCF</span><span class="sxs-lookup"><span data-stu-id="1376c-102">WCF Discovery Overview</span></span>

<span data-ttu-id="1376c-103">Las API de detección proporcionan un modelo de programación unificado para la detección y la publicación dinámica de servicios Web mediante el protocolo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="1376c-103">The Discovery APIs provide a unified programming model for the dynamic publication and discovery of Web services using the WS-Discovery protocol.</span></span> <span data-ttu-id="1376c-104">Estas API permiten a los servicios publicarse y a los clientes encontrar los servicios publicados.</span><span class="sxs-lookup"><span data-stu-id="1376c-104">These APIs allow services to publish themselves and clients to find published services.</span></span> <span data-ttu-id="1376c-105">Una vez que un servicio es reconocible, tiene la capacidad de enviar mensajes de anuncio, así como realizar escuchas y responder a solicitudes de detección.</span><span class="sxs-lookup"><span data-stu-id="1376c-105">Once a service is made discoverable, the service has the ability to send announcement messages as well as listen for and respond to discovery requests.</span></span> <span data-ttu-id="1376c-106">Los servicios reconocibles pueden enviar mensajes de Hola para anunciar su llegada a la red, así como mensajes de Adiós para anunciar su salida de la red.</span><span class="sxs-lookup"><span data-stu-id="1376c-106">Discoverable services can send Hello messages to announce their arrival on a network and Bye messages to announce their departure from a network.</span></span> <span data-ttu-id="1376c-107">Para encontrar un servicio, los clientes envían a una solicitud `Probe` que contiene criterios específicos, como tipos de contratos de servicios, palabras clave y ámbito de red.</span><span class="sxs-lookup"><span data-stu-id="1376c-107">To find a service, clients send a `Probe` request that contains specific criteria such as service contract type, keywords, and scope on the network.</span></span> <span data-ttu-id="1376c-108">Los servicios reciben la solicitud `Probe` y determinan si coinciden con los criterios.</span><span class="sxs-lookup"><span data-stu-id="1376c-108">Services receive the `Probe` request and determine whether they match the criteria.</span></span> <span data-ttu-id="1376c-109">Si un servicio coincide, responde devolviendo un mensaje `ProbeMatch` al cliente con la información necesaria para ponerse en contacto con el servicio.</span><span class="sxs-lookup"><span data-stu-id="1376c-109">If a service matches, it responds by sending a `ProbeMatch` message back to the client with the information necessary to contact the service.</span></span> <span data-ttu-id="1376c-110">Los clientes también pueden enviar solicitudes `Resolve` para buscar servicios que pueden haber cambiado la dirección de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="1376c-110">Clients can also send `Resolve` requests that allow them to find services that may have changed their endpoint address.</span></span> <span data-ttu-id="1376c-111">Los servicios coincidentes responden a las solicitudes `Resolve` devolviendo un mensaje `ResolveMatch` al cliente.</span><span class="sxs-lookup"><span data-stu-id="1376c-111">Matching services respond to `Resolve` requests by sending a `ResolveMatch` message back to the client.</span></span>  
  
## <a name="ad-hoc-and-managed-modes"></a><span data-ttu-id="1376c-112">Modos ad hoc y administrados</span><span class="sxs-lookup"><span data-stu-id="1376c-112">Ad-Hoc and Managed Modes</span></span>  

 <span data-ttu-id="1376c-113">Las API de detección admiten dos modos diferentes: administrado y ad hoc.</span><span class="sxs-lookup"><span data-stu-id="1376c-113">The Discovery API supports two different modes: Managed and Ad-Hoc.</span></span> <span data-ttu-id="1376c-114">En el modo administrado, hay un servidor centralizado, denominado proxy de detección, que contiene información sobre los servicios disponibles.</span><span class="sxs-lookup"><span data-stu-id="1376c-114">In Managed mode there is a centralized server called a discovery proxy that maintains information about available services.</span></span> <span data-ttu-id="1376c-115">El proxy de detección se puede rellenar con información sobre servicios de diferentes maneras.</span><span class="sxs-lookup"><span data-stu-id="1376c-115">The discovery proxy can be populated with information about services in a variety of ways.</span></span> <span data-ttu-id="1376c-116">Por ejemplo, los servicios pueden enviar mensajes de anuncio durante el inicio al proxy de detección, o el proxy puede leer datos de una base de datos o un archivo de configuración para determinar qué servicios están disponibles.</span><span class="sxs-lookup"><span data-stu-id="1376c-116">For example, services can send announcement messages during start up to the discovery proxy or the proxy may read data from a database or a configuration file to determine what services are available.</span></span> <span data-ttu-id="1376c-117">El modo en que se rellena el proxy de detección depende por completo del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="1376c-117">How the discovery proxy is populated is completely up to the developer.</span></span> <span data-ttu-id="1376c-118">Los clientes utilizan el proxy de detección para recuperar información sobre servicios disponibles.</span><span class="sxs-lookup"><span data-stu-id="1376c-118">Clients use the discovery proxy to retrieve information about available services.</span></span> <span data-ttu-id="1376c-119">Cuando un cliente busca un servicio, envía un mensaje `Probe` al proxy de detección y el proxy determina si alguno de los servicios que conoce coincide con el servicio que busca el cliente.</span><span class="sxs-lookup"><span data-stu-id="1376c-119">When a client searches for a service it sends a `Probe` message to the discovery proxy and the proxy determines whether any of the services it knows about match the service the client is searching for.</span></span> <span data-ttu-id="1376c-120">Si hay coincidencias, el proxy de detección devuelve una respuesta `ProbeMatch` al cliente.</span><span class="sxs-lookup"><span data-stu-id="1376c-120">If there are matches the discovery proxy sends a `ProbeMatch` response back to the client.</span></span> <span data-ttu-id="1376c-121">A continuación, el cliente puede ponerse en contacto con el servicio de forma directa a través de la información de servicio devuelta por el proxy.</span><span class="sxs-lookup"><span data-stu-id="1376c-121">The client can then contact the service directly using the service information returned from the proxy.</span></span> <span data-ttu-id="1376c-122">El principio básico del modo administrado es que las solicitudes de detección se envían en modo de unidifusión a una autoridad, el proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="1376c-122">The key principle behind Managed mode is that the discovery requests are sent in a unicast manner to one authority, the discovery proxy.</span></span> <span data-ttu-id="1376c-123">El sistema .NET Framework contiene componentes clave que le permiten compilar su propio proxy.</span><span class="sxs-lookup"><span data-stu-id="1376c-123">The .NET Framework contains key components that allow you to build your own proxy.</span></span> <span data-ttu-id="1376c-124">Los clientes y los servicios pueden buscar el proxy a través de varios métodos:</span><span class="sxs-lookup"><span data-stu-id="1376c-124">Clients and services can locate the proxy by multiple methods:</span></span>  
  
- <span data-ttu-id="1376c-125">El proxy puede responder a los mensajes ad hoc.</span><span class="sxs-lookup"><span data-stu-id="1376c-125">The proxy can respond to ad-hoc messages.</span></span>  
  
- <span data-ttu-id="1376c-126">El proxy puede enviar un mensaje de anuncio durante el inicio.</span><span class="sxs-lookup"><span data-stu-id="1376c-126">The proxy can send an announcement message during start up.</span></span>  
  
- <span data-ttu-id="1376c-127">Los clientes y los servicios se pueden escribir para buscar un punto de conexión conocido concreto.</span><span class="sxs-lookup"><span data-stu-id="1376c-127">Clients and services can be written to look for a specific well-known endpoint.</span></span>  
  
 <span data-ttu-id="1376c-128">En modo ad hoc, no hay ningún servidor centralizado.</span><span class="sxs-lookup"><span data-stu-id="1376c-128">In Ad-Hoc mode, there is no centralized server.</span></span> <span data-ttu-id="1376c-129">Todos los mensajes de detección, como anuncios de servicio y solicitudes de clientes, se envían en modo de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="1376c-129">All discovery messages such as service announcements and client requests are sent in a multicast fashion.</span></span> <span data-ttu-id="1376c-130">De forma predeterminada, .NET Framework contiene soporte para la detección ad hoc en el protocolo UDP.</span><span class="sxs-lookup"><span data-stu-id="1376c-130">By default the .NET Framework contains support for Ad-Hoc discovery over the UDP protocol.</span></span> <span data-ttu-id="1376c-131">Por ejemplo, si un servicio se configura para enviar un anuncio de Hola durante el inicio, lo manda en una dirección de multidifusión conocida mediante el protocolo UDP.</span><span class="sxs-lookup"><span data-stu-id="1376c-131">For example, if a service is configured to send out a Hello announcement on start up, it sends it out over a well-known, multicast address using the UDP protocol.</span></span> <span data-ttu-id="1376c-132">Los clientes tienen que realizar escuchas activas de estos anuncios y procesarlos de forma correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1376c-132">Clients have to actively listen for these announcements and process them accordingly.</span></span> <span data-ttu-id="1376c-133">Cuando un cliente envía un mensaje `Probe` para un servicio, se envía a través de la red mediante un protocolo de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="1376c-133">When a client sends a `Probe` message for a service it is sent over the network using a multicast protocol.</span></span> <span data-ttu-id="1376c-134">Cada servicio que recibe la solicitud determina si ésta coincide con los criterios del mensaje `Probe` y responde directamente al cliente con un mensaje `ProbeMatch` si el servicio coincide con los criterios especificados en el mensaje `Probe`.</span><span class="sxs-lookup"><span data-stu-id="1376c-134">Each service that receives the request determines whether it matches the criteria in the `Probe` message and responds directly to the client with a `ProbeMatch` message if the service matches the criteria specified in the `Probe` message.</span></span>  
  
## <a name="benefits-of-using-wcf-discovery"></a><span data-ttu-id="1376c-135">Ventajas de utilizar la Detección de WCF</span><span class="sxs-lookup"><span data-stu-id="1376c-135">Benefits of Using WCF Discovery</span></span>  

 <span data-ttu-id="1376c-136">Dado que la Detección de WCF se implementa mediante el protocolo WS-Discovery, es interoperable con otros clientes, servicios y proxys que también implementan WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="1376c-136">Because WCF Discovery is implemented using the WS-Discovery protocol it is interoperable with other clients, services, and proxies that implement WS-Discovery as well.</span></span> <span data-ttu-id="1376c-137">La Detección de WCF se compila en las API de WCF existentes, lo que facilita la adición de la funcionalidad de detección a los servicios y clientes existentes.</span><span class="sxs-lookup"><span data-stu-id="1376c-137">WCF Discovery is built upon the existing WCF APIs, which makes it easy to add Discovery functionality to your existing services and clients.</span></span> <span data-ttu-id="1376c-138">La detectabilidad del servicio se puede agregar con facilidad a través de la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1376c-138">Service discoverability can be easily added through the application configuration settings.</span></span> <span data-ttu-id="1376c-139">Además, la Detección de WCF también permite usar el protocolo de detección en otros transportes como redes del mismo nivel, superposiciones de nomenclatura y HTTP.</span><span class="sxs-lookup"><span data-stu-id="1376c-139">In addition, WCF Discovery also supports using the discovery protocol over other transports such as peer net, naming overlay, and HTTP.</span></span> <span data-ttu-id="1376c-140">La Detección de WCF proporciona soporte para un modo administrado de operación en el que se usa un proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="1376c-140">WCF Discovery provides support for a Managed mode of operation where a discovery proxy is used.</span></span> <span data-ttu-id="1376c-141">Esto puede reducir el tráfico de red, ya que los mensajes se envían directamente al proxy de detección en lugar de enviar mensajes de multidifusión a toda la red.</span><span class="sxs-lookup"><span data-stu-id="1376c-141">This can reduce network traffic as messages are sent directly to the discovery proxy instead of sending multicast messages to the entire network.</span></span> <span data-ttu-id="1376c-142">La Detección de WCF también permite una mayor flexibilidad al trabajar con servicios Web.</span><span class="sxs-lookup"><span data-stu-id="1376c-142">WCF Discovery also allows for more flexibility when working with Web services.</span></span> <span data-ttu-id="1376c-143">Por ejemplo, puede cambiar la dirección de un servicio sin tener que reconfigurar ni el cliente ni el servicio.</span><span class="sxs-lookup"><span data-stu-id="1376c-143">For example, you can change the address of a service without having to reconfigure the client or the service.</span></span> <span data-ttu-id="1376c-144">Cuando un cliente debe acceder al servicio, puede emitir un mensaje `Probe` a través de una solicitud `Find` y esperar a que el servicio responda con su dirección actual.</span><span class="sxs-lookup"><span data-stu-id="1376c-144">When a client must access the service it can issue a `Probe` message through a `Find` request and expect the service to respond with its current address.</span></span> <span data-ttu-id="1376c-145">La Detección de WCF permite a un cliente buscar un servicio en función de diversos criterios, incluidos tipos de contrato, elementos de enlace, espacio de nombres, ámbito y palabras clave o números de versión.</span><span class="sxs-lookup"><span data-stu-id="1376c-145">WCF Discovery allows a client to search for a service based on different criteria including contract types, binding elements, namespace, scope, and keywords or version numbers.</span></span> <span data-ttu-id="1376c-146">La Detección de WCF habilita la detección de diseño y de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1376c-146">WCF Discovery enables runtime and design time discovery.</span></span> <span data-ttu-id="1376c-147">La adición de la detección a la aplicación se puede usar para habilitar otros escenarios como tolerancia a errores y configuración automática.</span><span class="sxs-lookup"><span data-stu-id="1376c-147">Adding discovery to your application can be used to enable other scenarios such as fault tolerance and auto configuration.</span></span>  
  
## <a name="service-publication"></a><span data-ttu-id="1376c-148">Publicación de servicios</span><span class="sxs-lookup"><span data-stu-id="1376c-148">Service Publication</span></span>  

 <span data-ttu-id="1376c-149">Para hacer un servicio reconocible, debe agregarse <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> al host de servicio, así como un extremo de detección para especificar dónde realizar escuchas para los mensajes de detección.</span><span class="sxs-lookup"><span data-stu-id="1376c-149">To make a service discoverable, a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> must be added to the service host and a discovery endpoint must be added to specify where to listen for discovery messages.</span></span> <span data-ttu-id="1376c-150">El siguiente ejemplo de código muestra cómo se puede modificar un servicio auto-hospedado para hacerlo reconocible.</span><span class="sxs-lookup"><span data-stu-id="1376c-150">The following code example shows how a self-hosted service can be modified to make it discoverable.</span></span>  
  
```csharp  
Uri baseAddress = new Uri($"http://{System.Net.Dns.GetHostName()}:8000/discovery/scenarios/calculatorservice/{Guid.NewGuid().ToString()}/");

// Create a ServiceHost for the CalculatorService type.
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
{
    // Add calculator endpoint
    serviceHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), string.Empty);

    // ** DISCOVERY ** //
    // Make the service discoverable by adding the discovery behavior
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());

    // ** DISCOVERY ** //
    // Add the discovery endpoint that specifies where to publish the services
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());

    // Open the ServiceHost to create listeners and start listening for messages.
    serviceHost.Open();

    // The service can now be accessed.
    Console.WriteLine("Press <ENTER> to terminate service.");
    Console.ReadLine();
}
```  
  
 <span data-ttu-id="1376c-151">Debe agregarse una instancia <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> a una descripción de servicio para que el servicio sea reconocible.</span><span class="sxs-lookup"><span data-stu-id="1376c-151">A <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> instance must be added to a service description for the service to be discoverable.</span></span> <span data-ttu-id="1376c-152">Debe agregarse una instancia <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> al host de servicio para indicar al servicio dónde realizar escuchas para las solicitudes de detección.</span><span class="sxs-lookup"><span data-stu-id="1376c-152">A <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instance must be added to the service host to tell the service where to listen for discovery requests.</span></span> <span data-ttu-id="1376c-153">En este ejemplo, se agrega <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> (que se deriva de <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>) para especificar que el servicio debe realizar escuchas de solicitudes de detección en el transporte multidifusión de UDP.</span><span class="sxs-lookup"><span data-stu-id="1376c-153">In this example, a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> (which is derived from <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>) is added to specify that the service should listen for discovery requests over the UDP multicast transport.</span></span> <span data-ttu-id="1376c-154"><xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> se utiliza para la detección ad hoc porque todos los mensajes se envían en modo de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="1376c-154">The <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> is used for Ad-Hoc discovery because all messages are sent in a multicast fashion.</span></span>  
  
## <a name="announcement"></a><span data-ttu-id="1376c-155">Anuncio</span><span class="sxs-lookup"><span data-stu-id="1376c-155">Announcement</span></span>  

 <span data-ttu-id="1376c-156">De forma predeterminada, la publicación del servicio no manda mensajes de anuncio.</span><span class="sxs-lookup"><span data-stu-id="1376c-156">By default, service publication does not send out announcement messages.</span></span> <span data-ttu-id="1376c-157">El servicio se debe configurar para mandar mensajes de anuncio.</span><span class="sxs-lookup"><span data-stu-id="1376c-157">The service must be configured to send out announcement messages.</span></span> <span data-ttu-id="1376c-158">Esto proporciona una flexibilidad adicional a los escritores del servicio, ya que pueden anunciar el servicio de forma independiente de la realización de escuchas de mensajes de detección.</span><span class="sxs-lookup"><span data-stu-id="1376c-158">This provides additional flexibility for service writers because they can announce the service separately from listening for discovery messages.</span></span> <span data-ttu-id="1376c-159">El anuncio de servicio también se puede usar como mecanismo de registro de los servicios con un proxy de detección u otros registros del servicio.</span><span class="sxs-lookup"><span data-stu-id="1376c-159">Service announcement can also be used as a mechanism for registering services with a discovery proxy or other service registries.</span></span> <span data-ttu-id="1376c-160">El siguiente código muestra cómo configurar un servicio para enviar mensajes de anuncio en un enlace de UDP.</span><span class="sxs-lookup"><span data-stu-id="1376c-160">The following code shows how to configure a service to send announcement messages over a UDP binding.</span></span>  
  
```csharp  
Uri baseAddress = new Uri($"http://{System.Net.Dns.GetHostName()}:8000/discovery/scenarios/calculatorservice/{Guid.NewGuid().ToString()}/");

// Create a ServiceHost for the CalculatorService type.
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
{
    // Add calculator endpoint
    serviceHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), string.Empty);

    // ** DISCOVERY ** //
    // Make the service discoverable by adding the discovery behavior
    ServiceDiscoveryBehavior discoveryBehavior = new ServiceDiscoveryBehavior();
    serviceHost.Description.Behaviors.Add(discoveryBehavior);

    // Send announcements on UDP multicast transport
    discoveryBehavior.AnnouncementEndpoints.Add(
      new UdpAnnouncementEndpoint());

    // ** DISCOVERY ** //
    // Add the discovery endpoint that specifies where to publish the services
    serviceHost.Description.Endpoints.Add(new UdpDiscoveryEndpoint());

    // Open the ServiceHost to create listeners and start listening for messages.
    serviceHost.Open();

    // The service can now be accessed.
    Console.WriteLine("Press <ENTER> to terminate service.");
    Console.ReadLine();
}
```  
  
## <a name="service-discovery"></a><span data-ttu-id="1376c-161">Detección de servicios</span><span class="sxs-lookup"><span data-stu-id="1376c-161">Service Discovery</span></span>  

 <span data-ttu-id="1376c-162">Una aplicación cliente puede usar la clase <xref:System.ServiceModel.Discovery.DiscoveryClient> para buscar servicios.</span><span class="sxs-lookup"><span data-stu-id="1376c-162">A client application can use the <xref:System.ServiceModel.Discovery.DiscoveryClient> class to find services.</span></span> <span data-ttu-id="1376c-163">El desarrollador crea una instancia de la clase <xref:System.ServiceModel.Discovery.DiscoveryClient> que pasa un punto de conexión de detección que especifica dónde se deben enviar los mensajes `Probe` o `Resolve`.</span><span class="sxs-lookup"><span data-stu-id="1376c-163">The developer creates an instance of the <xref:System.ServiceModel.Discovery.DiscoveryClient> class that passes in a discovery endpoint that specifies where to send `Probe` or `Resolve` messages.</span></span> <span data-ttu-id="1376c-164">A continuación, el cliente llama a <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, que especifica los criterios de búsqueda dentro de una instancia <xref:System.ServiceModel.Discovery.FindCriteria>.</span><span class="sxs-lookup"><span data-stu-id="1376c-164">The client then calls <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> that specifies search criteria within a <xref:System.ServiceModel.Discovery.FindCriteria> instance.</span></span> <span data-ttu-id="1376c-165">Si se encuentran servicios correspondientes, <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> devuelve una recopilación de <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>.</span><span class="sxs-lookup"><span data-stu-id="1376c-165">If matching services are found, <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> returns a collection of <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>.</span></span> <span data-ttu-id="1376c-166">El siguiente código muestra cómo llamar al método `Find` y, a continuación, conectarse a un servicio detectado.</span><span class="sxs-lookup"><span data-stu-id="1376c-166">The following code shows how to call the `Find` method and then connect to a discovered service.</span></span>  
  
```csharp  
class Client
{
    static EndpointAddress serviceAddress;
  
    static void Main()
    {  
        if (FindService())
        {
            InvokeService();
        }
    }  
  
    // ** DISCOVERY ** //  
    static bool FindService()  
    {  
        Console.WriteLine("\nFinding Calculator Service ..");  
        DiscoveryClient discoveryClient =
            new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
        Collection<EndpointDiscoveryMetadata> calculatorServices =
            (Collection<EndpointDiscoveryMetadata>)discoveryClient.Find(new FindCriteria(typeof(ICalculator))).Endpoints;  
  
        discoveryClient.Close();  
  
        if (calculatorServices.Count == 0)  
        {  
            Console.WriteLine("\nNo services are found.");  
            return false;  
        }  
        else  
        {  
            serviceAddress = calculatorServices[0].Address;  
            return true;  
        }  
    }  
  
    static void InvokeService()  
    {  
        Console.WriteLine("\nInvoking Calculator Service at {0}\n", serviceAddress);  
  
        // Create a client  
        CalculatorClient client = new CalculatorClient();  
        client.Endpoint.Address = serviceAddress;  
        client.Add(10,3);  
    }
}  
```  
  
## <a name="discovery-and-message-level-security"></a><span data-ttu-id="1376c-167">Detección y seguridad de nivel de mensaje</span><span class="sxs-lookup"><span data-stu-id="1376c-167">Discovery and Message Level Security</span></span>  

 <span data-ttu-id="1376c-168">Al usar la seguridad de nivel de mensaje, es necesario especificar una <xref:System.ServiceModel.EndpointIdentity> en el punto de conexión de detección de servicio y una <xref:System.ServiceModel.EndpointIdentity> coincidente en el punto de conexión de detección de cliente.</span><span class="sxs-lookup"><span data-stu-id="1376c-168">When using message level security it is necessary to specify an <xref:System.ServiceModel.EndpointIdentity> on the service discovery endpoint and a matching <xref:System.ServiceModel.EndpointIdentity> on the client discovery endpoint.</span></span> <span data-ttu-id="1376c-169">Para obtener más información acerca de la seguridad de nivel de mensaje, consulte [seguridad de mensajes](message-security-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="1376c-169">For more information about message level security, see [Message Security](message-security-in-wcf.md).</span></span>  
  
## <a name="discovery-and-web-hosted-services"></a><span data-ttu-id="1376c-170">Servicios de hospedaje web y detección</span><span class="sxs-lookup"><span data-stu-id="1376c-170">Discovery and Web Hosted Services</span></span>  

 <span data-ttu-id="1376c-171">Para que los servicios WCF puedan detectarse, deben estar ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="1376c-171">In order for WCF services to be discoverable they must be running.</span></span> <span data-ttu-id="1376c-172">Los servicios WCF hospedados en IIS o WAS no se ejecutan hasta que IIS/WAS recibe un mensaje enlazado al servicio, de modo que no pueden detectarse de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1376c-172">WCF services hosted under IIS or WAS do not run until IIS/WAS receives a message bound for the service, so they cannot be discoverable by default.</span></span>  <span data-ttu-id="1376c-173">Hay dos opciones para hacer que los servicios hospedados en web puedan detectarse:</span><span class="sxs-lookup"><span data-stu-id="1376c-173">There are two options for making Web-Hosted services discoverable:</span></span>  
  
1. <span data-ttu-id="1376c-174">Usar la característica de inicio automático de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="1376c-174">Use the Windows Server AppFabric Auto-Start feature</span></span>  
  
2. <span data-ttu-id="1376c-175">Usar un proxy de detección para comunicarse en nombre del servicio</span><span class="sxs-lookup"><span data-stu-id="1376c-175">Use a discovery proxy to communicate on behalf of the service</span></span>  
  
 <span data-ttu-id="1376c-176">Windows Server AppFabric tiene una característica de inicio automático que permite que un servicio se inicie antes de recibir ningún mensaje.</span><span class="sxs-lookup"><span data-stu-id="1376c-176">Windows Server AppFabric has an Auto-Start feature that will allow a service to be started before receiving any messages.</span></span> <span data-ttu-id="1376c-177">Con este inicio automático establecido, un servicio hospedado por IIS/WAS se puede configurar como detectable.</span><span class="sxs-lookup"><span data-stu-id="1376c-177">With this Auto-Start set, an IIS/WAS hosted service can be configured to be discoverable.</span></span> <span data-ttu-id="1376c-178">Para obtener más información acerca de la característica de inicio automático, consulte [característica de inicio automático de Windows Server AppFabric](/previous-versions/appfabric/ee677260(v=azure.10)).</span><span class="sxs-lookup"><span data-stu-id="1376c-178">For more information about the Auto-Start feature see, [Windows Server AppFabric Auto-Start Feature](/previous-versions/appfabric/ee677260(v=azure.10)).</span></span> <span data-ttu-id="1376c-179">Además de activar la característica de inicio automático, debe configurar el servicio para la detección.</span><span class="sxs-lookup"><span data-stu-id="1376c-179">Along with turning on the Auto-Start feature, you must configure the service for discovery.</span></span> <span data-ttu-id="1376c-180">Para obtener más información, consulte [Cómo: agregar detectabilidad a un servicio WCF y configurar la](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)[detección en un archivo de configuración](configuring-discovery-in-a-configuration-file.md)mediante programación.</span><span class="sxs-lookup"><span data-stu-id="1376c-180">For more information, see [How to: Programmatically Add Discoverability to a WCF Service and Client](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)[Configuring Discovery in a Configuration File](configuring-discovery-in-a-configuration-file.md).</span></span>  
  
 <span data-ttu-id="1376c-181">Se puede usar un proxy de detección para comunicarse en nombre del servicio WCF cuando el servicio no se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="1376c-181">A discovery proxy can be used to communicate on behalf of the WCF service when the service is not running.</span></span> <span data-ttu-id="1376c-182">El proxy puede escuchar para sondear o resolver los mensajes, y responder al cliente.</span><span class="sxs-lookup"><span data-stu-id="1376c-182">The proxy can listen for probe or resolve messages and respond to the client.</span></span> <span data-ttu-id="1376c-183">El cliente puede entonces enviar los mensajes directamente al servicio.</span><span class="sxs-lookup"><span data-stu-id="1376c-183">The client can then send messages directly to the service.</span></span> <span data-ttu-id="1376c-184">Cuando el cliente envíe un mensaje al servicio, se creará una instancia del mismo para responderlo.</span><span class="sxs-lookup"><span data-stu-id="1376c-184">When the client sends a message to the service it will be instantiated to respond to the message.</span></span> <span data-ttu-id="1376c-185">Para obtener más información sobre la implementación de un proxy de detección, vea [implementación de un proxy de detección](implementing-a-discovery-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="1376c-185">For more information about implementing a discovery proxy see, [Implementing a Discovery Proxy](implementing-a-discovery-proxy.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1376c-186">Para que la detección de WCF funcione correctamente, todas las NIC (controlador de interfaz de red) solo deben tener una dirección IP.</span><span class="sxs-lookup"><span data-stu-id="1376c-186">For WCF Discovery to work correctly, all NICs (Network Interface Controller) should only have 1 IP address.</span></span>
