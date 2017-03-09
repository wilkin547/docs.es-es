---
title: "RemoveHandler (Instrucci&#243;n) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.RemoveHandlerMethod"
  - "vb.RemoveHandler"
  - "RemoveHandler"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "RemoveHandler (palabra clave)"
  - "RemoveHandler (instrucción)"
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# RemoveHandler (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Quita la asociación entre un evento y un controlador de eventos.  
  
## Sintaxis  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`event`|Nombre del evento que se va a controlar.|  
|`eventhandler`|Nombre del procedimiento que controla actualmente el evento.|  
  
## Comentarios  
 Las instrucciones `AddHandler` y `RemoveHandler` permiten iniciar y detener el control del evento de un evento específico en cualquier momento de la ejecución del programa.  
  
> [!NOTE]
>  Para los eventos personalizados, la instrucción `RemoveHandler` llama al descriptor de acceso `RemoveHandler` del evento.  Para obtener más información sobre eventos personalizados, vea [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## Ejemplo  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#17)]  
  
## Vea también  
 [AddHandler \(Instrucción\)](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Eventos](../../../visual-basic/programming-guide/language-features/events/events.md)