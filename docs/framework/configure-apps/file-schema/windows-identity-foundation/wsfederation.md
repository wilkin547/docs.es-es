---
title: <wsFederation>
ms.date: 03/30/2017
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
author: BrucePerlerMS
ms.openlocfilehash: 53f3943524c45a43ddb60553b8ff45f19df66b14
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152468"
---
# <a name="wsfederation"></a>\<wsFederation>
Proporciona la <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> configuración para el (WSFAM).  
  
[**\<configuración>**](../configuration-element.md)\
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
|authenticationType|URI que especifica el tipo de autenticación. Establece el parámetro wauth de solicitud de inicio de sesión de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que el parámetro wauth no se incluye en la solicitud.|  
|Frescura|Edad máxima deseada de las solicitudes de autenticación, en minutos. Establece el parámetro wfresh de solicitud de inicio de sesión de WS-Federation. Opcional. El valor predeterminado es 0. Opcional. **Advertencia:**  En la próxima versión de .NET `freshness` Framework 4.5, el atributo será de tipo `xs:string` y su valor predeterminado será `null`.|  
|homeRealm|El dominio principal del proveedor de identidades (IdP) que se usará para la autenticación. Establece el parámetro whr de solicitud de inicio de sesión de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que el parámetro whr no se incluye en la solicitud.|  
|issuer|El URI del emisor de tokens previsto. Establece la dirección URL base de las solicitudes de inicio de sesión de WS-Federation y las solicitudes de cierre de sesión necesarias.|  
|persistentCookiesOnPassiveRedirects|Especifica si las cookies persistentes se emiten en la autenticación. Opcional. El valor predeterminado es "false", no se emiten cookies.|  
|passiveRedirectEnabled|Especifica si WSFAM está habilitado para redirigir automáticamente las solicitudes no autorizadas a un STS. Opcional. El valor predeterminado es "true", las solicitudes no autorizadas se redirigen automáticamente.|  
|policy|Dirección URL que especifica la ubicación de la directiva relevante que se usará en las solicitudes de inicio de sesión. El valor predeterminado es una cadena vacía. Establece el parámetro wp de solicitud de inicio de sesión de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que el wp parámetro no se incluye en la solicitud.|  
|realm|El URI del reino solicitante. (Un URI que identifica al usuario de confianza (RP) para el servicio de token de seguridad (STS).) Establece el parámetro de solicitud de inicio de sesión wS-Federation de solicitud. Necesario.|  
|reply|Una dirección URL que identifica la dirección en la que la aplicación de usuario de confianza (RP) desea recibir las respuestas del Servicio de token de seguridad (STS). Establece el parámetro wreply de solicitud de inicio de sesión de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que el parámetro wreply no se incluye en la solicitud.|  
|request|La solicitud de emisión de tokens. Establece el parámetro wreq de solicitud de inicio de sesión de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que el parámetro wreq no se incluye en la solicitud. Sin incluir el wreq o el parámetro wreqptr en la solicitud implica que el STS sabe qué tipo de token emitir.|  
|requestPtr|Dirección URL que especifica la ubicación de la solicitud de emisión de tokens. Establece el parámetro wreqptr de solicitud. Opcional. El valor predeterminado es una cadena vacía, que especifica que el parámetro wreqptr no se incluye en la solicitud. Sin incluir el wreq o el parámetro wreqptr en la solicitud implica que el STS sabe qué tipo de token emitir.|  
|requireHttps|Especifica si la comunicación con el servicio de token de seguridad (STS) debe usar el protocolo HTTPS. Opcional. El valor predeterminado es "true", se debe usar HTTPS.|  
|resource|Un URI que identifica el recurso al que se obtiene acceso, el usuario de confianza (RP), al servicio de token de seguridad (STS). Opcional. Establece el parámetro wres de solicitud de inicio de sesión de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que el parámetro wres no se incluye en la solicitud. **Nota:** wres es un parámetro heredado. Especifique `realm` el atributo para utilizar el parámetro wtrealm en su lugar.|  
|signInQueryString|Proporciona un punto de extensibilidad para especificar parámetros de consulta definidos por la aplicación en la dirección URL de solicitud de inicio de sesión de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que no se deben incluir parámetros adicionales en la solicitud. Los parámetros se especifican como un fragmento `"param1=value1&param2=value2&param3=value3"` de cadena de consulta utilizando el siguiente formulario: y así sucesivamente. **Nota:**  En un archivo de configuración, el carácter '&" de `&`la cadena de consulta debe especificarse mediante su referencia de entidad, .|  
|signOutQueryString|Proporciona un punto de extensibilidad para especificar parámetros de consulta definidos por la aplicación en la dirección URL de solicitud de inicio de sesión de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que no se deben incluir parámetros adicionales en la solicitud. Los parámetros se especifican como un fragmento `"param1=value1&param2=value2&param3=value3"` de cadena de consulta utilizando el siguiente formulario: y así sucesivamente. **Nota:**  En un archivo de configuración, el carácter '&" de `&`la cadena de consulta debe especificarse mediante su referencia de entidad, .|  
|signOutReply|Especifica la dirección URL a la que el servicio de token de seguridad (STS) debe redirigir al cliente durante el cierre de sesión pasivo a través del protocolo WS-Federation. Establece el parámetro wreply en una solicitud de cierre de sesión de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que no se deben incluir parámetros adicionales en la solicitud.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|Contiene los valores <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> que configuran (WSFAM) y (SAM). <xref:System.IdentityModel.Services.SessionAuthenticationModule>|  
  
## <a name="remarks"></a>Observaciones  
 Puede usar `<wsFederation>` el elemento para configurar la configuración predeterminada del parámetro WS-Federation y el comportamiento predeterminado para WSFAM. La configuración de parámetros `<wsFederation>` WS-Federation definida <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> en el elemento establece propiedades equivalentes expuestas por la clase. Estas propiedades siguen siendo las mismas para cada solicitud emitida por WSFAM. Puede cambiar los parámetros de WS-Federation dinámicamente durante el procesamiento de solicitudes agregando controladores de eventos para los eventos expuestos por WSFAM; por ejemplo, <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> el evento. Para obtener más información, <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> consulte la documentación de la clase.  
  
 El `<wsFederation>` elemento se representa <xref:System.IdentityModel.Services.Configuration.WSFederationElement> mediante la clase. El propio objeto de configuración <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> está representado por la clase. Se <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> establece una única <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> instancia en el <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> objeto al que se tiene acceso a través de la propiedad y proporciona configuración para WSFAM.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML `<wsFederation>` muestra un elemento que especifica la configuración de WSFAM.  
  
> [!WARNING]
> En este ejemplo, el WSFAM no es necesario utilizar HTTPS. Esto se `requireHttps` debe a `<wsFederation>` que `false`el atributo del elemento se establece . Esta configuración no se recomienda para la mayoría de los entornos de producción, ya que puede presentar un riesgo de seguridad.  
  
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
