---
title: If (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.IfOperator
- IfOperator
helpviewer_keywords:
- ternary operators [Visual Basic]
- conditional execution
- If expressions [Visual Basic]
- conditional operator [Visual Basic]
- If Operator [Visual Basic]
ms.assetid: dd56c9df-7cd4-442c-9ba6-20c70ee44c8f
ms.openlocfilehash: 25b0d7e85fe1c1e0d0589b4b9a9db2d85ca71526
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965921"
---
# <a name="if-operator-visual-basic"></a>If (Operador) (Visual Basic)
Usa evaluación de cortocircuito para devolver condicionalmente uno de dos valores. El `If` operador se puede llamar con tres argumentos o con dos argumentos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
If( [argument1,] argument2, argument3 )  
```  
  
## <a name="if-operator-called-with-three-arguments"></a>Si llama operador con tres argumentos  
 Cuando `If` se llama con tres argumentos, el primer argumento debe evaluarse en un valor que se puede convertir un `Boolean`. Que `Boolean` valor determinará cuál de los otros dos argumentos se evalúan y se devuelve. En la lista siguiente se aplica solo cuando el `If` se denomina operador mediante el uso de tres argumentos.  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`argument1`|Obligatorio. `Boolean`. Determina cuál de los otros argumentos para evaluar y devolver.|  
|`argument2`|Obligatorio. `Object`. Evaluada y devuelto si `argument1` se evalúa como `True`.|  
|`argument3`|Obligatorio. `Object`. Evaluada y devuelto si `argument1` se evalúa como `False` o si `argument1` es un [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable que se evalúa como [nada](../../../visual-basic/language-reference/nothing.md).|  
  
 Un `If` operador que se llama con tres argumentos funciona como un `IIf` función salvo que usa la evaluación de cortocircuito. Un `IIf` función siempre evalúa las tres de los argumentos, mientras que un `If` operador que tiene tres argumentos evalúa sólo dos de ellos. La primera `If` argumento se evalúa y el resultado se convierte como un `Boolean` valor, `True` o `False`. Si el valor es `True`, `argument2` es evalúa y devuelve su valor, pero `argument3` no se evalúa. Si el valor de la `Boolean` expresión es `False`, `argument3` es evalúa y devuelve su valor, pero `argument2` no se evalúa. Los ejemplos siguientes ilustran el uso de `If` cuando se usan tres argumentos:  
  
 [!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]  
  
 El ejemplo siguiente muestra el valor de la evaluación de cortocircuito. El ejemplo muestra dos intentos para dividir la variable `number` variable `divisor` salvo cuando `divisor` es cero. En ese caso, se debe devolver un 0 y no se debe realizar ningún intento para realizar la división porque daría lugar a un error en tiempo de ejecución. Dado que el `If` usar expresiones de evaluación de cortocircuito, se evalúa como el segundo o tercer argumento, dependiendo del valor del primer argumento. Si el primer argumento es true, el divisor no es cero y es seguro evaluar el segundo argumento y realizar la división. Si el primer argumento es false, solo el tercer argumento se evalúa y se devuelve 0. Por lo tanto, si el divisor es 0, no se realiza ningún intento para realizar la división y se produce ningún error. Sin embargo, dado que `IIf` no utiliza la evaluación de cortocircuito, se evalúa el segundo argumento incluso cuando el primer argumento es false. Esto produce un error de división por cero de tiempo de ejecución.  
  
 [!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]  
  
## <a name="if-operator-called-with-two-arguments"></a>Si llama operador con dos argumentos  
 El primer argumento `If` puede omitirse. Esto permite al operador a llamarse con solo dos argumentos. En la lista siguiente se aplica solo cuando el `If` se denomina operador con dos argumentos.  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`argument2`|Obligatorio. `Object`. Debe ser una referencia o tipo que acepta valores NULL. Evalúa y se devuelve cuando se evalúa en algo distinto `Nothing`.|  
|`argument3`|Obligatorio. `Object`. Evaluada y devuelto si `argument2` se evalúa como `Nothing`.|  
  
 Cuando el `Boolean` argumento se omite, el primer argumento debe ser una referencia o tipo que acepta valores NULL. Si el primer argumento se evalúa como `Nothing`, se devuelve el valor del segundo argumento. En todos los demás casos, se devuelve el valor del primer argumento. El siguiente ejemplo ilustra cómo funciona esta evaluación.  
  
 [!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [Tipos de valor que aceptan valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Nothing](../../../visual-basic/language-reference/nothing.md)
