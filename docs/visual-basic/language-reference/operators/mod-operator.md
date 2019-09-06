---
title: Mod (Operador, Visual Basic)
ms.date: 04/24/2018
f1_keywords:
- vb.Mod
helpviewer_keywords:
- remainder (Mod operator)
- division operator [Visual Basic], Mod operator
- modulus operator [Visual Basic], Visual Basic
- Mod operator [Visual Basic]
- operators [Visual Basic], division
- arithmetic operators [Visual Basic], Mod
- math operators [Visual Basic]
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
ms.openlocfilehash: dc1e866836bb7420ffe17210b5be7a5e1d4048d0
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2019
ms.locfileid: "70374487"
---
# <a name="mod-operator-visual-basic"></a>Operador mod (Visual Basic)

Divide dos números y devuelve solo el resto.

## <a name="syntax"></a>Sintaxis

```vb
result = number1 Mod number2
```

## <a name="parts"></a>Elementos

`result` \
Necesario. Cualquier variable o propiedad numérica.

`number1` \
Necesario. Cualquier expresión numérica.

`number2` \
Necesario. Cualquier expresión numérica.

## <a name="supported-types"></a>Tipos admitidos

todos los tipos numéricos. Esto incluye los tipos de punto flotante y sin signo y `Decimal`.

## <a name="result"></a>Resultado

El resultado es el resto después `number1` de dividir por `number2`. Por ejemplo, la expresión `14 Mod 4` se evalúa como 2.

> [!NOTE]
> Hay una diferencia entre el *resto* y el *módulo* en las matemáticas, con resultados diferentes para los números negativos. El `Mod` operador de Visual Basic, el operador `op_Modulus` de .NET Framework y la instrucción máquina [de Il subyacente](<xref:System.Reflection.Emit.OpCodes.Rem>) realizan una operación de resto.

El resultado de una `Mod` operación conserva el signo del dividendo, `number1`, y, por tanto, puede ser positivo o negativo. El resultado siempre está en el intervalo (-`number2`, `number2`), Exclusive. Por ejemplo:

```vb
Public Module Example
   Public Sub Main()
      Console.WriteLine($" 8 Mod  3 = {8 Mod 3}")
      Console.WriteLine($"-8 Mod  3 = {-8 Mod 3}")
      Console.WriteLine($" 8 Mod -3 = {8 Mod -3}")
      Console.WriteLine($"-8 Mod -3 = {-8 Mod -3}")
   End Sub
End Module
' The example displays the following output:
'       8 Mod  3 = 2
'      -8 Mod  3 = -2
'       8 Mod -3 = 2
'      -8 Mod -3 = -2
```

## <a name="remarks"></a>Comentarios

`number1` Si o `number2` es un valor de punto flotante, se devuelve el resto del punto flotante de la división. El tipo de datos del resultado es el tipo de datos más pequeño que puede contener todos los valores posibles que son el resultado de la división `number1` con `number2`los tipos de datos de y.

Si `number1` o`number2` se evalúa como [Nothing](../../../visual-basic/language-reference/nothing.md), se trata como cero.

Entre los operadores relacionados se incluyen los siguientes:

- El [operador \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) devuelve el cociente entero de una división. Por ejemplo, la expresión `14 \ 4` se evalúa como 3.

- El [operador/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) devuelve el cociente completo, incluido el resto, como un número de punto flotante. Por ejemplo, la expresión `14 / 4` se evalúa como 3,5.

## <a name="attempted-division-by-zero"></a>División intentada por cero

Si `number2` se evalúa como cero, el comportamiento `Mod` del operador depende del tipo de datos de los operandos:
- Una división <xref:System.DivideByZeroException> integral inicia una excepción si `number2` no se puede determinar en tiempo de compilación y genera un error `BC30542 Division by zero occurred while evaluating this expression` en tiempo de compilación `number2` si se evalúa como cero en tiempo de compilación.
- Una división de punto flotante devuelve <xref:System.Double.NaN?displayProperty=nameWithType>.

## <a name="equivalent-formula"></a>Fórmula equivalente

La expresión `a Mod b` es equivalente a cualquiera de las siguientes fórmulas:

`a - (b * (a \ b))`

`a - (b * Fix(a / b))`

## <a name="floating-point-imprecision"></a>Imprecisión de punto flotante

Al trabajar con números de punto flotante, recuerde que no siempre tienen una representación decimal exacta en la memoria. Esto puede dar lugar a resultados inesperados de ciertas operaciones, como la comparación `Mod` de valores y el operador. Para obtener más información, vea [solución de problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).

## <a name="overloading"></a>Sobrecarga

El `Mod` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento. Si el código se `Mod` aplica a una instancia de una clase o estructura que incluya este tipo de sobrecarga, asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se `Mod` usa el operador para dividir dos números y devolver solo el resto. Si cualquier número es un número de punto flotante, el resultado es un número de punto flotante que representa el resto.

[!code-vb[VbVbalrOperators#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#31)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestran los posibles imprecisión de operandos de punto flotante. En la primera instrucción, los operandos son `Double`y 0,2 es una fracción binaria repetida infinitamente con un valor almacenado de 0.20000000000000001. En la segunda instrucción, el carácter `D` de tipo literal fuerza ambos operandos a `Decimal`y 0,2 tiene una representación precisa.

[!code-vb[VbVbalrOperators#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#32)]

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Solución de problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [Operador (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
