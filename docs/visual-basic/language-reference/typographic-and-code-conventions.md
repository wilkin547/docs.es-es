---
title: Convenciones tipográficas y de código (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- best practices [Visual Basic], coding conventions
- conventions [Visual Basic], Visual Basic coding
- typographic conventions [Visual Basic]
- document conventions [Visual Basic]
- conventions [Visual Basic], documentation
- Visual Basic code, conventions
ms.assetid: 1916cd81-ea9d-4faa-81f7-4a0d864b60f4
ms.openlocfilehash: eb7a33ef21bf6beda730dffa8eb7ff9cabe599fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="typographic-and-code-conventions-visual-basic"></a>Convenciones tipográficas y de código (Visual Basic)
Documentación de Visual Basic utiliza la siguiente tipográfico y convenciones de código.  
  
## <a name="typographic-conventions"></a>Convenciones tipográficas  
  
|Ejemplo|Descripción|  
|-------------|-----------------|  
|`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`|Palabras clave específicas del idioma y los miembros de tiempo de ejecución tienen letras mayúsculas iniciales y se da formato como se muestra en este ejemplo.|  
|**SmallProject**, **ButtonCollection**|Palabras y frases que se le solicita que escriba se da formato como se muestra en este ejemplo.|  
|[Module (instrucción)](../../visual-basic/language-reference/statements/module-statement.md)|Como se muestra en este ejemplo, se da formato a vínculos que puede hacer clic para ir a otra página de ayuda.|  
|*objeto*, *variableName*, `argumentList`|Tal como se muestra en este ejemplo, se da formato a los marcadores de posición para obtener información que proporcione.|  
|[Shadows], [ *expressionList* ]|En la sintaxis, los elementos opcionales aparecen entre corchetes.|  
|{ `Public` &#124; `Friend` &#124; `Private` }|En la sintaxis, cuando debe tomar una decisión entre dos o más elementos de los elementos están entre llaves y separados por barras verticales.<br /><br /> Debe seleccionar uno y solo uno de los elementos.|  
|[ `Protected` &#124; `Friend` ]|En la sintaxis, si tiene la opción de seleccionar entre dos o más elementos de los elementos son entre corchetes y separados por barras verticales.<br /><br /> Puede seleccionar cualquier combinación de los elementos, o no hay ningún elemento.|  
|[{ `ByVal` &#124; `ByRef` }]|En la sintaxis, cuando puede seleccionar no más de un elemento, pero también puede omitir los elementos por completo, los elementos se incluyen entre corchetes entre llaves y separados por barras verticales.|  
|*memberName*1, *memberName*2, *memberName*3|Varias instancias del mismo marcador de posición se distinguen por los subíndices, tal como se muestra en el ejemplo.|  
|*Nombredemiembro1*<br /><br /> ...<br /><br /> *memberNameN*|En la sintaxis de puntos suspensivos (...) se utiliza para indicar un número indefinido de elementos del tipo inmediatamente delante de los puntos suspensivos.<br /><br /> En el código, puntos suspensivos significan que el código que se omite por razones de claridad.|  
|ESC, ESCRIBA|Los nombres de clave y las secuencias de claves en el teclado aparecen en todas las letras mayúsculas.|  
|ALT + F1|Cuando aparezca la signos más (+) entre los nombres de clave, debe mantener presionada una tecla mientras presiona la otra. Por ejemplo, ALT + F1 significa mantener presionada la tecla ALT mientras presiona la tecla F1.|  
  
## <a name="code-conventions"></a>Convenciones de código  
  
|Ejemplo|Descripción|  
|-------------|-----------------|  
|`sampleString = "Hello, world!"`|Ejemplos de código aparecen en una fuente de punto fijo y se da formato como se muestra en este ejemplo.|  
|La instrucción anterior establece el valor de `sampleString` a "Hello, world!"|Elementos de código en texto explicativo aparecen en una fuente de tamaño fijo, como se muestra en este ejemplo.|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|Comentarios de código se introducen mediante un apóstrofo (') o la palabra clave REM.|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|Un espacio seguido por un carácter de subrayado (_) al final de una línea indica que la instrucción continúa en la línea siguiente.|  
  
## <a name="see-also"></a>Vea también  
 [Referencia del lenguaje Visual Basic](../../visual-basic/language-reference/index.md)  
 [Palabras clave](../../visual-basic/language-reference/keywords/index.md)  
 [Miembros de la biblioteca en tiempo de ejecución de Visual Basic](../../visual-basic/language-reference/runtime-library-members.md)  
 [Convenciones de nomenclatura de Visual Basic](../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [Interrumpir y combinar instrucciones en código](../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 [Comentarios en código](../../visual-basic/programming-guide/program-structure/comments-in-code.md)
