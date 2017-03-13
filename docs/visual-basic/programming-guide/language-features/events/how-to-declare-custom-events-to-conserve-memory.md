---
title: "C&#243;mo: Declarar eventos personalizados para conservar memoria (Visual Basic) | Microsoft Docs"
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
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# C&#243;mo: Declarar eventos personalizados para conservar memoria (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Hay varias circunstancias en las que es importante que una aplicación mantenga un bajo uso de memoria.  Los eventos personalizados permiten a la aplicación utilizar memoria sólo para los eventos que controla.  
  
 De manera predeterminada, cuando una clase declara un evento, el compilador asigna memoria para que un campo almacene información de eventos.  Si una clase tiene muchos eventos no usados, ocupan memoria inútilmente.  
  
 En lugar de utilizar la implementación predeterminada de los eventos que Visual Basic proporciona, puede utilizar los eventos personalizados para administrar más cuidadosamente el uso de memoria.  
  
## Ejemplo  
 En este ejemplo, la clase utiliza una instancia de la clase <xref:System.ComponentModel.EventHandlerList>, almacenada en el campo `Events`, para guardar información sobre los eventos que están en uso.  La clase <xref:System.ComponentModel.EventHandlerList> es una clase de lista optimizada diseñada para contener delegados.  
  
 Todos los eventos de la clase usan el campo `Events` para realizar un seguimiento de qué métodos está controlando cada evento.  
  
 [!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## Vea también  
 <xref:System.ComponentModel.EventHandlerList>   
 [Eventos](../../../../visual-basic/programming-guide/language-features/events/events.md)   
 [Cómo: Declarar eventos personalizados para evitar bloqueos](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)