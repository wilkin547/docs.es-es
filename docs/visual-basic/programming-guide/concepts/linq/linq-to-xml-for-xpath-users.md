---
title: LINQ to XML para usuarios de XPath
ms.date: 07/20/2015
ms.assetid: 0e64911c-a7cc-4c20-b927-ca99078b5656
ms.openlocfilehash: 7942d33831644875f390e9128965fe1c36433808
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84368795"
---
# <a name="linq-to-xml-for-xpath-users-visual-basic"></a>LINQ to XML para los usuarios de XPath (Visual Basic)

En este conjunto de temas se muestran varias expresiones XPath y sus equivalentes de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 Todos los ejemplos utilizan la funcionalidad XPath en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] que está disponible con los métodos de extensión de <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>. Los ejemplos ejecutan la expresión XPath y la expresión [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. A continuación, cada ejemplo compara los resultados de ambas consultas, validando que la expresión XPath sea funcionalmente equivalente a la consulta de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Como ambos tipos de consultas devuelven nodos del mismo árbol XML, la comparación del resultado de las consultas se realiza mediante identidad referencial.  
  
## <a name="in-this-section"></a>En esta sección  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[Comparación de XPath y LINQ to XML](../../../../csharp/programming-guide/concepts/linq/comparison-of-xpath-and-linq-to-xml.md)|Proporciona información general de las similitudes y diferencias entre XPath y [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].|  
|[Cómo: buscar un elemento secundario (XPath-LINQ to XML) (Visual Basic)](how-to-find-a-child-element-xpath-linq-to-xml.md)|Compara el eje del elemento secundario XPath con el [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A> método.<br /><br /> La expresión XPath asociada es:`"DeliveryNotes"`.|  
|[Cómo: buscar una lista de elementos secundarios (XPath-LINQ to XML) (Visual Basic)](how-to-find-a-list-of-child-elements-xpath-linq-to-xml.md)|Compara el eje de los elementos secundarios de XPath con el [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A> eje.<br /><br /> La expresión XPath asociada es:`"./*"`|  
|[Cómo: buscar el elemento raíz (XPath-LINQ to XML) (Visual Basic)](how-to-find-the-root-element-xpath-linq-to-xml.md)|Compara cómo obtener el elemento raíz con XPath y [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> La expresión XPath asociada es:`"/PurchaseOrders"`|  
|[Cómo: buscar elementos descendientes (XPath-LINQ to XML) (Visual Basic)](how-to-find-descendant-elements-xpath-linq-to-xml.md)|Compara cómo obtener los elementos descendientes con un nombre específico con XPath y [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> La expresión XPath asociada es:`"//Name"`|  
|[Cómo: filtrar por un atributo (XPath-LINQ to XML) (Visual Basic)](how-to-filter-on-an-attribute-xpath-linq-to-xml.md)|Compara cómo obtener los elementos descendientes con un nombre especificado y con un atributo con un valor especificado con XPath y [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> La expresión XPath asociada es:`"./Address[@Type='Shipping']"`|  
|[Cómo: buscar elementos relacionados (XPath-LINQ to XML) (Visual Basic)](how-to-find-related-elements-xpath-linq-to-xml.md)|Compara cómo obtener un elemento seleccionando en un atributo al que hace referencia el valor de otro elemento con XPath y [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> La expresión XPath asociada es:`"./Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]"`|  
|[Cómo: buscar elementos en un espacio de nombres (XPath-LINQ to XML) (Visual Basic)](how-to-find-elements-in-a-namespace.md)|Compara el uso de la clase XPath <xref:System.Xml.XmlNamespaceManager> con la [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XName.Namespace%2A> propiedad de la <xref:System.Xml.Linq.XName> clase para trabajar con espacios de nombres XML.<br /><br /> La expresión XPath asociada es:`"./aw:*"`|  
|[Cómo: buscar elementos del mismo nivel anteriores (XPath-LINQ to XML) (Visual Basic)](how-to-find-preceding-siblings-xpath-linq-to-xml.md)|Compara el eje `preceding-sibling` de XPath con el eje secundario de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType>.<br /><br /> La expresión XPath asociada es:`"preceding-sibling::*"`|  
|[Cómo: buscar descendientes de un elemento secundario (XPath-LINQ to XML) (Visual Basic)](how-to-find-descendants-of-a-child-element-xpath-linq-to-xml.md)|Compara cómo obtener los elementos descendientes de un elemento secundario con un nombre específico con XPath y [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> La expresión XPath asociada es:`"./Paragraph//Text/text()"`|  
|[Cómo: buscar una Unión de dos rutas de acceso de ubicación (XPath-LINQ to XML) (Visual Basic)](how-to-find-a-union-of-two-location-paths-xpath.md)|Compara el uso del operador de unión, <code>&#124;</code>, en XPath con el operador de consulta estándar <xref:System.Linq.Enumerable.Concat%2A> en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> La expresión XPath asociada es:<code>"//Category&#124;//Price"</code>|  
|[Cómo: buscar nodos del mismo nivel (XPath-LINQ to XML) (Visual Basic)](how-to-find-sibling-nodes-xpath-linq-to-xml.md)|Compara cómo buscar todos los elementos del mismo nivel de un nodo que tiene un nombre específico con XPath y [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> La expresión XPath asociada es:`"../Book"`|  
|[Cómo: buscar un atributo del elemento primario (XPath-LINQ to XML) (Visual Basic)](how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml.md)|Compara cómo desplazarse al elemento primario y buscar un atributo asociado usando XPath y [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> La expresión XPath asociada es:`"../@id"`|  
|[Cómo: buscar atributos de elementos del mismo nivel con un nombre específico (XPath-LINQ to XML) (Visual Basic)](how-to-find-attributes-of-siblings-with-a-specific-name.md)|Compara cómo buscar atributos específicos de los elementos del mismo nivel del nodo de contexto con XPath y [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> La expresión XPath asociada es:`"../Book/@id"`|  
|[Cómo: buscar elementos con un atributo específico (XPath-LINQ to XML) (Visual Basic)](how-to-find-elements-with-a-specific-attribute.md)|Compara cómo buscar todos los elementos que contienen un atributo específico usando XPath y [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> La expresión XPath asociada es:`"./*[@Select]"`|  
|[Cómo: buscar elementos secundarios en función de la posición (XPath-LINQ to XML) (Visual Basic)](how-to-find-child-elements-based-on-position.md)|Compara cómo buscar un elemento basándose en su posición relativa usando XPath y [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> La expresión XPath asociada es:`"Test[position() >= 2 and position() <= 4]"`|  
|[Cómo: buscar el elemento del mismo nivel inmediatamente anterior (XPath-LINQ to XML) (Visual Basic)](how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml.md)|Compara cómo buscar el elemento del mismo nivel inmediatamente anterior de un nodo usando XPath y [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].<br /><br /> La expresión XPath asociada es:`"preceding-sibling::*[1]"`|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Xml.XPath?displayProperty=nameWithType>
- [Consultar árboles XML (Visual Basic)](querying-xml-trees.md)
- [Procesamiento de datos XML con el modelo de datos XPath](../../../../standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
