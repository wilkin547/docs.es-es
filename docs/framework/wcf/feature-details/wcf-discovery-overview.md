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
# <a name="wcf-discovery-overview"></a>Información general de Detección de WCF

Las API de detección proporcionan un modelo de programación unificado para la detección y la publicación dinámica de servicios Web mediante el protocolo WS-Discovery. Estas API permiten a los servicios publicarse y a los clientes encontrar los servicios publicados. Una vez que un servicio es reconocible, tiene la capacidad de enviar mensajes de anuncio, así como realizar escuchas y responder a solicitudes de detección. Los servicios reconocibles pueden enviar mensajes de Hola para anunciar su llegada a la red, así como mensajes de Adiós para anunciar su salida de la red. Para encontrar un servicio, los clientes envían a una solicitud `Probe` que contiene criterios específicos, como tipos de contratos de servicios, palabras clave y ámbito de red. Los servicios reciben la solicitud `Probe` y determinan si coinciden con los criterios. Si un servicio coincide, responde devolviendo un mensaje `ProbeMatch` al cliente con la información necesaria para ponerse en contacto con el servicio. Los clientes también pueden enviar solicitudes `Resolve` para buscar servicios que pueden haber cambiado la dirección de punto de conexión. Los servicios coincidentes responden a las solicitudes `Resolve` devolviendo un mensaje `ResolveMatch` al cliente.  
  
## <a name="ad-hoc-and-managed-modes"></a>Modos ad hoc y administrados  

 Las API de detección admiten dos modos diferentes: administrado y ad hoc. En el modo administrado, hay un servidor centralizado, denominado proxy de detección, que contiene información sobre los servicios disponibles. El proxy de detección se puede rellenar con información sobre servicios de diferentes maneras. Por ejemplo, los servicios pueden enviar mensajes de anuncio durante el inicio al proxy de detección, o el proxy puede leer datos de una base de datos o un archivo de configuración para determinar qué servicios están disponibles. El modo en que se rellena el proxy de detección depende por completo del desarrollador. Los clientes utilizan el proxy de detección para recuperar información sobre servicios disponibles. Cuando un cliente busca un servicio, envía un mensaje `Probe` al proxy de detección y el proxy determina si alguno de los servicios que conoce coincide con el servicio que busca el cliente. Si hay coincidencias, el proxy de detección devuelve una respuesta `ProbeMatch` al cliente. A continuación, el cliente puede ponerse en contacto con el servicio de forma directa a través de la información de servicio devuelta por el proxy. El principio básico del modo administrado es que las solicitudes de detección se envían en modo de unidifusión a una autoridad, el proxy de detección. El sistema .NET Framework contiene componentes clave que le permiten compilar su propio proxy. Los clientes y los servicios pueden buscar el proxy a través de varios métodos:  
  
- El proxy puede responder a los mensajes ad hoc.  
  
- El proxy puede enviar un mensaje de anuncio durante el inicio.  
  
- Los clientes y los servicios se pueden escribir para buscar un punto de conexión conocido concreto.  
  
 En modo ad hoc, no hay ningún servidor centralizado. Todos los mensajes de detección, como anuncios de servicio y solicitudes de clientes, se envían en modo de multidifusión. De forma predeterminada, .NET Framework contiene soporte para la detección ad hoc en el protocolo UDP. Por ejemplo, si un servicio se configura para enviar un anuncio de Hola durante el inicio, lo manda en una dirección de multidifusión conocida mediante el protocolo UDP. Los clientes tienen que realizar escuchas activas de estos anuncios y procesarlos de forma correspondiente. Cuando un cliente envía un mensaje `Probe` para un servicio, se envía a través de la red mediante un protocolo de multidifusión. Cada servicio que recibe la solicitud determina si ésta coincide con los criterios del mensaje `Probe` y responde directamente al cliente con un mensaje `ProbeMatch` si el servicio coincide con los criterios especificados en el mensaje `Probe`.  
  
## <a name="benefits-of-using-wcf-discovery"></a>Ventajas de utilizar la Detección de WCF  

 Dado que la Detección de WCF se implementa mediante el protocolo WS-Discovery, es interoperable con otros clientes, servicios y proxys que también implementan WS-Discovery. La Detección de WCF se compila en las API de WCF existentes, lo que facilita la adición de la funcionalidad de detección a los servicios y clientes existentes. La detectabilidad del servicio se puede agregar con facilidad a través de la configuración de la aplicación. Además, la Detección de WCF también permite usar el protocolo de detección en otros transportes como redes del mismo nivel, superposiciones de nomenclatura y HTTP. La Detección de WCF proporciona soporte para un modo administrado de operación en el que se usa un proxy de detección. Esto puede reducir el tráfico de red, ya que los mensajes se envían directamente al proxy de detección en lugar de enviar mensajes de multidifusión a toda la red. La Detección de WCF también permite una mayor flexibilidad al trabajar con servicios Web. Por ejemplo, puede cambiar la dirección de un servicio sin tener que reconfigurar ni el cliente ni el servicio. Cuando un cliente debe acceder al servicio, puede emitir un mensaje `Probe` a través de una solicitud `Find` y esperar a que el servicio responda con su dirección actual. La Detección de WCF permite a un cliente buscar un servicio en función de diversos criterios, incluidos tipos de contrato, elementos de enlace, espacio de nombres, ámbito y palabras clave o números de versión. La Detección de WCF habilita la detección de diseño y de tiempo de ejecución. La adición de la detección a la aplicación se puede usar para habilitar otros escenarios como tolerancia a errores y configuración automática.  
  
