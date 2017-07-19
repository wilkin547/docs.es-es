---
title: "&lt;tokenReplayCache&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;tokenReplayCache&gt;
Registra una caché de símbolo \(token\) de reproducción con un servicio o una colección de controladores de token de seguridad.  
  
## Sintaxis  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <tokenReplayCache type=xs:string>  
      </tokenReplayCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|type|Un tipo que se deriva de la <xref:System.IdentityModel.Tokens.TokenReplayCache> clase.  Para obtener más información acerca de cómo especificar una personalizada `type`, consulte [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).|  
  
### Elementos secundarios  
 None  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<caches\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registra las memorias caché utilizadas por un servicio o una colección de controladores de token de seguridad.|  
  
## Comentarios  
 La caché de símbolo \(token\) de reproducción se utiliza para detectar reproducidos símbolos \(tokens\).  Está habilitada la detección de reproducción de símbolo \(token\) de la [\<tokenReplayDetection\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) elemento, que también especifica la hora de caducidad máximo de símbolos \(tokens\).  
  
## Ejemplo  
 El XML siguiente muestra la configuración de una caché personalizada para la detección de tokens reproducidos.  
  
```  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## Vea también  
 <xref:System.IdentityModel.Tokens.TokenReplayCache>   
 [\<tokenReplayDetection\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)