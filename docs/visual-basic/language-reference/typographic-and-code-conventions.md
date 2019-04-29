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
ms.openlocfilehash: 3255dff8268cd5500a1244716f37bf30f5b43cfb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698608"
---
# <a name="typographic-and-code-conventions-visual-basic"></a>Convenciones tipográficas y de código (Visual Basic)
Documentación de Visual Basic usa las convenciones de código y siguiente tipográficas.  
  
## <a name="typographic-conventions"></a>Convenciones tipográficas  
  
|Ejemplo|Descripción|  
|-------------|-----------------|  
|`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`|Palabras clave específicas del lenguaje y los miembros de tiempo de ejecución tienen letras mayúsculas iniciales y se da formato como se muestra en este ejemplo.|  
|**SmallProject**, **ButtonCollection**|Las palabras y frases que se indique el tipo se da formato como se muestra en este ejemplo.|  
|[Module (instrucción)](../../visual-basic/language-reference/statements/module-statement.md)|Puede hacer clic para ir a otra página de Ayuda de vínculos se formatean como se muestra en este ejemplo.|  
|*object*, *variableName*, `argumentList`|Marcadores de posición para la información que proporcione se formatean como se muestra en este ejemplo.|  
|[Shadows], [ *expressionList* ]|En la sintaxis, los elementos opcionales aparecen entre corchetes.|  
|{ `Public` &#124; `Friend` &#124; `Private` }|En la sintaxis, cuando hay que elegir entre dos o más elementos, los elementos están entre llaves y separados por barras verticales.<br /><br /> Debe seleccionar uno y solo uno de los elementos.|  
|[ `Protected` &#124; `Friend` ]|En la sintaxis, cuando tenga la opción de seleccionar entre dos o más elementos, los elementos están entre corchetes y separados por barras verticales.<br /><br /> Puede seleccionar cualquier combinación de los elementos, o no hay ningún elemento.|  
|[{ `ByVal` &#124; `ByRef` }]|En la sintaxis, cuando puede seleccionar no más de un elemento, pero también puede omitir los elementos por completo, los elementos están entre corchetes entre llaves y separados por barras verticales.|  
|*memberName*1, *memberName*2, *memberName*3|Varias instancias del mismo marcador de posición se diferencian por los subíndices, como se muestra en el ejemplo.|  
|*memberName1*<br /><br /> ...<br /><br /> *memberNameN*|En la sintaxis de puntos suspensivos (...) se utiliza para indicar un número indefinido de elementos del tipo inmediatamente delante de los puntos suspensivos.<br /><br /> En el código, los puntos suspensivos significan omitido por motivos de claridad del código.|  
|ESC, ESCRIBA|Los nombres de clave y las secuencias de teclas del teclado aparecen en todas las letras en mayúsculas.|  
|ALT+F1|Cuando se muestren signos más (+) entre los nombres de clave, debe mantener presionada una tecla mientras se presiona la otra. Por ejemplo, ALT + F1 significa mantener presionada la tecla ALT mientras se presiona la tecla F1.|  
  
## <a name="code-conventions"></a>Convenciones de código  
  
|Ejemplo|Descripción|  
|-------------|-----------------|  
|`sampleString = "Hello, world!"`|Ejemplos de código aparecen en una fuente de punto fijo y se da formato como se muestra en este ejemplo.|  
|La instrucción anterior establece el valor de `sampleString` a "Hello, world!"|Los elementos de código en el texto explicativo aparecen en una fuente de punto fijo, tal como se muestra en este ejemplo.|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|Comentarios del código se introducen mediante un apóstrofo (') o la palabra clave REM.|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|Un espacio seguido por un carácter de subrayado (_) al final de una línea indica que la instrucción continúa en la línea siguiente.|  
  
## <a name="see-also"></a>Vea también

- [Referencia del lenguaje Visual Basic](../../visual-basic/language-reference/index.md)
- [Palabras clave](../../visual-basic/language-reference/keywords/index.md)
- [Miembros de la biblioteca en tiempo de ejecución de Visual Basic](../../visual-basic/language-reference/runtime-library-members.md)
- [Convenciones de nomenclatura de Visual Basic](../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [Cómo: Interrumpir y combinar instrucciones en código](../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [Comentarios en código](../../visual-basic/programming-guide/program-structure/comments-in-code.md)
