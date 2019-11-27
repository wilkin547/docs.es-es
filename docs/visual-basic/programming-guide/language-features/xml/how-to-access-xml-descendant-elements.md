---
title: 'Cómo: Obtener acceso a elementos descendientes XML'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: 63a094c3c2b20736f0ef6589c76d53b7cc96b29a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332313"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a>Cómo: Obtener acceso a elementos descendientes XML (Visual Basic)
En este ejemplo se muestra cómo usar una propiedad de eje descendiente para tener acceso a todos los elementos XML que tienen un nombre especificado y que están incluidos en un elemento XML. En concreto, usa la propiedad `Value` para obtener el valor del primer elemento de la colección que devuelve la propiedad de eje descendiente `name`. La propiedad `name` eje descendiente obtiene todos los elementos denominados `name` incluidos en el objeto `contacts`. En este ejemplo también se usa la propiedad de eje descendiente `phone` para tener acceso a todos los descendientes denominados `phone` incluidos en el objeto `contacts`.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Una referencia al espacio de nombres <xref:System.Xml.Linq>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [Propiedad del eje descendiente XML](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [Propiedad de valor XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [Obtener acceso a XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
