---
title: "&lt;caches&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;caches&gt;
Registra las cachés de los símbolos de sesión y la detección de reproducción de símbolo \(token\).  
  
## Sintaxis  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 None  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<sessionSecurityTokenCache\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|Registra una caché para símbolos de sesión con un servicio o una colección de controladores de token de seguridad.|  
|[\<tokenReplayCache\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|Registra una caché de símbolo \(token\) de reproducción con un servicio o una colección de controladores de token de seguridad.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Especifica la configuración de la identidad de nivel de servicio.|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Proporciona la configuración de una colección de seguridad de los controladores de símbolo \(token\).|  
  
## Comentarios  
 A `<caches>` elemento se puede especificar el nivel de servicio en el `<identityConfiguration>` elemento o en el nivel de colección de controlador de símbolo \(token\) de seguridad en el `<securityTokenHandlerConfiguration>` elemento.  Configuración en una colección de controladores de símbolo \(token\) de reemplaza las especificadas en el servicio.  
  
 El `<caches>` elemento está representado por el <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> clase.  Las cachés configuradas están representadas por el <xref:System.IdentityModel.Configuration.IdentityModelCaches> clase.  
  
## Ejemplo  
 El XML siguiente muestra la configuración de una caché personalizada para la celebración de los tokens de seguridad de sesión \(<xref:System.IdentityModel.Tokens.SessionSecurityToken>\).  Se toma la configuración de la `ClaimsAwareWebFarm` ejemplo.  
  
```  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```