---
title: '- Operador (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
ms.openlocfilehash: 8526f632b7e54c03bd16c3af70375179cd7cf277
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724478"
---
# <a name="--operator-visual-basic"></a>- (Operador, Visual Basic)
Devuelve la diferencia entre dos expresiones numéricas o el valor negativo de una expresión numérica.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a>Elementos  
 `expression1`  
 Obligatorio. Cualquier expresión numérica.  
  
 `expression2`  
 Obligatoria a menos que el `–` operador calcula un valor negativo. Cualquier expresión numérica.  
  
## <a name="result"></a>Resultado  
 El resultado es la diferencia entre `expression1` y `expression2`, o el valor negado de `expression1`.  
  
 El tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`. Vea las tablas "Aritmética de enteros" en [tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="supported-types"></a>Tipos admitidos  
 todos los tipos numéricos. Esto incluye los tipos sin signo y de punto flotante y `Decimal`.  
  
## <a name="remarks"></a>Comentarios  
 En el primer uso, se muestra en la sintaxis mostrada anteriormente, el `–` operador es la *binario* operador aritmético de sustracción de la diferencia entre dos expresiones numéricas.  
  
 En el segundo uso se muestra en la sintaxis mostrada anteriormente, el `–` operador es la *unario* operador de negación para el valor negativo de una expresión. En este sentido, la negación invierte el signo de `expression1` para que el resultado es positivo si `expression1` es negativo.  
  
 Si una de las expresiones se evalúa como [nada](../../../visual-basic/language-reference/nothing.md), el `–` operador lo trata como cero.  
  
> [!NOTE]
>  El `–` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que comprende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `–` operador para calcular y devolver la diferencia entre dos números y, a continuación, para negar un número.  
  
 [!code-vb[VbVbalrOperators#10](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]  
  
 Tras la ejecución de estas instrucciones, `binaryResult` contiene 124.45 y `unaryResult` contiene -334.90.  
  
## <a name="see-also"></a>Vea también
- [-= (Operador) (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
