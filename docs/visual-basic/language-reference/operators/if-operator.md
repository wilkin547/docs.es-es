---
title: "If (Operador) (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.IfOperator"
  - "IfOperator"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ejecución condicional"
  - "operador condicional [Visual Basic]"
  - "expresiones If [Visual Basic]"
  - "If (operador) [Visual Basic]"
  - "operadores ternarios"
ms.assetid: dd56c9df-7cd4-442c-9ba6-20c70ee44c8f
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# If (Operador) (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Utiliza la evaluación de cortocircuito para devolver condicionalmente uno de dos valores.  Se puede llamar al operador `If` con tres argumentos o con dos argumentos.  
  
## Sintaxis  
  
```  
If( [argument1,] argument2, argument3 )  
```  
  
## Operador "If" llamado con tres argumentos  
 Cuando se llama a `If` utilizando tres argumentos, el primer argumento se debe evaluar en un valor que se pueda convertir en `Boolean`.  Ese valor `Boolean` determinará cuál de los otros dos argumentos se evalúa y devuelve.  La lista siguiente sólo se aplica cuando se llama al operador `If` utilizando tres argumentos.  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`argument1`|Obligatorio.  `Boolean`.  Determina cuál de los otros argumentos se va a evaluar y devolver.|  
|`argument2`|Obligatorio.  `Object`.  Se evalúa y devuelve si `argument1` se evalúa en `True`.|  
|`argument3`|Obligatorio.  `Object`.  Evalúa y volver si `argument1` se evalúa como `False` o si `argument1` es una variable de [Valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` que evalúa [nada](../../../visual-basic/language-reference/nothing.md).|  
  
 A un operador `If` al que se llama con tres argumentos funciona como función `IIf` salvo que utiliza la evaluación de cortocircuito.  Una función `IIf` siempre evalúa sus tres argumentos, mientras que un operador `If` que tiene tres argumentos evalúa sólo dos de ellos.  Se evalúa el primer argumento `If` y el resultado se convierte como valor de tipo `Boolean`, `True` o `False`.  Si el valor es `True`, se evalúa `argument2` y se devuelve su valor, pero no se evalúa `argument3`.  Si el valor de la expresión `Boolean` es `False`, se evalúa `argument2` y se devuelve su valor, pero no se evalúa `argument3`.  Los ejemplos siguientes muestran el uso de `If` cuando se utilizan tres argumentos:  
  
 [!code-vb[VbVbalrOperators#100](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_1.vb)]  
  
 El ejemplo siguiente muestra el valor de la evaluación de cortocircuito.  El ejemplo muestra dos intentos de dividir la variable `number` por `divisor` salvo cuando `divisor` es cero.  En ese caso, se debe devolver un 0 y no se debe realizar ningún intento para llevar a cabo la división porque se provocaría un error en tiempo de ejecución.  Dado que la expresión `If` utiliza la evaluación de cortocircuito, evalúa el segundo o el tercer argumento, en función del valor del primer argumento.  Si el valor del primer argumento es true, el divisor no es cero y es seguro evaluar el segundo argumento y realizar la división.  Si el valor del primer argumento es false, sólo se evalúa el tercer argumento y se devuelve un 0.  Por consiguiente, cuando el divisor es 0, no se realiza ningún intento para llevar a cabo la división y no se produce ningún error.  Sin embargo, puesto que `IIf` no utiliza la evaluación de cortocircuito, se evalúa el segundo argumento aunque el valor del primer argumento sea false  y se produce un error de división por cero en tiempo de ejecución.  
  
 [!code-vb[VbVbalrOperators#101](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_2.vb)]  
  
## Operador "If" llamado con dos argumentos  
 Se puede pasar por alto el primer argumento a `If`.  De esta forma, se puede llamar al operador utilizando sólo dos argumentos.  La lista siguiente sólo se aplica cuando se llama al operador `If` con dos argumentos.  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`argument2`|Obligatorio.  `Object`.  Debe ser una referencia o un tipo que acepte valores NULL.  Se evalúa y devuelve cuando se evalúa en algo distinto de `Nothing`.|  
|`argument3`|Obligatorio.  `Object`.  Se evalúa y devuelve si `argument2` se evalúa en `Nothing`.|  
  
 Cuando se omite el argumento `Boolean`, el primer argumento debe ser una referencia o un tipo que acepte valores NULL.  Si el primer argumento se evalúa en `Nothing`, se devuelve el valor del segundo argumento.  En el resto de los casos, se devuelve el valor del primer argumento.  El ejemplo siguiente muestra cómo funciona esta evaluación.  
  
 [!code-vb[VbVbalrOperators#102](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_3.vb)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Interaction.IIf%2A>   
 [Tipos de valor que aceptan valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Nothing](../../../visual-basic/language-reference/nothing.md)