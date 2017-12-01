---
title: Cambiar declaraciones de espacio de nombres en un documento XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 627882efcbc41310ee177cba984e4add5b07bd15
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a>Cambiar declaraciones de espacio de nombres en un documento XML
El **XmlDocument** expone declaraciones de espacio de nombres y **xmlns** atributos como parte del modelo de objetos de documento. Estos se almacenan en la **XmlDocument**, por lo que cuando guarda el documento, puede conservar la ubicación de estos atributos. Si se cambian estos atributos no tiene ningún efecto el **nombre**, **NamespaceURI**, y **prefijo** propiedades de otros nodos que ya estén en el árbol. Por ejemplo, si carga el documento siguiente, la `test` elemento tiene **NamespaceURI**`123.`  
  
```xml  
<test xmlns="123"/>  
```  
  
 Si quita el `xmlns` atributo como sigue, entonces, el `test` elemento todavía tiene la **NamespaceURI** de `123`.  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 Del mismo modo, si agrega otro `xmlns` atribuir a la `doc` elemento tal como sigue, entonces, el `test` elemento todavía tiene **NamespaceURI** `123`.  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 Por lo tanto, cambiar `xmlns` atributos no tendrán ningún efecto hasta que guardar y volver a cargar la **XmlDocument** objeto.  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de documento (DOM) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
