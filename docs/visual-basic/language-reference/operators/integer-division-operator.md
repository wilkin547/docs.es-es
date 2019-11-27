---
title: '\ (Operador)'
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
ms.openlocfilehash: 2b4cca99ed54195162530bb8eb950bd251bfbff9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347120"
---
# <a name="-operator-visual-basic"></a>\ (Operador, Visual Basic)
Divide dos números y devuelve un resultado entero.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
expression1 \ expression2  
```  
  
## <a name="parts"></a>Elementos  
 `expression1`  
 Obligatorio. Cualquier expresión numérica.  
  
 `expression2`  
 Obligatorio. Cualquier expresión numérica.  
  
## <a name="supported-types"></a>Tipos admitidos  
 Todos los tipos numéricos, incluidos los tipos de punto flotante y sin signo y `Decimal`.  
  
## <a name="result"></a>Resultado  
 El resultado es el cociente entero de `expression1` dividida por `expression2`, que descarta cualquier resto y solo conserva la parte entera. Esto se conoce como *truncamiento*.  
  
 El tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`. Vea las tablas "aritmética de enteros" en [tipos de datos de resultados de operadores](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
 El [operador/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) devuelve el cociente completo, que conserva el resto de la parte fraccionaria.  
  
## <a name="remarks"></a>Comentarios  
 Antes de realizar la división, Visual Basic intenta convertir cualquier expresión numérica de punto flotante en `Long`. Si `Option Strict` se `On`, se produce un error del compilador. Si `Option Strict` se `Off`, es posible un <xref:System.OverflowException> si el valor está fuera del intervalo del [tipo de datos Long](../../../visual-basic/language-reference/data-types/long-data-type.md). La conversión a `Long` también está sujeta a *redondeo bancario*. Para obtener más información, vea "partes fraccionarias" en [funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Si `expression1` o `expression2` se evalúa como [Nothing](../../../visual-basic/language-reference/nothing.md), se trata como cero.  
  
## <a name="attempted-division-by-zero"></a>División intentada por cero  
 Si `expression2` se evalúa como cero, el operador de `\` produce una excepción <xref:System.DivideByZeroException>. Esto es así para todos los tipos de datos numéricos de los operandos.  
  
> [!NOTE]
> El operador de `\` se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el operador `\` para realizar la división de enteros. El resultado es un entero que representa el cociente entero de los dos operandos, con el resto descartado.  
  
 [!code-vb[VbVbalrOperators#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#18)]  
  
 Las expresiones del ejemplo anterior devuelven los valores 2, 3, 33 y-22, respectivamente.  
  
## <a name="see-also"></a>Vea también

- [\\= (operador)](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [Operador/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
