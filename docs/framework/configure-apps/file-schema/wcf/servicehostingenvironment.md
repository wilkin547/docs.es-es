---
title: <serviceHostingEnvironment>
ms.date: 03/30/2017
ms.assetid: 4f8a7c4f-e735-4987-979a-b74fcdae2652
ms.openlocfilehash: 165dbed1b78d00f8d4dd3e482b9fee8a23db60da
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399614"
---
# \<serviceHostingEnvironment>
Este elemento define el tipo en el que el entorno de hospedaje de servicio crea instancias de un transporte determinado. Si este elemento está vacío, se usa el tipo predeterminado. Este elemento solo se puede usar en los archivos de configuración del nivel de aplicación o equipo.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceHostingEnvironment>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="Boolean"
                           minFreeMemoryPercentageToActivateService="Integer"
                           multipleSiteBindingsEnabled="Boolean">
  <baseAddressPrefixFilters>
    <add prefix="string" />
  </baseAddressPrefixFilters>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|aspNetCompatibilityEnabled|Un valor booleano que indica si se ha activado el modo de compatibilidad de ASP.NET para la aplicación actual. De manera predeterminada, es `false`.<br /><br /> Cuando este atributo se establece en `true` , las solicitudes a los servicios Windows Communication Foundation (WCF) fluyen a través de la canalización HTTP ASP.net y se prohíbe la comunicación a través de protocolos que no son http. Para obtener más información, vea [servicios WCF y ASP.net](../../../wcf/feature-details/wcf-services-and-aspnet.md).|  
|minFreeMemoryPercentageToActivateService|Un entero que especifica la cantidad mínima de memoria libre que debe estar disponible para el sistema, antes de que se pueda activar un servicio WCF. **PRECAUCIÓN:**  Si se especifica este atributo junto con la confianza parcial en el archivo Web. config de un servicio WCF, se producirá una <xref:System.Security.SecurityException> cuando se ejecute el servicio.|  
|multipleSiteBindingsEnabled|Valor booleano que especifica si están habilitados varios enlaces de IIS por sitio.<br /><br /> IIS se compone de sitios web, que son contenedores de aplicaciones virtuales que contienen directorios virtuales. Se puede tener acceso a la aplicación de un sitio a través de uno o varios enlaces de IIS. Un enlace de IIS proporciona dos piezas de información: un protocolo de enlace e información de enlace. El protocolo de enlace define el esquema sobre el que se produce la comunicación, y la información de enlace es la información usada para tener acceso al sitio. Un ejemplo de un protocolo de enlace puede ser HTTP, mientras que la información de enlace puede contener una dirección IP, un puerto, un encabezado de host, etc.<br /><br /> IIS permite especificar varios enlaces de IIS por sitio, lo que genera varias direcciones base por esquema. Sin embargo, un servicio de Windows Communication Foundation (WCF) hospedado en un sitio permite el enlace solo a una baseAddress por esquema.<br /><br /> Para habilitar varios enlaces de IIS por sitio para un servicio de Windows Communication Foundation (WCF), establezca este atributo en `true` . Observe que solo se admiten varios enlaces del sitio para el protocolo HTTP. La dirección de puntos de conexión en el archivo de configuración tiene que ser un URI completo.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<baseAddressPrefixFilters>](baseaddressprefixfilters.md)|Una colección de elementos de configuración que especifican los filtros de prefijo de las direcciones base usadas por el host de servicio.|  
|[\<serviceActivations>](serviceactivations.md)|Sección de configuración que describe la configuración de activación.|  
|[\<transportConfigurationTypes>](transportconfigurationtypes.md)|Una colección de elementos de configuración que identifican el tipo de un transporte determinado.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|serviceModel|El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation (WCF).|  
  
## <a name="remarks"></a>Comentarios  
 De forma predeterminada, los servicios WCF se ejecutan en paralelo con ASP.NET en dominios de aplicación hospedados (AppDomain). Aunque WCF y ASP.NET pueden coexistir en el mismo AppDomain, la canalización de HTTP de ASP.NET no procesa de forma predeterminada las solicitudes de WCF. Como resultado, varios elementos de la plataforma de la aplicación ASP.NET no están disponibles para los servicios WCF. Entre ellas se incluyen las siguientes:  
  
- Autorización de dirección URL/archivo de ASP.NET  
  
- Suplantación de ASP.NET  
  
- Estado de sesión basado en cookies  
  
- HttpContext.Current  
  
- Extensibilidad de la canalización a través de HttpModule personalizado  
  
 Si sus servicios WCF necesitan funcionar en el contexto de ASP.NET, y solo comunicarse sobre HTTP, puede usar el modo de compatibilidad de ASP.NET de WCF. Este modo se activa cuando el atributo `aspNetCompatibilityEnabled` se establece en `true` en el nivel de aplicación. Las implementaciones del servicio deben declarar su capacidad de ejecutarse en modo de compatibilidad usando la clase <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>. Cuando el modo de compatibilidad está habilitado  
  
- Se exige la autorización de dirección URL/archivo de ASP.NET antes que la autorización de WCF. Una decisión de autorización se basa en la identidad a nivel de transporte de la solicitud. Se omiten las identidades a nivel de mensaje.  
  
- Las operaciones del servicio WCF empiezan a ejecutarse en el contexto de suplantación de ASP.NET. Si la suplantación de ASP.NET y la suplantación de WCF están habilitadas para un servicio concreto, se aplica el contexto de suplantación de WCF.  
  
- HttpContext.Current se puede usar del código del servicio WCF y se evita que los servicios expongan los puntos de conexión que no son HTTP.  
  
- La canalización de ASP.NET procesa las solicitudes de WCF. HttpModules que se ha configurado para actuar en solicitudes entrante también puede procesar las solicitudes de WCF. Éstas pueden incluir componentes de plataforma de ASP.NET (por ejemplo, <xref:System.Web.SessionState.SessionStateModule>), y también módulos personalizados de terceros.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra cómo habilitar el modo de compatibilidad de ASP.  
  
## <a name="code"></a>Código  
  
```xml  
<serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [Hospedar aplicaciones de WPF](../../../wcf/feature-details/hosting.md)
- [Servicios WCF y ASP.NET](../../../wcf/feature-details/wcf-services-and-aspnet.md)
