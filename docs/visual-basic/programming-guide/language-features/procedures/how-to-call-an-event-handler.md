---
title: Filtrar Llamar a un controlador de eventos en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 3690d1c2eb8ece9059b8b25b5a14bef2021bc8f6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59320176"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Filtrar Llamar a un controlador de eventos en Visual Basic
Un *eventos* es una acción o aparición, como un mouse ha superado un límite de crédito o haga clic en, que es reconocido por algún componente del programa, y para el que puede escribir código para responder. Un *controlador de eventos* es el código que escribe para responder a un evento.  
  
 Un controlador de eventos en Visual Basic es un `Sub` procedimiento. Sin embargo, no normalmente se llama, la misma manera que otras `Sub` procedimientos. En su lugar, se identifica el procedimiento como un controlador para el evento. Puede hacerlo con un [controla](../../../../visual-basic/language-reference/statements/handles-clause.md) cláusula y un [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variable, o con un [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md). Mediante un `Handles` cláusula es el modo predeterminado para declarar un controlador de eventos en Visual Basic. Esta es la manera en que los controladores de eventos se escriben los diseñadores al programar en el entorno de desarrollo integrado (IDE). El `AddHandler` instrucción es adecuada para generar eventos de forma dinámica en tiempo de ejecución.  
  
 Cuando se produce el evento, Visual Basic llama automáticamente al procedimiento del controlador de eventos. Cualquier código que tenga acceso a los eventos puede provocar que se produzcan al ejecutar un [RaiseEvent (instrucción)](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).  
  
 Puede asociar más de un controlador de eventos con el mismo evento. En algunos casos puede desasociar un controlador de un evento. Para más información, vea [Eventos](../../../../visual-basic/programming-guide/language-features/events/index.md).  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>Para llamar a un controlador de eventos con identificadores y WithEvents  
  
1. Asegúrese de que el evento se declara con un [Event (instrucción)](../../../../visual-basic/language-reference/statements/event-statement.md).  
  
2. Declare una variable de objeto en el módulo o clase de nivel, con el [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) palabra clave. El `As` cláusula para esta variable debe especificar la clase que provoca el evento.  
  
3. En la declaración de control de eventos `Sub` procedimiento, agregue un [controla](../../../../visual-basic/language-reference/statements/handles-clause.md) cláusula que especifica el `WithEvents` variable y el nombre del evento.  
  
4. Cuando se produce el evento, Visual Basic llama automáticamente el `Sub` procedimiento. El código puede usar un `RaiseEvent` instrucción para hacer que se produzca el evento.  
  
     En el ejemplo siguiente se define un evento y un `WithEvents` variable que hace referencia a la clase que provoca el evento. El control de eventos `Sub` procedimiento usa un `Handles` cláusula para especificar la clase y que controla el evento.  
  
     [!code-vb[VbVbcnProcedures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#4)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a>Para llamar a un controlador de eventos mediante AddHandler  
  
1. Asegúrese de que el evento se declara con un `Event` instrucción.  
  
2. Ejecutar un [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md) para conectar de forma dinámica el control de eventos `Sub` procedimiento con el evento.  
  
3. Cuando se produce el evento, Visual Basic llama automáticamente el `Sub` procedimiento. El código puede usar un `RaiseEvent` instrucción para hacer que se produzca el evento.  
  
     En el ejemplo siguiente se define un `Sub` procedimiento para controlar el <xref:System.Windows.Forms.Form.Closing> eventos de un formulario. A continuación, usa el [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md) para asociar el `catchClose` procedimiento como un controlador de eventos <xref:System.Windows.Forms.Form.Closing>.  
  
     [!code-vb[VbVbcnProcedures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#5)]  
  
     Puede desasociar un controlador de eventos a un evento mediante la ejecución de la [RemoveHandler (instrucción)](../../../../visual-basic/language-reference/statements/removehandler-statement.md).  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Procedimientos Sub](./sub-procedures.md)
- [Sub (Instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [AddressOf (Operador)](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Filtrar para crear un procedimiento](./how-to-create-a-procedure.md)
- [Filtrar apara llamar a un procedimiento que no devuelve un valor](./how-to-call-a-procedure-that-does-not-return-a-value.md)
