---
title: Cambiar declaraciones de espacio de nombres en un documento XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5457eab1f34eb3e7424d508509f5dd6a42ffb51f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976934"
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a>Cambiar declaraciones de espacio de nombres en un documento XML
**XmlDocument** expone declaraciones de espacios de nombres y atributos **xmlns**como parte del modelo de objetos de documento. Estos se almacenan en **XmlDocument**, de modo que, al guardar el documento, puede conservar la ubicación de dichos atributos. Si se cambian estos atributos, no se produce ningún efecto en las propiedades **Name**, **NamespaceURI** y **Prefix** de otros nodos que ya estén en el árbol. Por ejemplo, si carga el siguiente documento, el elemento `test` tiene **NamespaceURI** `123.`  
  
```xml  
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
doc.documentElement.SetAttribute("xmlns","456")
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 Por tanto, si se cambian los atributos `xmlns` no se produce ningún efecto hasta que se guarde y se recargue el objeto **XmlDocument**.  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
