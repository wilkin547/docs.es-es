---
description: 'Más información acerca de cómo: obtener acceso a elementos secundarios XML (Visual Basic)'
title: Procedimiento para obtener acceso a elementos secundarios XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: fad4d45853006762bc319b0ff8f9143ef13058da
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433244"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a>Cómo: Obtener acceso a elementos secundarios XML (Visual Basic)

En este ejemplo se muestra cómo usar una propiedad de eje secundario para tener acceso a todos los elementos secundarios XML que tienen un nombre especificado en un elemento XML. En concreto, usa la <xref:System.Xml.Linq.XElement.Value%2A> propiedad para obtener el valor del primer elemento de la colección que `name` devuelve la propiedad del eje secundario. La `name` propiedad del eje secundario obtiene todos los elementos secundarios denominados `phone` en el `contact` objeto. En este ejemplo también se usa la `phone` propiedad del eje secundario para obtener acceso a todos los elementos secundarios denominados `phone` contenidos en el `contact` objeto.  
  
## <a name="example"></a>Ejemplo  

 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compile-the-code"></a>Compilar el código  

 Para este ejemplo se necesita:  
  
- Una referencia al espacio de nombres <xref:System.Xml.Linq>.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [XML Child Axis Property](../../../language-reference/xml-axis/xml-child-axis-property.md)
- [Propiedad de valor XML](../../../language-reference/xml-axis/xml-value-property.md)
- [Obtener acceso a XML en Visual Basic](accessing-xml.md)
- [XML](index.md)
