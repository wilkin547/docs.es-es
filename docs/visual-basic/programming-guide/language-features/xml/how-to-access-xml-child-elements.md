---
title: Procedimiento Elementos secundarios XML Access (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: cd1b0db5305c7879d89cfdfff6cd458d6dea14f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973035"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a>Procedimiento Elementos secundarios XML Access (Visual Basic)
Este ejemplo muestra cómo usar a un elemento secundario de la propiedad de eje para tener acceso a todos los elementos secundarios XML que tienen un nombre especificado en un elemento XML. En concreto, usa el <xref:System.Xml.Linq.XElement.Value%2A> propiedad para obtener el valor del primer elemento de la colección que la `name` devuelve de propiedad de eje secundario. El `name` propiedad de eje secundario obtiene todos los elementos secundarios denominados `phone` en el `contact` objeto. En este ejemplo también usa el `phone` propiedad de eje secundario para tener acceso a todos los elementos secundarios denominados `phone` que están contenidas en el `contact` objeto.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Una referencia al espacio de nombres <xref:System.Xml.Linq>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [Propiedad del eje secundario XML](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [Propiedad de valor XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [Obtener acceso a XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
