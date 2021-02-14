---
description: 'Más información acerca de cómo: calcular valores numéricos (Visual Basic)'
title: Procedimiento para calcular valores numéricos
ms.date: 07/20/2015
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations [Visual Basic], numeric expressions
- precedence [Visual Basic], of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
ms.openlocfilehash: 35acd7b9b1732514a8fe4399b6a815dce62b2468
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100435595"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a>Cómo: Calcular valores numéricos (Visual Basic)

Puede calcular valores numéricos mediante el uso de expresiones numéricas. Una *expresión numérica* es una expresión que contiene literales, constantes y variables que representan valores numéricos y operadores que actúan sobre esos valores.  
  
## <a name="calculating-numeric-values"></a>Calcular valores numéricos  
  
#### <a name="to-calculate-a-numeric-value"></a>Para calcular un valor numérico  
  
- Combinar uno o más literales numéricos, constantes y variables en una expresión numérica. En el ejemplo siguiente se muestran algunas expresiones numéricas válidas.  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     Las tres primeras líneas muestran un literal, una constante y una variable. Cada uno de ellos forma una expresión numérica válida por sí sola. La línea final muestra una combinación de una variable con dos literales.  
  
     Tenga en cuenta que una expresión numérica no forma una instrucción Visual Basic completa. Debe utilizar la expresión como parte de una instrucción completa.  
  
#### <a name="to-store-a-numeric-value"></a>Para almacenar un valor numérico  
  
- Puede usar una instrucción de asignación para asignar el valor representado por una expresión numérica a una variable, como se muestra en el ejemplo siguiente.  
  
     [!code-vb[VbVbalrOperators#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#82)]  
  
     En el ejemplo anterior, el valor de la expresión en el lado derecho del operador igual ( `=` ) se asigna a la variable `j` en el lado izquierdo del operador, por lo que se `j` evalúa como 276.  
  
     Para más información, vea [Statements](../../../language-reference/statements/index.md) (Instrucciones).  
  
## <a name="multiple-operators"></a>Varios operadores  

 Si la expresión numérica contiene más de un operador, el orden en el que se evalúan viene determinado por las reglas de prioridad de los operadores. Para invalidar las reglas de prioridad de los operadores, incluya expresiones entre paréntesis, como en el ejemplo anterior. primero se evalúan las expresiones delimitadas.  
  
#### <a name="to-override-normal-operator-precedence"></a>Para invalidar la prioridad de operador normal  
  
- Use paréntesis para encerrar las operaciones que desea que se realicen en primer lugar. En el ejemplo siguiente se muestran dos resultados diferentes con los mismos operandos y operadores.  
  
     [!code-vb[VbVbalrOperators#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#83)]  
  
     En el ejemplo anterior, el cálculo de `j` realiza el operador de suma ( `+` ) en primer lugar, ya que los paréntesis en torno `(67 + i)` a la invalidación de la prioridad normal y el valor asignado a `j` es 276 (4 veces 69). El cálculo de `k` realiza los operadores con su prioridad normal ( `*` antes `+` ) y el valor asignado a `k` es 270 (268 más 2).  
  
     Para obtener más información, vea [precedencia de operadores en Visual Basic](../../../language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>Consulte también

- [Operadores y expresiones](index.md)
- [Comparaciones de valores](value-comparisons.md)
- [Instrucciones](../../../language-reference/statements/index.md)
- [Prioridad de operador en Visual Basic](../../../language-reference/operators/operator-precedence.md)
- [Operadores aritméticos](../../../language-reference/operators/arithmetic-operators.md)
- [Combinación eficaz de operadores](efficient-combination-of-operators.md)
