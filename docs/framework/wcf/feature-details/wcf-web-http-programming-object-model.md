---
title: Modelo de objetos de programación web HTTP de WCF
ms.date: 03/30/2017
ms.assetid: ed96b5fc-ca2c-4b0d-bdba-d06b77c3cb2a
ms.openlocfilehash: 39c7ec31827d1cde5d95516cc3867f9d6bf9817f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739867"
---
# <a name="wcf-web-http-programming-object-model"></a>Modelo de objetos de programación web HTTP de WCF
El modelo de programación WEB HTTP de WCF permite a los desarrolladores exponer servicios Web de Windows Communication Foundation (WCF) a través de solicitudes HTTP básicas sin necesidad de SOAP. El modelo de programación WEB HTTP de WCF se basa en el modelo de extensibilidad de WCF existente. Define las clases siguientes:  
  
 **Modelo de programación:**  
  
- <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>  
  
- <xref:System.ServiceModel.Web.WebGetAttribute>  
  
- <xref:System.ServiceModel.Web.WebInvokeAttribute>  
  
- <xref:System.ServiceModel.Web.WebServiceHost>  
  
 **Infraestructura de canales y distribuidores:**  
  
- <xref:System.ServiceModel.WebHttpBinding>  
  
- <xref:System.ServiceModel.Description.WebHttpBehavior>  
  
 **Clases de utilidad y puntos de extensibilidad:**  
  
- <xref:System.UriTemplate>  
  
- <xref:System.UriTemplateTable>  
  
- <xref:System.ServiceModel.Dispatcher.QueryStringConverter>  
  
- <xref:System.ServiceModel.Dispatcher.WebHttpDispatchOperationSelector>  
  
## <a name="aspnetcacheprofileattribute"></a>AspNetCacheProfileAttribute  
 La clase <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, cuando se aplica a una operación de servicio, indica el perfil de caché de resultados de ASP.NET en el archivo de configuración que debe usar para almacenar en la memoria caché las respuestas de la operación realizada en la memoria caché de resultados de ASP.NET. Esta propiedad toma solo uno parámetro, el nombre de perfil de memoria caché que especifica la configuración de la memoria caché en el archivo de configuración.  
  
## <a name="webgetattribute"></a>WebGetAttribute  
 El atributo de la clase <xref:System.ServiceModel.Web.WebGetAttribute> se usa para marcar una operación de servicio como operación que responde a las solicitudes de HTTP GET. Es un comportamiento de operación pasivo (los métodos <xref:System.ServiceModel.Description.IOperationBehavior> no hacen nada) que agrega los metadatos a la descripción de la operación. La aplicación de <xref:System.ServiceModel.Web.WebGetAttribute> no tiene ningún efecto, a menos que se agregue al comportamiento del servicio un comportamiento que busque estos metadatos en la descripción de la operación (concretamente, <xref:System.ServiceModel.Description.WebHttpBehavior>). El atributo <xref:System.ServiceModel.Web.WebGetAttribute> adopta los parámetros opcionales mostrados en la siguiente tabla.  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|`BodyStyle`|Controla si encapsular las solicitudes y respuestas enviadas y recibidas desde la operación de servicio a la que se aplica el atributo.|  
|`RequestFormat`|Controla cómo se da formato a los mensajes de solicitud.|  
|`ResponseFormat`|Controla cómo se da formato a los mensajes de respuesta.|  
|`UriTemplate`|Especifica la plantilla URI que controla qué solicitudes HTTP se asignan a la operación de servicio a la que se aplica el atributo.|  
  
## <a name="webhttpbinding"></a>WebHttpBinding  
 La clase <xref:System.ServiceModel.WebHttpBinding> incorpora los codificadores de tipo XML, JSON y de datos binarios sin formato que usan <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>. Se compone de un <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, un <xref:System.ServiceModel.Channels.HttpTransportBindingElement> y un objeto <xref:System.ServiceModel.WebHttpSecurity>. <xref:System.ServiceModel.WebHttpBinding> se ha diseñado para utilizarse junto con <xref:System.ServiceModel.Description.WebHttpBehavior>.  
  
