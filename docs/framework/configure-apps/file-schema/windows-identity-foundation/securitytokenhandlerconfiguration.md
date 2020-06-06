---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: e3e65820fa4dc341371d4f67689a288cd3f63951
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152572"
---
# \<securityTokenHandlerConfiguration>
Proporciona la configuración para la colección de controladores de token.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration saveBootstrapContext=xs:boolean  
          maximumClockSkew=TimeSpan>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|saveBootstrapContext|Especifica si los tokens de arranque deben incluirse en el token de sesión. El valor también se puede establecer en una colección de controladores de tokens estableciendo el `saveBootstrapContext` atributo en el [\<identityConfiguration>](identityconfiguration.md) elemento. Un valor establecido en la colección de controladores de tokens invalida el valor establecido en el servicio.|  
|maximumClockSkew|<xref:System.TimeSpan>Que especifica el sesgo de reloj máximo permitido. Controla el sesgo de reloj máximo permitido al realizar operaciones dependientes del tiempo, como la validación de la hora de expiración de una sesión de inicio de sesión. El valor predeterminado es 5 minutos, "00:05:00". Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, vea [valores TimeSpan](../windows-workflow-foundation/index.md). El sesgo de reloj máximo también se puede establecer en el nivel de servicio estableciendo el `maximumClockSkew` atributo en el [\<identityConfiguration>](identityconfiguration.md) elemento. Un valor establecido en la colección de controladores de tokens invalida el valor establecido en el servicio.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<audienceUris>](audienceuris.md)|Especifica el conjunto de URI que son identificadores aceptables de este usuario de confianza. Opcional.|  
|[\<caches>](caches.md)|Registra las cachés utilizadas para los tokens de sesión y la detección de reproducción de tokens. Se puede especificar en el nivel de servicio o en una colección de controladores de tokens de seguridad. Opcional.|  
|[\<certificateValidation>](certificatevalidation.md)|Controla la configuración que usan los controladores de token para validar certificados. Se puede especificar en el nivel de servicio o en una colección de controladores de tokens de seguridad. Esta configuración se invalida si un controlador concreto se configura con su propio validador. Opcional.|  
|[\<issuerNameRegistry>](issuernameregistry.md)|Configura el registro de nombres de emisores que usan los controladores de la colección de controladores de tokens. Opcional.|  
|[\<issuerTokenResolver>](issuertokenresolver.md)|Registra el solucionador de tokens de emisor que usan los controladores en la colección de controladores de tokens. La resolución de tokens del emisor se usa para resolver el token de firma en los tokens y mensajes entrantes. Opcional.|  
|[\<serviceTokenResolver>](servicetokenresolver.md)|Registra la resolución del token de servicio que usan los controladores en la colección de controladores de tokens. La resolución de tokens de servicio se usa para resolver el token de cifrado en mensajes y tokens entrantes. Opcional.|  
|[\<tokenReplayDetection>](tokenreplaydetection.md)|Habilita la detección de reproducción de tokens y especifica la hora de expiración de los tokens. Se puede especificar en el nivel de servicio o en una colección de controladores de tokens de seguridad. Opcional.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|Especifica una colección de controladores de tokens de seguridad que se registran con el punto de conexión.|  
  
## <a name="remarks"></a>Comentarios  
 En esta sección se proporcionan los valores de propiedad de un <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> objeto. Los valores configurados en esta sección reemplazan a los configurados en el servicio. Algunos de estos valores se pueden reemplazar a su vez por los valores que se especifican cuando se agrega un controlador a la colección de controladores de tokens de seguridad.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>
      <securityTokenHandlerConfiguration>  
  
        <audienceUris>  
          <clear/>  
          <add value="http://www.example.com/myapp/" />  
        </audienceUris>  
  
        <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel">  
          <trustedIssuers>  
            <add thumbprint="97249e1a … 4c9158de" name="contoso.com" />  
          </trustedIssuers>  
        </issuerNameRegistry>  
  
        <issuerTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
        <serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```
