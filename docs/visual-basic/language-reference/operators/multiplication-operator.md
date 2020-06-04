---
title: '* Operador'
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
ms.openlocfilehash: f1a7653fb3006ab3c9736ec168a8c5ea028f4763
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409331"
---
# <a name="-operator-visual-basic"></a>* (Operador, Visual Basic)
Multiplica dos números.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
number1 * number2  
```  
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`number1`|Obligatorio. Cualquier expresión numérica.|  
|`number2`|Necesario. Cualquier expresión numérica.|  
  
## <a name="result"></a>Resultado  
 El resultado es el producto de `number1` y `number2` .  
  
## <a name="supported-types"></a>Tipos admitidos  
 Todos los tipos numéricos, incluidos los tipos de punto flotante y sin signo y `Decimal` .  
  
## <a name="remarks"></a>Observaciones  
 El tipo de datos del resultado depende de los tipos de los operandos. En la tabla siguiente se muestra cómo se determina el tipo de datos del resultado.  
  
|Tipos de datos de operando|Tipo de datos de resultados|  
|---|---|  
|Ambas expresiones son tipos de datos enteros ([SByte](../data-types/sbyte-data-type.md), [byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [ushort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ULong](../data-types/ulong-data-type.md))|Un tipo de datos numérico adecuado para los tipos de datos de `number1` y `number2` . Vea las tablas "aritmética de enteros" en [tipos de datos de resultados de operadores](data-types-of-operator-results.md).|  
|Ambas expresiones son [decimales](../data-types/decimal-data-type.md)|`Decimal`|  
|Ambas expresiones son [únicas](../data-types/single-data-type.md)|`Single`|  
|Cualquier expresión es un tipo de datos de punto flotante ( `Single` o [Double](../data-types/double-data-type.md)), pero no ambos `Single` ( `Decimal` la nota no es un tipo de datos de punto flotante)|`Double`|  
  
 Si una expresión se evalúa como [Nothing](../nothing.md), se trata como cero.  
  
## <a name="overloading"></a>Sobrecarga  
 El `*` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa el `*` operador para multiplicar dos números. El resultado es el producto de los dos operandos.  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a>Consulte también

- [* = (Operador)](multiplication-assignment-operator.md)
- [Operadores aritméticos](arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Operadores aritméticos en Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
