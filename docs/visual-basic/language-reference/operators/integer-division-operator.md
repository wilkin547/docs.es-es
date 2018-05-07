---
title: '\ (Operador, Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
ms.openlocfilehash: ef3946e871e1dc248b54932e16f6cae6026da08e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-visual-basic"></a>\ (Operador, Visual Basic)
Divide dos números y devuelve un resultado entero.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
expression1 \ expression2  
```  
  
## <a name="parts"></a>Elementos  
 `expression1`  
 Requerido. Cualquier expresión numérica.  
  
 `expression2`  
 Requerido. Cualquier expresión numérica.  
  
## <a name="supported-types"></a>Tipos admitidos  
 Todos los tipos numéricos, incluidos los tipos sin signo y de punto flotante y `Decimal`.  
  
## <a name="result"></a>Resultado  
 El resultado es el cociente entero de `expression1` dividido por `expression2`, que descarta cualquier resto y conserva sólo la parte entera. Esto se conoce como *truncamiento*.  
  
 El tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`. Vea las tablas "Aritmética de enteros" en [tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
 El [/ (operador) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) devuelve el cociente completo, que conserva el resto en la parte fraccionaria.  
  
## <a name="remarks"></a>Comentarios  
 Antes de realizar la división, Visual Basic intenta convertir cualquier expresión numérica de punto flotante a `Long`. Si `Option Strict` es `On`, se produce un error del compilador. Si `Option Strict` es `Off`, <xref:System.OverflowException> es posible si el valor está fuera del intervalo de la [tipo de datos Long](../../../visual-basic/language-reference/data-types/long-data-type.md). La conversión a `Long` también está sujeto a *el redondeo bancario*. Para obtener más información, vea "Partes fraccionarias" en [funciones de conversión de tipo](../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Si `expression1` o `expression2` se evalúa como [nada](../../../visual-basic/language-reference/nothing.md), se trata como cero.  
  
## <a name="attempted-division-by-zero"></a>División por cero intentada  
 Si `expression2` se evalúa como cero, el `\` operador produce una <xref:System.DivideByZeroException> excepción. Esto es cierto para todos los tipos de datos numéricos de los operandos.  
  
> [!NOTE]
>  El `\` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido. Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `\` operador que se va a realizar la división de enteros. El resultado es un entero que representa el cociente entero de los dos operandos, rechazando el resto.  
  
 [!code-vb[VbVbalrOperators#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/integer-division-operator_1.vb)]  
  
 Las expresiones en el ejemplo anterior devuelven valores de 2, 3, 33 y -22 respectivamente.  
  
## <a name="see-also"></a>Vea también  
 [\\= (Operador)](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [/ (Operador, Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)  
 [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
