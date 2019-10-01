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
ms.openlocfilehash: 244c0598c65ba691decc09c36293799571211a40
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701152"
---
# <a name="if-operator-visual-basic"></a>If (Operador) (Visual Basic)
Usa la evaluación de cortocircuito para devolver condicionalmente uno de dos valores. Se puede llamar al operador `If` con tres argumentos o con dos argumentos.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
If( [argument1,] argument2, argument3 )  
```  
  
## <a name="if-operator-called-with-three-arguments"></a>Operador if llamado con tres argumentos  
 Cuando se llama a `If` mediante tres argumentos, el primer argumento debe evaluarse como un valor que se pueda convertir en `Boolean`. Ese valor `Boolean` determinará cuál de los otros dos argumentos se evalúa y se devuelve. La lista siguiente solo se aplica cuando se llama al operador `If` mediante tres argumentos.  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`argument1`|Obligatorio. `Boolean` Determina cuál de los otros argumentos que se evaluarán y devolverán.|  
|`argument2`|Obligatorio. `Object` Se evalúa y se devuelve si `argument1` se evalúa como `True`.|  
|`argument3`|Obligatorio. `Object` Se evalúa y se devuelve si `argument1` se evalúa como `False` o si `argument1` es una variable `Boolean` que [acepta valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)que se evalúa como [Nothing](../../../visual-basic/language-reference/nothing.md).|  
  
 Un operador `If` al que se llama con tres argumentos funciona como una función `IIf`, salvo que usa la evaluación de cortocircuito. Una función `IIf` siempre evalúa los tres argumentos, mientras que un operador `If` que tiene tres argumentos solo evalúa dos de ellos. Se evalúa el primer argumento `If` y el resultado se convierte en un valor `Boolean`, `True` o `False`. Si el valor es `True`, se evalúa `argument2` y se devuelve su valor, pero no se evalúa `argument3`. Si el valor de la expresión `Boolean` es `False`, se evalúa `argument3` y se devuelve su valor, pero `argument2` no se evalúa. En los siguientes ejemplos se muestra el uso de `If` cuando se usan tres argumentos:  
  
 [!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]  
  
 En el ejemplo siguiente se muestra el valor de la evaluación de cortocircuito. En el ejemplo se muestran dos intentos de dividir la variable `number` por variable `divisor` excepto cuando `divisor` es cero. En ese caso, se debe devolver un 0 y no se debe realizar ningún intento para realizar la división porque se produciría un error en tiempo de ejecución. Dado que la expresión `If` usa la evaluación de cortocircuito, evalúa el segundo o el tercer argumento, dependiendo del valor del primer argumento. Si el primer argumento es true, el divisor no es cero y es seguro evaluar el segundo argumento y realizar la división. Si el primer argumento es false, solo se evalúa el tercer argumento y se devuelve 0. Por lo tanto, cuando el divisor es 0, no se realiza ningún intento de realizar la división y no se producen resultados de error. Sin embargo, como `IIf` no utiliza la evaluación de cortocircuito, el segundo argumento se evalúa incluso cuando el primer argumento es false. Esto produce un error de división por cero en tiempo de ejecución.  
  
 [!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]  
  
## <a name="if-operator-called-with-two-arguments"></a>Operador if llamado con dos argumentos  
 Se puede omitir el primer argumento de `If`. Esto permite llamar al operador usando solo dos argumentos. La lista siguiente solo se aplica cuando se llama al operador `If` con dos argumentos.  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`argument2`|Obligatorio. `Object` Debe ser una referencia o un tipo que acepte valores NULL. Se evalúa y se devuelve cuando se evalúa en un valor distinto de `Nothing`.|  
|`argument3`|Obligatorio. `Object` Se evalúa y se devuelve si `argument2` se evalúa como `Nothing`.|  
  
 Cuando se omite el argumento `Boolean`, el primer argumento debe ser una referencia o un tipo que acepte valores NULL. Si el primer argumento se evalúa como `Nothing`, se devuelve el valor del segundo argumento. En todos los demás casos, se devuelve el valor del primer argumento. En el ejemplo siguiente se muestra cómo funciona esta evaluación.  
  
 [!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [Tipos de valor que aceptan valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Nothing](../../../visual-basic/language-reference/nothing.md)
