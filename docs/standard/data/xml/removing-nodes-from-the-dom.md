---
title: "C&#243;mo quitar nodos del DOM | Microsoft Docs"
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
ms.assetid: 0a98e0ca-0555-45c1-ab69-0d8d20ca1abd
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# C&#243;mo quitar nodos del DOM
Para quitar un nodo del Modelo de objetos de documento XML \(DOM\), utilice el método <xref:System.Xml.XmlNode.RemoveChild%2A> para quitar un nodo específico.  Cuando se quita un nodo, el método quita el subárbol que pertenece al nodo que se está quitando; es decir, no se trata de un nodo hoja.  
  
 Para quitar varios nodos del DOM, utilice el método <xref:System.Xml.XmlNode.RemoveAll%2A> para quitar todos los atributos y nodos secundarios, si es preciso, del nodo actual.  
  
 Si está trabajando con <xref:System.Xml.XmlNamedNodeMap>, puede quitar un nodo con el método <xref:System.Xml.XmlNamedNodeMap.RemoveNamedItem%2A>.  
  
 Para quitar atributos, vea [Cómo quitar atributos de un nodo de elemento en DOM](../../../../docs/standard/data/xml/removing-attributes-from-an-element-node-in-the-dom.md).  
  
## Vea también  
 [Modelo de objetos de documento XML \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)