---
description: 'Más información acerca de: DiscoveryClient y DynamicEndpoint'
title: DiscoveryClient y DynamicEndpoint
ms.date: 03/30/2017
ms.assetid: 7cd418f0-0eab-48d1-a493-7eb907867ec3
ms.openlocfilehash: 34f6c5d7d8958f4a28a6bff950f3f6dad81871ae
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743179"
---
# <a name="discoveryclient-and-dynamicendpoint"></a><span data-ttu-id="ca8ef-103">DiscoveryClient y DynamicEndpoint</span><span class="sxs-lookup"><span data-stu-id="ca8ef-103">DiscoveryClient and DynamicEndpoint</span></span>

<span data-ttu-id="ca8ef-104"><xref:System.ServiceModel.Discovery.DiscoveryClient> y <xref:System.ServiceModel.Discovery.DynamicEndpoint> son dos clases usadas en el lado cliente para buscar servicios.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-104"><xref:System.ServiceModel.Discovery.DiscoveryClient> and <xref:System.ServiceModel.Discovery.DynamicEndpoint> are two classes used on the client side to search for services.</span></span> <span data-ttu-id="ca8ef-105"><xref:System.ServiceModel.Discovery.DiscoveryClient> le proporciona una lista de servicios que coinciden con un conjunto concreto de criterios y le permite conectarse a los servicios.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-105"><xref:System.ServiceModel.Discovery.DiscoveryClient> provides you with a list of services that match a specific set of criteria and allows you to connect to the services.</span></span> <span data-ttu-id="ca8ef-106"><xref:System.ServiceModel.Discovery.DynamicEndpoint> realiza la misma operación y además, conecta automáticamente con uno de los servicios que se encontró.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-106"><xref:System.ServiceModel.Discovery.DynamicEndpoint> performs the same operation and in addition, automatically connects to one of the services that was found.</span></span> <span data-ttu-id="ca8ef-107">Cualquier punto de conexión se puede convertir en <xref:System.ServiceModel.Discovery.DynamicEndpoint>, los criterios de búsqueda también se pueden agregar a través de la configuración. Por tanto, <xref:System.ServiceModel.Discovery.DynamicEndpoint> es útil si necesita la detección en su solución pero no desea modificar la lógica del cliente; solo necesita modificar los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-107">Any endpoint can be made into a <xref:System.ServiceModel.Discovery.DynamicEndpoint>, the search criteria can also be added in configuration, thus <xref:System.ServiceModel.Discovery.DynamicEndpoint> is useful when you need discovery in your solution but do not want to modify the client logic – you only need to modify the endpoints.</span></span> <span data-ttu-id="ca8ef-108">Por otra parte, <xref:System.ServiceModel.Discovery.DiscoveryClient> se puede usar para obtener un control más preciso sobre la operación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-108"><xref:System.ServiceModel.Discovery.DiscoveryClient> on the other hand can be used to gain finer control over your search operation.</span></span> <span data-ttu-id="ca8ef-109">Más abajo, se elaboran los usos y ventajas de cada uno.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-109">The uses and benefits of each are elaborated below.</span></span>  
  
