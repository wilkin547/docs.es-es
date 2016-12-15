---
title: "Exit (Instrucci&#243;n, Visual Basic) | Microsoft Docs"
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
  - "vb.Exit"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "code, salir"
  - "ejecución, finalizar"
  - "ejecución, detener"
  - "Exit (instrucción)"
  - "archivos, cerrar"
  - "finalización del programa"
  - "programas, salir"
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Exit (Instrucci&#243;n, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Sale de un procedimiento o bloque y transfiere el control inmediatamente a la instrucción que sigue a la llamada al procedimiento o a la definición del bloque.  
  
## Sintaxis  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## Instrucciones  
 `Exit Do`  
 Sale inmediatamente del bucle `Do` en el que aparece.  La ejecución continúa con la instrucción que sigue a la instrucción `Loop`.  `Exit Do` solo se puede usar en un bucle `Do`.  Cuando se utiliza dentro de bucles `Do` anidados, `Exit Do` sale del bucle más profundo y transfiere el control al siguiente nivel de anidamiento.  
  
 `Exit For`  
 Sale inmediatamente del bucle `For` en el que aparece.  La ejecución continúa con la instrucción que sigue a la instrucción `Next`.  `Exit For` solo se puede usar dentro de un bucle `For`...`Next` o `For Each`...`Next`.  Cuando se utiliza dentro de bucles `For` anidados, `Exit For` sale del bucle más profundo y transfiere el control al siguiente nivel de anidamiento.  
  
 `Exit Function`  
 Sale inmediatamente del procedimiento `Function` en el que aparece.  La ejecución continua con la instrucción que sigue a la instrucción que llamó al procedimiento `Function`.  `Exit Function` solo se puede usar en un procedimiento `Function`.  
  
 Para especificar un valor devuelto, puede asignar el valor al nombre de función en una línea delante de la instrucción `Exit Function`.  Para asignar el valor devuelto y salir de la función en una sola instrucción, puede usar [Return \(Instrucción\)](../../../visual-basic/language-reference/statements/return-statement.md) en su lugar.  
  
 `Exit Property`  
 Sale inmediatamente del procedimiento `Property` en el que aparece.  La ejecución continúa con la instrucción que llamó al procedimiento `Property`, es decir, con la instrucción que solicita o establece el valor de la propiedad.  `Exit Property` solo se puede usar en el procedimiento `Get` o `Set` de una propiedad.  
  
 Para especificar un valor devuelto en un procedimiento `Get`, puede asignar el valor al nombre de función en una línea delante de la instrucción `Exit Property`.  Para asignar el valor devuelto y salir del procedimiento `Get` en una sola instrucción, puede usar la instrucción `Return` en su lugar.  
  
 En un procedimiento `Set`, la instrucción `Exit Property` es equivalente a la instrucción `Return`.  
  
 `Exit Select`  
 Sale inmediatamente del bloque `Select Case` en el que aparece.  La ejecución continúa con la instrucción que sigue a la instrucción `End Select`.  `Exit Select` solo se puede usar en una instrucción `Select Case`.  
  
 `Exit Sub`  
 Sale inmediatamente del procedimiento `Sub` en el que aparece.  La ejecución continua con la instrucción que sigue a la instrucción que llamó al procedimiento `Sub`.  `Exit Sub` solo se puede usar en un procedimiento `Sub`.  
  
 En un procedimiento `Sub`, la instrucción `Exit Sub` es equivalente a la instrucción `Return`.  
  
 `Exit Try`  
 Sale inmediatamente del bloque `Try` o `Catch` en el que aparece.  La ejecución continúa con el bloque `Finally`, si procede, o, de lo contrario, con la instrucción siguiente a la instrucción `End Try`.  `Exit Try` solo se puede usar en un bloque `Try` o `Catch` y no en un bloque `Finally`.  
  
 `Exit While`  
 Sale inmediatamente del bucle `While` en el que aparece.  La ejecución continúa con la instrucción que sigue a la instrucción `End While`.  `Exit While` solo se puede usar en un bucle `While`.  Cuando se utiliza dentro de bucles anidados `While`, `Exit While` transfiere el control al bucle que está anidado un nivel por encima del bucle donde aparece `Exit While`.  
  
## Comentarios  
 No deben confundirse las instrucciones `Exit` con las instrucciones `End`.  `Exit` no define el final de una instrucción.  
  
## Ejemplo  
 En el siguiente ejemplo, el estado del bucle detiene el bucle cuando la variable `index` es superior a 100.  La instrucción `If` del bucle, sin embargo, hace que la instrucción `Exit Do` detenga el bucle cuando la variable índice es mayor de 10.  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_1.vb)]  
  
## Ejemplo  
 El ejemplo siguiente asigna el valor devuelto al nombre de función `myFunction` y, a continuación, utiliza la instrucción `Exit Function` para volver de la función.  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_2.vb)]  
  
## Ejemplo  
 En el ejemplo siguiente se usa [Return \(Instrucción\)](../../../visual-basic/language-reference/statements/return-statement.md) para asignar el valor devuelto y salir de la función.  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_3.vb)]  
  
## Vea también  
 [Continue \(Instrucción\)](../../../visual-basic/language-reference/statements/continue-statement.md)   
 [Do...Loop \(Instrucción\)](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [End \(Instrucción\)](../../../visual-basic/language-reference/statements/end-statement.md)   
 [For Each...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [For...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Return \(Instrucción\)](../../../visual-basic/language-reference/statements/return-statement.md)   
 [Stop \(Instrucción\)](../../../visual-basic/language-reference/statements/stop-statement.md)   
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Try...Catch...Finally \(Instrucción\)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)