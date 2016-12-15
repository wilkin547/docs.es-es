---
title: "Instrucci&#243;n If...Then...Else (Visual Basic) | Microsoft Docs"
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
  - "vb.ElseIf"
  - "vb.Then"
  - "vb.If"
  - "vb.EndIf"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "bifurcación, condicional"
  - "flujo de control, bifurcación"
  - "Else (instrucción) [Visual Basic]"
  - "ElseIf (instrucción), If...Then...Else"
  - "ejecución, condicional"
  - "If (operador) [Visual Basic]"
  - "If (instrucción)"
  - "If (instrucción), If...Then...Else"
  - "If...Then...Else (instrucciones)"
  - "IIf (función), e instrucciones If...Then...Else"
  - "Is (operador) [Visual Basic], en instrucciones If...Then...Else"
  - "Then (instrucción), If...Then...Else"
  - "TypeOf...Is (expresión), e instrucciones If...Then...Else"
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
caps.latest.revision: 29
caps.handback.revision: 29
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Instrucci&#243;n If...Then...Else (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ejecuta condicionalmente un grupo de instrucciones en función del valor de una expresión.  
  
## Sintaxis  
  
```  
' Multiple-line syntax:  
If condition [ Then ]  
    [ statements ]  
[ ElseIf elseifcondition [ Then ]  
    [ elseifstatements ] ]  
[ Else  
    [ elsestatements ] ]  
End If  
  
' Single-line syntax:  
If condition Then [ statements ] [ Else [ elsestatements ] ]  
```  
  
## Elementos  
 `condition`  
 Requerido.  Expresión.  Debe evaluarse en `True` o `False`, o en un tipo de datos que sea implícitamente convertible a `Boolean`.  
  
 Si la expresión es una variable [Valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)`Boolean` que evalúa [Nada](../../../visual-basic/language-reference/nothing.md), se trata la condición como si la expresión no es `True`, y ejecuta el bloque `Else` .  
  
 `Then`  
 Obligatorio en la sintaxis de una línea, opcional en la sintaxis de varias líneas.  
  
 `statements`  
 Opcional.  Se ejecutan una o más instrucciones que siguen a `If`...`Then` que se ejecutan si `condition` se evalúa como `True`.  
  
 `elseifcondition`  
 Obligatorio si `ElseIf` está presente.  Expresión.  Debe evaluarse en `True` o `False`, o en un tipo de datos que sea implícitamente convertible a `Boolean`.  
  
 `elseifstatements`  
 Opcional.  Se ejecutan una o más instrucciones que siguen a `ElseIf`...`Then` que se ejecutan si `elseifcondition` se evalúa como `True`.  
  
 `elsestatements`  
 Opcional.  Una o más instrucciones que se ejecutan si ninguna expresión `condition` o `elseifcondition` anterior se evalúa como `True`.  
  
 `End If`  
 Termina el bloque `If`...`Then`...`Else`.  
  
## Comentarios  
  
## Sintaxis de varias líneas  
 Cuando se encuentra una instrucción `If`...`Then`...`Else`, se prueba `condition`.  Si `condition` es `True`, se ejecutan las instrucciones que están a continuación de `Then`.  Si `condition` es `False`, cada instrucción `ElseIf` \(si hay alguna\) se evalúa en orden.  Cuando se encuentra una `elseifcondition` que sea `True`, se ejecutan las instrucciones que siguen inmediatamente a la instrucción `ElseIf` asociada.  Si `elseifcondition` se evalúa como `True`, o si no hay ninguna instrucción `ElseIf`, se ejecutan las instrucciones situadas después de `Else`.  Después de la ejecución de las instrucciones que siguen a `Then`, `ElseIf` o `Else`, la ejecución continúa con la instrucción que sigue a `End If`.  
  
 Las cláusulas `ElseIf` y `Else` son opcionales.  Puede tener tantas cláusulas `ElseIf` como desee en una instrucción `If`...`Then`...`Else`, pero no puede aparecer ninguna cláusula `ElseIf` después de una cláusula `Else`.  `If`...`Then`...`Else` las instrucciones se pueden anidar una dentro de otra.  
  
 Con la sintaxis de varias líneas, la instrucción `If` debe ser la única instrucción incluida en la primera línea.  Las instrucciones `ElseIf`, `Else` y `End If` pueden ir precedidas solamente por una etiqueta de línea.  El bloque `If`...`Then`...`Else` debe terminar con una instrucción `End If`.  
  
> [!TIP]
>  La [Select...Case \(Instrucción\)](../../../visual-basic/language-reference/statements/select-case-statement.md) puede ser más útil al evaluar una única expresión que tiene varios valores posibles.  
  
## Sintaxis de una única línea  
 Puede utilizar la sintaxis de una sola línea para pruebas cortas y sencillas.  Sin embargo, la sintaxis de varias líneas proporciona más estructura y flexibilidad y, generalmente, es más fácil de leer, mantener y depurar.  
  
 Lo que sigue a la palabra clave `Then` se examina para determinar si una declaración es un `If` de una sola línea.  Si aparece cualquier otra cosa que no sea un comentario después de `Then` en la misma línea, ésta se trata como una instrucción `If` de una sola línea.  Si no está presente `Then`, debe ser el comienzo de una instrucción `If`...`Then`...`Else` de varias líneas.  
  
 En la sintaxis de una línea, puede que se ejecuten varias instrucciones como resultado de una decisión `If`...`Then`.  Todas las instrucciones deben estar en la misma línea y separarse con dos puntos.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra el uso de la sintaxis de varias líneas de la instrucción `If`...`Then`...`Else`.  
  
 [!code-vb[VbVbalrStatements#101](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_1.vb)]  
  
## Ejemplo  
 El ejemplo siguiente contiene instrucciones `If`...`Then`...`Else` anidadas.  
  
 [!code-vb[VbVbalrStatements#102](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_2.vb)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra el uso de la sintaxis de una única línea.  
  
 [!code-vb[VbVbalrStatements#103](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/if-then-else-statement_3.vb)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>   
 <xref:Microsoft.VisualBasic.Interaction.Switch%2A>   
 [\#If...Then...\#Else \(Directivas\)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [Select...Case \(Instrucción\)](../../../visual-basic/language-reference/statements/select-case-statement.md)   
 [Estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Estructuras de decisión](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)   
 [If \(operador\)](../../../visual-basic/language-reference/operators/if-operator.md)