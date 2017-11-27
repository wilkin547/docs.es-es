---
title: "Cómo: Obtener acceso a elementos descendientes XML (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7b3b6c8ac96bd18a379804b83f3ab3e48a5b0c89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
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
