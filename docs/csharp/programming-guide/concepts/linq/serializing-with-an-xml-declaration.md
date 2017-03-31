---
title: "Serializar con una declaración XML (C#) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: c237fa4a-a042-40fd-886f-17b54c66bb75
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5c0389630c7fc4b8aa394974b7e42cce2a5101a4
ms.lasthandoff: 03/13/2017

---
# <a name="serializing-with-an-xml-declaration-c"></a>Serializar con una declaración XML (C#)
En este tema se describe cómo controlar si la serialización genera una declaración XML.  
  
## <a name="xml-declaration-generation"></a>Generación de declaración XML  
 Serializar en un <xref:System.IO.File> o <xref:System.IO.TextWriter> usando los métodos <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> o <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> genera una declaración XML. Cuando serializa en un elemento <xref:System.Xml.XmlWriter>, la configuración del sistema de escritura (especificada en un objeto <xref:System.Xml.XmlWriterSettings>) determina si se genera una declaración XML o no.  
  
 Si está serializando en una cadena mediante el método `ToString`, el XML resultante no incluirá una declaración XML.  
  
### <a name="serializing-with-an-xml-declaration"></a>Serializar con una declaración XML  
 En el ejemplo siguiente se crea un elemento <xref:System.Xml.Linq.XElement>, se guarda el documento en un archivo y, luego, se imprime el archivo en la consola:  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", "child content")  
);  
root.Save("Root.xml");  
string str = File.ReadAllText("Root.xml");  
Console.WriteLine(str);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a>Serializar sin una declaración XML  
 En el ejemplo siguiente se muestra cómo guardar un elemento <xref:System.Xml.Linq.XElement> en un <xref:System.Xml.XmlWriter>.  
  
```csharp  
StringBuilder sb = new StringBuilder();  
XmlWriterSettings xws = new XmlWriterSettings();  
xws.OmitXmlDeclaration = true;  
  
using (XmlWriter xw = XmlWriter.Create(sb, xws)) {  
    XElement root = new XElement("Root",  
        new XElement("Child", "child content")  
    );  
    root.Save(xw);  
}  
Console.WriteLine(sb.ToString());  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a>Vea también  
 [Serializar árboles XML (C#)](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
