---
title: '* Operador (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
ms.openlocfilehash: b5b601c7604cb7ce1afaebc98b2157634a77fda4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701093"
---
# <a name="-operator-visual-basic"></a>* (Operador, Visual Basic)
Multiplica dos números.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
number1 * number2  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`number1`|Obligatorio. Cualquier expresión numérica.|  
|`number2`|Obligatorio. Cualquier expresión numérica.|  
  
## <a name="result"></a>Resultado  
 El resultado es el producto de `number1` y `number2`.  
  
## <a name="supported-types"></a>Tipos admitidos  
 Todos los tipos numéricos, incluidos los tipos de punto flotante y sin signo y `Decimal`.  
  
## <a name="remarks"></a>Comentarios  
 El tipo de datos del resultado depende de los tipos de los operandos. En la tabla siguiente se muestra cómo se determina el tipo de datos del resultado.  
  
|Tipos de datos de operando|Tipo de datos de resultados|  
|---|---|  
|Ambas expresiones son tipos de datos enteros ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [ushort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|Un tipo de datos numérico adecuado para los tipos de datos de `number1` y `number2`. Vea las tablas "aritmética de enteros" en [tipos de datos de resultados de operadores](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Ambas expresiones son [decimales](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`|  
|Ambas expresiones son [únicas](../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`|  
|Cualquiera de las expresiones es un tipo de datos de punto flotante (`Single` o [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)), pero no ambos `Single` (tenga en cuenta que `Decimal` no es un tipo de datos de punto flotante)|`Double`|  
  
 Si una expresión se evalúa como [Nothing](../../../visual-basic/language-reference/nothing.md), se trata como cero.  
  
## <a name="overloading"></a>Sobrecarga  
 El operador `*` se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa el operador `*` para multiplicar dos números. El resultado es el producto de los dos operandos.  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a>Vea también

- [Operador *=](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
