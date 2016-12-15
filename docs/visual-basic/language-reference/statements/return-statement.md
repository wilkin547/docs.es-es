---
title: "Return (Instrucci&#243;n, Visual Basic) | Microsoft Docs"
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
  - "vb.Return"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "flujo de control, devolver el control a expresiones"
  - "expresiones [Visual Basic], devolver el control a"
  - "Return (instrucción)"
  - "Return (instrucción), sintaxis"
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Return (Instrucci&#243;n, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Devuelve el control al código que llamó a un procedimiento `Function`, `Sub`, `Get`, `Set` u `Operator`.  
  
## Sintaxis  
  
```  
Return  
-or-  
Return expression  
```  
  
## Parte  
 `expression`  
 Requerido en un procedimiento `Function`, `Get` u `Operator`.  Expresión que representa el valor que se devolverá al código de llamada.  
  
## Comentarios  
 En un procedimiento `Sub` o `Set`, la instrucción `Return` es equivalente a `Exit Sub` o `Exit Property`, y no se debe proporcionar un valor `expression`.  
  
 En un procedimiento `Function`, `Get` u `Operator`, la instrucción `Return` debe incluir un valor `expression` y este valor `expression` debe dar como resultado un tipo de datos que se pueda convertir al tipo de valor devuelto del procedimiento.  En un procedimiento `Function` o `Get`, también puede asignar una expresión al nombre del procedimiento para que actúe como el valor devuelto y, a continuación, ejecutar `Exit Function` o `Exit Property`.  En un procedimiento `Operator`, debe utilizar `Return``expression`.  
  
 Puede incluir tantas instrucciones `Return` en el mismo procedimiento como sea necesario.  
  
> [!NOTE]
>  El código de un bloque `Finally` se ejecuta después de encontrase con una instrucción `Return` en un bloque `Try` o `Catch`, pero antes de ejecutar dicha instrucción `Return`.  una instrucción de `Return` no se puede incluir en un bloque de `Finally` .  
  
## Ejemplo  
 En el siguiente ejemplo se usa varias veces la instrucción `Return` para volver al código de llamada cuando el procedimiento ya no tiene que hacer nada más.  
  
 [!code-vb[VbVbalrStatements#53](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/return-statement_1.vb)]  
  
## Vea también  
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Get \(Instrucción\)](../../../visual-basic/language-reference/statements/get-statement.md)   
 [Set \(Instrucción\)](../../../visual-basic/language-reference/statements/set-statement.md)   
 [Operator \(Instrucción\)](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Exit \(Instrucción\)](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [Try...Catch...Finally \(Instrucción\)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)