## <a name="discoveryclient"></a><span data-ttu-id="ca8ef-110">DiscoveryClient</span><span class="sxs-lookup"><span data-stu-id="ca8ef-110">DiscoveryClient</span></span>  

 <span data-ttu-id="ca8ef-111"><xref:System.ServiceModel.Discovery.DiscoveryClient> define métodos Find sincrónicos y asincrónicos, así como eventos <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> y <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged>.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-111">The <xref:System.ServiceModel.Discovery.DiscoveryClient> defines synchronous and asynchronous Find methods, <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> and <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> events.</span></span>  <span data-ttu-id="ca8ef-112">También define métodos Resolve sincrónicos y asincrónicos, así como un evento <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveCompleted>.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-112">It also defines synchronous and asynchronous Resolve methods and a <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveCompleted> event.</span></span> <span data-ttu-id="ca8ef-113">Utilice los métodos <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> o <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> para buscar servicios.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-113">Use the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> or <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> methods to search for services.</span></span> <span data-ttu-id="ca8ef-114">Ambos métodos toma una instancia <xref:System.ServiceModel.Discovery.FindCriteria> que le permite especificar los nombres de tipo de contrato, ámbitos, número máximo de resultados solicitados y reglas de coincidencia de ámbito.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-114">Both of these methods take a <xref:System.ServiceModel.Discovery.FindCriteria> instance that allows you to specify contract type names, scopes, maximum number of results requested, and scope matching rules.</span></span> <span data-ttu-id="ca8ef-115">Los eventos <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> y <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> se pueden usar al llamar al método <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-115">The <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> and <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> events can be used when calling the <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> method.</span></span> <span data-ttu-id="ca8ef-116"><xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> se desencadena siempre que <xref:System.ServiceModel.Discovery.DiscoveryClient> recibe una respuesta de un servicio.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-116"><xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> is fired whenever the <xref:System.ServiceModel.Discovery.DiscoveryClient> receives a response from a service.</span></span> <span data-ttu-id="ca8ef-117">Se puede utilizar para mostrar una barra de progreso que muestra el progreso de la operación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-117">It can be used to display a progress bar showing the progress of the find operation.</span></span> <span data-ttu-id="ca8ef-118">También se puede utilizar para intervenir en la búsqueda de respuestas a medida que se reciben.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-118">It can also be used to act on find responses as they are received.</span></span> <span data-ttu-id="ca8ef-119">El evento <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> se desencadena cuando finaliza la operación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-119">The <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> event is fired when the find operation completes.</span></span> <span data-ttu-id="ca8ef-120">Esto puede pasar porque se haya recibido el número máximo de respuestas o si ha transcurrido <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-120">This may happen because the maximum number of responses has been received or if the <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> has elapsed.</span></span> <span data-ttu-id="ca8ef-121">Cuando la operación de búsqueda finaliza, los resultados se devuelven en una instancia <xref:System.ServiceModel.Discovery.FindResponse>.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-121">When the find operation completes the results are returned in a <xref:System.ServiceModel.Discovery.FindResponse> instance.</span></span> <span data-ttu-id="ca8ef-122"><xref:System.ServiceModel.Discovery.FindResponse> contiene una recopilación de <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> que incluye las direcciones, los nombres del tipo de contrato, las extensiones, los URI de escucha y los ámbitos de los servicios coincidentes.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-122">The <xref:System.ServiceModel.Discovery.FindResponse> contains a collection of <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> which contains the addresses, contract type names, extensions, listen URIs, and scopes of the matching services.</span></span> <span data-ttu-id="ca8ef-123">A continuación, puede utilizar esta información para conectarse y llamar a uno de los servicios coincidentes.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-123">You can then use this information to connect to and call one of the matching services.</span></span> <span data-ttu-id="ca8ef-124">En el ejemplo siguiente se muestra cómo llamar al método System. ServiceModel. Discovery. DiscoveryClient. Find (System. ServiceModel. Discovery. FindCriteria) y usar los metadatos devueltos para llamar al servicio encontrado.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-124">The following example shows how to call the System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria) method and use the returned metadata to call the found service.</span></span> <span data-ttu-id="ca8ef-125">Una ventaja de usar <xref:System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria)> es que puede almacenar en caché la lista de puntos de conexión que ha encontrado y usarlos más adelante.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-125">A benefit of using <xref:System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria)> is that you can cache the list of endpoints you’ve found and use them at a later time.</span></span> <span data-ttu-id="ca8ef-126">Con esta memoria caché, puede crear una lógica personalizada para administrar diversas condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-126">With this cache, you can build custom logic to handle various failure conditions.</span></span>  
  
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
  
 <span data-ttu-id="ca8ef-127">En el siguiente ejemplo, se muestra cómo realizar una operación de búsqueda de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-127">The following example shows how to perform a find operation asynchronously.</span></span>  
  
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
  
 <span data-ttu-id="ca8ef-128">Utilice los métodos <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> y <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveAsync%28System.ServiceModel.Discovery.ResolveCriteria%29> para buscar un servicio basado en su dirección de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-128">Use the <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> and <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveAsync%28System.ServiceModel.Discovery.ResolveCriteria%29> methods to locate a service based on its endpoint address.</span></span> <span data-ttu-id="ca8ef-129">Esto es útil cuando la dirección del extremo no es ninguna red direccionable.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-129">This is useful when the endpoint address is not network addressable.</span></span> <span data-ttu-id="ca8ef-130">Los métodos Resolve toman una instancia de <xref:System.ServiceModel.Discovery.ResolveCriteria> que le permite especificar la dirección del punto de conexión del servicio que está resolviendo, la duración máxima de la operación de resolución y un conjunto de extensiones.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-130">The Resolve methods take an instance of <xref:System.ServiceModel.Discovery.ResolveCriteria> which allows you to specify the endpoint address of the service you are resolving, the maximum duration of the resolve operation, and a set of extensions.</span></span> <span data-ttu-id="ca8ef-131">En el ejemplo siguiente, se muestra cómo utilizar el método <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> para resolver un servicio.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-131">The following example shows how to use the <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> method to resolve a service.</span></span>  
  
