---
title: Estructuras de decisión (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
ms.openlocfilehash: 20b60fb425278dacb56ee5f888967554a1f76aeb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825383"
---
# <a name="decision-structures-visual-basic"></a>Estructuras de decisión (Visual Basic)
Visual Basic le permite probar condiciones y realizar diferentes operaciones en función de los resultados de la prueba. Se puede comprobar una condición es true o false para distintos valores de una expresión, o varias excepciones que se genera cuando se ejecuta una serie de instrucciones.  
  
 La siguiente ilustración muestra una estructura de decisión que comprueba una condición es true y realiza acciones diferentes dependiendo de si es true o false.  
  
 ![Diagrama de flujo de If... Entonces... Otra construcción](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")  
Emprender acciones diferentes cuando una condición es true y cuando es false  
  
## <a name="ifthenelse-construction"></a>If... Entonces... Construcción else  
 `If...Then...Else` construcciones le permiten probar uno o más condiciones y ejecutar una o varias instrucciones según cada condición. Puede probar condiciones y realizar acciones de las maneras siguientes:  
  
-   Ejecutar una o varias instrucciones si una condición es `True`  
  
-   Ejecutar una o varias instrucciones si una condición es `False`  
  
-   Ejecutar algunas instrucciones si una condición es `True` y otros usuarios si es `False`  
  
-   Probar una condición adicional si es un requisito previo `False`  
  
 La estructura de control que ofrece todas estas posibilidades es la [si... Entonces... Else (instrucción)](../../../../visual-basic/language-reference/statements/if-then-else-statement.md). Puede usar una versión de línea, si tiene una prueba y una instrucción para ejecutar. Si tiene un conjunto de condiciones y acciones más complejo, puede usar la versión de varias líneas.  
  
## <a name="selectcase-construction"></a>Seleccione... Construcción de casos  
 El `Select...Case` construcción que le permite evaluar una expresión una vez y ejecutar distintos conjuntos de instrucciones basadas en diferentes valores posibles. Para obtener más información, consulte [seleccione... Instrucción de caso](../../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="trycatchfinally-construction"></a>Try... Catch... Por último, construcción  
 `Try...Catch...Finally` permiten ejecutar un conjunto de instrucciones en un entorno que conserva el control si cualquiera de las instrucciones provoca una excepción. Puede realizar acciones diferentes para diferentes excepciones. También puede especificar un bloque de código que se ejecuta antes de salir de la totalidad `Try...Catch...Finally` construcción, independientemente de lo que ocurre. Para obtener más información, vea [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally [Instrucción, Visual Basic]).  
  
> [!NOTE]
>  Para muchas de las estructuras de control, al hacer clic en una palabra clave, se resaltan todas las palabras clave en la estructura. Por ejemplo, al hacer clic en `If` en un `If...Then...Else` construcción, todas las instancias de `If`, `Then`, `ElseIf`, `Else`, y `End If` se resaltan en la construcción. Para mover a la palabra clave resaltada siguiente o anterior, presione CTRL + MAYÚS + flecha abajo o CTRL + MAYÚS + flecha arriba.  
  
## <a name="see-also"></a>Vea también

- [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Estructuras de bucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Estructuras de control adicionales](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [Estructuras de control anidadas](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [If (operador)](../../../../visual-basic/language-reference/operators/if-operator.md)
