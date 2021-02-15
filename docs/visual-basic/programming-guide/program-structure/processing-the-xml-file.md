---
description: Más información acerca de cómo procesar el archivo XML (Visual Basic)
title: Procesamiento del archivo XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments [Visual Basic], parsing [Visual Basic]
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
ms.openlocfilehash: 2314e7dafbd747f9a19b73d06d71c73631e53861
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468400"
---
# <a name="processing-the-xml-file-visual-basic"></a>Procesar el archivo XML (Visual Basic)

El compilador genera una cadena de identificador para cada construcción del código que se etiqueta para generar documentación. (Para obtener información sobre cómo etiquetar el código, vea [etiquetas de comentario XML](../../language-reference/xmldoc/index.md)). La cadena de identificador identifica la construcción de forma única. Los programas que procesan el archivo XML pueden usar la cadena de identificador para identificar el elemento de metadatos/reflexión de .NET Framework correspondiente.  
  
 El archivo XML no es una representación jerárquica del código; es una lista plana con un identificador generado para cada elemento.  
  
 El compilador cumple las siguientes reglas cuando genera las cadenas de identificador:  
  
- No se coloca espacio en blanco en la cadena.  
  
- La primera parte de la cadena ID identifica el tipo de miembro identificado, mediante un carácter único seguido de dos puntos. Se utilizan los siguientes tipos de miembro.  
  
|Carácter|Descripción|  
|---|---|  
|N|namespace<br /><br /> No puede agregar comentarios de documentación a un espacio de nombres, pero puede hacer referencias CREF a ellos, si se admiten.|  
|T|tipo: `Class` , `Module` , `Interface` , `Structure` , `Enum` , `Delegate`|  
|F|campo `Dim`|  
|P|propiedad: `Property` (incluidas las propiedades predeterminadas)|  
|M|método: `Sub` , `Function` , `Declare` , `Operator`|  
|E|ceso `Event`|  
|!|cadena de error<br /><br /> El resto de la cadena proporciona información sobre el error. El compilador Visual Basic genera información de error para los vínculos que no se pueden resolver.|  
  
- La segunda parte de `String` es el nombre completo del elemento, a partir de la raíz del espacio de nombres. El nombre del elemento, sus tipos envolventes y el espacio de nombres se separan por puntos. Si el nombre del propio elemento contiene puntos, se reemplazan por el signo de número (#). Se supone que ningún elemento tiene un signo de número directamente en su nombre. Por ejemplo, el nombre completo del `String` constructor sería `System.String.#ctor` .  
  
- Para propiedades y métodos, si hay argumentos para el método, sigue la lista de argumentos entre paréntesis. Si no hay ningún argumento, tampoco habrá paréntesis. Los argumentos están separados por comas. La codificación de cada argumento sigue directamente cómo se codifica en una firma .NET Framework.  
  
## <a name="example"></a>Ejemplo  

 En el código siguiente se muestra cómo se generan las cadenas de identificador de una clase y sus miembros.  
  
 [!code-vb[VbVbcnXmlDocComments#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#10)]  
  
## <a name="see-also"></a>Consulte también

- [-doc](../../reference/command-line-compiler/doc.md)
- [Procedimiento para crear documentación XML](how-to-create-xml-documentation.md)
