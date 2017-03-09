---
title: "Throw (Instrucci&#243;n, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Throw"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "control de excepciones, throw (instrucción)"
  - "control de excepciones, no estructurado"
  - "On Error (instrucción), producir excepciones"
  - "control estructurado de excepciones, throw (instrucciones)"
  - "throw (instrucción)"
  - "throw (instrucción), acerca de las instrucciones throw"
  - "producir excepciones"
  - "producir excepciones, throw (instrucción)"
  - "control de excepciones try-catch, throw (instrucciones)"
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Throw (Instrucci&#243;n, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Produce una excepción dentro de un procedimiento.  
  
## Sintaxis  
  
```  
Throw [ expression ]  
```  
  
## Parte  
 `expression`  
 Proporciona información acerca de la excepción que se va a producir.  Opcional si se encuentra en una instrucción `Catch`; en caso contrario, es necesaria.  
  
## Comentarios  
 La instrucción `Throw` produce una excepción que puede controlar con código estructurado de control de excepciones \(`Try`...`Catch`...`Finally`\) o código no estructurado de control de excepciones \(`On Error GoTo`\).  Puede utilizar la instrucción `Throw` para interceptar errores dentro del código porque Visual Basic asciende por la pila de llamadas hasta que encuentra el código de control de excepciones apropiado.  
  
 Una instrucción `Throw` sin expresiones sólo se puede utilizar en una instrucción `Catch`; en este caso, la instrucción vuelve a producir la excepción que controla la instrucción `Catch`.  
  
 La instrucción `Throw` restablece la pila de llamadas para la excepción `expression`.  Si no se proporciona `expression`, la pila de llamadas queda sin modificar.  Puede tener acceso a la pila de llamadas para la excepción a través de la propiedad <xref:System.Exception.StackTrace%2A>.  
  
## Ejemplo  
 En el siguiente código se utiliza la instrucción `Throw` para producir una excepción:  
  
 [!code-vb[VbVbalrStatements#84](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/throw-statement_1.vb)]  
  
## Requisitos  
 **Espacio de nombres:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Módulo:** `Interaction`  
  
 **Ensamblado:** biblioteca en tiempo de ejecución de Visual Basic \(en Microsoft.VisualBasic.dll\)  
  
## Vea también  
 [Try...Catch...Finally \(Instrucción\)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [On Error \(Instrucción\)](../../../visual-basic/language-reference/statements/on-error-statement.md)