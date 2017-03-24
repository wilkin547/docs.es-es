---
title: "Cómo: llamar a un controlador de eventos en Visual Basic | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers, calling
- event handlers
- procedures, event handlers
- procedures, calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c5b300feca3415d1283d24179795a4ae92c61e52
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Cómo: Llamar a un controlador de eventos en Visual Basic
Un *eventos* es una acción o aparición, como un mouse, haga clic en o un límite de crédito superado, que es reconocido por algún componente del programa y, por lo que puede escribir código para responder. Un *controlador de eventos* es el código que escriba para responder a un evento.  
  
 Un controlador de eventos en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] es un `Sub` procedimiento. Sin embargo, no normalmente se llama, la misma manera que otras `Sub` procedimientos. En su lugar, se identifica el procedimiento como un controlador para el evento. Puede hacerlo con un [controla](../../../../visual-basic/language-reference/statements/handles-clause.md) cláusula y un [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) variable, o con un [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md). Con un `Handles` cláusula es el modo predeterminado para declarar un controlador de eventos en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Esta es la manera en que los controladores de eventos se escriben por los diseñadores de programación en el entorno de desarrollo integrado (IDE). El `AddHandler` instrucción es adecuada para generar eventos de forma dinámica en tiempo de ejecución.  
  
 Cuando se produce el evento, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] llama automáticamente al procedimiento del controlador de eventos. Cualquier código que tenga acceso al evento puede hacer que se produzcan al ejecutar un [RaiseEvent (instrucción)](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).  
  
 Puede asociar más de un controlador de eventos con el mismo evento. En algunos casos, puede desasociar un controlador de un evento. Para obtener más información, consulte [eventos](../../../../visual-basic/programming-guide/language-features/events/index.md).  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>Para llamar a un controlador de eventos utilizando Handles y WithEvents  
  
1.  Asegúrese de que el evento se declara con un [Event (instrucción)](../../../../visual-basic/language-reference/statements/event-statement.md).  
  
2.  Declare una variable de objeto en el módulo o clase nivel, con el [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) (palabra clave). El `As` cláusula de esta variable debe especificar la clase que provoca el evento.  
  
3.  En la declaración de control de eventos `Sub` procedimiento, agregue un [controla](../../../../visual-basic/language-reference/statements/handles-clause.md) cláusula que especifica la `WithEvents` variable y el nombre del evento.  
  
4.  Cuando se produce el evento, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] llama automáticamente a la `Sub` procedimiento. El código puede utilizar un `RaiseEvent` instrucción para hacer que se produzca el evento.  
  
     En el ejemplo siguiente se define un evento y un `WithEvents` variable que hace referencia a la clase que provoca el evento. El control de eventos `Sub` procedimiento utiliza un `Handles` cláusula para especificar la clase y controla el evento.  
  
     [!code-vb[VbVbcnProcedures Nº&4;](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a>Para llamar a un controlador de eventos mediante AddHandler  
  
1.  Asegúrese de que el evento se declara con un `Event` instrucción.  
  
2.  Ejecutar un [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md) para conectar de forma dinámica el control de eventos `Sub` procedimiento con el evento.  
  
3.  Cuando se produce el evento, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] llama automáticamente a la `Sub` procedimiento. El código puede utilizar un `RaiseEvent` instrucción para hacer que se produzca el evento.  
  
     En el ejemplo siguiente se define un `Sub` procedimiento para controlar la <xref:System.Windows.Forms.Form.Closing>eventos de un formulario.</xref:System.Windows.Forms.Form.Closing> A continuación, utiliza el [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md) para asociar el `catchClose` procedimiento como un controlador de eventos <xref:System.Windows.Forms.Form.Closing>.</xref:System.Windows.Forms.Form.Closing>  
  
     [!code-vb[VbVbcnProcedures&#5;](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]  
  
     Puede desasociar un controlador de eventos de un evento ejecutando la [RemoveHandler (instrucción)](../../../../visual-basic/language-reference/statements/removehandler-statement.md).  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)   
 [Sub (procedimientos)](./sub-procedures.md)   
 [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [AddressOf (operador)](../../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Cómo: crear un procedimiento](./how-to-create-a-procedure.md)   
 [Llamar a un procedimiento que no devuelve un valor](./how-to-call-a-procedure-that-does-not-return-a-value.md)
