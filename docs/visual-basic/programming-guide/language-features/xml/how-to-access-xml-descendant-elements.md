---
title: Procedimiento para obtener acceso a elementos descendientes XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: dcbaf1f9022d86f40a90ef6a1e0033f627caeef2
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058214"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a>Cómo: Obtener acceso a elementos descendientes XML (Visual Basic)

En este ejemplo se muestra cómo usar una propiedad de eje descendiente para tener acceso a todos los elementos XML que tienen un nombre especificado y que están incluidos en un elemento XML. En concreto, usa la `Value` propiedad para obtener el valor del primer elemento de la colección que `name` devuelve la propiedad de eje descendiente. La `name` propiedad de eje descendiente obtiene todos los elementos denominados `name` contenidos en el `contacts` objeto. En este ejemplo también se usa la `phone` propiedad AXIS descendiente para tener acceso a todos los descendientes denominados `phone` contenidos en el `contacts` objeto.  
  
## <a name="example"></a>Ejemplo  

 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compile-the-code"></a>Compilar el código  

 Para este ejemplo se necesita:  
  
- Una referencia al espacio de nombres <xref:System.Xml.Linq>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [XML Descendant Axis Property](../../../language-reference/xml-axis/xml-descendant-axis-property.md)
- [Propiedad de valor XML](../../../language-reference/xml-axis/xml-value-property.md)
- [Obtener acceso a XML en Visual Basic](accessing-xml.md)
- [XML](index.md)
