---
title: "&lt;identityConfiguration&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# &lt;identityConfiguration&gt;
Especifica la configuración de la identidad de nivel de servicio.  
  
## Sintaxis  
  
```  
<system.identityModel>  
  <identityConfiguration  
      name=xs:string  
      saveBootstrapContext=xs:boolean>  
      maximumClockSkew=TimeSpan >  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|name|El valor predeterminado es 2000.  Obligatorio.  None  Elemento  Para obtener más información, vea el elemento [\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md).|  
|Descripción|Especifica si debe incluirse bootstrap símbolos \(tokens\) en el símbolo de sesión.  El valor también puede establecer en una colección de controladores de símbolo \(token\) estableciendo la `saveBootstrapContext` de atributo en el [\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) elemento.  Un valor establecido en la colección de controladores de símbolo \(token\) reemplaza el valor establecido en el servicio.|  
|maximumClockSkew|A <xref:System.TimeSpan> especifica que el sesgo de d reloj máximo permitido.  Controla el sesgo de d reloj máximo permitido al realizar operaciones de sensibles al tiempo, como la validación de la hora de caducidad de una sesión de inicio de sesión.  El valor predeterminado es 5 minutos, "00: 05".  Para obtener más información acerca de cómo especificar <xref:System.TimeSpan> valores, consulte [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_TimespanValues).  En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  Atributo|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<caches\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Descripción  type  Opcional.|  
|[\<certificateValidation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Controla la configuración que utilizan controladores de símbolo \(token\) para validar certificados.  Se puede especificar en el nivel de servicio o en una colección de controladores de token de seguridad.  Opcional.|  
|[\<claimsAuthenticationManager\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthenticationmanager.md)|Registra un administrador de autenticación de reclamaciones para las notificaciones entrantes.  Opcional.|  
|[\<claimsAuthorizationManager\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md)|Obligatorio.  Opcional.|  
|[\<claimTypeRequired\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|None  Opcional.|  
|[\<securityTokenHandlers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Elemento  Descripción  Opcional.|  
|[\<tokenReplayDetection\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|Permite la detección de reproducción de símbolo \(token\) y especifica la hora de caducidad de símbolos \(tokens\).  Se puede especificar en el nivel de servicio o en una colección de controladores de token de seguridad.  Opcional.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<system.identityModel\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)|Proporciona una configuración para habilitar las opciones de base de identidad de Windows \(WIF\) en las aplicaciones.|  
  
## Comentarios  
 Múltiples identidad es posible definir configuraciones, cada uno con un nombre único.  El comportamiento es como sigue:  
  
1.  Si no hay `<identityConfiguration>` se especifica el elemento.  Una configuración de la identidad predeterminada se crea en tiempo de ejecución y rellena con valores predeterminados.  
  
2.  Si un único `<identityConfiguration>` se especifica el elemento.  Es la configuración predeterminada de la identidad.  No importa si es con nombre o sin nombre.  
  
3.  En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  Atributo  Descripción  
  
> [!WARNING]
>  type  El elemento sin nombre será la configuración de la identidad predeterminada.  
  
 Algunos de los valores especificados en el `<identityConfiguration>` se puede reemplazar el elemento de la configuración de una colección de controladores de token de seguridad o la configuración de los controladores de token de seguridad individual.  
  
> [!IMPORTANT]
>  Elemento  Descripción  Si la aplicación no es una aplicación Web pasiva, el [\<claimsAuthorizationManager\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) elemento \(y sus elementos de directiva de secundarios, si está presente\) de la configuración de identidad que se hace referencia son los únicos valores que se aplica.  Todas los demás valores se omiten.  Para obtener más información, vea el elemento [\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md).  
  
 El `<identityConfiguration>` elemento está representado por el <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> clase.  Elemento  
  
> [!IMPORTANT]
>  Descripción  Estos elementos en su lugar, deben especificarse en el [\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) elemento.  
>   
>  -   [\<audienceUris\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)  
> -   [\<issuerNameRegistry\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)  
> -   [\<issuerTokenResolver\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)  
> -   [\<serviceTokenResolver\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)  
  
## Ejemplo  
 En el ejemplo siguiente se crea una configuración de identidad con el nombre "alternateConfiguration".  La configuración de identidad especifica la configuración predeterminada.  
  
```  
<system.identityModel>  
    <identityConfiguration name="alternateConfiguration"/>  
</system.identityModel>  
```  
  
## Vea también  
 <xref:System.IdentityModel.Configuration.IdentityConfiguration>   
 <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>