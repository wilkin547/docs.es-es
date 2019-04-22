---
title: Conserva los espacios en blanco mientras Serializing2
ms.date: 07/20/2015
ms.assetid: 2d7abbd4-37f4-422b-89dd-0a694b5edc17
ms.openlocfilehash: a8903268f5ae1c2bc6c71a0998ba7d932f01e0ec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814476"
---
# <a name="preserving-white-space-while-serializing"></a>Mantener un espacio en blanco al serializar
En este tema se describe cómo controlar los espacios en blanco a la hora de serializar un árbol XML.  
  
 Un caso muy común es aquel en el que se leen datos XML con sangría, se crea un árbol XML en memoria sin ningún nodo de texto con espacios en blanco (es decir, sin preservar los espacios en blanco), se realizan ciertas operaciones sobre el XML y éste se guarda con sangría. Si se serializa el XML con formato, solo se preservan en el XML aquellos espacios en blanco más significativos. Éste es el comportamiento predeterminado en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 Otro escenario muy común es aquel en el que se lee y se modifica código XML en el que se ha aplicado sangría de forma intencionada. Es posible que no desee modificar esta sangría de ninguna forma. Para hacerlo en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], puede preservar los espacios en blanco a la hora de cargar o analizar el XML y si deshabilita el formato cuando serialice el XML.  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a>Tratamiento de los espacios en blanco en los métodos que serializan árboles XML  
 Los siguientes métodos de las clases <xref:System.Xml.Linq.XElement> y <xref:System.Xml.Linq.XDocument> serializan un árbol XML. Es posible serializar un árbol XML en un archivo, un <xref:System.IO.TextReader> o un <xref:System.Xml.XmlReader>. El método `ToString` serializa en una cadena.  
  
-   <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>  
  
-   <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>  
  
-   [XElement.ToString()](xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType)
  
-   [XDocument.ToString()](xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType)
  
 Si el método no recibe un <xref:System.Xml.Linq.SaveOptions> como argumento, entonces el método realizará un formato (sangría) del XML serializado. En ese caso, se descartarán todos los espacios en blanco del árbol XML que no sean significativos.  
  
 Si el método toma <xref:System.Xml.Linq.SaveOptions> como argumento, se puede especificar que el método no dé formato (sangría) al XML serializado. En ese caso, se preservarán todos los espacios en blanco del árbol XML.  
  
## <a name="see-also"></a>Vea también

- [Serializar árboles XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
