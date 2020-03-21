---
title: DiscoveryClient y DynamicEndpoint
ms.date: 03/30/2017
ms.assetid: 7cd418f0-0eab-48d1-a493-7eb907867ec3
ms.openlocfilehash: c6d87a04a6787725ad7c4546650485af932882b0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185180"
---
# <a name="discoveryclient-and-dynamicendpoint"></a><span data-ttu-id="fb924-102">DiscoveryClient y DynamicEndpoint</span><span class="sxs-lookup"><span data-stu-id="fb924-102">DiscoveryClient and DynamicEndpoint</span></span>
<span data-ttu-id="fb924-103"><xref:System.ServiceModel.Discovery.DiscoveryClient> y <xref:System.ServiceModel.Discovery.DynamicEndpoint> son dos clases usadas en el lado cliente para buscar servicios.</span><span class="sxs-lookup"><span data-stu-id="fb924-103"><xref:System.ServiceModel.Discovery.DiscoveryClient> and <xref:System.ServiceModel.Discovery.DynamicEndpoint> are two classes used on the client side to search for services.</span></span> <span data-ttu-id="fb924-104"><xref:System.ServiceModel.Discovery.DiscoveryClient> le proporciona una lista de servicios que coinciden con un conjunto concreto de criterios y le permite conectarse a los servicios.</span><span class="sxs-lookup"><span data-stu-id="fb924-104"><xref:System.ServiceModel.Discovery.DiscoveryClient> provides you with a list of services that match a specific set of criteria and allows you to connect to the services.</span></span> <span data-ttu-id="fb924-105"><xref:System.ServiceModel.Discovery.DynamicEndpoint> realiza la misma operación y además, conecta automáticamente con uno de los servicios que se encontró.</span><span class="sxs-lookup"><span data-stu-id="fb924-105"><xref:System.ServiceModel.Discovery.DynamicEndpoint> performs the same operation and in addition, automatically connects to one of the services that was found.</span></span> <span data-ttu-id="fb924-106">Cualquier punto de conexión se puede convertir en <xref:System.ServiceModel.Discovery.DynamicEndpoint>, los criterios de búsqueda también se pueden agregar a través de la configuración. Por tanto, <xref:System.ServiceModel.Discovery.DynamicEndpoint> es útil si necesita la detección en su solución pero no desea modificar la lógica del cliente; solo necesita modificar los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="fb924-106">Any endpoint can be made into a <xref:System.ServiceModel.Discovery.DynamicEndpoint>, the search criteria can also be added in configuration, thus <xref:System.ServiceModel.Discovery.DynamicEndpoint> is useful when you need discovery in your solution but do not want to modify the client logic – you only need to modify the endpoints.</span></span> <span data-ttu-id="fb924-107">Por otra parte, <xref:System.ServiceModel.Discovery.DiscoveryClient> se puede usar para obtener un control más preciso sobre la operación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="fb924-107"><xref:System.ServiceModel.Discovery.DiscoveryClient> on the other hand can be used to gain finer control over your search operation.</span></span> <span data-ttu-id="fb924-108">Más abajo, se elaboran los usos y ventajas de cada uno.</span><span class="sxs-lookup"><span data-stu-id="fb924-108">The uses and benefits of each are elaborated below.</span></span>  
  
