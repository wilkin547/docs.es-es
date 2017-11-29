---
title: "Cómo: Declarar eventos personalizados para conservar memoria (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: eec9a2fc687f481ab40313e35cbde81c25b81ae8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a>Cómo: Declarar eventos personalizados para conservar memoria (Visual Basic)
Hay varias circunstancias cuando es importante que una aplicación mantener el uso de memoria baja. Eventos personalizados que la aplicación pueda utilizar memoria sólo para los eventos que administra.  
  
 De forma predeterminada, cuando una clase declara un evento, el compilador asigna memoria para un campo almacenar la información del evento. Si una clase tiene muchos eventos no usados, innecesariamente ocupan memoria.  
  
 En lugar de usar la implementación predeterminada de eventos que proporciona Visual Basic, puede usar eventos personalizados para administrar el uso de memoria más detenidamente.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, la clase utiliza una instancia de la <xref:System.ComponentModel.EventHandlerList> (clase), almacenado en el `Events` campo para almacenar información sobre los eventos en uso. El <xref:System.ComponentModel.EventHandlerList> es una clase de lista optimizada diseñada para contener delegados.  
  
 Todos los eventos de la clase usan el `Events` campo para realizar un seguimiento de qué métodos está controlando cada evento.  
  
 [!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ComponentModel.EventHandlerList>  
 [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Declarar eventos personalizados para evitar bloqueos](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