## <a name="service-publication"></a>Publicación de servicios  

 Para hacer un servicio reconocible, debe agregarse <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> al host de servicio, así como un extremo de detección para especificar dónde realizar escuchas para los mensajes de detección. El siguiente ejemplo de código muestra cómo se puede modificar un servicio auto-hospedado para hacerlo reconocible.  
  
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
  
 Debe agregarse una instancia <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> a una descripción de servicio para que el servicio sea reconocible. Debe agregarse una instancia <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> al host de servicio para indicar al servicio dónde realizar escuchas para las solicitudes de detección. En este ejemplo, se agrega <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> (que se deriva de <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>) para especificar que el servicio debe realizar escuchas de solicitudes de detección en el transporte multidifusión de UDP. <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> se utiliza para la detección ad hoc porque todos los mensajes se envían en modo de multidifusión.  
  
## <a name="announcement"></a>Anuncio  

 De forma predeterminada, la publicación del servicio no manda mensajes de anuncio. El servicio se debe configurar para mandar mensajes de anuncio. Esto proporciona una flexibilidad adicional a los escritores del servicio, ya que pueden anunciar el servicio de forma independiente de la realización de escuchas de mensajes de detección. El anuncio de servicio también se puede usar como mecanismo de registro de los servicios con un proxy de detección u otros registros del servicio. El siguiente código muestra cómo configurar un servicio para enviar mensajes de anuncio en un enlace de UDP.  
  
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
  
## <a name="service-discovery"></a>Detección de servicios  

 Una aplicación cliente puede usar la clase <xref:System.ServiceModel.Discovery.DiscoveryClient> para buscar servicios. El desarrollador crea una instancia de la clase <xref:System.ServiceModel.Discovery.DiscoveryClient> que pasa un punto de conexión de detección que especifica dónde se deben enviar los mensajes `Probe` o `Resolve`. A continuación, el cliente llama a <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, que especifica los criterios de búsqueda dentro de una instancia <xref:System.ServiceModel.Discovery.FindCriteria>. Si se encuentran servicios correspondientes, <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> devuelve una recopilación de <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>. El siguiente código muestra cómo llamar al método `Find` y, a continuación, conectarse a un servicio detectado.  
  
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
  
## <a name="discovery-and-message-level-security"></a>Detección y seguridad de nivel de mensaje  

 Al usar la seguridad de nivel de mensaje, es necesario especificar una <xref:System.ServiceModel.EndpointIdentity> en el punto de conexión de detección de servicio y una <xref:System.ServiceModel.EndpointIdentity> coincidente en el punto de conexión de detección de cliente. Para obtener más información acerca de la seguridad de nivel de mensaje, consulte [seguridad de mensajes](message-security-in-wcf.md).  
  
## <a name="discovery-and-web-hosted-services"></a>Servicios de hospedaje web y detección  

 Para que los servicios WCF puedan detectarse, deben estar ejecutándose. Los servicios WCF hospedados en IIS o WAS no se ejecutan hasta que IIS/WAS recibe un mensaje enlazado al servicio, de modo que no pueden detectarse de forma predeterminada.  Hay dos opciones para hacer que los servicios hospedados en web puedan detectarse:  
  
1. Usar la característica de inicio automático de Windows Server AppFabric  
  
2. Usar un proxy de detección para comunicarse en nombre del servicio  
  
 Windows Server AppFabric tiene una característica de inicio automático que permite que un servicio se inicie antes de recibir ningún mensaje. Con este inicio automático establecido, un servicio hospedado por IIS/WAS se puede configurar como detectable. Para obtener más información acerca de la característica de inicio automático, consulte [característica de inicio automático de Windows Server AppFabric](/previous-versions/appfabric/ee677260(v=azure.10)). Además de activar la característica de inicio automático, debe configurar el servicio para la detección. Para obtener más información, consulte [Cómo: agregar detectabilidad a un servicio WCF y configurar la](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)[detección en un archivo de configuración](configuring-discovery-in-a-configuration-file.md)mediante programación.  
  
 Se puede usar un proxy de detección para comunicarse en nombre del servicio WCF cuando el servicio no se está ejecutando. El proxy puede escuchar para sondear o resolver los mensajes, y responder al cliente. El cliente puede entonces enviar los mensajes directamente al servicio. Cuando el cliente envíe un mensaje al servicio, se creará una instancia del mismo para responderlo. Para obtener más información sobre la implementación de un proxy de detección, vea [implementación de un proxy de detección](implementing-a-discovery-proxy.md).  
  
> [!NOTE]
> Para que la detección de WCF funcione correctamente, todas las NIC (controlador de interfaz de red) solo deben tener una dirección IP.
