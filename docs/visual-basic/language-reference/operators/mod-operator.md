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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5120823f4e001fc3aff71f267176311e2465597a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604855"
---
# <a name="mod-operator-visual-basic"></a>Mod (operador) (Visual Basic)
Divide dos números y devuelve solamente el resto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
number1 Mod number2  
```  
  
## <a name="parts"></a>Elementos  
 `number1`  
 Requerido. Cualquier expresión numérica.  
  
 `number2`  
 Requerido. Cualquier expresión numérica.  
  
## <a name="supported-types"></a>Tipos admitidos  
 todos los tipos numéricos. Esto incluye los tipos sin signo y de punto flotante y `Decimal`.  
  
## <a name="result"></a>Resultado

El resultado es el resto después de `number1` se divide por `number2`. Por ejemplo, la expresión `14 Mod 4` se evalúa como 2.  

> [!NOTE]
> Hay una diferencia entre *resto* y *módulo* en matemáticas, con resultados diferentes para los números negativos. El `Mod` operador en Visual Basic, .NET Framework `op_Modulus` operador y el subyacente [rem]<xref:System.Reflection.Emit.OpCodes.Rem> instrucción IL realizan una operación de resto.

El resultado de un `Mod` operación conserva el signo del dividendo, `number1`, por lo que puede ser positivo o negativo. El resultado siempre está en el intervalo (-`number2`, `number2`), exclusivo. Por ejemplo:

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
 Si el valor `number1` o `number2` es un valor de punto flotante, se devuelve el resto de la división de punto flotante. El tipo de datos del resultado es el tipo de datos más pequeño que puede contener todos los valores posibles que son el resultado de la división con los tipos de datos de `number1` y `number2`.  
  
 Si `number1` o `number2` se evalúa como [nada](../../../visual-basic/language-reference/nothing.md), se trata como cero.  
  
 Los operadores relacionados son los siguientes:  
  
-   El [\ (operador) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) devuelve el cociente entero de una división. Por ejemplo, la expresión `14 \ 4` es 3.  
  
-   El [/ (operador) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) devuelve el cociente completo, incluido el resto, como un número de punto flotante. Por ejemplo, la expresión `14 / 4` se evalúa como 3.5.  
  
## <a name="attempted-division-by-zero"></a>División por cero intentada  
 Si `number2` se evalúa como cero, el comportamiento de la `Mod` operador depende del tipo de datos de los operandos. Una división de enteros produce una <xref:System.DivideByZeroException> excepción. Devuelve una división de coma flotante <xref:System.Double.NaN>.  
  
## <a name="equivalent-formula"></a>Fórmula equivalente  
 La expresión `a Mod b` es equivalente a cualquiera de las fórmulas siguientes:  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## <a name="floating-point-imprecision"></a>Punto flotante imprecisión  
 Cuando trabaje con números de punto flotante, recuerde que no siempre tienen una representación decimal precisa en memoria. Esto puede provocar resultados inesperados en ciertas operaciones, como comparación de valores y la `Mod` operador. Para obtener más información, consulte [solución de problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="overloading"></a>Sobrecarga  
 El `Mod` puede ser *sobrecargados*, lo que significa que una clase o estructura puede volver a definir su comportamiento. Si el código se aplica `Mod` a una instancia de una clase o estructura que incluye una sobrecarga de este tipo, asegúrese de conocer su comportamiento redefinido. Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Mod` operador dividir dos números y devolver únicamente el resto. Si uno de ellos es un número de punto flotante, el resultado es un número de punto flotante que representa el resto.  
  
 [!code-vb[VbVbalrOperators#31](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra la posible imprecisión de operandos de punto flotante. En la primera instrucción, los operandos son `Double`, y 0.2 es una fracción binaria infinitamente repetitiva con un valor almacenado de 0,20000000000000001. En la segunda instrucción, el literal de tipo carácter `D` obliga a que ambos operandos para `Decimal`, y 0.2 tiene una representación precisa.  
  
 [!code-vb[VbVbalrOperators#32](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/mod-operator_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Solución de problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [\ (Operador) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
