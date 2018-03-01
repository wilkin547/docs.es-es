---
title: Cambiar propiedades de prefijo de espacio de nombres
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
ms.assetid: d5c87cbe-4d69-429f-aad5-3103c2ca2770
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3cb0db0fbffa5f42fb09f29da2976727451e3741
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="changing-namespace-prefix-properties"></a>Cambiar propiedades de prefijo de espacio de nombres
La clase **XmlNode** permite cambiar el prefijo de espacio de nombres asociado a un nodo concreto. Por ejemplo, en el código siguiente se muestra el prefijo de un elemento que se está cambiando.  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "b"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "b";  
Console.WriteLine(doc.InnerXml);  
```  
  
 **Salida**  
  
```xml  
<b:test xmlns:a="123" xmlns:b="456" />  
```  
  
 Si se modifica el prefijo de un nodo, no se cambia su espacio de nombres. El espacio de nombres solo puede establecerse al crear el nodo. Al mantener el árbol, los nuevos atributos de espacio de nombres se pueden mantener de modo que se ajusten al prefijo establecido. Si no se puede crear el nuevo espacio de nombres, se cambia el prefijo de forma que el nodo conserva su nombre local y espacio de nombres. En el ejemplo siguiente se muestra la adición de un atributo de espacio de nombres.  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<test xmlns='123'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "a"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<test xmlns='123'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "a";  
Console.WriteLine(doc.InnerXml);  
```  
  
 **Salida**  
  
```xml  
<a:test xmlns="123" xmlns:a="123" />  
```  
  
 Cuando el árbol se mantuvo en una cadena como resultado de la llamada a **doc.InnerXml**, el atributo `xmlns:a='123'` se agregó para conservar el espacio de nombres del elemento `test`. Era `'123'` y sigue siendo `'123'`.  
  
## <a name="see-also"></a>Vea también  
 [Document Object Model (DOM) para XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
