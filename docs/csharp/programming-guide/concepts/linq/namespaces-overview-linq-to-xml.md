---
title: Información general sobre los espacios de nombres (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 16283322-8238-4918-ab11-802ac6748eb7
ms.openlocfilehash: 4d422d9f72eb3297cffda72c441d6370d519f450
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45698437"
---
# <a name="namespaces-overview-linq-to-xml"></a>Información general sobre los espacios de nombres (LINQ to XML)
Este tema presenta los espacios de nombres, la clase <xref:System.Xml.Linq.XName> y la clase <xref:System.Xml.Linq.XNamespace>.  
  
## <a name="xml-names"></a>Nombres XML  
 Los nombres XML a menudo son una fuente de complejidad en la programación XML. Un nombre XML se compone de un espacio de nombres XML (también denominado URI de espacio de nombres XML) y un nombre local. Un espacio de nombres XML es similar a un espacio de nombres en un programa basado en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Permite calificar de manera exclusiva los nombres de los elementos y los atributos. Evita conflictos de nombres entre varias partes de un documento XML. Una vez que haya declarado un espacio de nombres XML, puede seleccionar un nombre local que sólo debe ser único en dicho espacio de nombres.  
  
 Otro aspecto de los nombres XML son los *prefijos de espacios de nombres* XML. Los prefijos XML generan la mayor parte de la complejidad de los nombres XML. Estos prefijos permiten crear un acceso directo de un espacio de nombres XML, lo que hace que el documento XML sea más conciso y comprensible. Sin embargo, los prefijos XML dependen de su contexto para tener un significado, lo que aumenta la complejidad. Por ejemplo, el prefijo XML `aw` podría asociarse a un espacio de nombres XML en una parte del árbol XML y a un espacio de nombres XML diferente en una parte distinta de dicho árbol.  
  
 Una de la ventajas de usar [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] con C# consiste en no tener que usar prefijos XML. Cuando [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] carga o analiza un documento XML, cada prefijo XML se resuelve en su espacio de nombres XML correspondiente. Después, cuando trabaje con un documento que usa espacios de nombres, la mayoría de las veces tendrá acceso a dichos espacios de nombres mediante el URI de éstos, y no mediante prefijo. Cuando los desarrolladores trabajan con nombres XML en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], siempre lo hacen con un nombre XML completo (es decir, un espacio de nombres XML y un nombre local). Sin embargo, si es necesario, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] permite trabajar con prefijos de espacios de nombres y controlarlos.  
  
 En [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], la clase que representa los nombres XML es <xref:System.Xml.Linq.XName>. Los nombres XML aparecen frecuentemente en la API [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], y cuando se requiera un nombre XML, encontrará un parámetro <xref:System.Xml.Linq.XName>. En cambio, apenas se trabaja directamente con un objeto <xref:System.Xml.Linq.XName>. <xref:System.Xml.Linq.XName> contiene una conversión implícita de cadena.  
  
 Para obtener más información, consulte <xref:System.Xml.Linq.XNamespace> y <xref:System.Xml.Linq.XName>.  
  
## <a name="see-also"></a>Vea también

- [Trabajar con espacios de nombres XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)
