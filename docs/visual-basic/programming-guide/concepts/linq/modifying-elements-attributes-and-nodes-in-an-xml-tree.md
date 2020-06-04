---
title: Modificar elementos, atributos y nodos de un Tree1 XML
ms.date: 07/20/2015
ms.assetid: 865cf54e-f8ac-4871-863b-a3e6fc61a4b9
ms.openlocfilehash: 002e87d58ad1a3730889225bf4b3e50448431f2d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360935"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a>Modificar elementos, atributos y nodos de un árbol XML
La tabla siguiente resume los métodos y las propiedades que puede usar para modificar un elemento, sus elementos secundarios o sus atributos.  
  
 Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XElement>.  
  
|Método|Description|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|Reemplaza un elemento por XML analizado.|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|Quita todo el contenido (atributos y nodos secundarios) de un elemento.|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|Quita los atributos de un elemento.|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|Reemplaza todo el contenido (nodos secundarios y atributos) de un elemento.|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|Reemplaza los atributos de un elemento.|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|Establece el valor de un atributo. Crea el atributo si no existe. Si el valor se establece en `null`, quita el atributo.|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|Establece el valor de un elemento secundario. Crea el elemento si no existe. Si el valor se establece en `null`, quita el elemento.|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|Reemplaza el contenido (nodos secundarios) de un elemento por el texto especificado.|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|Establece el valor de un elemento.|  
  
 Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XAttribute>.  
  
|Método|Description|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|Establece el valor de un atributo.|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|Establece el valor de un atributo.|  
  
 Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XNode> (incluyendo <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>).  
  
|Método|Description|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|Reemplaza un nodo por contenido nuevo.|  
  
 Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>).  
  
|Método|Description|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|Reemplaza los nodos secundarios por contenido nuevo.|  
  
## <a name="see-also"></a>Consulte también

- [Modificar árboles XML (LINQ to XML) (Visual Basic)](modifying-xml-trees-linq-to-xml.md)
