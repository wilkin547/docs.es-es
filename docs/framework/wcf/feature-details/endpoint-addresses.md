---
title: "Direcciones de punto de conexión"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- addresses [WCF]
- Windows Communication Foundation [WCF], addresses
- WCF [WCF], addresses
ms.assetid: 13f269e3-ebb1-433c-86cf-54fbd866a627
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 52c5dfd84a55e727e465e2bd6214462fd57c334f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="endpoint-addresses"></a>Direcciones de punto de conexión
Cada punto de conexión tiene una dirección asociada a él, que se utiliza para ubicar e identificar el punto de conexión. Esta dirección está compuesta principalmente de un Identificador uniforme de recursos (URI), que especifica la ubicación del extremo. La dirección del extremo se representa en el modelo de programación de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] mediante la clase <xref:System.ServiceModel.EndpointAddress>, que contiene una propiedad <xref:System.ServiceModel.EndpointAddress.Identity%2A> opcional que permite la autenticación del extremo por parte otros extremos que intercambian mensajes con él, y un conjunto de propiedades <xref:System.ServiceModel.EndpointAddress.Headers%2A> opcionales, que definen cualquier otro encabezado SOAP requerido para alcanzar el servicio. Los encabezados opcionales proporcionan información de direccionamiento adicional y más detallada para identificar o interactuar con el extremo de servicio. La dirección de un extremo se representa en la conexión como una referencia de extremo (EPR) WS-Addressing.  
  
## <a name="uri-structure-of-an-address"></a>Estructura URI de una Dirección  
 El URI de la dirección de la mayoría de transportes tiene cuatro partes. Por ejemplo, las cuatro partes del URI http://www.fabrikam.com:322/mathservice.svc/secureEndpoint se puede dividir en los siguientes elementos:  
  
-   Esquema: http:  
  
-   Equipo: www.fabrikam.com  
  
-   (opcional) Puerto: 322  
  
-   Ruta de acceso: /mathservice.svc/secureEndpoint  
  
## <a name="defining-an-address-for-a-service"></a>Definición de una dirección para un Servicio  
 La dirección de extremo de un servicio puede especificarse de manera imperativa mediante código o de manera declarativa mediante configuración. Normalmente, no resulta muy práctico definir los extremos en el código ya que los enlaces y las direcciones de un servicio implementado son, por lo general, diferentes de los utilizados durante el desarrollo del servicio. Generalmente, es más práctico definir extremos de servicio mediante la configuración en lugar del código. Mantener la información del enlace y el direccionamiento fuera del código permite cambiar los extremos sin tener que recompilar ni implementar la aplicación.  
  
