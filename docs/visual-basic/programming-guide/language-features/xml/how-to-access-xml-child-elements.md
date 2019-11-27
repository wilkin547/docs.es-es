---
title: 'Cómo: Obtener acceso a elementos secundarios XML'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: af5ea809cb0777b16230f20e133764dd5f1f86d9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332338"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a>Cómo: Obtener acceso a elementos secundarios XML (Visual Basic)
En este ejemplo se muestra cómo usar una propiedad de eje secundario para tener acceso a todos los elementos secundarios XML que tienen un nombre especificado en un elemento XML. En concreto, usa la propiedad <xref:System.Xml.Linq.XElement.Value%2A> para obtener el valor del primer elemento de la colección que devuelve la propiedad del eje secundario `name`. La propiedad `name` eje secundario obtiene todos los elementos secundarios denominados `phone` en el objeto `contact`. En este ejemplo también se usa la propiedad del eje secundario `phone` para tener acceso a todos los elementos secundarios denominados `phone` contenidos en el objeto `contact`.  
  
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
