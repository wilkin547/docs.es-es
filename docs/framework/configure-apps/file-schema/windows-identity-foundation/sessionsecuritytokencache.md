---
title: "&lt;sessionSecurityTokenCache&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;sessionSecurityTokenCache&gt;
Elemento  
  
## Sintaxis  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|type|Descripción  Para obtener más información acerca de cómo especificar una personalizada `type`, consulte [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).|  
  
### Elementos secundarios  
 None  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<caches\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registra las memorias caché utilizadas por un servicio o una colección de controladores de token de seguridad.|  
  
## Ejemplo  
 El XML siguiente muestra la configuración de una caché personalizada para la celebración de los tokens de seguridad de sesión \(<xref:System.IdentityModel.Tokens.SessionSecurityToken>\).  Se toma la configuración de la `ClaimsAwareWebFarm` ejemplo.  Para obtener más información acerca de este ejemplo, consulte [índice de ejemplo de código WIF](../../../../../docs/framework/security/wif-code-sample-index.md).  
  
```  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## Vea también  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>