### <a name="defining-an-address-in-configuration"></a>Definición de una dirección mediante configuración  
 Para definir un punto de conexión en un archivo de configuración, utilice la [ \<extremo >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento. Para obtener más información y un ejemplo, vea [al especificar una dirección de punto de conexión](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).  
  
### <a name="defining-an-address-in-code"></a>Definición de una dirección mediante código  
 Una dirección de extremo se puede crear mediante código con la clase <xref:System.ServiceModel.EndpointAddress>. Para obtener más información y un ejemplo, vea [al especificar una dirección de punto de conexión](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).  
  
### <a name="endpoints-in-wsdl"></a>puntos de conexión en WSDL  
 Una dirección de extremo también se puede representar en WSDL como un elemento EPR de WS-Addressing dentro del elemento `wsdl:port` del extremo correspondiente. El EPR contiene la dirección del punto de conexión, así como todas las propiedades de la dirección. Para obtener más información y un ejemplo, vea [al especificar una dirección de punto de conexión](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).  
  
## <a name="multiple-iis-binding-support-in-net-framework-35"></a>Varios IIS compatibilidad con enlaces en .NET Framework 3.5  
 Los proveedores de acceso a Internet a menudo hospedan muchas aplicaciones en el mismo servidor y en el mismo sitio para aumentar la densidad del sitio y reducir el costo total de propiedad. Estas aplicaciones se enlazan normalmente en las diferentes direcciones base. Un sitio web de Internet Information Services (IIS) puede contener varias aplicaciones. Se puede tener acceso a las aplicaciones en un sitio a través de uno o más enlaces de IIS.  
  
 Los enlaces de IIS proporcionan dos partes de información: un protocolo de enlace e información de enlace. El protocolo de enlace define el esquema sobre el que se produce la comunicación, y la información de enlace es la información utilizada para tener acceso al sitio.  
  
 El siguiente ejemplo muestra los componentes que se pueden encontrar en un enlace de IIS:  
  
-   Protocolo de enlace: HTTP  
  
-   Información de enlace: Dirección IP, puerto, encabezado de host  
  
 IIS puede especificar varios enlaces para cada sitio, que resulta en varias direcciones base para cada esquema. Antes de [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no admitía varias direcciones para un esquema y, si se especificaban, se iniciaba una excepción <xref:System.ArgumentException> durante la activación.  
  
 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] permite a los proveedores de acceso a Internet hospedar varias aplicaciones con direcciones base diferentes para el mismo esquema en el mismo sitio.  
  
 Por ejemplo, un sitio podría contener las direcciones base siguientes:  
  
-   http://payroll.myorg.com/Service.svc  
  
-   http://shipping.myorg.com/Service.svc  
  
 Con [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], especifica un filtro de prefijo en el nivel del AppDomain en el archivo de configuración. Esto se hace la [ \<baseAddressPrefixFilters >](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md) elemento, que contiene una lista de prefijos. Las direcciones base de entrada, proporcionadas por IIS, se filtran en función de la lista de prefijos opcional. De forma predeterminada, cuando no se especifica un prefijo, se atraviesan todas las direcciones. Al especificar el prefijo, se provoca que solo la dirección base coincidente para ese esquema se pase a través.  
  
 A continuación, se muestra un ejemplo de código de configuración que utiliza filtros de prefijos.  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="net.tcp://payroll.myorg.com:8000"/>  
        <add prefix="http://shipping.myorg.com:8000"/>  
    </baseAddressPrefixFilters>  
  </serviceHostingEnvironment>  
</system.serviceModel>  
```  
  
 En el ejemplo anterior, net.tcp://payroll.myorg.com: 8000 y http://shipping.myorg.com: 8000 son las únicas direcciones base, para sus esquemas respectivos, que se pasan a través.  
  
 `baseAddressPrefixFilter` no admite los caracteres comodín.  
  
 Las direcciones base proporcionadas por IIS pueden tener direcciones enlazadas a otros esquemas no presentes en la lista `baseAddressPrefixFilters`. Estas direcciones no se filtran.  
  
## <a name="multiple-iis-binding-support-in-net-framework-4-and-later"></a>Compatibilidad de varios enlaces IIS en .NET Framework 4.0 y posteriores  
 A partir de .NET 4, puede habilitar la compatibilidad con varios enlaces en IIS sin tener que elegir una sola dirección base mediante el establecimiento del valor de la propiedad <xref:System.ServiceModel.ServiceHostingEnvironment> de la clase <xref:System.ServiceModel.ServiceHostingEnvironment.MultipleSiteBindingsEnabled%2A>  en true. Esta compatibilidad se limita a los esquemas del protocolo HTTP.  
  
 El siguiente es un ejemplo de código de configuración que usa multipleSiteBindingsEnabled en [ \<serviceHostingEnvironment >](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md).  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment multipleSiteBindingsEnabled="true" >  
  </serviceHostingEnvironment>  
</system.serviceModel>  
```  
  
 Cuando se habilitan varios enlaces de sitios mediante esta configuración, se ignora cualquier configuración de baseAddressPrefixFilters, tanto para el protocolo HTTP como para el protocolo no HTTP.  
  
 Para obtener más información y ejemplos, vea [admiten varios enlaces de sitio de IIS](../../../../docs/framework/wcf/feature-details/supporting-multiple-iis-site-bindings.md) y <xref:System.ServiceModel.ServiceHostingEnvironment.MultipleSiteBindingsEnabled%2A>.  
  
## <a name="extending-addressing-in-wcf-services"></a>Extensión del direccionamiento en servicios WCF  
 El modelo de direccionamiento predeterminado de los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa el URI de la dirección de extremo para los siguientes fines:  
  
-   Para especificar la dirección del agente de escuchas de servicio, la ubicación en la que el extremo realiza escuchas de mensajes,  
  
-   Para especificar el filtro de dirección de SOAP, la dirección que espera un extremo como un encabezado SOAP.  
  
 Se pueden especificar los valores de cada uno de estos propósitos por separado, permitiendo varias extensiones de direccionamiento que cubren escenarios útiles:  
  
-   Intermediarios SOAP: un mensaje enviado por un cliente atraviesa uno o más servicios adicionales que procesan el mensaje antes de que alcance su destino final. Los intermediarios SOAP pueden realizar varias tareas, como almacenar en memoria caché, enrutar, equilibrar la carga o validar el esquema en los mensajes. Para lograr este escenario, los mensajes se envían a una dirección física independiente (`via`) que hace referencia al intermediario en lugar de simplemente a una dirección lógica (`wsa:To`) que hace referencia al destino final.  
  
-   La dirección que realiza escuchas del extremo es un URI privado y está establecida en un valor diferente del de su propiedad `listenURI`.  
  
 La dirección de transporte especificada por `via` es la ubicación a la que se debería enviar inicialmente un mensaje de camino a alguna otra dirección remota especificada por el parámetro `to` donde se encuentra el servicio. En la mayoría de los escenarios de Internet, el URI `via` es igual que la propiedad <xref:System.ServiceModel.EndpointAddress.Uri%2A> de la dirección final `to` del servicio. Estas dos direcciones solo se pueden distinguir cuando es necesario el enrutamiento manual.  
  
### <a name="addressing-headers"></a>Encabezados de direccionamiento  
 Uno o más encabezados SOAP pueden direccionar un extremo además de su URI básico. Un conjunto de escenarios donde esto es útil es un conjunto de escenarios intermediarios de SOAP donde un extremo requiere que los clientes de ese extremo incluyan encabezados SOAP destinados a intermediarios.  
  
 Puede definir encabezados de dirección personalizados de dos maneras: mediante código o mediante configuración:  
  
-   Mediante código, los encabezados de dirección personalizados se crean usando la clase <xref:System.ServiceModel.Channels.AddressHeader> y, a continuación, se utilizan en la construcción de una clase <xref:System.ServiceModel.EndpointAddress>.  
  
-   En configuración, personalizado [ \<encabezados >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) se especifican como elementos secundarios de la [ \<extremo >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) elemento.  
  
 Generalmente, la configuración es preferible al código, puesto que permite cambiar los encabezados después de la implementación.  
  
### <a name="custom-listening-addresses"></a>Direcciones de escuchas personalizadas  
 Puede establecer la dirección de escuchas en un valor diferente que el URI del extremo. Esto es útil en escenarios intermediarios donde la dirección SOAP que se va a exponer es la de un intermediario de SOAP público, mientras que la dirección donde el extremo realmente realiza escuchas es una dirección de la red privada.  
  
 Puede especificar una dirección de escuchas personalizada mediante código o configuración:  
  
-   Mediante código, especifique una dirección de escuchas personalizada agregando una clase <xref:System.ServiceModel.Description.ClientViaBehavior> a la colección de comportamientos del extremo.  
  
-   En configuración, especifique una dirección de escucha personalizada con el `ListenUri` atributo del servicio [ \<extremo >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) elemento.  
  
### <a name="custom-soap-address-filter"></a>Filtro de direcciones SOAP personalizado  
 <xref:System.ServiceModel.EndpointAddress.Uri%2A> se utiliza junto con cualquier propiedad <xref:System.ServiceModel.EndpointAddress.Headers%2A> para definir el filtro de direcciones SOAP de un extremo (<xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A>). De forma predeterminada, este filtro comprueba que un mensaje entrante tenga un encabezado de mensaje `To` que coincida con el URI del extremo y que todos los encabezados de extremo necesarios se encuentren en el mensaje.  
  
 En algunos escenarios, un extremo recibe todos los mensajes que llegan en el transporte subyacente y no solo aquéllos con el encabezado `To` adecuado. Para habilitar esto, el usuario puede utilizar la clase <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>.  
  
## <a name="see-also"></a>Vea también  
 [Especificación de una dirección de punto de conexión](../../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
 [Autenticación e identidad de servicio](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
