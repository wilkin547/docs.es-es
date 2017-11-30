---
title: "Información general sobre los espacios de nombres (LINQ to XML)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8eb31fa-4b26-4acf-8050-6e705687f458
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 082172720abd39634f7183367d4d7b8d53d2bb7e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="namespaces-overview-linq-to-xml"></a>Información general sobre los espacios de nombres (LINQ to XML)
Este tema presenta los espacios de nombres, la clase <xref:System.Xml.Linq.XName> y la clase <xref:System.Xml.Linq.XNamespace>.  
  
## <a name="xml-names"></a>Nombres XML  
 Los nombres XML a menudo son una fuente de complejidad en la programación XML. Un nombre XML se compone de un espacio de nombres XML (también denominado URI de espacio de nombres XML) y un nombre local. Un espacio de nombres XML es similar a un espacio de nombres en un programa basado en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Permite calificar de manera exclusiva los nombres de los elementos y los atributos. Evita conflictos de nombres entre varias partes de un documento XML. Una vez que haya declarado un espacio de nombres XML, puede seleccionar un nombre local que sólo debe ser único en dicho espacio de nombres.  
  
 Otro aspecto de los nombres XML son los *prefijos de espacios de nombres* XML. Los prefijos XML generan la mayor parte de la complejidad de los nombres XML. Estos prefijos permiten crear un acceso directo de un espacio de nombres XML, lo que hace que el documento XML sea más conciso y comprensible. Sin embargo, los prefijos XML dependen de su contexto para tener un significado, lo que aumenta la complejidad. Por ejemplo, el prefijo XML `aw` podría asociarse a un espacio de nombres XML en una parte del árbol XML y a un espacio de nombres XML diferente en una parte distinta de dicho árbol.  
  
 Cuando se usa [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] con literales XML y Visual Basic, debe usar los prefijos de espacio de nombres cuando se trabaja con documentos en espacios de nombres.  
  
 En [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], la clase que representa los nombres XML es <xref:System.Xml.Linq.XName>. Los nombres XML aparecen frecuentemente en la API [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], y cuando se requiera un nombre XML, encontrará un parámetro <xref:System.Xml.Linq.XName>. En cambio, apenas se trabaja directamente con un objeto <xref:System.Xml.Linq.XName>. <xref:System.Xml.Linq.XName> contiene una conversión implícita de cadena.  
  
 Para obtener más información, consulte <xref:System.Xml.Linq.XNamespace> y <xref:System.Xml.Linq.XName>.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con espacios de nombres XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
