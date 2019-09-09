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
ms.openlocfilehash: d30d871d48bc87e050a072cd01a38065be20616c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933258"
---
# <a name="-operator-visual-basic"></a>/ (Operador, Visual Basic)
Divide dos números y devuelve un resultado de punto flotante.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
expression1 / expression2  
```  
  
## <a name="parts"></a>Elementos  
 `expression1`  
 Necesario. Cualquier expresión numérica.  
  
 `expression2`  
 Necesario. Cualquier expresión numérica.  
  
## <a name="supported-types"></a>Tipos admitidos  
 Todos los tipos numéricos, incluidos los tipos de punto flotante y sin signo `Decimal`y.  
  
## <a name="result"></a>Resultado  
 El resultado es el cociente completo de `expression1` `expression2`dividido entre, incluido cualquier resto.  
  
 El [operador \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) devuelve el cociente entero, que quita el resto.  
  
## <a name="remarks"></a>Comentarios  
 El tipo de datos del resultado depende de los tipos de los operandos. En la tabla siguiente se muestra cómo se determina el tipo de datos del resultado.  
  
|Tipos de datos de operando|Tipo de datos de resultados|  
|------------------------|----------------------|  
|Ambas expresiones son tipos de datos enteros ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [ushort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|`Double`|  
|Una expresión es un tipo de datos [único](../../../visual-basic/language-reference/data-types/single-data-type.md) y la otra no es [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Single`|  
|Una expresión es un tipo de datos [decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) y la otra no es [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) o [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Decimal`|  
|Cualquier expresión es un tipo de datos [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)|`Double`|  
  
 Antes de que se realice la división, cualquier expresión numérica entera se `Double`amplía a. Si asigna el resultado a un tipo de datos entero, Visual Basic intenta convertir el resultado de `Double` a ese tipo. Esto puede producir una excepción si el resultado no cabe en ese tipo. En concreto, vea "se ha intentado la división por cero" en esta página de ayuda.  
  
 Si `expression1` o`expression2` se evalúa como [Nothing](../../../visual-basic/language-reference/nothing.md), se trata como cero.  
  
## <a name="attempted-division-by-zero"></a>División intentada por cero  
 Si `expression2` se evalúa como cero, el `/` operador se comporta de forma diferente para los distintos tipos de datos de operando. En la tabla siguiente se muestran los posibles comportamientos.  
  
|Tipos de datos de operando|Comportamiento si `expression2` es cero|  
|------------------------|---------------------------------------|  
|Punto flotante (`Single` o `Double`)|Devuelve Infinity (<xref:System.Double.PositiveInfinity> o <xref:System.Double.NegativeInfinity>) o <xref:System.Double.NaN> (no un número) si `expression1` también es cero.|  
|`Decimal`|Produce<xref:System.DivideByZeroException>|  
|Entero (con signo o sin signo)|Se produce <xref:System.OverflowException> un intento de conversión de nuevo a un tipo entero, ya <xref:System.Double.NegativeInfinity>que los tipos enteros no pueden aceptar <xref:System.Double.PositiveInfinity>, o<xref:System.Double.NaN>|  
  
> [!NOTE]
> El `/` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se `/` usa el operador para realizar una división de punto flotante. El resultado es el cociente de los dos operandos.  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 Las expresiones del ejemplo anterior devuelven los valores 2,5 y 3,333333. Tenga en cuenta que el resultado siempre es el punto`Double`flotante (), aunque ambos operandos son constantes de tipo entero.  
  
## <a name="see-also"></a>Vea también

- [/= (Operador) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [Operador (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [Tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)
- [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
