---
title: Estructuras de decisión
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
ms.openlocfilehash: d0d4039ff2edc61ee8b4b732c6adcb6e420d73ea
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353976"
---
# <a name="decision-structures-visual-basic"></a>Estructuras de decisión (Visual Basic)
Visual Basic le permite probar condiciones y realizar diferentes operaciones en función de los resultados de esa prueba. Puede comprobar si una condición es true o false, para varios valores de una expresión o para diversas excepciones generadas al ejecutar una serie de instrucciones.  
  
 En la ilustración siguiente se muestra una estructura de decisión que comprueba si una condición es verdadera y realiza diferentes acciones en función de si es true o false.  
  
 ![Un diagrama de flujo de If...Then...Else construcción.](./media/decision-structures/if-then-else-construction.gif)  
  
## <a name="ifthenelse-construction"></a>If...Then...Else construcción  
 `If...Then...Else` construcciones permiten probar una o varias condiciones y ejecutar una o varias instrucciones en función de cada condición. Puede probar las condiciones y tomar medidas de las siguientes maneras:  
  
- Ejecutar una o varias instrucciones si se `True` una condición  
  
- Ejecutar una o varias instrucciones si se `False` una condición  
  
- Ejecutar algunas instrucciones si se `True` una condición y otras si se `False`  
  
- Probar una condición adicional si se `False` una condición anterior  
  
 La estructura de control que ofrece todas estas posibilidades es el [... Después... Else (instrucción](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)). Puede usar una versión de una sola línea si solo tiene una prueba y una instrucción para ejecutarse. Si tiene un conjunto más complejo de condiciones y acciones, puede usar la versión de varias líneas.  
  
## <a name="selectcase-construction"></a>Select...Case construcción  
 La construcción `Select...Case` permite evaluar una expresión una vez y ejecutar diferentes conjuntos de instrucciones en función de valores posibles diferentes. Para obtener más información, vea [Select... Instrucción Case](../../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="trycatchfinally-construction"></a>Try...Catch...Finally, construcción  
 `Try...Catch...Finally` construcciones permiten ejecutar un conjunto de instrucciones en un entorno que conserva el control si una de las instrucciones produce una excepción. Puede realizar diferentes acciones para diferentes excepciones. Opcionalmente, puede especificar un bloque de código que se ejecuta antes de salir de toda la construcción `Try...Catch...Finally`, independientemente de lo que suceda. Para obtener más información, vea [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally [Instrucción, Visual Basic]).  
  
> [!NOTE]
> En el caso de muchas estructuras de control, al hacer clic en una palabra clave, se resaltan todas las palabras clave de la estructura. Por ejemplo, al hacer clic en `If` en una construcción de `If...Then...Else`, se resaltan todas las instancias de `If`, `Then`, `ElseIf`, `Else`y `End If` de la construcción. Para desplazarse a la palabra clave resaltada siguiente o anterior, presione CTRL + MAYÚS + flecha abajo o CTRL + MAYÚS + flecha arriba.  
  
## <a name="see-also"></a>Vea también

- [Flujo de control](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Estructuras de bucle](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Estructuras de control adicionales](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [Estructuras de control anidadas](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [If (operador)](../../../../visual-basic/language-reference/operators/if-operator.md)