## <a name="webinvokeattribute"></a>WebInvokeAttribute  
 El atributo <xref:System.ServiceModel.Web.WebInvokeAttribute> es similar a <xref:System.ServiceModel.Web.WebGetAttribute>, pero se utiliza para marcar una operación de servicio como una operación que responde a las solicitudes HTTP que no son GET. Es un comportamiento de operación pasivo (los métodos <xref:System.ServiceModel.Description.IOperationBehavior> no hacen nada) que agrega los metadatos a la descripción de la operación. La aplicación de <xref:System.ServiceModel.Web.WebInvokeAttribute> no tiene ningún efecto, a menos que se agregue al comportamiento del servicio un comportamiento que busque estos metadatos en la descripción de la operación (concretamente, <xref:System.ServiceModel.Description.WebHttpBehavior>).  
  
 El atributo <xref:System.ServiceModel.Web.WebInvokeAttribute> adopta los parámetros opcionales mostrados en la siguiente tabla.  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|`BodyStyle`|Controla si encapsular las solicitudes y respuestas enviadas y recibidas desde la operación de servicio a la que se aplica el atributo.|  
|`Method`|Especifica el método HTTP al que se asigna la operación del servicio.|  
|`RequestFormat`|Controla cómo se da formato a los mensajes de solicitud.|  
|`ResponseFormat`|Controla cómo se da formato a los mensajes de respuesta.|  
|`UriTemplate`|Especifica la plantilla URI que controla qué solicitudes GET se asignan a la operación de servicio a la que se aplica el atributo.|  
  
## <a name="uritemplate"></a>UriTemplate  
 La clase <xref:System.UriTemplate> permite definir un conjunto de direcciones URI estructuralmente similares. Las plantillas se componen de dos partes, una ruta de acceso y una consulta. Una ruta de acceso consiste en una serie de segmentos delimitados por una barra diagonal (/). Cada segmento puede tener un valor literal, un valor de variable (escrito entre llaves [{}], restringido para que coincida con el contenido de exactamente un segmento) o un carácter comodín (escrito como un asterisco [\*], que coincide con "el resto de la ruta de acceso"), que debe aparecer al final de la ruta de acceso. La expresión de consulta puede omitirse completamente. Si está presente, especifica una serie no ordenada de pares nombre/valor. Los elementos de la expresión de consulta pueden ser pares literales (? x = 2) o pares de variables (? x = {*valor*}). No se permiten los valores no emparejados. el modelo de programación HTTP WEB de WCF utiliza <xref:System.UriTemplate> internamente para asignar direcciones URI específicas o grupos de direcciones URI a las operaciones de servicio.  
  
## <a name="uritemplatetable"></a>UriTemplateTable  
 La clase <xref:System.UriTemplateTable> representa un conjunto asociativo de objetos <xref:System.UriTemplate> enlazado a un objeto elegido por el desarrollador. Le permite hacer coincidir los identificadores uniformes de recursos (URI) del candidato con las plantillas del conjunto y recuperar los datos asociados a las plantillas correspondientes. el modelo de programación HTTP WEB de WCF utiliza <xref:System.UriTemplateTable> internamente para asignar direcciones URI específicas o grupos de direcciones URI a las operaciones de servicio.  
  
## <a name="webservicehost"></a>WebServiceHost  
 <xref:System.ServiceModel.Web.WebServiceHost> extiende <xref:System.ServiceModel.ServiceHost> para facilitar el hospedaje de un servicio de estilo Web no SOAP. Si <xref:System.ServiceModel.Web.WebServiceHost> no encuentra puntos de conexión en la descripción del servicio, crea automáticamente un punto de conexión predeterminado en la dirección base del servicio. Al crear un punto de conexión HTTP predeterminado, el <xref:System.ServiceModel.Web.WebServiceHost> también deshabilita la página de ayuda de HTTP y la funcionalidad GET del lenguaje de descripción de servicios Web (WSDL) para que el punto de conexión de metadatos no interfiera con el punto de conexión HTTP predeterminado. <xref:System.ServiceModel.Web.WebServiceHost> también garantiza que todos los extremos que usan <xref:System.ServiceModel.WebHttpBinding> tengan el <xref:System.ServiceModel.Description.WebHttpBehavior> necesario adjunto. Finalmente, cuando se utiliza en un directorio virtual protegido, <xref:System.ServiceModel.Web.WebServiceHost> configura automáticamente el enlace del punto de conexión para trabajar con la configuración de seguridad de Internet Information Services (IIS) asociada.  
  