## <a name="discoveryclient"></a><span data-ttu-id="fb924-109">DiscoveryClient</span><span class="sxs-lookup"><span data-stu-id="fb924-109">DiscoveryClient</span></span>  
 <span data-ttu-id="fb924-110"><xref:System.ServiceModel.Discovery.DiscoveryClient> define métodos Find sincrónicos y asincrónicos, así como eventos <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> y <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged>.</span><span class="sxs-lookup"><span data-stu-id="fb924-110">The <xref:System.ServiceModel.Discovery.DiscoveryClient> defines synchronous and asynchronous Find methods, <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> and <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> events.</span></span>  <span data-ttu-id="fb924-111">También define métodos Resolve sincrónicos y asincrónicos, así como un evento <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveCompleted>.</span><span class="sxs-lookup"><span data-stu-id="fb924-111">It also defines synchronous and asynchronous Resolve methods and a <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveCompleted> event.</span></span> <span data-ttu-id="fb924-112">Utilice los métodos <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> o <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> para buscar servicios.</span><span class="sxs-lookup"><span data-stu-id="fb924-112">Use the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> or <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> methods to search for services.</span></span> <span data-ttu-id="fb924-113">Ambos métodos toma una instancia <xref:System.ServiceModel.Discovery.FindCriteria> que le permite especificar los nombres de tipo de contrato, ámbitos, número máximo de resultados solicitados y reglas de coincidencia de ámbito.</span><span class="sxs-lookup"><span data-stu-id="fb924-113">Both of these methods take a <xref:System.ServiceModel.Discovery.FindCriteria> instance that allows you to specify contract type names, scopes, maximum number of results requested, and scope matching rules.</span></span> <span data-ttu-id="fb924-114">Los eventos <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> y <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> se pueden usar al llamar al método <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="fb924-114">The <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> and <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> events can be used when calling the <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> method.</span></span> <span data-ttu-id="fb924-115"><xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> se desencadena siempre que <xref:System.ServiceModel.Discovery.DiscoveryClient> recibe una respuesta de un servicio.</span><span class="sxs-lookup"><span data-stu-id="fb924-115"><xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> is fired whenever the <xref:System.ServiceModel.Discovery.DiscoveryClient> receives a response from a service.</span></span> <span data-ttu-id="fb924-116">Se puede utilizar para mostrar una barra de progreso que muestra el progreso de la operación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="fb924-116">It can be used to display a progress bar showing the progress of the find operation.</span></span> <span data-ttu-id="fb924-117">También se puede utilizar para intervenir en la búsqueda de respuestas a medida que se reciben.</span><span class="sxs-lookup"><span data-stu-id="fb924-117">It can also be used to act on find responses as they are received.</span></span> <span data-ttu-id="fb924-118">El evento <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> se desencadena cuando finaliza la operación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="fb924-118">The <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> event is fired when the find operation completes.</span></span> <span data-ttu-id="fb924-119">Esto puede pasar porque se haya recibido el número máximo de respuestas o si ha transcurrido <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A>.</span><span class="sxs-lookup"><span data-stu-id="fb924-119">This may happen because the maximum number of responses has been received or if the <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> has elapsed.</span></span> <span data-ttu-id="fb924-120">Cuando la operación de búsqueda finaliza, los resultados se devuelven en una instancia <xref:System.ServiceModel.Discovery.FindResponse>.</span><span class="sxs-lookup"><span data-stu-id="fb924-120">When the find operation completes the results are returned in a <xref:System.ServiceModel.Discovery.FindResponse> instance.</span></span> <span data-ttu-id="fb924-121"><xref:System.ServiceModel.Discovery.FindResponse> contiene una recopilación de <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> que incluye las direcciones, los nombres del tipo de contrato, las extensiones, los URI de escucha y los ámbitos de los servicios coincidentes.</span><span class="sxs-lookup"><span data-stu-id="fb924-121">The <xref:System.ServiceModel.Discovery.FindResponse> contains a collection of <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> which contains the addresses, contract type names, extensions, listen URIs, and scopes of the matching services.</span></span> <span data-ttu-id="fb924-122">A continuación, puede utilizar esta información para conectarse y llamar a uno de los servicios coincidentes.</span><span class="sxs-lookup"><span data-stu-id="fb924-122">You can then use this information to connect to and call one of the matching services.</span></span> <span data-ttu-id="fb924-123">En el ejemplo siguiente se muestra cómo llamar al método System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria) y usar los metadatos devueltos para llamar al servicio encontrado.</span><span class="sxs-lookup"><span data-stu-id="fb924-123">The following example shows how to call the System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria) method and use the returned metadata to call the found service.</span></span> <span data-ttu-id="fb924-124">Una ventaja <xref:System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria)> de usar es que puede almacenar en caché la lista de puntos de conexión que ha encontrado y usarlos más adelante.</span><span class="sxs-lookup"><span data-stu-id="fb924-124">A benefit of using <xref:System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria)> is that you can cache the list of endpoints you’ve found and use them at a later time.</span></span> <span data-ttu-id="fb924-125">Con esta memoria caché, puede crear una lógica personalizada para administrar diversas condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="fb924-125">With this cache, you can build custom logic to handle various failure conditions.</span></span>  
  
