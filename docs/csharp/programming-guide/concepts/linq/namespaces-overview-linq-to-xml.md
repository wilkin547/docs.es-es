---
title: "Información general sobre los espacios de nombres (LINQ to XML) | Microsoft Docs"
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
ms.assetid: 16283322-8238-4918-ab11-802ac6748eb7
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
ms.openlocfilehash: 73eb9d0808666238e55abdf53888ec0f9b501fe2
ms.lasthandoff: 03/13/2017

---
# <a name="namespaces-overview-linq-to-xml"></a>Información general sobre los espacios de nombres (LINQ to XML)
En este tema se presentan los espacios de nombres, la clase <xref:System.Xml.Linq.XName> y la clase <xref:System.Xml.Linq.XNamespace>.  
  
## <a name="xml-names"></a>Nombres XML  
 Los nombres XML a menudo son una fuente de complejidad en la programación XML. Un nombre XML se compone de un espacio de nombres XML (también denominado URI de espacio de nombres XML) y un nombre local. Un espacio de nombres XML es similar a un espacio de nombres en un programa basado en [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]. Permite calificar de manera exclusiva los nombres de los elementos y los atributos. Evita conflictos de nombres entre varias partes de un documento XML. Una vez que haya declarado un espacio de nombres XML, puede seleccionar un nombre local que sólo debe ser único en dicho espacio de nombres.  
  
 Otro aspecto de los nombres XML son los *prefijos de espacios de nombres* XML. Los prefijos XML generan la mayor parte de la complejidad de los nombres XML. Estos prefijos permiten crear un acceso directo de un espacio de nombres XML, lo que hace que el documento XML sea más conciso y comprensible. Sin embargo, los prefijos XML dependen de su contexto para tener un significado, lo que aumenta la complejidad. Por ejemplo, el prefijo XML `aw` podría asociarse a un espacio de nombres XML en una parte del árbol XML y a un espacio de nombres XML diferente en una parte distinta de dicho árbol.  
  
 Una de la ventajas de usar [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] con C# consiste en no tener que usar prefijos XML. Cuando [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] carga o analiza un documento XML, cada prefijo XML se resuelve en su espacio de nombres XML correspondiente. Después, cuando trabaje con un documento que usa espacios de nombres, la mayoría de las veces tendrá acceso a dichos espacios de nombres mediante el URI de éstos, y no mediante prefijo. Cuando los desarrolladores trabajan con nombres XML en [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], siempre lo hacen con un nombre XML completo (es decir, un espacio de nombres XML y un nombre local). Sin embargo, si es necesario, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] permite trabajar con prefijos de espacios de nombres y controlarlos.  
  
 En [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], la clase que representa a los nombres XML es <xref:System.Xml.Linq.XName>. Los nombres XML aparecen frecuentemente en la API [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] y, allá donde se necesite un nombre XML, encontrará un parámetro <xref:System.Xml.Linq.XName>. Pero raras veces se trabaja directamente con <xref:System.Xml.Linq.XName>. <xref:System.Xml.Linq.XName> contiene una conversión implícita de cadena.  
  
 Para más información, vea <xref:System.Xml.Linq.XNamespace> y <xref:System.Xml.Linq.XName>.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con espacios de nombres XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)