## <a name="webservicehostfactory"></a>WebServiceHostFactory  
 La clase <xref:System.ServiceModel.Activation.WebServiceHostFactory> se utiliza para la creación dinámica de un <xref:System.ServiceModel.Web.WebServiceHost> cuando un servicio se hospeda en IIS o en WAS (servicio de activación de procesos de Windows). A diferencia de un servicio hospedado en si mismo, en el que la aplicación de hospedaje crea la instancia <xref:System.ServiceModel.Web.WebServiceHost>, los servicios hospedados en IIS o WAS utilizan esta clase para crear el <xref:System.ServiceModel.Web.WebServiceHost> del servicio. Se llama al método <xref:System.ServiceModel.Activation.WebServiceHostFactory.CreateServiceHost%28System.Type%2CSystem.Uri%5B%5D%29> cuando se recibe una solicitud de entrada para el servicio.  
  
## <a name="webhttpbehavior"></a>WebHttpBehavior  
 La clase <xref:System.ServiceModel.Description.WebHttpBehavior> proporciona los formateadores, los selectores de la operación y otros elementos necesarios para que se admita el servicio de estilo web en el nivel de modelo de servicio. Esto se implementa como comportamiento de punto de conexión (utilizado junto con <xref:System.ServiceModel.WebHttpBinding>) y permite especificar los formateadores y selectores de operación de cada punto de conexión, lo que permite que una misma implementación de servicio exponga puntos de conexión SOAP y POX.  
  
### <a name="extending-webhttpbehavior"></a>Extender WebHttpBehavior  
 <xref:System.ServiceModel.Description.WebHttpBehavior> es extensible utilizando distintos métodos virtuales: <xref:System.ServiceModel.Description.WebHttpBehavior.GetOperationSelector%28System.ServiceModel.Description.ServiceEndpoint%29>, <xref:System.ServiceModel.Description.WebHttpBehavior.GetReplyClientFormatter%28System.ServiceModel.Description.OperationDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%29>, <xref:System.ServiceModel.Description.WebHttpBehavior.GetRequestClientFormatter%28System.ServiceModel.Description.OperationDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%29>, <xref:System.ServiceModel.Description.WebHttpBehavior.GetReplyDispatchFormatter%28System.ServiceModel.Description.OperationDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%29>y <xref:System.ServiceModel.Description.WebHttpBehavior.GetRequestDispatchFormatter%28System.ServiceModel.Description.OperationDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%29>. Los desarrolladores pueden derivar una clase de <xref:System.ServiceModel.Description.WebHttpBehavior> e invalidar estos métodos para personalizar el comportamiento predeterminado.  
  
 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> es un ejemplo de cómo extender <xref:System.ServiceModel.Description.WebHttpBehavior>. <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> permite a los puntos de conexión de Windows Communication Foundation (WCF) recibir solicitudes HTTP de un cliente AJAX de ASP.NET basado en explorador. El [servicio Ajax mediante http post](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) es un ejemplo del uso de este punto de extensibilidad.  
  
> [!WARNING]
> Cuando se usa el <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>, no se admiten objetos <xref:System.UriTemplate> dentro de los atributos <xref:System.ServiceModel.Web.WebGetAttribute> o <xref:System.ServiceModel.Web.WebInvokeAttribute>.  
  
## <a name="webhttpdispatchoperationselector"></a>WebHttpDispatchOperationSelector  
 La clase <xref:System.ServiceModel.Dispatcher.WebHttpDispatchOperationSelector> usa las clases <xref:System.UriTemplate> y <xref:System.UriTemplateTable> para enviar las llamadas a las operaciones del servicio.  
  
## <a name="compatibility"></a>Compatibilidad  
 El modelo de programación WEB HTTP de WCF no utiliza mensajes basados en SOAP y, por lo tanto, no admite los protocolos WS-*. No obstante, puede exponer el mismo contrato en dos extremos diferentes, uno que use SOAP y otro que no lo haga. Vea [Cómo: exponer un contrato a SOAP y clientes Web](../../../../docs/framework/wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients.md) para obtener un ejemplo.  
  
## <a name="security"></a>de seguridad  

Dado que el modelo de programación WEB HTTP de WCF no admite los protocolos WS-*, la única manera de proteger un servicio Web basado en el modelo de programación WEB HTTP de WCF es exponer el servicio mediante SSL. Para obtener más información acerca de cómo configurar SSL con IIS 7,0, consulte [How to implement SSL in IIS](https://support.microsoft.com/help/299875/how-to-implement-ssl-in-iis).
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
- <xref:System.ServiceModel.Web.WebInvokeAttribute>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- <xref:System.ServiceModel.Dispatcher.WebHttpDispatchOperationSelector>
- [Información general del modelo de programación web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)
