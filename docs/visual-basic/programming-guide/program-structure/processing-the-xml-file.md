---
title: Procesar el archivo XML (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML comments, parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 72b2832d0131adf39a37ebd9297b43fb34ea49ba
ms.lasthandoff: 03/13/2017

---
# <a name="processing-the-xml-file-visual-basic"></a>Procesar el archivo XML (Visual Basic)
El compilador genera una cadena de identificador para cada construcción de código que tiene una etiqueta para generar la documentación. (Para obtener información sobre cómo etiquetar el código, consulte [etiquetas de comentario XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) La cadena de identificador identifica de forma única la construcción. Los programas que procesan el archivo XML pueden utilizar la cadena de identificador para identificar la correspondiente [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] elemento de metadatos y reflexión.  
  
 El archivo XML no es una representación jerárquica del código; es una lista plana con un identificador generado para cada elemento.  
  
 El compilador cumple las siguientes reglas cuando genera las cadenas de identificación:  
  
-   Ningún espacio en blanco se coloca en la cadena.  
  
-   La primera parte de la cadena de identificador identifica el tipo de miembro que se identifican con un único carácter seguido de dos puntos. Se utilizan los siguientes tipos de miembro.  
  
|Carácter|Descripción|  
|---|---|  
|N|namespace<br /><br /> No se puede agregar comentarios de documentación a un espacio de nombres, pero se pueden hacer referencias CREF a ellos, si se admite.|  
|T|type: `Class`, `Module`, `Interface`, `Structure`, `Enum`,`Delegate`|  
|F|campo:`Dim`|  
|P|propiedad: `Property` (incluidas las propiedades de forma predeterminada)|  
|M|method: `Sub`, `Function`, `Declare`,`Operator`|  
|E|evento:`Event`|  
|!|cadena de error<br /><br /> El resto de la cadena proporciona información sobre el error. El [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador genera información de error para vínculos que no se pueden resolver.|  
  
-   La segunda parte de la `String` es el nombre completo del elemento, empezando por la raíz del espacio de nombres. El nombre del elemento, los tipos contenedores y el espacio de nombres separados por puntos. Si el nombre del elemento ya contiene puntos, éstos se reemplazan por el signo de número (#). Se supone que ningún elemento contiene un signo de número directamente en su nombre. Por ejemplo, el nombre completo de la `String` constructor sería `System.String.#ctor`.  
  
-   Para propiedades y métodos, si no hay argumentos para el método, sigue la lista de argumentos entre paréntesis. Si no hay ningún argumento, paréntesis no están presentes. Los argumentos se separan por comas. La codificación de cada argumento indica directamente cómo se codifica en un [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] firma.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra cómo las cadenas de ID de una clase y sus miembros se generan.  
  
 [!code-vb[VbVbcnXmlDocComments&#10;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)   
 [Crear documentación XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
