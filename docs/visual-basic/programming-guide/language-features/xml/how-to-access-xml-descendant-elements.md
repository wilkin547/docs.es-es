---
title: 'Cómo: Obtener acceso a elementos descendientes XML (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: 6d41844b540631df96740ce56818c125cf85e928
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a>Cómo: Obtener acceso a elementos descendientes XML (Visual Basic)
Este ejemplo muestra cómo usar una propiedad de eje descendiente para tener acceso a todos los elementos XML que tienen el nombre especificado y que están incluidos en un elemento XML. En concreto, usa el `Value` propiedad para obtener el valor del primer elemento de la colección que la `name` devuelve de la propiedad de eje descendiente. El `name` propiedad de eje descendiente Obtiene todos los elementos llamados `name` que están contenidas en el `contacts` objeto. Este ejemplo también utiliza el `phone` propiedad de eje descendiente para tener acceso a todos los descendientes con el nombre `phone` que están contenidas en el `contacts` objeto.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbXMLSamples#31](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-descendant-elements_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una referencia al espacio de nombres <xref:System.Xml.Linq>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>  
 [Propiedad del eje descendiente XML](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)  
 [Propiedad de valor XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [Obtener acceso a XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
