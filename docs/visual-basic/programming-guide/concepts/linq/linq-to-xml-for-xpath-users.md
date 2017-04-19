---
title: LINQ to XML para usuarios de XPath (Visual Basic) | Documentos de Microsoft
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
ms.assetid: 0e64911c-a7cc-4c20-b927-ca99078b5656
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 376e7d67edf1719dc1a020974b38e3600831d660
ms.lasthandoff: 03/13/2017


---
# <a name="linq-to-xml-for-xpath-users-visual-basic"></a>LINQ to XML para usuarios de XPath (Visual Basic)
En este conjunto de temas se muestran varias expresiones XPath y sus equivalentes de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
 Todos los ejemplos utilizan la funcionalidad XPath en [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] que debe ponerse a disposición por los métodos de extensión en <xref:System.Xml.XPath.Extensions?displayProperty=fullName>.</xref:System.Xml.XPath.Extensions?displayProperty=fullName> Los ejemplos ejecutan la expresión XPath y la expresión [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]. A continuación, cada ejemplo compara los resultados de ambas consultas, validando que la expresión XPath sea funcionalmente equivalente a la consulta de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]. Como ambos tipos de consultas devuelven nodos del mismo árbol XML, la comparación del resultado de las consultas se realiza mediante identidad referencial.  
  
## <a name="in-this-section"></a>En esta sección  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[Comparación de XPath y LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/comparison-of-xpath-and-linq-to-xml.md)|Proporciona información general de las similitudes y diferencias entre XPath y [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].|  
|[Cómo: buscar un elemento secundario (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-child-element-xpath-linq-to-xml.md)|Compara el eje del elemento secundario XPath con el [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] <xref:System.Xml.Linq.XContainer.Element%2A>método.</xref:System.Xml.Linq.XContainer.Element%2A><br /><br /> La expresión XPath asociada es:`"DeliveryNotes"`.|  
|[Cómo: buscar una lista de elementos secundarios (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-list-of-child-elements-xpath-linq-to-xml.md)|Compara el eje de elementos secundarios de XPath con el [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A>eje.</xref:System.Xml.Linq.XContainer.Elements%2A><br /><br /> La expresión XPath asociada es:`"./*"`|  
|[Cómo: buscar el elemento raíz (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-root-element-xpath-linq-to-xml.md)|Compara cómo obtener el elemento raíz con XPath y [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> La expresión XPath asociada es:`"/PurchaseOrders"`|  
|[Cómo: buscar elementos descendientes (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-descendant-elements-xpath-linq-to-xml.md)|Compara cómo obtener los elementos descendientes con un nombre específico con XPath y [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> La expresión XPath asociada es:`"//Name"`|  
|[Cómo: filtrar en un atributo (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-filter-on-an-attribute-xpath-linq-to-xml.md)|Compara cómo obtener los elementos descendientes con un nombre especificado y con un atributo con un valor especificado con XPath y [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> La expresión XPath asociada es:`".//Address[@Type='Shipping']"`|  
|[Cómo: buscar elementos relacionados (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-related-elements-xpath-linq-to-xml.md)|Compara cómo obtener un elemento seleccionando en un atributo al que hace referencia el valor de otro elemento con XPath y [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> La expresión XPath asociada es:`".//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]"`|  
|[Cómo: buscar elementos en un Namespace (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-elements-in-a-namespace.md)|Compara el uso de la expresión XPath <xref:System.Xml.XmlNamespaceManager>clase con la [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] <xref:System.Xml.Linq.XName.Namespace%2A>propiedad de la <xref:System.Xml.Linq.XName>clase para trabajar con espacios de nombres XML.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XName.Namespace%2A> </xref:System.Xml.XmlNamespaceManager><br /><br /> La expresión XPath asociada es:`"./aw:*"`|  
|[Cómo: buscar elementos relacionados (XPath-LINQ to XML) anteriores (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-preceding-siblings-xpath-linq-to-xml.md)|Compara la expresión XPath `preceding-sibling` eje para el [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] secundarios <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName>eje.</xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName><br /><br /> La expresión XPath asociada es:`"preceding-sibling::*"`|  
|[Cómo: buscar descendientes de un elemento secundario (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-descendants-of-a-child-element-xpath-linq-to-xml.md)|Compara cómo obtener los elementos descendientes de un elemento secundario con un nombre específico con XPath y [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> La expresión XPath asociada es:`"./Paragraph//Text/text()"`|  
|[Cómo: buscar la unión de dos rutas de ubicación (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-union-of-two-location-paths-xpath.md)|Compara el uso del operador union, `&#124;`, en XPath con el <xref:System.Linq.Enumerable.Concat%2A>operador de consulta estándar en [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</xref:System.Linq.Enumerable.Concat%2A><br /><br /> La expresión XPath asociada es:`"//Category&#124;//Price"`|  
|[Cómo: buscar nodos relacionados (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-sibling-nodes-xpath-linq-to-xml.md)|Compara cómo buscar todos los elementos del mismo nivel de un nodo que tiene un nombre específico con XPath y [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> La expresión XPath asociada es:`"../Book"`|  
|[Cómo: buscar un atributo del elemento primario (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml.md)|Compara cómo desplazarse al elemento primario y buscar un atributo asociado usando XPath y [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> La expresión XPath asociada es:`"../@id"`|  
|[Cómo: buscar atributos de elementos relacionados con un nombre específico (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-attributes-of-siblings-with-a-specific-name.md)|Compara cómo buscar atributos específicos de los elementos del mismo nivel del nodo de contexto con XPath y [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> La expresión XPath asociada es:`"``../Book/@id``"`|  
|[Cómo: buscar elementos con un atributo específico (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-elements-with-a-specific-attribute.md)|Compara cómo buscar todos los elementos que contienen un atributo específico usando XPath y [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> La expresión XPath asociada es:`"./*[@Select]"`|  
|[Cómo: buscar elementos secundarios en función de la posición (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-child-elements-based-on-position.md)|Compara cómo buscar un elemento basándose en su posición relativa usando XPath y [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> La expresión XPath asociada es:`"Test[position() >= 2 and position() <= 4]"`|  
|[Cómo: buscar el elemento relacionado anterior inmediato (XPath-LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml.md)|Compara cómo buscar el elemento del mismo nivel inmediatamente anterior de un nodo usando XPath y [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> La expresión XPath asociada es:`"preceding-sibling::*[1]"`|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.XPath?displayProperty=fullName></xref:System.Xml.XPath?displayProperty=fullName>   
 [Consultar árboles XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)   
 [Procesar datos XML mediante el modelo de datos XPath](http://msdn.microsoft.com/library/536c6fce-1453-4654-9c72-bca54d47e081)
