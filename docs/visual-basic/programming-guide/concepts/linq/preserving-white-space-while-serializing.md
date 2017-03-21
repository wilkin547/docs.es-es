---
title: Conservar espacio en blanco mientras Serializing2 | Documentos de Microsoft
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
ms.assetid: 2d7abbd4-37f4-422b-89dd-0a694b5edc17
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
ms.openlocfilehash: 9efa2940af9321401e7f9c01d6fb9d1f48616711
ms.lasthandoff: 03/13/2017

---
# <a name="preserving-white-space-while-serializing"></a>Mantener un espacio en blanco al serializar
En este tema se describe cómo controlar los espacios en blanco a la hora de serializar un árbol XML.  
  
 Un caso muy común es aquel en el que se leen datos XML con sangría, se crea un árbol XML en memoria sin ningún nodo de texto con espacios en blanco (es decir, sin preservar los espacios en blanco), se realizan ciertas operaciones sobre el XML y éste se guarda con sangría. Si se serializa el XML con formato, solo se preservan en el XML aquellos espacios en blanco más significativos. Éste es el comportamiento predeterminado en [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
 Otro escenario muy común es aquel en el que se lee y se modifica código XML en el que se ha aplicado sangría de forma intencionada. Es posible que no desee modificar esta sangría de ninguna forma. Para hacerlo en [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], puede preservar los espacios en blanco a la hora de cargar o analizar el XML y si deshabilita el formato cuando serialice el XML.  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a>Tratamiento de los espacios en blanco en los métodos que serializan árboles XML  
 Los métodos siguientes en el <xref:System.Xml.Linq.XElement>y <xref:System.Xml.Linq.XDocument>clases serializan un árbol XML.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> Puede serializar un árbol XML en un archivo, un <xref:System.IO.TextReader>, o un <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> </xref:System.IO.TextReader> El método `ToString` serializa en una cadena..  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=fullName>  
  
 Si el método no toma <xref:System.Xml.Linq.SaveOptions>como argumento, entonces el método realizará un formato (sangría) al XML serializado.</xref:System.Xml.Linq.SaveOptions> En ese caso, se descartarán todos los espacios en blanco del árbol XML que no sean significativos.  
  
 Si el método toma <xref:System.Xml.Linq.SaveOptions>como argumento, a continuación, puede especificar que el método no dé formato (sangría) al XML serializado.</xref:System.Xml.Linq.SaveOptions> En ese caso, se preservarán todos los espacios en blanco del árbol XML.  
  
## <a name="see-also"></a>Vea también  
 [Serializar árboles XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
