---
title: "GoTo (Instrucci&#243;n) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.GoTo"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "bifurcación"
  - "bifurcación, conditional"
  - "bifurcación, incondicional"
  - "instrucciones condicionales, GoTo (instrucción)"
  - "flujo de control, bifurcación"
  - "GoTo (instrucción)"
  - "GoTo (instrucción), sintaxis"
  - "bifurcación incondicional"
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# GoTo (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Realiza una bifurcación incondicional a una línea especificada en un procedimiento.  
  
## Sintaxis  
  
```  
GoTo line  
```  
  
## Parte  
 `line`  
 Obligatorio.  Cualquier etiqueta de línea.  
  
## Comentarios  
 La instrucción `GoTo` únicamente puede bifurcarse a líneas en el procedimiento en el que aparece.  La línea debe tener una etiqueta de la línea a la que puede hacer referencia `GoTo`.  Para obtener más información, vea [Cómo: Aplicar etiquetas a las instrucciones](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).  
  
> [!NOTE]
>  Las instrucciones `GoTo` pueden dificultar la lectura y el mantenimiento del código.  Siempre que sea posible, utilice en su lugar una estructura de control.  Para obtener más información, vea [Flujo de control](../../../visual-basic/programming-guide/language-features/control-flow/index.md).  
  
 No puede utilizar una instrucción `GoTo` para realizar una bifurcación desde fuera de una construcción `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With` o `Using`...`End Using` a una etiqueta situada dentro de ella.  
  
## Bifurcación y construcciones Try  
 Dentro de una construcción `Try`...`Catch`...`Finally`, se aplican las reglas siguientes a la bifurcación con la instrucción `GoTo`.  
  
|Bloque o región|Bifurcación hacia dentro desde fuera|Bifurcación hacia fuera desde dentro|  
|---------------------|------------------------------------------|------------------------------------------|  
|Bloque `Try`|Sólo desde un bloque `Catch` de la misma construcción <sup>1</sup>|Sólo hacia fuera de la construcción completa|  
|Bloque `Catch`|Nunca se permite|Sólo hacia fuera de la construcción completa o al bloque `Try` de la misma construcción <sup>1</sup>|  
|Bloque `Finally`|Nunca se permite|Nunca se permite|  
  
 <sup>1</sup> Si una construcción `Try`...`Catch`...`Finally` está anidada dentro de otra, un bloque `Catch` se puede bifurcar hacia el interior del bloque `Try` de su propio nivel de anidación, pero no hacia el interior de ningún otro bloque `Try`.  Una construcción `Try`...`Catch`...`Finally` anidada debe estar completamente contenida dentro de un bloque `Try` o `Catch` de la construcción dentro de la que está anidada.  
  
 La ilustración siguiente muestra una construcción `Try` anidada dentro de otra.  Las distintas bifurcaciones entre los bloques de las dos construcciones se señalan como válidas o no válidas.  
  
 ![Diagrama gráfico de bifurcación en construcciones Try](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")  
Bifurcaciones válidas y no válidas en construcciones Try  
  
## Ejemplo  
 En este ejemplo se usa la instrucción `GoTo` para bifurcar hacia etiquetas de línea ubicadas en un procedimiento.  
  
 [!code-vb[VbVbalrStatements#31](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/goto-statement_1.vb)]  
  
## Vea también  
 [Do...Loop \(Instrucción\)](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [For...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [For Each...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [If...Then...Else \(Instrucción\)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [Select...Case \(Instrucción\)](../../../visual-basic/language-reference/statements/select-case-statement.md)   
 [Try...Catch...Finally \(Instrucción\)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [While...End While \(Instrucción\)](../../../visual-basic/language-reference/statements/while-end-while-statement.md)   
 [With...End With \(Instrucción\)](../../../visual-basic/language-reference/statements/with-end-with-statement.md)