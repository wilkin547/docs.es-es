---
title: Serializar en archivos, escritores y XmlWriters3 | Documentos de Microsoft
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
ms.assetid: 7a0c24df-79ef-41a0-87f5-e6cf79382da9
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
ms.openlocfilehash: 98662b8d84459ed051d048084c2755fa7aaf8247
ms.lasthandoff: 03/13/2017

---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a>Serializar en archivos, escritores de texto y escritores XML
Puede serializar árboles XML en un <xref:System.IO.File>, un <xref:System.IO.TextWriter>, o un <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File>  
  
 Puede serializar cualquier componente XML, incluidos <xref:System.Xml.Linq.XDocument>y <xref:System.Xml.Linq.XElement>, en una cadena utilizando el `ToString` método.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument>  
  
 Si desea suprimir el formato al serializar en una cadena, puede utilizar el <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName>método.</xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=fullName>  
  
 Comportamiento de Thedefault al serializar a un archivo es dar formato (sangría) al XML resultante documento. Cuando aplica una sangría, en el árbol XML no se conservan los espacios en blanco más insignificantes. Para serializar con formato, use una de las sobrecargas de los métodos siguientes que no toman <xref:System.Xml.Linq.SaveOptions>como argumento:</xref:System.Xml.Linq.SaveOptions>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>  
  
 Si desea que la opción no aplique una sangría y conservar el espacio en blanco insignificante en el árbol XML, use una de las sobrecargas de los métodos siguientes que toma <xref:System.Xml.Linq.SaveOptions>como argumento:</xref:System.Xml.Linq.SaveOptions>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>  
  
 Por obtener ejemplos, vea el tema de referencia correspondiente.  
  
## <a name="see-also"></a>Vea también  
 [Serializar árboles XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
