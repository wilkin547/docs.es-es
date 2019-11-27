---
title: Procesar el archivo XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
ms.openlocfilehash: 4230fd88b4b60c631135f5b7fb15f4b6272b5351
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347303"
---
# <a name="processing-the-xml-file-visual-basic"></a>Procesar el archivo XML (Visual Basic)
El compilador genera una cadena de identificador para cada construcción del código que se etiqueta para generar documentación. (Para obtener información sobre cómo etiquetar el código, vea [etiquetas de comentario XML](../../../visual-basic/language-reference/xmldoc/index.md)). La cadena de identificador identifica la construcción de forma única. Los programas que procesan el archivo XML pueden usar la cadena de identificador para identificar el elemento de metadatos/reflexión de .NET Framework correspondiente.  
  
 El archivo XML no es una representación jerárquica del código; es una lista plana con un identificador generado para cada elemento.  
  
 El compilador cumple las siguientes reglas cuando genera las cadenas de identificador:  
  
- No se coloca espacio en blanco en la cadena.  
  
- La primera parte de la cadena ID identifica el tipo de miembro identificado, mediante un carácter único seguido de dos puntos. Se utilizan los siguientes tipos de miembro.  
  
|Carácter|Descripción|  
|---|---|  
|N|namespace<br /><br /> No puede agregar comentarios de documentación a un espacio de nombres, pero puede hacer referencias CREF a ellos, si se admiten.|  
|T|tipo: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`|  
|F|campo: `Dim`|  
|P|propiedad: `Property` (incluidas las propiedades predeterminadas)|  
|M|método: `Sub`, `Function`, `Declare`, `Operator`|  
|E|evento: `Event`|  
|!|cadena de error<br /><br /> El resto de la cadena proporciona información sobre el error. El compilador Visual Basic genera información de error para los vínculos que no se pueden resolver.|  
  
- La segunda parte de la `String` es el nombre completo del elemento, a partir de la raíz del espacio de nombres. El nombre del elemento, sus tipos envolventes y el espacio de nombres se separan por puntos. Si el nombre del propio elemento contiene puntos, se reemplazan por el signo de número (#). Se supone que ningún elemento tiene un signo de número directamente en su nombre. Por ejemplo, el nombre completo del constructor `String` sería `System.String.#ctor`.  
  
- Para propiedades y métodos, si hay argumentos para el método, sigue la lista de argumentos entre paréntesis. Si no hay ningún argumento, tampoco habrá paréntesis. Los argumentos están separados por comas. La codificación de cada argumento sigue directamente cómo se codifica en una firma .NET Framework.  
  
## <a name="example"></a>Ejemplo  
 En el código siguiente se muestra cómo se generan las cadenas de identificador de una clase y sus miembros.  
  
 [!code-vb[VbVbcnXmlDocComments#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#10)]  
  
## <a name="see-also"></a>Vea también

- [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)
- [Crear documentación XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
