---
title: LINQ to XML Annotations2 | Documentos de Microsoft
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
ms.assetid: c3e8b3ff-fceb-4428-b0ca-1ed6f128aac8
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1f2e5bea1cde74548daa1697b6a0a819e3eba3e4
ms.lasthandoff: 03/13/2017


---
# <a name="linq-to-xml-annotations"></a>Anotaciones de LINQ to XML
Las anotaciones de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] le permite asociar cualquier objeto de cualquier tipo con un componente XML de un árbol XML.  
  
 Para agregar una anotación a un componente XML, como un <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XAttribute>, se llama a la <xref:System.Xml.Linq.XObject.AddAnnotation%2A>método.</xref:System.Xml.Linq.XObject.AddAnnotation%2A> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> Las anotaciones se obtienen por tipos.  
  
 Tenga en cuenta que las anotaciones no forman parte del conjunto de información de XML, por lo que no se serializan o deserializan.  
  
## <a name="methods"></a>Métodos  
 Puede utilizar los siguientes métodos a la hora de trabajar con anotaciones:  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A></xref:System.Xml.Linq.XObject.AddAnnotation%2A>|Agrega un objeto a la lista de anotaciones de un <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject>|  
|<xref:System.Xml.Linq.XObject.Annotation%2A></xref:System.Xml.Linq.XObject.Annotation%2A>|Obtiene el primer objeto de anotación del tipo especificado de un <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject>|  
|<xref:System.Xml.Linq.XObject.Annotations%2A></xref:System.Xml.Linq.XObject.Annotations%2A>|Obtiene una colección de anotaciones del tipo especificado para una <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject>|  
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A></xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|Quita las anotaciones del tipo especificado de un <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject>|  
  
## <a name="see-also"></a>Vea también  
 [Avanzada de LINQ to XML Programming (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
