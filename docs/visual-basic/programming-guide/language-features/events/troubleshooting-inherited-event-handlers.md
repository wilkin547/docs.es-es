---
title: "Solucionar problemas de controladores de eventos heredados en Visual Basic | Microsoft Docs"
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
  - "controladores de eventos, solucionar problemas"
  - "control de eventos, solucionar problemas"
  - "eventos heredados"
  - "solucionar problemas de eventos"
  - "solucionar problemas de Visual Basic, controladores de eventos"
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Solucionar problemas de controladores de eventos heredados en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Este tema enumera problemas comunes que surgen con controladores de eventos en componentes heredados.  
  
## Procedimientos  
  
#### El código de un controlador de eventos se ejecuta dos veces por llamada  
  
-   Un controlador de eventos heredado no debe incluir una cláusula [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md).  El método de la clase base está asociado ya con el evento y se iniciará en consecuencia.  Quite la cláusula `Handles` del método heredado.  
  
     [!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#32)]  
  
-   Si el método heredado no tiene una palabra clave `Handles`, compruebe que el código no contiene una instrucción [AddHandler \(Instrucción\)](../../../../visual-basic/language-reference/statements/addhandler-statement.md) o métodos adicionales que controlen el mismo evento.  
  
## Vea también  
 [Eventos](../../../../visual-basic/programming-guide/language-features/events/events.md)