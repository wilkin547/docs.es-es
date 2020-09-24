---
title: <serviceDebug>
ms.date: 03/30/2017
ms.assetid: 6d7ea986-f232-49fe-842c-f934d9966889
ms.openlocfilehash: 8236e581ee754a39ae32fa97084b8e2bfbaee652
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153877"
---
# \<serviceDebug>

Especifica las características de depuración y de información de ayuda para un servicio Windows Communication Foundation (WCF).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceDebug>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<serviceDebug httpHelpPageBinding="String"
              httpHelpPageBindingConfiguration="String"
              httpHelpPageEnabled="Boolean"
              httpHelpPageUrl="Uri"
              httpsHelpPageBinding="String"
              httpsHelpPageBindingConfiguration="String"
              httpsHelpPageEnabled="Boolean"
              httpsHelpPageUrl="Uri"
              includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|httpHelpPageBinding|Valor de cadena que especifica el tipo de enlace que se va a usar cuando se utilice HTTP para tener acceso a la página de ayuda del servicio.<br /><br /> Solo se admitirán los enlaces con elementos de enlace internos que admiten <xref:System.ServiceModel.Channels.IReplyChannel?displayProperty=nameWithType>. Además, la propiedad <xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType> del enlace debe ser <xref:System.ServiceModel.Channels.MessageVersion.None?displayProperty=nameWithType>.|  
|httpHelpPageBindingConfiguration|Cadena que especifica el nombre del enlace que se especifica en el atributo `httpHelpPageBinding`, que hace referencia a la información de configuración adicional de este enlace. El mismo nombre se debe definir en la sección `<bindings>`.|  
|httpHelpPageEnabled|Valor booleano que controla si WCF publica una página de ayuda HTML en la dirección especificada por el `httpHelpPageUrl` atributo. De manera predeterminada, es `true`.<br /><br /> Puede establecer esta propiedad en `false` para deshabilitar la publicación de una página de ayuda HTML visible en exploradores HTML.<br /><br /> Para asegurarse de que la página de ayuda HTML se publica en la ubicación controlada por el atributo `httpHelpPageUrl`, debe establecer este atributo en `true`. Además, se debe cumplir una de las condiciones siguientes:<br /><br /> -El `httpHelpPageUrl` atributo es una dirección absoluta que admite el esquema del protocolo http.<br />-Hay una dirección base para el servicio que admite el esquema del protocolo HTTP.<br /><br /> Aunque se produzca una excepción si una dirección absoluta que no admite el esquema del protocolo HTTP está asignada al atributo `httpHelpPageUrl`, cualquier otro escenario en el que ninguno de los criterios anteriores se cumpla tiene como resultado que no se produzca ninguna excepción ni ninguna página de ayuda HTML.|  
|httpHelpPageUrl|Un URI que especifica la dirección URL basada en HTTP relativa o absoluta del archivo de ayuda HTML personalizado que el usuario ve cuando el punto de conexión se ve mediante un explorador HTML.<br /><br /> Puede utilizar este atributo para habilitar el uso de un archivo de ayuda HTML personalizado que se devuelve de una solicitud Http/Get, por ejemplo, de un explorador HTML. La ubicación del archivo de ayuda HTML se resuelve como sigue.<br /><br /> 1. Si el valor de este atributo es una dirección relativa, la ubicación del archivo de ayuda HTML es el valor de la dirección base del servicio que admite solicitudes HTTP, más este valor de propiedad.<br />2. Si el valor de este atributo es una dirección absoluta y admite solicitudes HTTP, la ubicación del archivo de ayuda HTML es el valor de esta propiedad.<br />3. Si el valor de este atributo es absoluto pero no admite solicitudes HTTP, se produce una excepción.<br /><br /> Este atributo solo es válido cuando el `httpHelpPageEnabled` atributo es `true` .|  
|httpsHelpPageBinding|Valor de cadena que especifica el tipo de enlace que se va a usar cuando se utilice HTTPS para tener acceso a la página de ayuda del servicio.<br /><br /> Solo se admitirán los enlaces con elementos de enlace internos que admiten <xref:System.ServiceModel.Channels.IReplyChannel>. Además, la propiedad <xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType> del enlace debe ser <xref:System.ServiceModel.Channels.MessageVersion.None?displayProperty=nameWithType>.|  
|httpsHelpPageBindingConfiguration|Cadena que especifica el nombre del enlace que se especifica en el atributo `httpsHelpPageBinding`, que hace referencia a la información de configuración adicional de este enlace. El mismo nombre se debe definir en la sección `<bindings>`.|  
|httpsHelpPageEnabled|Valor booleano que controla si WCF publica una página de ayuda HTML en la dirección especificada por el `httpsHelpPageUrl` atributo. De manera predeterminada, es `true`.<br /><br /> Puede establecer esta propiedad en `false` para deshabilitar la publicación de una página de ayuda HTML visible en exploradores HTML.<br /><br /> Para asegurarse de que la página de ayuda HTML se publica en la ubicación controlada por el atributo `httpsHelpPageUrl`, debe establecer este atributo en `true`. Además, se debe cumplir una de las condiciones siguientes:<br /><br /> -El `httpsHelpPageUrl` atributo es una dirección absoluta que admite el esquema del protocolo HTTPS.<br />-Hay una dirección base para el servicio que admite el esquema del protocolo HTTPS.<br /><br /> Aunque se produzca una excepción si una dirección absoluta que no admite el esquema de protocolo HTTPS está asignada al atributo `httpsHelpPageUrl`, cualquier otro escenario en el que ninguno de los criterios anteriores se cumple tiene como resultado que no se produzca ninguna excepción ni ninguna página de ayuda HTML.|  
|httpsHelpPageUrl|Un URI que especifica la dirección URL basada en HTTPS relativa o absoluta del archivo de ayuda HTML personalizado que el usuario ve cuando el extremo se ve mediante un explorador HTML.<br /><br /> Puede utilizar este atributo para habilitar el uso de un archivo de ayuda HTML personalizado que se devuelve de una solicitud HTTPS/Get, por ejemplo, de un explorador HTML. La ubicación del archivo de ayuda HTML se resuelve como sigue:<br /><br /> -Si el valor de esta propiedad es una dirección relativa, la ubicación del archivo de ayuda HTML es el valor de la dirección base del servicio que admite solicitudes HTTPS, más este valor de propiedad.<br />-Si el valor de esta propiedad es una dirección absoluta y admite solicitudes HTTPS, la ubicación del archivo de ayuda HTML es el valor de esta propiedad.<br />-Si el valor de esta propiedad es absoluto pero no admite solicitudes HTTPS, se produce una excepción.<br /><br /> Este atributo solo es válido cuando el `httpHelpPageEnabled` atributo es `true` .|  
|includeExceptionDetailInFaults|Un valor que especifica si incluir la información de excepción administrada en el detalle de errores SOAP devueltos al cliente para su depuración. El valor predeterminado es `false`.<br /><br /> Si se establece el atributo en `true`, puede permitir el flujo de información de excepción administrada al cliente para propósitos de depuración, así como la publicación de archivos de información HTML para usuarios que examinen el servicio en exploradores web. **PRECAUCIÓN:**  Devolver información de excepción administrada a los clientes puede suponer un riesgo para la seguridad. Esto es porque los detalles de excepción exponen información acerca de la implementación de servicio interna que podría ser usada por clientes no autorizados.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Especifica un elemento de comportamiento.|  
  
