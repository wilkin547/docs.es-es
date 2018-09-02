---
title: Procesar el archivo XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
ms.openlocfilehash: 524a54443b8f2365252f11282ca29fc492bef351
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43398578"
---
# <a name="processing-the-xml-file-visual-basic"></a>Procesar el archivo XML (Visual Basic)
El compilador genera una cadena de identificador para cada construcción del código que se etiqueta para generar documentación. (Para obtener información sobre cómo etiquetar el código, vea [etiquetas de comentario XML](../../../visual-basic/language-reference/xmldoc/index.md).) La cadena de identificador identifica la construcción de forma exclusiva. Los programas que procesan el archivo XML pueden usar la cadena de identificador para identificar la correspondiente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] elemento reflexión o de metadatos.  
  
 El archivo XML no es una representación jerárquica del código; es una lista plana con un identificador generado para cada elemento.  
  
 El compilador cumple las siguientes reglas cuando genera las cadenas de identificador:  
  
-   No se coloca espacio en blanco en la cadena.  
  
-   La primera parte de la cadena ID identifica el tipo de miembro identificado, mediante un carácter único seguido de dos puntos. Se usan los siguientes tipos de miembro.  
  
|Carácter|Descripción|  
|---|---|  
|N|namespace<br /><br /> No se puede agregar comentarios de documentación a un espacio de nombres, pero puede hacer referencias cruzadas a ellos, si se admite.|  
|T|tipo: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`|  
|F|campo: `Dim`|  
|P|propiedad: `Property` (incluidas las propiedades de forma predeterminada)|  
|M|método: `Sub`, `Function`, `Declare`, `Operator`|  
|E|evento: `Event`|  
|!|cadena de error<br /><br /> El resto de la cadena proporciona información sobre el error. El compilador de Visual Basic genera información de error para vínculos que no se puede resolver.|  
  
-   La segunda parte de la `String` es el nombre completo del elemento, empezando por la raíz del espacio de nombres. El nombre del elemento, sus tipos envolventes y el espacio de nombres están separados por puntos. Si el nombre del elemento ya contiene puntos, se reemplazan por el signo de número (#). Se supone que no hay ningún elemento tiene un signo de número directamente en su nombre. Por ejemplo, el nombre completo de la `String` constructor sería `System.String.#ctor`.  
  
-   Para propiedades y métodos, si hay argumentos para el método, sigue la lista de argumentos entre paréntesis. Si no hay ningún argumento, tampoco habrá paréntesis. Los argumentos están separados por comas. La codificación de cada argumento indica directamente cómo se codifica en un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] firma.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra cómo las cadenas de identificador para una clase y sus miembros se generan.  
  
 [!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [Crear documentación XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
