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
ms.openlocfilehash: 192309a7ca728feb300e867bf2340e669e9da16c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603969"
---
# <a name="if-operator-visual-basic"></a>If (Operador) (Visual Basic)
Usa evaluación de cortocircuito para devolver condicionalmente uno de dos valores. La `If` puede llamar al operador con tres argumentos o con dos argumentos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
If( [argument1,] argument2, argument3 )  
```  
  
## <a name="if-operator-called-with-three-arguments"></a>Si llama a operador con tres argumentos  
 Cuando `If` se llama con tres argumentos, el primer argumento debe evaluarse en un valor que se puede convertir en un `Boolean`. Que `Boolean` valor va a determinar cuál de los otros dos argumentos se evalúa y se devuelve. En la lista siguiente se aplica solo cuando el `If` se denomina operador mediante el uso de tres argumentos.  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`argument1`|Requerido. `Boolean`. Determina cuál de los otros argumentos para evaluar y devolver.|  
|`argument2`|Requerido. `Object`. Evaluada y devuelto si `argument1` se evalúa como `True`.|  
|`argument3`|Requerido. `Object`. Evaluada y devuelto si `argument1` se evalúa como `False` o si `argument1` es un [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable que se evalúa como [nada](../../../visual-basic/language-reference/nothing.md).|  
  
 Un `If` operador que se llama con tres argumentos funciona como un `IIf` función salvo que usa la evaluación de cortocircuito. Un `IIf` función siempre evalúa las tres de sus argumentos, mientras que un `If` operando que tiene tres argumentos se evalúa como sólo dos de ellos. La primera `If` argumento se evalúa y se convierte el resultado como un `Boolean` valor, `True` o `False`. Si el valor es `True`, `argument2` es evalúa y se devuelve su valor, pero `argument3` no se evalúa. Si el valor de la `Boolean` expresión es `False`, `argument3` es evalúa y se devuelve su valor, pero `argument2` no se evalúa. Los siguientes ejemplos ilustran el uso de `If` cuando se usan tres argumentos:  
  
 [!code-vb[VbVbalrOperators#100](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_1.vb)]  
  
 En el ejemplo siguiente se muestra el valor de la evaluación de cortocircuito. El ejemplo muestra dos intentos para dividir variable `number` variable `divisor` excepto cuando `divisor` es cero. En ese caso, se debe devolver un valor 0, y no se debe realizar ningún intento para realizar la división porque produciría un error en tiempo de ejecución. Dado que el `If` usar expresiones de evaluación de cortocircuito, se evalúa como el segundo o tercer argumento, dependiendo del valor del primer argumento. Si el primer argumento es true, el divisor no es cero y es seguro evaluar el segundo argumento y realizar la división. Si el primer argumento es false, solo el tercer argumento se evalúa y se devuelve un valor 0. Por lo tanto, si el divisor es 0, se realiza ningún intento para realizar la división y se produce ningún error. Sin embargo, dado que `IIf` no utiliza la evaluación de cortocircuito, se evalúa el segundo argumento incluso cuando el primer argumento es false. Se produce un error de división por cero de tiempo de ejecución.  
  
 [!code-vb[VbVbalrOperators#101](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_2.vb)]  
  
## <a name="if-operator-called-with-two-arguments"></a>Si llama a operador con dos argumentos  
 El primer argumento `If` puede omitirse. Esto permite que el operador que se va a llamar mediante solo dos argumentos. En la lista siguiente se aplica solo cuando el `If` se denomina operador con dos argumentos.  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`argument2`|Requerido. `Object`. Debe ser una referencia o tipo que acepta valores NULL. Evalúa y se devuelve cuando se evalúa en algo distinto de `Nothing`.|  
|`argument3`|Requerido. `Object`. Evaluada y devuelto si `argument2` se evalúa como `Nothing`.|  
  
 Cuando el `Boolean` argumento se omite, el primer argumento debe ser una referencia o tipo que acepta valores NULL. Si el primer argumento se evalúa como `Nothing`, se devuelve el valor del segundo argumento. En todos los demás casos, se devuelve el valor del primer argumento. En el ejemplo siguiente se muestra cómo funciona esta evaluación.  
  
 [!code-vb[VbVbalrOperators#102](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_3.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Interaction.IIf%2A>  
 [Tipos de valor que aceptan valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [Nothing](../../../visual-basic/language-reference/nothing.md)
