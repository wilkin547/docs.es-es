---
title: '&lt;wsFederation&gt;'
ms.date: 03/30/2017
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: de7be463403b675e5f03786e85807e6685348680
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltwsfederationgt"></a>&lt;wsFederation&gt;
Proporciona la configuración para el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM).  
  
\<system.identityModel.services >  
\<federationConfiguration >  
\<wsFederation >  
  
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
|authenticationType|Un URI que especifica el tipo de autenticación. Establece el parámetro de wauth de inicio de sesión de la solicitud de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que el parámetro wauth no está incluido en la solicitud.|  
|índice de actualización|El tiempo máximo deseado de las solicitudes de autenticación, en minutos. Establece el parámetro de wfresh de inicio de sesión de la solicitud de WS-Federation. Opcional. El valor predeterminado es cero. Opcional. **Advertencia:** en la próxima versión de .NET Framework 4.5, la `freshness` será el atributo de tipo `xs:string` y su valor predeterminado será `null`.|  
|homeRealm|El dominio de inicio del proveedor de identidades (IP) que se usará para la autenticación. Establece el parámetro de horas de servicio de inicio de sesión de la solicitud de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que el parámetro whr no está incluido en la solicitud.|  
|issuer|El URI del emisor del token previsto. Establece las solicitudes de inicio de sesión de dirección URL de WS-Federation base y las solicitudes de cierre de sesión necesarias.|  
|persistentCookiesOnPassiveRedirects|Especifica si las cookies persistentes se emiten en la autenticación. Opcional. El valor predeterminado es "false", no se emiten las cookies.|  
|passiveRedirectEnabled|Especifica si está habilitado el WSFAM para redirigir solicitudes no autorizadas de manera automática a un STS. Opcional. El valor predeterminado es "true", automáticamente se redirigen las solicitudes no autorizadas.|  
|de excepción no controlada|Una dirección URL que especifica la ubicación de la directiva correspondiente a usar en las solicitudes de inicio de sesión. El valor predeterminado es una cadena vacía. Establece el parámetro de wp de inicio de sesión de la solicitud de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que el parámetro wp no está incluido en la solicitud.|  
|realm|El URI del territorio del solicitante. (Un URI que identifica el usuario de confianza (RP) para el servicio de token de seguridad (STS).) Establece el parámetro de solicitud de solicitud wtrealm inicio de sesión de WS-Federation. Requerido.|  
|reply|Una dirección URL que identifica la dirección a la que la aplicación del usuario (RP) autenticado le gustaría recibir respuestas desde el servicio de Token de seguridad (STS). Establece el parámetro de wreply de inicio de sesión de la solicitud de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que el parámetro wreply no está incluido en la solicitud.|  
|request|La solicitud de emisión de tokens. Establece el parámetro wreq de WebRequest de inicio de sesión de la solicitud de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que el parámetro wreq de WebRequest no se incluye en la solicitud. No incluya el wreq de WebRequest o el parámetro wreqptr en la solicitud implica que el STS sabe qué tipo de token que se va a emitir.|  
|requestPtr|Una dirección URL que especifica la ubicación de la solicitud de emisión de tokens. Establece el parámetro de solicitud wreqptr. Opcional. El valor predeterminado es una cadena vacía, que especifica que el parámetro wreqptr no está incluido en la solicitud. No incluya el wreq de WebRequest o el parámetro wreqptr en la solicitud implica que el STS sabe qué tipo de token que se va a emitir.|  
|requireHttps|Especifica si la comunicación con el servicio de token de seguridad (STS) debe utilizar el protocolo HTTPS. Opcional. El valor predeterminado es "true", se debe usar HTTPS.|  
|recurso|Un URI que identifica el recurso que se obtiene acceso, el usuario de confianza (RP), a la que el servicio de token de seguridad (STS). Opcional. Establece el parámetro de wres de inicio de sesión de la solicitud de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que el parámetro wres no está incluido en la solicitud. **Nota:** wres es un parámetro heredado. Especifique el `realm` atributo que desea usar el parámetro wtrealm en su lugar.|  
|signInQueryString|Proporciona un punto de extensibilidad para especificar parámetros de consulta de aplicación definida en la dirección URL de inicio de sesión de la solicitud de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que no se debe incluir ningún parámetro adicional en la solicitud. Los parámetros se especifican como un fragmento de la cadena de consulta con el formato siguiente: `"param1=value1&param2=value2&param3=value3"` y así sucesivamente. **Nota:** en un archivo de configuración del "&" carácter en la cadena de consulta debe especificarse utilizando su referencia de entidad, `&`.|  
|signOutQueryString|Proporciona un punto de extensibilidad para especificar parámetros de consulta de aplicación definida en la dirección URL de inicio de sesión de la solicitud de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que no se debe incluir ningún parámetro adicional en la solicitud. Los parámetros se especifican como un fragmento de la cadena de consulta con el formato siguiente: `"param1=value1&param2=value2&param3=value3"` y así sucesivamente. **Nota:** en un archivo de configuración del "&" carácter en la cadena de consulta debe especificarse utilizando su referencia de entidad, `&`.|  
|signOutReply|Especifica la dirección URL a la que se debe redirigir el cliente con el servicio de token de seguridad (STS) durante el cierre de sesión a través del protocolo WS-Federation pasivo. Establece el parámetro wreply en una solicitud de cierre de sesión de WS-Federation. Opcional. El valor predeterminado es una cadena vacía, que especifica que no se debe incluir ningún parámetro adicional en la solicitud.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Contiene los valores que configuran la <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) y <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="remarks"></a>Comentarios  
 Puede usar el `<wsFederation>` elemento que se va a configurar la configuración de parámetros de WS-Federation de manera predeterminada y comportamiento predeterminado para el WSFAM. Configuración de parámetros de WS-Federation definida en el `<wsFederation>` elemento establece las propiedades equivalentes expuestas por la <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> clase. Estas propiedades son iguales para cada solicitud emitida por la WSFAM. Puede cambiar los parámetros de WS-Federation dinámicamente durante la solicitud de procesamiento mediante la adición de controladores de eventos para los eventos expuestos por WSFAM; Por ejemplo, el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> eventos. Para obtener más información, consulte la documentación para el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> clase.  
  
 El `<wsFederation>` elemento representado por la <xref:System.IdentityModel.Services.Configuration.WSFederationElement> clase. El propio objeto de configuración se representa mediante la <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> clase. Una sola <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> instancia se establece en el <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> objeto que se tiene acceso a través de la <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> propiedad y proporciona la configuración para el WSFAM.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra un `<wsFederation>` elemento que especifica valores para el WSFAM.  
  
> [!WARNING]
>  En este ejemplo, la WSFAM no tiene que usar HTTPS. Esto es porque el `requireHttps` del atributo en el `<wsFederation>` se establece el elemento `false`. Esta configuración no se recomienda para la mayoría de los entornos de producción, tal y como puede suponer un riesgo de seguridad.  
  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>  
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
