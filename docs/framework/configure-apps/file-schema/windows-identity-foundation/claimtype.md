---
title: "&lt;claimType&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;claimType&gt;
Especifica un solo siniestro obligatorios u opcional para los tokens de seguridad entrantes.  
  
## Sintaxis  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
      <claimType type=URI optional=xs:boolean >  
      </claimType>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|type|Tipo de notificación.  Normalmente, un identificador URI.  Obligatorio.|  
|optional|Esta información es necesaria.  Opcional.|  
  
### Elementos secundarios  
 None  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<claimTypeRequired\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|Elemento|