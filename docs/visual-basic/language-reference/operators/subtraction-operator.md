---
title: '- Operator (Visual Basic) | Documentos de Microsoft'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Negate
- vb.-
dev_langs:
- VB
helpviewer_keywords:
- '- operator [Visual Basic]'
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator
- operators [Visual Basic], arithmetic
- subtraction operator, syntax
- arithmetic operators, subtraction
- difference operator
- math operators
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7f45094da7bc61687d9c767d25858aa214bf1978
ms.lasthandoff: 03/13/2017

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
 Obligatorio a menos que el `–` operador está calculando un valor negativo. Cualquier expresión numérica.  
  
## <a name="result"></a>Resultado  
 El resultado es la diferencia entre `expression1` y `expression2`, o el valor negado de `expression1`.  
  
 El tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`. Vea las tablas "Aritmética de enteros" en [tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="supported-types"></a>Tipos admitidos  
 todos los tipos numéricos. Esto incluye los tipos de punto flotante y sin signo y `Decimal`.  
  
## <a name="remarks"></a>Comentarios  
 En el primer uso se muestra en la sintaxis mostrada anteriormente, el `–` operador es la *binario* operador aritmético de sustracción de la diferencia entre dos expresiones numéricas.  
  
 En el segundo uso se muestra en la sintaxis mostrada anteriormente, el `–` operador es la *unario* operador de negación para el valor negativo de una expresión. En este sentido, la negación invierte el signo de `expression1` para que el resultado es positivo si `expression1` es negativo.  
  
 Si alguna expresión se evalúa como [nada](../../../visual-basic/language-reference/nothing.md), el `–` operador lo trata como cero.  
  
> [!NOTE]
>  El `–` operador puede *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de conocer su comportamiento redefinido. Para obtener más información, consulte [procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `–` operador para calcular y devolver la diferencia entre dos números y, a continuación, para negar un número.  
  
 [!code-vb[VbVbalrOperators&#10;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/subtraction-operator_1.vb)]  
  
 Tras la ejecución de estas instrucciones, `binaryResult` contiene 124.45 y `unaryResult` contiene -334.90.  
  
## <a name="see-also"></a>Vea también  
 [-= (Operador, Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
 [operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Precedencia de operadores en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)

