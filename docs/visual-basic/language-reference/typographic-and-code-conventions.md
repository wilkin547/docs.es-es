---
description: 'Más información acerca de: Convenciones tipográficas y de código (Visual Basic)'
title: Convenciones tipográficas y de código
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
ms.openlocfilehash: 44e8445bb56f4f0c8b2f4eedddecda46ffcebb68
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768810"
---
# <a name="typographic-and-code-conventions-visual-basic"></a>Convenciones tipográficas y de código (Visual Basic)

En Visual Basic documentación se utilizan las siguientes convenciones tipográficas y de código.  
  
## <a name="typographic-conventions"></a>Convenciones tipográficas  
  
|Ejemplo|Descripción|  
|-------------|-----------------|  
|`Sub`, `If`, `ChDir`, `Print`, `True`, `Debug`|Las palabras clave específicas del lenguaje y los miembros en tiempo de ejecución tienen letras mayúsculas iniciales y tienen el formato que se muestra en este ejemplo.|  
|**SmallProject**, **ButtonCollection**|Las palabras y frases que se le indiquen que escriba tienen el formato que se muestra en este ejemplo.|  
|[Module (Instrucción)](statements/module-statement.md)|Los vínculos en los que puede hacer clic para ir a otra página de ayuda tienen el formato que se muestra en este ejemplo.|  
|*Object*, *variablename*, `argumentList`|Los marcadores de posición para la información proporcionada se formatean como se muestra en este ejemplo.|  
|[Shadows], [ *expressionList* ]|En la sintaxis, los elementos opcionales se incluyen entre corchetes.|  
|{ `Public` &#124; `Friend` &#124; `Private` }|En la sintaxis, cuando debe elegir entre dos o más elementos, los elementos se incluyen entre llaves y se separan mediante barras verticales.<br /><br /> Debe seleccionar uno y solo uno de los elementos.|  
|[ `Protected` &#124; `Friend` ]|En la sintaxis, cuando se tiene la opción de seleccionar entre dos o más elementos, los elementos se incluyen entre corchetes y se separan mediante barras verticales.<br /><br /> Puede seleccionar cualquier combinación de elementos o ningún elemento.|  
|[{ `ByVal` &#124; `ByRef` }]|En la sintaxis, cuando se puede seleccionar no más de un elemento, pero también se pueden omitir los elementos por completo, los elementos se incluyen entre corchetes y se separan mediante barras verticales.|  
|*memberName* 1, *memberName* 2, *memberName* 3|Varias instancias del mismo marcador de posición se diferencian en los subíndices, tal y como se muestra en el ejemplo.|  
|*Nombredemiembro1*<br /><br /> ...<br /><br /> *memberNameN*|En la sintaxis, se usa un botón de puntos suspensivos (...) para indicar un número indefinido de elementos del tipo inmediatamente delante de los puntos suspensivos.<br /><br /> En el código, los puntos suspensivos indican que el código se ha omitido por razones de claridad.|  
|ESC, ENTRAR|Los nombres de clave y las secuencias de teclas del teclado aparecen en todas las letras mayúsculas.|  
|ALT+F1|Cuando aparecen signos más (+) entre los nombres de clave, se debe mantener presionada una tecla mientras se presiona la otra. Por ejemplo, ALT + F1 significa mantener presionada la tecla ALT mientras se presiona la tecla F1.|  
  
## <a name="code-conventions"></a>Convenciones de código  
  
|Ejemplo|Descripción|  
|-------------|-----------------|  
|`sampleString = "Hello, world!"`|Los ejemplos de código aparecen en una fuente de punto fijo y tienen el formato que se muestra en este ejemplo.|  
|La instrucción anterior establece el valor de `sampleString` en "Hello, World!"|Los elementos de código del texto explicativo aparecen en una fuente de punto fijo, tal como se muestra en este ejemplo.|  
|`' This is a comment.`<br /><br /> `REM This is also a comment.`|Los comentarios de código se introducen mediante un apóstrofo (') o la palabra clave REM.|  
|`sampleVar = "This is an " _`<br /><br /> `& "example" _`<br /><br /> `& " of how to continue code."`|Un espacio seguido de un carácter de subrayado (_) al final de una línea indica que la instrucción continúa en la línea siguiente.|  
  
## <a name="see-also"></a>Vea también

- [Referencia del lenguaje Visual Basic](index.md)
- [Palabras clave](keywords/index.md)
- [Miembros de la biblioteca en tiempo de ejecución de Visual Basic](runtime-library-members.md)
- [Convenciones de nomenclatura de Visual Basic](../programming-guide/program-structure/naming-conventions.md)
- [Procedimiento Interrupción y combinación de instrucciones en código](../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [Comentarios en código](../programming-guide/program-structure/comments-in-code.md)
