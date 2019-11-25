---
title: '* "??"'
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
ms.openlocfilehash: 4f6a8ea2c5f4e23791afdfe98d2a08bf67219048
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348361"
---
# <a name="-operator-visual-basic"></a>* (Operador, Visual Basic)
Multiplica dos números.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
number1 * number2  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|de esquema JSON|  
|---|---|  
|`number1`|Requerido. Cualquier expresión numérica.|  
|`number2`|Requerido. Cualquier expresión numérica.|  
  
## <a name="result"></a>Resultado  
 The result is the product of `number1` and `number2`.  
  
## <a name="supported-types"></a>Tipos admitidos  
 All numeric types, including the unsigned and floating-point types and `Decimal`.  
  
## <a name="remarks"></a>Comentarios  
 The data type of the result depends on the types of the operands. The following table shows how the data type of the result is determined.  
  
|Operand data types|Result data type|  
|---|---|  
|Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|A numeric data type appropriate for the data types of `number1` and `number2`. See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Both expressions are [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`|  
|Both expressions are [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`|  
|Either expression is a floating-point data type (`Single` or [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)) but not both `Single` (note `Decimal` is not a floating-point data type)|`Double`|  
  
 If an expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.  
  
## <a name="overloading"></a>Sobrecarga  
 The `*` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure. If your code uses this operator on such a class or structure, be sure you understand its redefined behavior. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 This example uses the `*` operator to multiply two numbers. The result is the product of the two operands.  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a>Vea también

- [Operador *=](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
