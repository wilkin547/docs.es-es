---
title: LINQ to XML Annotations2
ms.date: 07/20/2015
ms.assetid: c3e8b3ff-fceb-4428-b0ca-1ed6f128aac8
ms.openlocfilehash: edf8e0126c632deae6b6d4c235c4880d7b8687e8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831756"
---
# <a name="linq-to-xml-annotations"></a>Anotaciones de LINQ to XML
Las anotaciones de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] le permiten asociar cualquier objeto de cualquier tipo con un componente XML de un árbol XML.  
  
 Si desea agregar una anotación a un componente XML, como puede ser un <xref:System.Xml.Linq.XElement> o un <xref:System.Xml.Linq.XAttribute>, deberá llamar al método <xref:System.Xml.Linq.XObject.AddAnnotation%2A>. Las anotaciones se obtienen por tipos.  
  
 Tenga en cuenta que las anotaciones no forman parte del conjunto de información de XML, por lo que no se serializan o deserializan.  
  
## <a name="methods"></a>Métodos  
 Puede utilizar los siguientes métodos a la hora de trabajar con anotaciones:  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|Agrega un objeto a la lista de anotaciones de un <xref:System.Xml.Linq.XObject>.|  
|<xref:System.Xml.Linq.XObject.Annotation%2A>|Obtiene el primer objeto de anotación del tipo especificado a partir de un <xref:System.Xml.Linq.XObject>.|  
|<xref:System.Xml.Linq.XObject.Annotations%2A>|Obtiene una colección de anotaciones del tipo especificado a partir de un <xref:System.Xml.Linq.XObject>.|  
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|Elimina las anotaciones del tipo especificado de un <xref:System.Xml.Linq.XObject>.|  
  
## <a name="see-also"></a>Vea también

- [Avanzada de LINQ to XML (Visual Basic) de programación](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
