---
title: "Modificar elementos, atributos y nodos de un árbol XML | Microsoft Docs"
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
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6fa51b22af73d716b01444540edb7c8d814cd293
ms.lasthandoff: 03/13/2017


---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a>Modificar elementos, atributos y nodos de un árbol XML
La tabla siguiente resume los métodos y las propiedades que puede usar para modificar un elemento, sus elementos secundarios o sus atributos.  
  
 Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XElement>.  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>|Reemplaza un elemento por XML analizado.|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName>|Quita todo el contenido (atributos y nodos secundarios) de un elemento.|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName>|Quita los atributos de un elemento.|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=fullName>|Reemplaza todo el contenido (nodos secundarios y atributos) de un elemento.|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=fullName>|Reemplaza los atributos de un elemento.|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName>|Establece el valor de un atributo. Crea el atributo si no existe. Si el valor se establece en `null`, quita el atributo.|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName>|Establece el valor de un elemento secundario. Crea el elemento si no existe. Si el valor se establece en `null`, quita el elemento.|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>|Reemplaza el contenido (nodos secundarios) de un elemento por el texto especificado.|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=fullName>|Establece el valor de un elemento.|  
  
 Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XAttribute>.  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>|Establece el valor de un atributo.|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=fullName>|Establece el valor de un atributo.|  
  
 Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XNode> (incluido <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>).  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=fullName>|Reemplaza un nodo por contenido nuevo.|  
  
 Los métodos siguientes modifican un elemento <xref:System.Xml.Linq.XContainer> (incluido <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>).  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=fullName>|Reemplaza los nodos secundarios por contenido nuevo.|  
  
## <a name="see-also"></a>Vea también  
 [Modificar árboles XML (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
