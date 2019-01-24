---
title: Procedimiento Acceso a elementos descendientes de XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: f1248109dfcc853f701ea2ab61edc67d768e9663
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666181"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a>Procedimiento Acceso a elementos descendientes de XML (Visual Basic)
En este ejemplo se muestra cómo usar una propiedad de eje descendiente para tener acceso a todos los elementos XML que tiene un nombre especificado y que se incluyen en un elemento XML. En concreto, usa el `Value` propiedad para obtener el valor del primer elemento de la colección que la `name` devuelve de la propiedad de eje descendiente. El `name` propiedad de eje descendiente Obtiene todos los elementos llamados `name` que están contenidas en el `contacts` objeto. En este ejemplo también usa el `phone` propiedad de eje descendiente para tener acceso a todos los descendientes denominados `phone` que están contenidas en el `contacts` objeto.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbXMLSamples#31](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-descendant-elements_1.vb)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una referencia al espacio de nombres <xref:System.Xml.Linq>.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [Propiedad del eje descendiente XML](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [Propiedad de valor XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [Obtener acceso a XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
