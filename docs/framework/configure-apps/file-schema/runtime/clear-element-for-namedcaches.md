---
title: "&lt;clear&gt; (Elemento para &lt;namedCaches&gt;) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<clear> (elemento para <namedCaches>)"
  - "clear (elemento para <namedCaches>)"
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;clear&gt; (Elemento para &lt;namedCaches&gt;)
Borra todas las entradas `namedCache` en la colección `namedCaches` para una memoria caché en memoria.  
  
## Sintaxis  
  
```  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## Tipo  
 `Type`  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 `None`  
  
### Elementos secundarios  
 `None`  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<namedCaches\>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Contiene una colección de configuraciones de las instancias con nombre de <xref:System.Runtime.Caching.MemoryCache>.|  
  
## Comentarios  
 El elemento `clear` borra todas las entradas `namedCache` en la colección de caché con nombre para una memoria caché.  Puede usar el elemento `clear` antes de usar el elemento `add` para agregar una nueva entrada de la memoria caché con nombre para asegurarse de que no hay ninguna otra caché con nombre en la colección.  
  
## Vea también  
 [\<namedCaches\> \(Elemento, Configuración de caché\)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)