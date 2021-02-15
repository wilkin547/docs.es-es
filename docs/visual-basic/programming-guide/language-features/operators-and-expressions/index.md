---
description: 'Más información sobre: operadores y expresiones en Visual Basic'
title: Operadores y expresiones
ms.date: 07/20/2015
helpviewer_keywords:
- operators [Visual Basic], operands
- operators [Visual Basic]
- operands [Visual Basic], definition
- Visual Basic code, operators
- Visual Basic code, expressions
- operands
- expressions [Visual Basic]
ms.assetid: b86f3131-94ee-448f-96cd-79611e028b26
ms.openlocfilehash: 526051e16da29cd139abf587e1393ad331fdcdaa
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471401"
---
# <a name="operators-and-expressions-in-visual-basic"></a>Operadores y expresiones en Visual Basic

Un *operador* es un elemento de código que realiza una operación en uno o más elementos de código que contienen valores. Los elementos de valor incluyen variables, constantes, literales, propiedades, devoluciones de procedimientos `Function` y `Operator` y expresiones.  
  
 Una *expresión* es una serie de elementos de valor combinados con operadores, lo que produce un nuevo valor. Los operadores actúan en los elementos de valor mediante cálculos, comparaciones y otras operaciones.  
  
## <a name="types-of-operators"></a>Tipos de operadores  

 Visual Basic proporciona los siguientes tipos de operadores:  
  
- Los [operadores aritméticos](arithmetic-operators.md) realizan cálculos familiares en valores numéricos, incluido el desplazamiento de los patrones de bits.  
  
- Los [operadores de comparación](comparison-operators.md) comparan dos expresiones y devuelven un valor `Boolean` que representa el resultado de la comparación.  
  
- Los [operadores de concatenación](concatenation-operators.md) unen varias cadenas en una sola cadena.  
  
- Los [operadores lógicos y bit a bit de Visual Basic](logical-and-bitwise-operators.md) combinan valores `Boolean` o numéricos y devuelven un resultado del mismo tipo de datos que los valores.  
  
 Los elementos de valor que se combinan con un operador se denominan *operandos* de ese operador. Los operadores combinados con elementos de valor forman expresiones, salvo el operador de asignación, que forma una *instrucción*. Para más información, vea [Statements](../statements.md) (Instrucciones).  
  
## <a name="evaluation-of-expressions"></a>Evaluación de expresiones  

 El resultado final de una expresión representa un valor, que suele ser de un tipo de datos conocido, como un tipo `Boolean`, `String` o numérico.  
  
 A continuación se muestran ejemplos de expresiones.  
  
 `5 + 4`  
  
 `' The preceding expression evaluates to 9.`  
  
 `15 * System.Math.Sqrt(9) + x`  
  
 `' The preceding expression evaluates to 45 plus the value of x.`  
  
 `"Concat" & "ena" & "tion"`  
  
 `' The preceding expression evaluates to "Concatenation".`  
  
 `763 < 23`  
  
 `' The preceding expression evaluates to False.`  
  
 Varios operadores pueden realizar acciones en una sola expresión o instrucción, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrOperators#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#56)]  
  
 En el ejemplo anterior, Visual Basic realiza las operaciones en la expresión del lado derecho del operador de asignación ( `=` ) y, a continuación, asigna el valor resultante a la variable `x` de la izquierda. No hay ningún límite práctico al número de operadores que se pueden combinar en una expresión, pero es necesario conocer la [prioridad de operadores en Visual Basic](../../../language-reference/operators/operator-precedence.md) para asegurarse de que se obtienen los resultados esperados.  

## <a name="see-also"></a>Consulte también

- [Operadores](../../../language-reference/operators/index.md)
- [Combinación eficaz de operadores](efficient-combination-of-operators.md)
- [Instrucciones](../../../language-reference/statements/index.md)
