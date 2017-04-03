---
title: Anotaciones de LINQ to XML | Microsoft Docs
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
ms.assetid: 54e7b9d0-07f5-488f-9065-b6e6b870f810
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 13718f509eee46853020cfe1dd27ee85437d2e6d
ms.lasthandoff: 03/13/2017


---
# <a name="linq-to-xml-annotations"></a>Anotaciones de LINQ to XML
Las anotaciones de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] le permiten asociar cualquier objeto de cualquier tipo con un componente XML de un árbol XML.  
  
 Para agregar una anotación a un componente XML, como <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XAttribute>, llame al método <xref:System.Xml.Linq.XObject.AddAnnotation%2A>. Las anotaciones se obtienen por tipos.  
  
 Tenga en cuenta que las anotaciones no forman parte del conjunto de información de XML, por lo que no se serializan o deserializan.  
  
## <a name="methods"></a>Métodos  
 Puede utilizar los siguientes métodos a la hora de trabajar con anotaciones:  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|Agrega un objeto a la lista de anotaciones de <xref:System.Xml.Linq.XObject>.|  
|<xref:System.Xml.Linq.XObject.Annotation%2A>|Obtiene el primer objeto de anotación del tipo especificado a partir de <xref:System.Xml.Linq.XObject>.|  
|<xref:System.Xml.Linq.XObject.Annotations%2A>|Obtiene una colección de anotaciones del tipo especificado a partir de <xref:System.Xml.Linq.XObject>.|  
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|Quita las anotaciones del tipo especificado de <xref:System.Xml.Linq.XObject>.|  
  
## <a name="see-also"></a>Vea también  
 [Programación avanzada de LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
