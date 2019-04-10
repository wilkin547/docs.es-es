---
title: Búsqueda de detección y FindCriteria
ms.date: 03/30/2017
ms.assetid: 99016fa4-1778-495b-b4cc-0e22fbec42c6
ms.openlocfilehash: 6efbfe34bbe5b15696d247c291f1d88006a53a36
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59345786"
---
# <a name="discovery-find-and-findcriteria"></a>Búsqueda de detección y FindCriteria
La operación de búsqueda de detección la inicia un cliente para detectar uno o más servicios, y es una de las acciones principales en detección. Al realizar una búsqueda, se envía un mensaje de sondeo de WS-Discovery a través de la red. Los servicios que coinciden con los criterios especificados responden con mensajes ProbeMatch de WS-Discovery. Para obtener más información acerca de los mensajes de detección, consulte el [especificación WS-Discovery](https://go.microsoft.com/fwlink/?LinkID=122347).  
  
## <a name="discoveryclient"></a>DiscoveryClient  
 La clase <xref:System.ServiceModel.Discovery.DiscoveryClient> proporciona el mecanismo para realizar las operaciones de búsqueda y facilita la realización de operaciones del cliente de detección. Contiene un método <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, que realiza una búsqueda sincrónica (con bloqueo), y un método <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A>, que inicia una búsqueda asincrónica sin bloqueo. Ambos métodos toman un parámetro <xref:System.ServiceModel.Discovery.FindCriteria> y proporcionan resultados al usuario a través de un objeto <xref:System.ServiceModel.Discovery.FindResponse>.  
  
## <a name="findcriteria"></a>FindCriteria  
 <xref:System.ServiceModel.Discovery.FindCriteria> tiene varias propiedades, que pueden agruparse en criterios de búsqueda, que especifican qué servicios están buscando, y encuentra criterios de finalización (cuánto tiempo debe durar la búsqueda). Una clase <xref:System.ServiceModel.Discovery.FindCriteria> puede contener varios criterios de búsqueda. De forma predeterminada, el servicio tiene que coincidir con todos los componentes; de lo contrario, no se considera un servicio coincidente. Si desea encontrar servicios que solo coinciden con algunos de los criterios, puede implementar la lógica de búsqueda personalizada en el servicio o puede utilizar varias consultas.  
  
 Los criterios de búsqueda incluyen:  
  
-   <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement> -Opcional. El nombre del contrato del servicio que se busca y los criterios normalmente utilizados al buscar un servicio. Si se especifica más de un nombre de contrato, solo responderán los extremos del servicio que coincidan con TODOS los contratos. Tenga en cuenta que en WCF un punto de conexión sólo puede admitir un contrato.  
  
-   <xref:System.ServiceModel.Discovery.Configuration.ScopeElement> -Opcional. Los ámbitos son URI absolutos que se usan para categorizar puntos de conexión de servicio individuales. Puede que quiera usar esto en casos en los que varios extremos expongan el mismo contrato y desee averiguar un método para buscar un subconjunto de extremos. Si se especifica más de un ámbito, solo responderán los puntos de conexión de servicio que coincidan con TODOS los ámbitos.  
  
-   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchBy%2A> : Especifica el algoritmo de coincidencia que se usará al que coincidan con los ámbitos del mensaje de sondeo con los del extremo. Hay cinco reglas de coincidencia de ámbito admitidas:  
  
    -   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByExact?displayProperty=nameWithType> distingue mayúsculas de minúsculas básico la comparación de cadenas.  
  
    -   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByPrefix?displayProperty=nameWithType> coincide por segmentos separados por "/". Una búsqueda de `http://contoso/building1` coincide con un servicio con ámbito `http://contoso/building/floor1`. Tenga en cuenta que no coincide `http://contoso/building100` porque los dos últimos segmentos no coinciden.  
  
    -   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByLdap?displayProperty=nameWithType> coincide con ámbitos por segmentos mediante una dirección URL de LDAP.  
  
    -   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByUuid?displayProperty=nameWithType> coincide con ámbitos exactamente con una cadena del UUID.  
  
    -   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByNone?displayProperty=nameWithType> devuelve solamente los servicios que no especifican un ámbito.  
  
     Si no se especifica una regla de coincidencia de ámbito, se usa <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByPrefix>.  
  
 Los criterios de finalización incluyen:  
  
1. <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> -El tiempo máximo para esperar respuestas de los servicios en la red. La duración predeterminada es de 20 segundos.  
  
2. <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> -El número máximo de respuestas que se esperan. Si se reciben respuestas <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> antes de que haya transcurrido <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A>, la operación de búsqueda finaliza.  
  
## <a name="findresponse"></a>FindResponse  
 <xref:System.ServiceModel.Discovery.FindResponse> tiene un <xref:System.ServiceModel.Discovery.FindResponse.Endpoints%2A> propiedad de colección que contiene todas las respuestas enviadas por los servicios en la red coincidentes. Si ningún servicio responde, la colección está vacía. Si uno o más servicios respondieran, cada respuesta se almacenaría en un objeto <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>, que contiene la dirección, el contrato y cierta información adicional sobre el servicio.  
  
 En el siguiente ejemplo, se muestra cómo realizar una operación de búsqueda en código.  
  
```  
// Create DiscoveryClient  
DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
// Create FindCriteria  
FindCriteria findCriteria = new FindCriteria(typeof(IPrinterService));  
findCriteria.Scopes.Add(new Uri("http://www.contoso.com/building1/floor1"));  
findCriteria.Duration = TimeSpan.FromSeconds(10);   
  
// Find ICalculatorService endpoints              
FindResponse findResponse = discoveryClient.Find(findCriteria);  
  
Console.WriteLine("Found {0} ICalculatorService endpoint(s).", findResponse.Endpoints.Count)  
```  
  
## <a name="see-also"></a>Vea también

- [Información general de Detección de WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [Usar el canal del cliente de detección](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)
- [Detección con ámbitos](../../../../docs/framework/wcf/samples/discovery-with-scopes-sample.md)
- [Básico](../../../../docs/framework/wcf/samples/basic-sample.md)
