---
title: Procesar el archivo XML (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d44f58951d99f1b4b551af75dc0a0e895e337e2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="processing-the-xml-file-visual-basic"></a>Procesar el archivo XML (Visual Basic)
El compilador genera una cadena de identificador para cada construcción del código que se etiqueta para generar documentación. (Para obtener información sobre cómo etiquetar el código, vea [etiquetas de comentario XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).) La cadena de identificador identifica la construcción de forma exclusiva. Los programas que procesan el archivo XML pueden usar la cadena de identificador para identificar la correspondiente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] elemento de metadatos/reflexión.  
  
 El archivo XML no es una representación jerárquica del código; es una lista plana con un identificador generado para cada elemento.  
  
 El compilador cumple las siguientes reglas cuando genera las cadenas de identificador:  
  
-   Ningún espacio en blanco se coloca en la cadena.  
  
-   La primera parte de la cadena de identificador identifica el tipo de miembro que se identifican con un único carácter seguido de dos puntos. Se utilizan los siguientes tipos de miembro.  
  
|Carácter|Descripción|  
|---|---|  
|N|namespace<br /><br /> No se puede agregar comentarios de documentación a un espacio de nombres, pero puede hacer referencias CREF a ellos, si se admite.|  
|T|tipo: `Class`, `Module`, `Interface`, `Structure`, `Enum`,`Delegate`|  
|F|campo:`Dim`|  
|P|propiedad: `Property` (incluidas las propiedades de forma predeterminada)|  
|M|método: `Sub`, `Function`, `Declare`,`Operator`|  
|E|evento:`Event`|  
|!|cadena de error<br /><br /> El resto de la cadena proporciona información sobre el error. El [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilador genera información de error para vínculos que no se pueden resolver.|  
  
-   La segunda parte de la `String` es el nombre completo del elemento, empezando por la raíz del espacio de nombres. El nombre del elemento, sus tipos envolventes y el espacio de nombres separados por puntos. Si el nombre del elemento ya contiene puntos, éstos se reemplazan por el signo de número (#). Se supone que no hay ningún elemento contiene un signo de número directamente en su nombre. Por ejemplo, el nombre completo de la `String` constructor sería `System.String.#ctor`.  
  
-   Para propiedades y métodos, si hay argumentos para el método, sigue la lista de argumentos entre paréntesis. Si no hay ningún argumento, tampoco habrá paréntesis. Los argumentos están separados por comas. La codificación de cada argumento indica directamente cómo se codifica en un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] firma.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra cómo las cadenas de ID para una clase y sus miembros se generan.  
  
 [!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [Crear documentación XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
