---
title: Mantener un espacio en blanco al serializar | Microsoft Docs
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
ms.assetid: 0c4f8b98-483b-4cf8-86be-fa146eef90dc
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
ms.openlocfilehash: 1d6cebecd75bedc393b06261c1955a554c9cf18c
ms.lasthandoff: 03/13/2017

---
# <a name="preserving-white-space-while-serializing"></a>Mantener un espacio en blanco al serializar
En este tema se describe cómo controlar los espacios en blanco a la hora de serializar un árbol XML.  
  
 Un caso muy común es aquel en el que se leen datos XML con sangría, se crea un árbol XML en memoria sin ningún nodo de texto con espacios en blanco (es decir, sin preservar los espacios en blanco), se realizan ciertas operaciones sobre el XML y éste se guarda con sangría. Si se serializa el XML con formato, solo se preservan en el XML aquellos espacios en blanco más significativos. Éste es el comportamiento predeterminado en [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
 Otro escenario muy común es aquel en el que se lee y se modifica código XML en el que se ha aplicado sangría de forma intencionada. Es posible que no desee modificar esta sangría de ninguna forma. Para hacerlo en [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], puede preservar los espacios en blanco a la hora de cargar o analizar el XML y si deshabilita el formato cuando serialice el XML.  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a>Tratamiento de los espacios en blanco en los métodos que serializan árboles XML  
 Los métodos siguientes en las clases <xref:System.Xml.Linq.XElement> y <xref:System.Xml.Linq.XDocument> serializan un árbol XML. Un árbol XML se puede serializar en un archivo, un <xref:System.IO.TextReader> o un <xref:System.Xml.XmlReader>. El método `ToString` serializa en una cadena.  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=fullName>  
  
 Si el método no recibe <xref:System.Xml.Linq.SaveOptions> como argumento, dará formato (sangría) al XML serializado. En ese caso, se descartarán todos los espacios en blanco del árbol XML que no sean significativos.  
  
 Si el método recibe <xref:System.Xml.Linq.SaveOptions> como argumento, se puede especificar que no dé formato (sangría) al XML serializado. En ese caso, se preservarán todos los espacios en blanco del árbol XML.  
  
## <a name="see-also"></a>Vea también  
 [Serializar árboles XML (C#)](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
