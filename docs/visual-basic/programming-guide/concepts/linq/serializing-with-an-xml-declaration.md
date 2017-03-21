---
title: "Serializar con una declaración XML (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 8726f79e-2bb0-4ba0-969d-197cca591647
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 373df9b28ae7434d33ae81eba701d289cf1aa4f7
ms.lasthandoff: 03/13/2017

---
# <a name="serializing-with-an-xml-declaration-visual-basic"></a>Serializar con una declaración XML (Visual Basic)
En este tema se describe cómo controlar si la serialización genera una declaración XML.  
  
## <a name="xml-declaration-generation"></a>Generación de declaración XML  
 Serializar en un <xref:System.IO.File>o un <xref:System.IO.TextWriter>con el <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>método o la <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>método genera una declaración XML.</xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> </xref:System.IO.TextWriter> </xref:System.IO.File> Cuando serializa en un <xref:System.Xml.XmlWriter>, la configuración del escritor (especificada en un <xref:System.Xml.XmlWriterSettings>objeto) determina si se genera una declaración XML.</xref:System.Xml.XmlWriterSettings> </xref:System.Xml.XmlWriter>  
  
 Si está serializando en una cadena mediante el método `ToString`, el XML resultante no incluirá una declaración XML.  
  
### <a name="serializing-with-an-xml-declaration"></a>Serializar con una declaración XML  
 En el ejemplo siguiente se crea un <xref:System.Xml.Linq.XElement>, guarda el documento en un archivo y, a continuación, imprime el archivo en la consola:</xref:System.Xml.Linq.XElement>  
  
```vb  
Dim root As XElement = <Root>  
                           <Child>child content</Child>  
                       </Root>  
root.Save("Root.xml")  
Dim str As String = File.ReadAllText("Root.xml")  
Console.WriteLine(str)  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a>Serializar sin una declaración XML  
 En el ejemplo siguiente se muestra cómo guardar una <xref:System.Xml.Linq.XElement>a una <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.Xml.Linq.XElement>  
  
```vb  
Dim sb As StringBuilder = New StringBuilder()  
Dim xws As XmlWriterSettings = New XmlWriterSettings()  
xws.OmitXmlDeclaration = True  
  
Using xw As XmlWriter = XmlWriter.Create(sb, xws)  
    Dim root = <Root>  
                   <Child>child content</Child>  
               </Root>  
    root.Save(xw)  
End Using  
Console.WriteLine(sb.ToString())  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a>Vea también  
 [Serializar árboles XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
