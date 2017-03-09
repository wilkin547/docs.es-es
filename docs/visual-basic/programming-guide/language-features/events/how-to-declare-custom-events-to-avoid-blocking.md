---
title: "C&#243;mo: Declarar eventos personalizados para evitar bloqueos (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "eventos personalizados"
  - "declarar eventos, personalizados"
  - "eventos [Visual Basic], personalizados"
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# C&#243;mo: Declarar eventos personalizados para evitar bloqueos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Hay varias circunstancias en las que resulta importante que un controlador de eventos no bloquee los controladores de eventos subsiguientes.  Los eventos personalizados permiten al evento llamar de forma asincrónica a sus controladores de eventos.  
  
 De manera predeterminada, el campo de almacén de respaldo de una declaración de evento es un delegado multidifusión que combina de forma consecutiva todos los controladores de eventos.  Esto significa que si un controlador tarda mucho tiempo en completarse, bloquea a los demás controladores hasta que finaliza.  \(Los controladores de eventos con buen comportamiento no deben realizar operaciones largas ni que puedan producir bloqueos.\)  
  
 En lugar de utilizar la implementación predeterminada de eventos que proporciona Visual Basic, puede utilizar un evento personalizado para ejecutar los controladores de eventos de forma asincrónica.  
  
## Ejemplo  
 En este ejemplo, el descriptor de acceso `AddHandler` agrega el delegado para cada controlador del evento `Click` en un elemento <xref:System.Collections.ArrayList> almacenado en el campo `EventHandlerList`.  
  
 Cuando el código provoca el evento `Click`, el descriptor de acceso `RaiseEvent` invoca a todos los delegados del controlador de eventos de forma asincrónica con el método <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>.  Ese método invoca cada controlador en un subproceso de trabajo y vuelve inmediatamente, por lo que los controladores no se pueden bloquear entre si.  
  
 [!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#27)]  
  
## Vea también  
 <xref:System.Collections.ArrayList>   
 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>   
 [Eventos](../../../../visual-basic/programming-guide/language-features/events/events.md)   
 [Cómo: Declarar eventos personalizados para conservar memoria](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)