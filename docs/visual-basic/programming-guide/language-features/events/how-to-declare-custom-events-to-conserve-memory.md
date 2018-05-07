---
title: 'Cómo: Declarar eventos personalizados para conservar memoria (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: d19c91d66e458ca2317dc049d517b92fa7406ef6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
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
