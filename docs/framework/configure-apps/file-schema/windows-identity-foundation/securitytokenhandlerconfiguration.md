---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 168bdc4fbf640b201ebc61462d04727c23f838f2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a>&lt;securityTokenHandlerConfiguration&gt;
Proporciona la configuración de la colección de controladores de tokens.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration >  
  
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
|saveBootstrapContext|Especifica si los tokens de arranque deben incluirse en el token de sesión. El valor también puede establecerse en una colección de controlador de token estableciendo la `saveBootstrapContext` del atributo en el [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento. Un valor establecido en la colección de controlador de token reemplaza al valor establecido en el servicio.|  
|maximumClockSkew|Un <xref:System.TimeSpan> que define el sesgo de reloj permitido máximo. Controla el sesgo de reloj permitido máximo al realizar operaciones de sujetos a limitación temporal, como la validación de la fecha de expiración de una sesión de inicio de sesión. El valor predeterminado es 5 minutos, "00: 05:00". Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, consulte [valores de intervalo de tiempo](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md). El sesgo de reloj máximo también se puede establecer en el nivel de servicio estableciendo el `maximumClockSkew` del atributo en el [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento. Un valor establecido en la colección de controlador de token reemplaza al valor establecido en el servicio.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<audienceUris >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|Especifica el conjunto de URI que son identificadores aceptables de este usuario de confianza. Opcional.|  
|[\<almacena en memoria caché >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registra las memorias caché que se utiliza para la detección de reproducción de tokens y símbolos de sesión. Puede especificarse en el nivel de servicio o en una colección de controlador de token de seguridad. Opcional.|  
|[\<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Controla la configuración que usan los controladores de tokens para validar certificados. Puede especificarse en el nivel de servicio o en una colección de controlador de token de seguridad. Estos valores se sustituyen si se configura un controlador específico con su propio validador. Opcional.|  
|[\<issuerNameRegistry >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|Configura el registro de nombre de emisor que se usa por los controladores de la colección de controlador de token. Opcional.|  
|[\<issuerTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|Registra a la resolución del token de emisor que se usa por los controladores de la colección de controlador de token. La resolución del token de emisor se utiliza para resolver el token de firma en mensajes y los tokens entrantes. Opcional.|  
|[\<serviceTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|Registra a la resolución del token de servicio que usa controladores en la colección de controlador de token. La resolución del token de servicio se utiliza para resolver el token de cifrado de mensajes y los tokens entrantes. Opcional.|  
|[\<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|Habilita la detección de reproducción de tokens y especifica la hora de expiración de símbolos (tokens). Puede especificarse en el nivel de servicio o en una colección de controlador de token de seguridad. Opcional.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Especifica una colección de controladores de tokens de seguridad que están registrados con el punto de conexión.|  
  
## <a name="remarks"></a>Comentarios  
 Esta sección proporcionan valores de propiedad para un <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> objeto. Configuración realizada en esta sección reemplaza a las que configura en el servicio. Algunas de estas opciones a su vez, pueden reemplazarse por los valores que se especifican cuando se agrega un controlador a la colección de controlador de token de seguridad.  
  
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
