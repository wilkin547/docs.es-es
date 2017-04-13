---
title: "Actualizaciones din&#225;micas en NodeLists y NamedNodeMaps | Microsoft Docs"
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
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Actualizaciones din&#225;micas en NodeLists y NamedNodeMaps
Puesto que **XmlNodeList** y **XmlNamedNodeMap** contienen un conjunto de nodos, el documento XML se carga en la memoria y se modifica, el W3C establece que es necesario que estos objetos que contienen conjuntos de nodos sean dinámicos.  Es decir, si el documento subyacente cambia, deberían cambiar también los datos incluidos en estos dos objetos.  Por lo tanto, si tiene un **XmlNodeList** que contiene todos los elementos secundarios de un elemento en particular \(por ejemplo, elemento X\), entonces añada un elemento adicional, elemento Q, al documento bajo el elemento X.  El **XmlNodeList** debería tener el nuevo elemento Q añadido a esta colección.  Lo mismo sucede a la inversa.  Si se agrega un nodo a **XmlNodeList**, el documento subyacente también se actualiza.  
  
## Vea también  
 [Modelo de objetos de documento XML \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)