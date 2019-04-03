---
title: / (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./
helpviewer_keywords:
- division operator [Visual Basic], floating point
- floating-point numbers [Visual Basic], division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- operators [Visual Basic], division
- division operator [Visual Basic], syntax
- / operator [Visual Basic]
- math operators [Visual Basic]
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
ms.openlocfilehash: af2316f92e2904eee1e8c046b34b8147e40cb513
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825071"
---
# <a name="-operator-visual-basic"></a>/ (Operador, Visual Basic)
Divide dos números y devuelve un resultado de coma flotante.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
expression1 / expression2  
```  
  
## <a name="parts"></a>Elementos  
 `expression1`  
 Obligatorio. Cualquier expresión numérica.  
  
 `expression2`  
 Obligatorio. Cualquier expresión numérica.  
  
## <a name="supported-types"></a>Tipos admitidos  
 Todos los tipos numéricos, incluidos los tipos sin signo y de punto flotante y `Decimal`.  
  
## <a name="result"></a>Resultado  
 El resultado es el cociente completo de `expression1` dividido por `expression2`, incluido cualquier resto.  
  
 El [\ (operador) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) devuelve el cociente entero, que omite el resto.  
  
## <a name="remarks"></a>Comentarios  
 El tipo de datos del resultado depende de los tipos de los operandos. En la tabla siguiente se muestra cómo se determina el tipo de datos del resultado.  
  
|Tipos de datos de operando|Tipo de resultado de datos|  
|------------------------|----------------------|  
|Ambas expresiones son tipos de datos enteros ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [bytes](../../../visual-basic/language-reference/data-types/byte-data-type.md), [corto](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [entero](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [largo](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|`Double`|  
|Una expresión es un [único](../../../visual-basic/language-reference/data-types/single-data-type.md) tipo de datos y el otro no es un [dobles](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Single`|  
|Una expresión es un [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) tipo de datos y el otro no es un [único](../../../visual-basic/language-reference/data-types/single-data-type.md) o un [dobles](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Decimal`|  
|Cualquier expresión es un [doble](../../../visual-basic/language-reference/data-types/double-data-type.md) tipo de datos|`Double`|  
  
 Antes de realiza la división, las expresiones numéricas de enteras se amplían a `Double`. Si asigna el resultado a un tipo de datos entero, Visual Basic intenta convertir el resultado de `Double` a ese tipo. Esto puede producir una excepción si el resultado no se ajusta a ese tipo. En concreto, vea "Intentado de división por cero" en esta página de ayuda.  
  
 Si `expression1` o `expression2` se evalúa como [nada](../../../visual-basic/language-reference/nothing.md), se trata como cero.  
  
## <a name="attempted-division-by-zero"></a>División por cero intentada  
 Si `expression2` se evalúa como cero, el `/` operador tiene un comportamiento diferente para los tipos de datos diferentes de operando. La siguiente tabla muestra los comportamientos posibles.  
  
|Tipos de datos de operando|Comportamiento si `expression2` es cero|  
|------------------------|---------------------------------------|  
|Punto flotante (`Single` o `Double`)|Devuelve infinito (<xref:System.Double.PositiveInfinity> o <xref:System.Double.NegativeInfinity>), o <xref:System.Double.NaN> (no un número) si `expression1` también es cero|  
|`Decimal`|Se produce <xref:System.DivideByZeroException>|  
|Entero (con o sin signo)|Ha intentado la conversión a tipo entero produce <xref:System.OverflowException> porque no pueden aceptar tipos enteros <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, o <xref:System.Double.NaN>|  
  
> [!NOTE]
>  El `/` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `/` operador para realizar la división de punto flotante. El resultado es el cociente de los dos operandos.  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 Las expresiones en el ejemplo anterior devuelven valores de 2,5 y 3,333333. Tenga en cuenta que el resultado siempre es de punto flotante (`Double`), aunque ambos operandos son constantes de tipo entero.  
  
## <a name="see-also"></a>Vea también

- [/ = (Operador) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [\ (Operador) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [Tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)
- [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
