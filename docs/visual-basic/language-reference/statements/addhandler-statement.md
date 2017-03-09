---
title: "AddHandler (Instrucci&#243;n) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.AddHandlerMethod"
  - "addhandler"
  - "vb.addhandler"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "AddHandler (instrucción)"
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# AddHandler (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Asocia un evento a un controlador de eventos en tiempo de ejecución.  
  
## Sintaxis  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## Elementos  
 `event`  
 Nombre del evento que se va a controlar.  
  
 `eventhandler`  
 Nombre del procedimiento que controlará el evento.  
  
## Comentarios  
 Las instrucciones `AddHandler` y `RemoveHandler` permiten iniciar y detener el controlador del evento en cualquier momento de la ejecución del programa.  
  
 La firma del procedimiento `eventhandler` debe coincidir con la firma del evento `event`.  
  
 La palabra clave `Handles` y la instrucción `AddHandler` permiten especificar que ciertos procedimientos controlen eventos determinados, pero hay diferencias entre ambos.  La instrucción `AddHandler` conecta los procedimientos a los eventos en tiempo de ejecución.  Utilice la palabra clave `Handles` al definir un procedimiento para especificar que controla un evento determinado.  Para obtener más información, vea [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).  
  
> [!NOTE]
>  En los eventos personalizados, la instrucción `AddHandler` invoca al descriptor de acceso `AddHandler` del evento.  Para obtener más información sobre eventos personalizados, vea [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## Ejemplo  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#17)]  
  
## Vea también  
 [RemoveHandler \(Instrucción\)](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Eventos](../../../visual-basic/programming-guide/language-features/events/events.md)