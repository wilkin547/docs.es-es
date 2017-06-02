---
title: "&lt;remove&gt; (Elemento para &lt;namedCaches&gt;) | Microsoft Docs"
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
  - "<remove> (elemento) para namedCaches"
  - "remove (elemento) para namedCaches"
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# &lt;remove&gt; (Elemento para &lt;namedCaches&gt;)
Quita una entrada de la caché con nombre de la colección `namedCaches` de una memoria caché en memoria.  
  
## Sintaxis  
  
```  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## Tipo  
 `None`  
  
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
 El elemento `remove` quita una entrada `namedCache` de la colección de la caché con nombre de una memoria caché en memoria.  
  
## Vea también  
 [\<namedCaches\> \(Elemento, Configuración de caché\)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)