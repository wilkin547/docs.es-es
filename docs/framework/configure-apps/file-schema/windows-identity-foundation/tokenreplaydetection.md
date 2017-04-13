---
title: "&lt;tokenReplayDetection&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;tokenReplayDetection&gt;
Permite la detección simbólica de respuesta y especifica la fecha de expiración para tokens.  
  
## Sintaxis  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Tipo  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|enabled|Se habilita un valor que especifica si es de token volver a reproducir la detección; “true” habilitar la detección simbólica de respuesta.|  
|expirationPeriod|<xref:System.TimeSpan> que especifica el tiempo máximo para que un elemento se considere expirada y se quite de la memoria caché.  Para obtener más información sobre cómo especificar valores de <xref:System.TimeSpan> , vea [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_TimespanValues).|  
  
### Elementos secundarios  
 None  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Especifica valores de identidad de nivel de servicio.|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Proporciona la configuración para una colección de controladores de token de seguridad.|  
  
## Comentarios  
 Un elemento de `<tokenReplayDetection>` se puede especificar en el nivel de servicio bajo el elemento de `<identityConfiguration>` o en la colección de controlador de token de seguridad nivel bajo el elemento de `<securityTokenHandlerConfiguration>` .  Los valores de una colección simbólica de controlador reemplazan a los especificados en el servicio.  
  
 El elemento especifica el tipo de caché tokens de la respuesta [\<tokenReplayCache\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) .