```csharp
DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
FindCriteria criteria = new FindCriteria(typeof(ICalculatorService));  
FindResponse fr = dc.Find(criteria);  
  
if (fr.Endpoints.Count > 0)  
{  
   EndpointAddress ep = fr.Endpoints[0].Address;  
   CalculatorServiceClient client = new CalculatorServiceClient();  
  
    // Connect to the discovered service endpoint  
   client.Endpoint.Address = endpointAddress;  
   Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress);  
  
   double value1 = 100.00D;  
   double value2 = 15.99D;  
  
   // Call the Add service operation.  
   double result = client.Add(value1, value2);  
   Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
}  
else  
   Console.WriteLine("No matching endpoints found");  
```  
  
 <span data-ttu-id="fb924-126">En el siguiente ejemplo, se muestra cómo realizar una operación de búsqueda de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="fb924-126">The following example shows how to perform a find operation asynchronously.</span></span>  
  
```csharp
static void FindServiceAsync()  
{  
   DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());
   dc.FindCompleted += new EventHandler<FindCompletedEventArgs>( discoveryClient_FindCompleted);  
   dc.FindProgressChanged += new EventHandler<FindProgressChangedEventArgs>(discoveryClient_FindProgressChanged);  
   dc.FindAsync(new FindCriteria(typeof(ICalculatorService)));
}
static void discoveryClient_FindProgressChanged(object sender, FindProgressChangedEventArgs e)  
{  
   Console.WriteLine("Found service at: " + e.EndpointDiscoveryMetadata.Address  
}
  
static void discoveryClient_FindCompleted(object sender, FindCompletedEventArgs e)  
{
      if (e.Result.Endpoints.Count > 0)  
            {  
                EndpointAddress ep = e.Result.Endpoints[0].Address;  
                CalculatorServiceClient client = new CalculatorServiceClient();  
  
                // Connect to the discovered service endpoint  
                client.Endpoint.Address = ep;  
                Console.WriteLine("Invoking CalculatorService at {0}", ep);  
  
                double value1 = 100.00D;  
                double value2 = 15.99D;  
  
                double result = client.Add(value1, value2);  
                Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
            }  
            else  
                Console.WriteLine("No matching endpoints found");  
  
        }  
```
  
 <span data-ttu-id="fb924-127">Utilice los métodos <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> y <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveAsync%28System.ServiceModel.Discovery.ResolveCriteria%29> para buscar un servicio basado en su dirección de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="fb924-127">Use the <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> and <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveAsync%28System.ServiceModel.Discovery.ResolveCriteria%29> methods to locate a service based on its endpoint address.</span></span> <span data-ttu-id="fb924-128">Esto es útil cuando la dirección del extremo no es ninguna red direccionable.</span><span class="sxs-lookup"><span data-stu-id="fb924-128">This is useful when the endpoint address is not network addressable.</span></span> <span data-ttu-id="fb924-129">Los métodos Resolve toman una instancia de <xref:System.ServiceModel.Discovery.ResolveCriteria> que le permite especificar la dirección del punto de conexión del servicio que está resolviendo, la duración máxima de la operación de resolución y un conjunto de extensiones.</span><span class="sxs-lookup"><span data-stu-id="fb924-129">The Resolve methods take an instance of <xref:System.ServiceModel.Discovery.ResolveCriteria> which allows you to specify the endpoint address of the service you are resolving, the maximum duration of the resolve operation, and a set of extensions.</span></span> <span data-ttu-id="fb924-130">En el ejemplo siguiente, se muestra cómo utilizar el método <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> para resolver un servicio.</span><span class="sxs-lookup"><span data-stu-id="fb924-130">The following example shows how to use the <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> method to resolve a service.</span></span>  
  
