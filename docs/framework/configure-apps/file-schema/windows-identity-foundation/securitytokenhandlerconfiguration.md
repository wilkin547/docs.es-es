---
title: "&lt;securityTokenHandlerConfiguration&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# &lt;securityTokenHandlerConfiguration&gt;
mode  
  
## Sintaxis  
  
```  
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
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|saveBootstrapContext|Especifica si debe incluirse bootstrap símbolos \(tokens\) en el símbolo de sesión.  El valor también puede establecer en una colección de controladores de símbolo \(token\) estableciendo la `saveBootstrapContext` de atributo en el [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.  Opcional.|  
|Elemento|Descripción  Controla el sesgo de d reloj máximo permitido al realizar operaciones de sensibles al tiempo, como la validación de la hora de caducidad de una sesión de inicio de sesión.  El atributo  es necesario.  Para obtener más información acerca de cómo especificar <xref:System.TimeSpan> valores, consulte [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_TimespanValues).  El desfase de reloj máximo también puede establecer el nivel de servicio estableciendo la `maximumClockSkew` de atributo en el [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.  Un valor establecido en la colección de controladores de símbolo \(token\) reemplaza el valor establecido en el servicio.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<audienceUris\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|Especifica el conjunto de identificadores URI que son aceptables identificadores de esta parte que confía.  Opcional.|  
|[\<caches\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|El atributo  es necesario.  Se puede especificar en el nivel de servicio o en una colección de controladores de token de seguridad.  Opcional.|  
|[\<certificateValidation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Elemento  Descripción  Si un controlador específico está configurado con su propio control de validación, se pasan estos valores.  Opcional.|  
|[\<issuerNameRegistry\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|Configura el registro de nombre de emisor que utiliza controladores en la colección de controladores de símbolo \(token\).  Opcional.|  
|[\<issuerTokenResolver\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|Registra a la resolución de símbolo \(token\) de emisor que utiliza controladores en la colección de controladores de símbolo \(token\).  Se utiliza la resolución de símbolo \(token\) de emisor para resolver el token de firma de tokens y los mensajes entrantes.  Opcional.|  
|[\<serviceTokenResolver\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|Registra a la resolución de símbolo \(token\) de servicio que utiliza controladores en la colección de controladores de símbolo \(token\).  La resolución del servicio de símbolo \(token\) se utiliza para resolver el token de cifrado de mensajes y los tokens entrantes.  Opcional.|  
|[\<tokenReplayDetection\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|Permite la detección de reproducción de símbolo \(token\) y especifica la hora de caducidad de símbolos \(tokens\).  Se puede especificar en el nivel de servicio o en una colección de controladores de token de seguridad.  Opcional.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<securityTokenHandlers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Especifica una colección de controladores de token de seguridad registrados con el extremo.|  
  
## Comentarios  
 Esta sección proporciona los valores de propiedad para una <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> objeto.  Configuración de esta sección reemplaza a los configurados en el servicio.  Algunas de estas opciones a su vez, se pueden, reemplazar por los valores que se especifican cuando se agrega un controlador a la colección de controladores de token de seguridad.  
  
## Ejemplo  
  
```  
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