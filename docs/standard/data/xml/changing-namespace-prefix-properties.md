---
title: Cambiar propiedades de prefijo de espacio de nombres
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d5c87cbe-4d69-429f-aad5-3103c2ca2770
ms.openlocfilehash: a4ba378620d0c5ec01aaa5d87020c33fdbffcf01
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725357"
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

- [Document Object Model (DOM) para XML](xml-document-object-model-dom.md)