```csharp  
DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());  
ResolveCriteria criteria = new ResolveCriteria(endpointAddress);  
ResolveResponse response = dc.Resolve(criteria);  
EndpointAddress newEp = response.EndpointDiscoveryMetadata.Address;  
```  
  
## <a name="dynamicendpoint"></a><span data-ttu-id="fb924-131">DynamicEndpoint</span><span class="sxs-lookup"><span data-stu-id="fb924-131">DynamicEndpoint</span></span>  
 <span data-ttu-id="fb924-132"><xref:System.ServiceModel.Discovery.DynamicEndpoint>es un punto de conexión estándar (para obtener más información, consulte [Puntos de conexión estándar](../../../../docs/framework/wcf/feature-details/standard-endpoints.md)) que realiza la detección y selecciona automáticamente un servicio coincidente.</span><span class="sxs-lookup"><span data-stu-id="fb924-132"><xref:System.ServiceModel.Discovery.DynamicEndpoint> is a standard endpoint (For more information, see [Standard Endpoints](../../../../docs/framework/wcf/feature-details/standard-endpoints.md)) which performs discovery and automatically selects a matching service.</span></span> <span data-ttu-id="fb924-133">Simplemente cree una clase <xref:System.ServiceModel.Discovery.DynamicEndpoint> pasando el contrato que se va a buscar y el enlace para usar y pasar la instancia <xref:System.ServiceModel.Discovery.DynamicEndpoint> al cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="fb924-133">Just create a <xref:System.ServiceModel.Discovery.DynamicEndpoint> passing in the contract to search for and the binding to use and pass the <xref:System.ServiceModel.Discovery.DynamicEndpoint> instance to the WCF client.</span></span> <span data-ttu-id="fb924-134">En el siguiente ejemplo, se muestra cómo crear y usar una clase <xref:System.ServiceModel.Discovery.DynamicEndpoint> para llamar al servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="fb924-134">The following example shows how to create and use a <xref:System.ServiceModel.Discovery.DynamicEndpoint> to call the calculator service.</span></span> <span data-ttu-id="fb924-135">La detección se realiza cada vez que se abre el cliente.</span><span class="sxs-lookup"><span data-stu-id="fb924-135">The discovery is performed every time the client is opened.</span></span> <span data-ttu-id="fb924-136">Cualquier punto de conexión definido en <xref:System.ServiceModel.Discovery.DynamicEndpoint> la `kind ="dynamicEndpoint"` configuración también se puede convertir en un agregando el atributo al elemento de configuración del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="fb924-136">Any endpoint defined in configuration can also be turned into a <xref:System.ServiceModel.Discovery.DynamicEndpoint> by adding the `kind ="dynamicEndpoint"` attribute to the endpoint configuration element.</span></span>  
  
```csharp  
DynamicEndpoint dynamicEndpoint = new DynamicEndpoint(ContractDescription.GetContract(typeof(ICalculatorService)), new WSHttpBinding());  
CalculatorServiceClient client = new CalculatorServiceClient(dynamicEndpoint);  
  
Console.WriteLine("Invoking CalculatorService");  
Console.WriteLine();  
  
double value1 = 100.00D;  
double value2 = 15.99D;  
  
double result = client.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb924-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fb924-137">See also</span></span>

- [<span data-ttu-id="fb924-138">Detección con ámbitos</span><span class="sxs-lookup"><span data-stu-id="fb924-138">Discovery with Scopes</span></span>](../../../../docs/framework/wcf/samples/discovery-with-scopes-sample.md)
- [<span data-ttu-id="fb924-139">Básica</span><span class="sxs-lookup"><span data-stu-id="fb924-139">Basic</span></span>](../../../../docs/framework/wcf/samples/basic-sample.md)
