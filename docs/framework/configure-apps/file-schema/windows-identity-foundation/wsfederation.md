---
title: <wsFederation>
ms.date: 03/30/2017
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
author: BrucePerlerMS
ms.openlocfilehash: 93661af6c907d8cce1a73536a8ebca7bd53c00d8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185514"
---
# \<wsFederation>

Proporciona la configuración para el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsFederation>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml
<system.identityModel.services>  
  <federationConfiguration>  
    <wsFederation authenticationType=xs:string (URI)  
                  freshness=xs:decimal  
                  homerealm=xs:string (URI)  
                  issuer=xs:string (URI)  
                  persistentCookiesOnPassiveRedirects=xs:boolean  
                  passiveRedirectEnabled=xs:boolean  
                  policy=xs:string (URI)  
                  realm=xs:string (URI)  
                  reply=xs:string (URI)  
                  request=xs:string (URI)  
                  requestPtr=xs:string (URI)  
                  requireHttps=xs:boolean  
                  resource=xs:string (URI)  
                  signInQueryString=xs:string  
                  signOutQueryString=xs:string  
                  signOutReply=xs:string (URL)  
    </wsFederation>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|authenticationType|URI que especifica el tipo de autenticación. Establece el parámetro wauth de la solicitud de inicio de sesión de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que el parámetro wauth no se incluye en la solicitud.|  
