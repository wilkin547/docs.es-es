---
title: "Cambiar declaraciones de espacio de nombres en un documento XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Cambiar declaraciones de espacio de nombres en un documento XML
**XmlDocument** expone declaraciones de espacios de nombres y atributos **xmlns** como parte del modelo de objetos de documento.  Éstos se almacenan en **XmlDocument**, de modo que, al guardar el documento, puede conservar la ubicación de dichos atributos.  Si se cambian estos atributos, no se produce ningún efecto en las propiedades **Name**, **NamespaceURI** y **Prefix** de otros nodos que ya estén en el árbol.  Por ejemplo, si carga el siguiente documento, el elemento `test` tiene **NamespaceURI** `123.`  
  
```  
<test xmlns="123"/>  
```  
  
 Si quita el atributo `xmlns` como sigue, entonces el elemento `test` tiene todavía **NamespaceURI** de `123`.  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 Asimismo, si añade un atributo diferente `xmlns` al elemento `doc` tal como sigue, el elemento `test` tiene todavía **NamespaceURI** `123`.  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 Por tanto, si se cambian los atributos `xmlns` no se produce ningún efecto hasta que se guarde y se recargue el objeto **XmlDocument**.  
  
## Vea también  
 [Modelo de objetos de documento XML \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)