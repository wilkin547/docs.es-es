---
title: "Handles (Cl&#225;usula, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "Handles"
  - "vb.Handles"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Handles (palabra clave)"
ms.assetid: 1b051c0e-f499-42f6-acb5-6f4f27824b40
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Handles (Cl&#225;usula, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Declara que un procedimiento controla un evento especificado.  
  
## Sintaxis  
  
```  
  
proceduredeclaration Handles eventlist  
```  
  
## Elementos  
 `proceduredeclaration`  
 La declaración de procedimiento `Sub` del procedimiento que controlará el evento.  
  
 `eventlist`  
 Lista de los eventos que `proceduredeclaration` debe controlar, separados por comas.  Los eventos deben ser generados bien por la clase base de la clase actual o bien por un objeto declarado mediante la palabra clave `WithEvents`.  
  
## Comentarios  
 Utilice la palabra clave `Handles` al final de una declaración de procedimiento para que controle los eventos generados por una variable de objeto declarada mediante el uso de la palabra clave `WithEvents`.  La palabra clave `Handles` también puede usarse en una clase derivada para controlar eventos de una clase base.  
  
 La palabra clave `Handles` y la instrucción `AddHandler` permiten especificar que determinados procedimientos controlen eventos determinados, pero hay diferencias.  Use la palabra clave `Handles` al definir un procedimiento para especificar que controla un evento determinado.  La instrucción `AddHandler` conecta los procedimientos a los eventos en tiempo de ejecución.  Para obtener más información, vea [AddHandler \(Instrucción\)](../../../visual-basic/language-reference/statements/addhandler-statement.md).  
  
 Para los eventos personalizados, la aplicación invoca al descriptor de acceso `AddHandler` del evento cuando agrega el procedimiento como un controlador de eventos.  Para obtener más información sobre eventos personalizados, vea [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## Ejemplo  
 [!code-vb[VbVbalrEvents#2](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_1.vb)]  
  
 En el siguiente ejemplo se demuestra cómo una clase derivada puede usar la instrucción `Handles` para controlar un evento de una clase base.  
  
 [!code-vb[VbVbalrEvents#3](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_2.vb)]  
  
## Ejemplo  
 El siguiente ejemplo contiene dos controladores de eventos de botón para un proyecto **Aplicación WPF**.  
  
 [!code-vb[VbVbalrEvents#41](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_3.vb)]  
  
## Ejemplo  
 El siguiente ejemplo es equivalente al ejemplo anterior.  El `eventlist` en la cláusula `Handles` contiene los eventos de ambos botones.  
  
 [!code-vb[VbVbalrEvents#42](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/handles-clause_4.vb)]  
  
## Vea también  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)   
 [AddHandler \(Instrucción\)](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [RemoveHandler \(Instrucción\)](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Event \(Instrucción\)](../../../visual-basic/language-reference/statements/event-statement.md)   
 [RaiseEvent \(Instrucción\)](../../../visual-basic/language-reference/statements/raiseevent-statement.md)   
 [Eventos](../../../visual-basic/programming-guide/language-features/events/events.md)