```csharp  
DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());  
ResolveCriteria criteria = new ResolveCriteria(endpointAddress);  
ResolveResponse response = dc.Resolve(criteria);  
EndpointAddress newEp = response.EndpointDiscoveryMetadata.Address;  
```  
  
## <a name="dynamicendpoint"></a><span data-ttu-id="ca8ef-132">DynamicEndpoint</span><span class="sxs-lookup"><span data-stu-id="ca8ef-132">DynamicEndpoint</span></span>  

 <span data-ttu-id="ca8ef-133"><xref:System.ServiceModel.Discovery.DynamicEndpoint> es un punto de conexión estándar (para obtener más información, consulte [puntos de conexión estándar](standard-endpoints.md)) que realiza la detección y selecciona automáticamente un servicio coincidente.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-133"><xref:System.ServiceModel.Discovery.DynamicEndpoint> is a standard endpoint (For more information, see [Standard Endpoints](standard-endpoints.md)) which performs discovery and automatically selects a matching service.</span></span> <span data-ttu-id="ca8ef-134">Simplemente cree una clase <xref:System.ServiceModel.Discovery.DynamicEndpoint> pasando el contrato que se va a buscar y el enlace para usar y pasar la instancia <xref:System.ServiceModel.Discovery.DynamicEndpoint> al cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-134">Just create a <xref:System.ServiceModel.Discovery.DynamicEndpoint> passing in the contract to search for and the binding to use and pass the <xref:System.ServiceModel.Discovery.DynamicEndpoint> instance to the WCF client.</span></span> <span data-ttu-id="ca8ef-135">En el siguiente ejemplo, se muestra cómo crear y usar una clase <xref:System.ServiceModel.Discovery.DynamicEndpoint> para llamar al servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-135">The following example shows how to create and use a <xref:System.ServiceModel.Discovery.DynamicEndpoint> to call the calculator service.</span></span> <span data-ttu-id="ca8ef-136">La detección se realiza cada vez que se abre el cliente.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-136">The discovery is performed every time the client is opened.</span></span> <span data-ttu-id="ca8ef-137">Cualquier punto de conexión definido en la configuración también se puede convertir en agregando <xref:System.ServiceModel.Discovery.DynamicEndpoint> el `kind ="dynamicEndpoint"` atributo al elemento de configuración del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ca8ef-137">Any endpoint defined in configuration can also be turned into a <xref:System.ServiceModel.Discovery.DynamicEndpoint> by adding the `kind ="dynamicEndpoint"` attribute to the endpoint configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ca8ef-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca8ef-138">See also</span></span>

- [<span data-ttu-id="ca8ef-139">Detección con ámbitos</span><span class="sxs-lookup"><span data-stu-id="ca8ef-139">Discovery with Scopes</span></span>](../samples/discovery-with-scopes-sample.md)
- [<span data-ttu-id="ca8ef-140">Basic</span><span class="sxs-lookup"><span data-stu-id="ca8ef-140">Basic</span></span>](../samples/basic-sample.md)