|actualización|Edad máxima deseada de las solicitudes de autenticación, en minutos. Establece el parámetro wfresh de solicitud de inicio de sesión de WS-Federation. Opcional. El valor predeterminado es cero. Opcional. **ADVERTENCIA:**  En la siguiente versión de .NET Framework 4,5, el `freshness` atributo será de tipo `xs:string` y su valor predeterminado será `null` .|  
|homeRealm|Dominio de inicio del proveedor de identidades (IdP) que se va a usar para la autenticación. Establece el parámetro whr de solicitud de inicio de sesión de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que el parámetro whr no se incluye en la solicitud.|  
|issuer|El URI del emisor de tokens previsto. Establece la dirección URL base de las solicitudes de inicio de sesión y las solicitudes de cierre de sesión de WS-Federation necesarias.|  
|persistentCookiesOnPassiveRedirects|Especifica si las cookies persistentes se emiten en la autenticación. Opcional. El valor predeterminado es "false", no se emiten cookies.|  
|passiveRedirectEnabled|Especifica si el WSFAM está habilitado para redirigir automáticamente las solicitudes no autorizadas a un STS. Opcional. El valor predeterminado es "true", las solicitudes no autorizadas se redirigen automáticamente.|  
|policy|Una dirección URL que especifica la ubicación de la directiva relevante que se va a usar en las solicitudes de inicio de sesión. El valor predeterminado es una cadena vacía. Establece el parámetro wp de solicitud de inicio de sesión de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que el parámetro WP no se incluye en la solicitud.|  
|realm|El URI del territorio solicitante. (Un URI que identifica al usuario de confianza (RP) en el servicio de token de seguridad (STS)). Establece el parámetro de la solicitud de inicio de sesión de WS-Federation wtrealm. Obligatorio.|  
|reply|Una dirección URL que identifica la dirección en la que la aplicación de usuario de confianza (RP) desea recibir las respuestas del Servicio de token de seguridad (STS). Establece el parámetro wreply de la solicitud de inicio de sesión de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que el parámetro wreply no se incluye en la solicitud.|  
|request|Solicitud de emisión de tokens. Establece el parámetro wreq de solicitud de inicio de sesión de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que el parámetro wreq no se incluye en la solicitud. No incluir wreq o el parámetro wreqptr en la solicitud implica que el STS sabe qué tipo de token se debe emitir.|  
|requestPtr|Dirección URL que especifica la ubicación de la solicitud de emisión de tokens. Establece el parámetro wreqptr de la solicitud. Opcional. El valor predeterminado es una cadena vacía, que especifica que el parámetro wreqptr no se incluye en la solicitud. No incluir wreq o el parámetro wreqptr en la solicitud implica que el STS sabe qué tipo de token se debe emitir.|  
|requireHttps|Especifica si la comunicación con el servicio de token de seguridad (STS) debe usar el protocolo HTTPS. Opcional. El valor predeterminado es "true", se debe usar HTTPS.|  
|resource|Un URI que identifica el recurso al que se obtiene acceso, el usuario de confianza (RP), al servicio de token de seguridad (STS). Opcional. Establece el parámetro WRES de la solicitud de inicio de sesión de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que el parámetro WRES no se incluye en la solicitud. **Nota:**  WRES es un parámetro heredado. En `realm` su lugar, especifique el atributo para usar el parámetro wtrealm.|  
|signInQueryString|Proporciona un punto de extensibilidad para especificar los parámetros de consulta definidos por la aplicación en la dirección URL de la solicitud de inicio de sesión de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que no debe incluirse ningún parámetro adicional en la solicitud. Los parámetros se especifican como un fragmento de cadena de consulta con el siguiente formato: `"param1=value1&param2=value2&param3=value3"` y así sucesivamente. **Nota:**  En un archivo de configuración, el carácter "&" de la cadena de consulta debe especificarse mediante su referencia de entidad, `&` .|  
|signOutQueryString|Proporciona un punto de extensibilidad para especificar los parámetros de consulta definidos por la aplicación en la dirección URL de la solicitud de inicio de sesión de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que no debe incluirse ningún parámetro adicional en la solicitud. Los parámetros se especifican como un fragmento de cadena de consulta con el siguiente formato: `"param1=value1&param2=value2&param3=value3"` y así sucesivamente. **Nota:**  En un archivo de configuración, el carácter "&" de la cadena de consulta debe especificarse mediante su referencia de entidad, `&` .|  
|signOutReply|Especifica la dirección URL a la que el servicio de token de seguridad (STS) debe redirigir al cliente durante el cierre de sesión pasivo a través del protocolo WS-Federation. Establece el parámetro wreply en una solicitud de cierre de sesión de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que no debe incluirse ningún parámetro adicional en la solicitud.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|Contiene la configuración que configura el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) y el <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="remarks"></a>Observaciones  

 Puede usar el `<wsFederation>` elemento para configurar los valores predeterminados de los parámetros de WS-Federation y el comportamiento predeterminado de WSFAM. La configuración de los parámetros de WS-Federation se define en las `<wsFederation>` propiedades equivalentes del conjunto de elementos expuestas por la <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> clase. Estas propiedades siguen siendo las mismas para todas las solicitudes emitidas por WSFAM. Puede cambiar los parámetros de WS-Federation dinámicamente durante el procesamiento de la solicitud agregando controladores de eventos para los eventos expuestos por WSFAM; por ejemplo, el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> evento. Para obtener más información, vea la documentación de la <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> clase.  
  
 El `<wsFederation>` elemento se representa mediante la <xref:System.IdentityModel.Services.Configuration.WSFederationElement> clase. La clase representa el propio objeto de configuración <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> . <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration>Se establece una sola instancia en el <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> objeto al que se tiene acceso a través de la <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> propiedad y proporciona la configuración para el WSFAM.  
  
## <a name="example"></a>Ejemplo  

 En el XML siguiente se muestra un `<wsFederation>` elemento que especifica los valores para WSFAM.  
  
> [!WARNING]
> En este ejemplo, WSFAM no es necesario para usar HTTPS. Esto se debe a que el `requireHttps` atributo del `<wsFederation>` elemento está establecido `false` . Esta configuración no se recomienda para la mayoría de los entornos de producción, ya que puede suponer un riesgo para la seguridad.  
  
```xml
<wsFederation passiveRedirectEnabled="true"
              issuer="http://localhost:15839/wsFederationSTS/Issue"
              realm="http://localhost:50969/"
              reply="http://localhost:50969/"
              requireHttps="false"
              signOutReply="http://localhost:50969/SignedOutPage.html"
              signOutQueryString="Param1=value2&Param2=value2"
              persistentCookiesOnPassiveRedirects="true" />
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
