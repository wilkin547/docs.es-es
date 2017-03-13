---
title: "Continue (Instrucci&#243;n, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.continue"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Continue (instrucción) [Visual Basic]"
  - "bucles, transferir a la siguiente iteración"
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Continue (Instrucci&#243;n, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Transfiere controle inmediatamente a la siguiente iteración de un bucle.  
  
## Sintaxis  
  
```  
Continue { Do | For | While }  
```  
  
## Comentarios  
 Puede transferir desde dentro de un bucle `Do`, `For` o `While` a la siguiente iteración de ese bucle.  El control pasa inmediatamente a la comprobación de condición del bucle, que es equivalente a transferir a la instrucción `For` o `While`, o a la instrucción `Do` o `Loop` que contiene la cláusula `Until` o `While`.  
  
 Puede usar `Continue` en cualquier ubicación del bucle que permita transferencias.  Las reglas que permiten la transferencia del control son iguales que las de la [GoTo \(Instrucción\)](../../../visual-basic/language-reference/statements/goto-statement.md).  
  
 Por ejemplo, si un bucle está completamente incluido en un bloque `Try`, un bloque `Catch` o un bloque `Finally`, puede usar `Continue` para transferir el control fuera del bucle.  Por otra parte, si la estructura `Try`...`End Try` está contenida dentro del bucle, no puede usar `Continue` para transferir el control fuera del bloque `Finally` y utilizarlo para transferirlo fuera de un bloque `Try` o `Catch` sólo si lo transfiere completamente fuera de la estructura `Try`...`End Try`.  
  
 Si tiene bucles anidados del mismo tipo, por ejemplo un bucle `Do` dentro de otro bucle `Do`, una instrucción `Continue Do` pasa a la siguiente iteración del bucle `Do` más interno que lo contiene.  No puede utilizar `Continue` para pasar a la iteración siguiente de un bucle que contiene el mismo tipo.  
  
 Si tiene bucles anidados de distintos tipos, por ejemplo un bucle `Do` dentro de un bucle `For`, puede pasar a la siguiente iteración de cualquiera de esos bucles mediante `Continue Do` o `Continue For`.  
  
## Ejemplo  
 El ejemplo de código siguiente utiliza la instrucción `Continue While` para pasar a la siguiente columna de una matriz si un divisor es cero.  `Continue While` está dentro de un bucle `For`.  Transfiere a la instrucción `While col < lastcol`, que es la siguiente iteración del bucle `While` más interior que contiene el bucle `For`.  
  
 [!code-vb[VbVbalrStatements#14](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/continue-statement_1.vb)]  
  
## Vea también  
 [Do...Loop \(Instrucción\)](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [For...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [While...End While \(Instrucción\)](../../../visual-basic/language-reference/statements/while-end-while-statement.md)   
 [Try...Catch...Finally \(Instrucción\)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)