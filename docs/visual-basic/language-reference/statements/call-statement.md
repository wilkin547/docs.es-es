---
title: "Call (Instrucci&#243;n, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Call"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Call (instrucción)"
  - "procedimientos, Call (instrucción)"
  - "procedimientos, llamar"
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Call (Instrucci&#243;n, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Transfiere el control a un procedimiento `Function`, a un procedimiento `Sub` o a un procedimiento de la biblioteca de vínculos dinámicos \(DLL\).  
  
## Sintaxis  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## Elementos  
 `procedureName`  
 Obligatorio.  Nombre del procedimiento al que se llama.  
  
 `argumentList`  
 Opcional.  Lista de variables o expresiones que representan los argumentos que se pasan al procedimiento cuando se le llama.  Los argumentos múltiples se separan por comas.  Si se incluye `argumentList`, debe encerrarlo entre paréntesis.  
  
## Comentarios  
 Puede utilizar la palabra clave de `Call` cuando llama a un procedimiento.  Para la mayoría de las llamadas a procedimiento, no es necesario usar esta palabra clave.  
  
 Normalmente se utiliza la palabra clave de `Call` cuando la expresión denominada no comienza con un identificador.  El uso de la palabra clave de `Call` para otros usos no se recomienda.  
  
 Si el procedimiento devuelve un valor, la instrucción `Call` lo descarta.  
  
## Ejemplo  
 El código siguiente se muestran los dos ejemplos donde es necesaria la palabra clave de `Call` llamar a un procedimiento.  En ambos ejemplos, la expresión denominada no comienza con un identificador.  
  
 [!code-vb[VbVbalrStatements#97](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/call-statement_1.vb)]  
  
## Vea también  
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)