## <a name="remarks"></a>Comentarios  

 Establecer `includeExceptionDetailInFaults` en `true` permite al servicio devolver cualquier excepción producida por el código de aplicación incluso si la excepción no se declara mediante <xref:System.ServiceModel.FaultContractAttribute> . Este valor es útil al depurar los casos donde el servidor produce una excepción inesperada. Al usar este atributo, se devuelve un formulario serializado de la excepción desconocida y usted puede examinar más detalles de la excepción.  
  
> [!CAUTION]
> Devolver la información de excepción administrada a los clientes puede suponer un riesgo para la seguridad porque los datos de la excepción exponen información sobre la implementación de servicio interna que los clientes desautorizados podrían utilizar. Debido a los problemas de seguridad implicados, se recomienda encarecidamente que sólo realice este procedimiento en escenarios de depuración controlados. Debería establecer `includeExceptionDetailInFaults` en `false` al implementar su aplicación.  
  
 Para obtener más información sobre los problemas de seguridad relacionados con la excepción administrada, vea [especificar y controlar errores en contratos y servicios](../../../wcf/specifying-and-handling-faults-in-contracts-and-services.md). Para obtener un ejemplo de código, vea [comportamiento de depuración del servicio](../../../wcf/samples/service-debug-behavior.md).  
  
 También puede establecer `httpsHelpPageEnabled` y `httpsHelpPageUrl` para habilitar o deshabilitar la página de ayuda. Cada servicio puede exponer opcionalmente una página de ayuda que contiene información sobre el servicio que incluye el extremo para obtener WSDL para el servicio. Esto puede estar habilitado estableciendo `httpHelpPageEnabled` como `true`. Esto permite devolver la página de ayuda a una solicitud GET en la dirección base del servicio. Puede cambiar esta dirección estableciendo el  atributo `httpHelpPageUrl`. Además, puede hacerlo de manera segura utilizando HTTPS en lugar de HTTP.  
  
 Los atributos opcionales `httpHelpPageBinding` y `httpHelpPageBinding` le permiten configurar los enlaces utilizados para tener acceso a la página web del servicio. Si no se especifican, los enlaces predeterminados (`HttpTransportBindingElement`, en el caso de HTTP y `HttpsTransportBindingElement`, en el caso de HTTPS) se utilizan según corresponda para el acceso de página de ayuda del servicio. Observe que no puede utilizar estos atributos con los enlaces WCF integrados. Solo se admitirán los enlaces con elementos de enlace internos que admiten XREF: System. ServiceModel. Channels. IReplyChannel>. Además, la propiedad <xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType> del enlace debe ser <xref:System.ServiceModel.Channels.MessageVersion.None?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.ServiceDebugElement>
- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
- [Especificación y administración de errores en contratos y servicios](../../../wcf/specifying-and-handling-faults-in-contracts-and-services.md)
- [Administración de excepciones y errores](../../../wcf/extending/handling-exceptions-and-faults.md)
- [Comportamiento de depuración de servicio](../../../wcf/samples/service-debug-behavior.md)
