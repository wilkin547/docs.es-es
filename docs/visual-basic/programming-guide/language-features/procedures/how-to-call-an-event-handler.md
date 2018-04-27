---
title: 'Cómo: Llamar a un controlador de eventos en Visual Basic'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2b8a35459fdeb7cce0b494a9b3024a79bd4173cc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Cómo: Llamar a un controlador de eventos en Visual Basic
Un *eventos* es una acción o una aparición, como un mouse, haga clic en o un límite de crédito superado, que es reconocido por algún componente del programa y, por lo que puede escribir código para responder. Un *controlador de eventos* es el código que escribe para responder a un evento.  
  
 Un controlador de eventos en Visual Basic es un `Sub` procedimiento. Sin embargo, no normalmente se llama, la misma manera que otras `Sub` procedimientos. En su lugar, se identifica el procedimiento como un controlador para el evento. Puede hacerlo con un [controla](../../../../visual-basic/language-reference/statements/handles-clause.md) cláusula y un [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variable, o con un [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md). Mediante un `Handles` cláusula es el modo predeterminado para declarar un controlador de eventos en Visual Basic. Esta es la manera en que los controladores de eventos se escriben los diseñadores al programar en el entorno de desarrollo integrado (IDE). El `AddHandler` instrucción es adecuada para generar eventos de forma dinámica en tiempo de ejecución.  
  
 Cuando se produce el evento, Visual Basic llama automáticamente al procedimiento del controlador de eventos. Cualquier código que tenga acceso al evento puede hacer que se producen al ejecutar un [RaiseEvent (instrucción)](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).  
  
 Puede asociar más de un controlador de eventos con el mismo evento. En algunos casos puede desasociar un controlador de un evento. Para más información, vea [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md).  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>Para llamar a un controlador de eventos utilizando Handles y WithEvents  
  
1.  Asegúrese de que el evento se declara con un [Event (instrucción)](../../../../visual-basic/language-reference/statements/event-statement.md).  
  
2.  Declare una variable de objeto en el módulo o clase nivel, con el [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) palabra clave. El `As` cláusula para esta variable debe especificar la clase que provoca el evento.  
  
3.  En la declaración de control de eventos `Sub` procedimiento, agregue un [controla](../../../../visual-basic/language-reference/statements/handles-clause.md) cláusula que especifica la `WithEvents` variable y el nombre del evento.  
  
4.  Cuando se produce el evento, Visual Basic llama automáticamente a la `Sub` procedimiento. El código puede usar un `RaiseEvent` instrucción que se va a hacer que se produzca el evento.  
  
     En el ejemplo siguiente se define un evento y un `WithEvents` variable que hace referencia a la clase que provoca el evento. El control de eventos `Sub` procedimiento usa un `Handles` cláusula para especificar la clase y controla el evento.  
  
     [!code-vb[VbVbcnProcedures#4](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a>Para llamar a un controlador de eventos utilizando AddHandler  
  
1.  Asegúrese de que el evento se declara con un `Event` instrucción.  
  
2.  Ejecutar un [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md) para conectar de forma dinámica el control de eventos `Sub` procedimiento con el evento.  
  
3.  Cuando se produce el evento, Visual Basic llama automáticamente a la `Sub` procedimiento. El código puede usar un `RaiseEvent` instrucción que se va a hacer que se produzca el evento.  
  
     En el ejemplo siguiente se define un `Sub` procedimiento para controlar la <xref:System.Windows.Forms.Form.Closing> eventos de un formulario. A continuación, utiliza el [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md) para asociar el `catchClose` procedimiento como un controlador de eventos para <xref:System.Windows.Forms.Form.Closing>.  
  
     [!code-vb[VbVbcnProcedures#5](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]  
  
     Puede anular la asociación de un controlador de eventos de un evento mediante la ejecución de la [RemoveHandler (instrucción)](../../../../visual-basic/language-reference/statements/removehandler-statement.md).  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)  
 [Subprocedimientos](./sub-procedures.md)  
 [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [AddressOf (operador)](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Crear un procedimiento](./how-to-create-a-procedure.md)  
 [Llamar a un procedimiento que no devuelve un valor](./how-to-call-a-procedure-that-does-not-return-a-value.md)
