---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: d66771ec7ed52ace52df6bb3bfafdcf9cce989b5
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2018
ms.locfileid: "48838486"
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a>&lt;securityTokenHandlerConfiguration&gt;
Proporciona la configuración de la colección de controladores de token.  
  
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
|saveBootstrapContext|Especifica si los tokens de arranque deben incluirse en el token de sesión. El valor también se puede establecer en una colección de controladores de token estableciendo el `saveBootstrapContext` atributo el [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento. Un valor establecido en la colección de controladores de token reemplaza al valor establecido en el servicio.|  
|maximumClockSkew|Un <xref:System.TimeSpan> que especifica el sesgo del reloj máximo permitido. Controla el sesgo de reloj permitido máximo al realizar operaciones sensibles a la hora, como la validación de la hora de expiración de una inicio de sesión. El valor predeterminado es 5 minutos, "00: 05:00". Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, vea [valores Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md). El sesgo de reloj máximo también se puede establecer el nivel de servicio estableciendo el `maximumClockSkew` atributo el [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento. Un valor establecido en la colección de controladores de token reemplaza al valor establecido en el servicio.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<audienceUris >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|Especifica el conjunto de URI que son identificadores aceptables de este usuario autenticado. Opcional.|  
|[\<las memorias caché >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registra las memorias caché utilizadas para la detección de reproducción de tokens y los tokens de sesión. Puede especificarse en el nivel de servicio o en una colección de controladores de token de seguridad. Opcional.|  
|[\<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Controla la configuración que los controladores de token que se usan para validar los certificados. Puede especificarse en el nivel de servicio o en una colección de controladores de token de seguridad. Esta configuración se invalida si un controlador específico se configura con su propio validador. Opcional.|  
|[\<issuerNameRegistry >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|Configura el registro de nombre del emisor que se usa los controladores en la colección de controladores de token. Opcional.|  
|[\<issuerTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|Registra a la resolución del token del emisor que se usa los controladores en la colección de controladores de token. La resolución del emisor del token se utiliza para resolver el token de firma en mensajes y los tokens entrantes. Opcional.|  
|[\<serviceTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|Registra a la resolución de tokens de servicio que se usa los controladores en la colección de controladores de token. La resolución del servicio de token se usa para resolver el token cifrado en los mensajes y los tokens entrantes. Opcional.|  
|[\<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|Habilita la detección de reproducción de tokens y especifica la hora de expiración de tokens. Puede especificarse en el nivel de servicio o en una colección de controladores de token de seguridad. Opcional.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Especifica una colección de controladores de token de seguridad que están registrados con el punto de conexión.|  
  
## <a name="remarks"></a>Comentarios  
 Esta sección proporcionan valores de propiedad para un <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> objeto. Configurada en esta sección invalidará los configurados en el servicio. Algunos de estos valores pueden invalidarse a su vez, los valores que se especifican cuando se agrega un controlador a la colección de controladores de token de seguridad.  
  
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
