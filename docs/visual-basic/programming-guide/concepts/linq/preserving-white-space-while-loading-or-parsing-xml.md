---
title: Conservar espacio en blanco al cargar o analizar XML2 | Documentos de Microsoft
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
ms.assetid: ef6518e0-2c8d-462c-8b92-a16e9dc737ad
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 39e4270acc0e9a9df5c3855f8c087f41d9612197
ms.lasthandoff: 03/13/2017

---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a>Mantener un espacio en blanco al cargar o analizar XML
En este tema se describe cómo controlar el comportamiento de los espacios en blanco de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
 Un caso muy común es aquel en el que se leen datos XML con sangría, se crea un árbol XML en memoria sin ningún nodo de texto con espacios en blanco (es decir, sin preservar los espacios en blanco), se realizan ciertas operaciones sobre el XML y éste se guarda con sangría. Si se serializa el XML con formato, solo se preservan en el XML aquellos espacios en blanco más significativos. Éste es el comportamiento predeterminado en [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
 Otro escenario muy común es aquel en el que se lee y se modifica código XML en el que se ha aplicado sangría de forma intencionada. Es posible que no desee modificar esta sangría de ninguna forma. Para hacerlo en [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], puede preservar los espacios en blanco a la hora de cargar o analizar el XML y si deshabilita el formato cuando serialice el XML.  
  
 En este tema se describe el comportamiento de espacios en blanco de métodos que rellenan los árboles XML. Para obtener información acerca de cómo controlar los espacios en blanco al serializar árboles XML, vea [conservar espacio en blanco al serializar](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a>Comportamiento de métodos que rellenan árboles XML  
 Los métodos siguientes en el <xref:System.Xml.Linq.XElement>y <xref:System.Xml.Linq.XDocument>clases rellenan un árbol XML.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> Puede rellenar un árbol XML desde un archivo, un <xref:System.IO.TextReader>, un <xref:System.Xml.XmlReader>, o una cadena:</xref:System.Xml.XmlReader> </xref:System.IO.TextReader>  
  
-   <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>  
  
 Si el método no toma <xref:System.Xml.Linq.LoadOptions>como argumento, el método no conservará espacios en blanco insignificantes.</xref:System.Xml.Linq.LoadOptions>  
  
 En la mayoría de los casos, si el método toma <xref:System.Xml.Linq.LoadOptions>como argumento, opcionalmente se pueden conservar espacios en blanco insignificantes como nodos de texto en el árbol XML.</xref:System.Xml.Linq.LoadOptions> Sin embargo, si el método carga XML desde un <xref:System.Xml.XmlReader>, la <xref:System.Xml.XmlReader>determina si se conservan los espacios en blanco o no.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader> Configuración <xref:System.Xml.Linq.LoadOptions>no tiene ningún efecto.</xref:System.Xml.Linq.LoadOptions>  
  
 Con estos métodos, si se conservan los espacios en blanco, espacio en blanco no se inserta en el árbol XML como <xref:System.Xml.Linq.XText>nodos.</xref:System.Xml.Linq.XText> Si no se conservan los espacios en blanco, entonces no se insertan los nodos de texto.  
  
 Puede crear un árbol XML mediante un <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> Los nodos que se escriben en el <xref:System.Xml.XmlWriter>se rellenan en el árbol.</xref:System.Xml.XmlWriter> No obstante, al crear un árbol XML usando este método se conservan todos los nodos, independientemente de si el nodo es o no un espacio en blanco, o si el espacio en blanco es o no significativo.  
  
## <a name="see-also"></a>Vea también  
 [Analizar XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
