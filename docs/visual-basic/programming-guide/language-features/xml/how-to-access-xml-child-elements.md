---
title: 'Cómo: Obtener acceso a elementos secundarios XML (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: 4ec7743a30b8101d813ac414a8f5164aeb6c593d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a>Cómo: Obtener acceso a elementos secundarios XML (Visual Basic)
Este ejemplo muestra cómo utilizar a un elemento secundario de propiedad de eje para tener acceso a todos los elementos secundarios XML que tienen el nombre especificado en un elemento XML. En concreto, usa el <xref:System.Xml.Linq.XElement.Value%2A> propiedad para obtener el valor del primer elemento de la colección que la `name` devuelve de propiedad de eje secundario. El `name` propiedad de eje secundario obtiene todos los elementos secundarios llamados `phone` en la `contact` objeto. Este ejemplo también utiliza el `phone` propiedad de eje secundario para obtener acceso a todos los elementos secundarios llamados `phone` que están contenidas en el `contact` objeto.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbXMLSamples#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-child-elements_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una referencia al espacio de nombres <xref:System.Xml.Linq>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>  
 [Propiedad del eje secundario XML](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [Propiedad de valor XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [Obtener acceso a XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
