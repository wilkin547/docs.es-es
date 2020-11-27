---
title: DiscoveryClient y DynamicEndpoint
ms.date: 03/30/2017
ms.assetid: 7cd418f0-0eab-48d1-a493-7eb907867ec3
ms.openlocfilehash: 72e5beb1306b679cc3b546d77846b5d1e9bb8bb4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275016"
---
# <a name="discoveryclient-and-dynamicendpoint"></a>DiscoveryClient y DynamicEndpoint

<xref:System.ServiceModel.Discovery.DiscoveryClient> y <xref:System.ServiceModel.Discovery.DynamicEndpoint> son dos clases usadas en el lado cliente para buscar servicios. <xref:System.ServiceModel.Discovery.DiscoveryClient> le proporciona una lista de servicios que coinciden con un conjunto concreto de criterios y le permite conectarse a los servicios. <xref:System.ServiceModel.Discovery.DynamicEndpoint> realiza la misma operación y además, conecta automáticamente con uno de los servicios que se encontró. Cualquier punto de conexión se puede convertir en <xref:System.ServiceModel.Discovery.DynamicEndpoint>, los criterios de búsqueda también se pueden agregar a través de la configuración. Por tanto, <xref:System.ServiceModel.Discovery.DynamicEndpoint> es útil si necesita la detección en su solución pero no desea modificar la lógica del cliente; solo necesita modificar los puntos de conexión. Por otra parte, <xref:System.ServiceModel.Discovery.DiscoveryClient> se puede usar para obtener un control más preciso sobre la operación de búsqueda. Más abajo, se elaboran los usos y ventajas de cada uno.  
  
## <a name="discoveryclient"></a>DiscoveryClient  

 <xref:System.ServiceModel.Discovery.DiscoveryClient> define métodos Find sincrónicos y asincrónicos, así como eventos <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> y <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged>.  También define métodos Resolve sincrónicos y asincrónicos, así como un evento <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveCompleted>. Utilice los métodos <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> o <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> para buscar servicios. Ambos métodos toma una instancia <xref:System.ServiceModel.Discovery.FindCriteria> que le permite especificar los nombres de tipo de contrato, ámbitos, número máximo de resultados solicitados y reglas de coincidencia de ámbito. Los eventos <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> y <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> se pueden usar al llamar al método <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A>. <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> se desencadena siempre que <xref:System.ServiceModel.Discovery.DiscoveryClient> recibe una respuesta de un servicio. Se puede utilizar para mostrar una barra de progreso que muestra el progreso de la operación de búsqueda. También se puede utilizar para intervenir en la búsqueda de respuestas a medida que se reciben. El evento <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> se desencadena cuando finaliza la operación de búsqueda. Esto puede pasar porque se haya recibido el número máximo de respuestas o si ha transcurrido <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A>. Cuando la operación de búsqueda finaliza, los resultados se devuelven en una instancia <xref:System.ServiceModel.Discovery.FindResponse>. <xref:System.ServiceModel.Discovery.FindResponse> contiene una recopilación de <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> que incluye las direcciones, los nombres del tipo de contrato, las extensiones, los URI de escucha y los ámbitos de los servicios coincidentes. A continuación, puede utilizar esta información para conectarse y llamar a uno de los servicios coincidentes. En el ejemplo siguiente se muestra cómo llamar al método System. ServiceModel. Discovery. DiscoveryClient. Find (System. ServiceModel. Discovery. FindCriteria) y usar los metadatos devueltos para llamar al servicio encontrado. Una ventaja de usar <xref:System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria)> es que puede almacenar en caché la lista de puntos de conexión que ha encontrado y usarlos más adelante. Con esta memoria caché, puede crear una lógica personalizada para administrar diversas condiciones de error.  
  
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
  
 En el siguiente ejemplo, se muestra cómo realizar una operación de búsqueda de forma asincrónica.  
  
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
  
 Utilice los métodos <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> y <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveAsync%28System.ServiceModel.Discovery.ResolveCriteria%29> para buscar un servicio basado en su dirección de punto de conexión. Esto es útil cuando la dirección del extremo no es ninguna red direccionable. Los métodos Resolve toman una instancia de <xref:System.ServiceModel.Discovery.ResolveCriteria> que le permite especificar la dirección del punto de conexión del servicio que está resolviendo, la duración máxima de la operación de resolución y un conjunto de extensiones. En el ejemplo siguiente, se muestra cómo utilizar el método <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> para resolver un servicio.  
  
```csharp  
DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());  
ResolveCriteria criteria = new ResolveCriteria(endpointAddress);  
ResolveResponse response = dc.Resolve(criteria);  
EndpointAddress newEp = response.EndpointDiscoveryMetadata.Address;  
```  
  
## <a name="dynamicendpoint"></a>DynamicEndpoint  

 <xref:System.ServiceModel.Discovery.DynamicEndpoint> es un punto de conexión estándar (para obtener más información, consulte [puntos de conexión estándar](standard-endpoints.md)) que realiza la detección y selecciona automáticamente un servicio coincidente. Simplemente cree una clase <xref:System.ServiceModel.Discovery.DynamicEndpoint> pasando el contrato que se va a buscar y el enlace para usar y pasar la instancia <xref:System.ServiceModel.Discovery.DynamicEndpoint> al cliente de WCF. En el siguiente ejemplo, se muestra cómo crear y usar una clase <xref:System.ServiceModel.Discovery.DynamicEndpoint> para llamar al servicio de calculadora. La detección se realiza cada vez que se abre el cliente. Cualquier punto de conexión definido en la configuración también se puede convertir en agregando <xref:System.ServiceModel.Discovery.DynamicEndpoint> el `kind ="dynamicEndpoint"` atributo al elemento de configuración del punto de conexión.  
  
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
  
## <a name="see-also"></a>Vea también

- [Detección con ámbitos](../samples/discovery-with-scopes-sample.md)
- [Basic](../samples/basic-sample.md)
