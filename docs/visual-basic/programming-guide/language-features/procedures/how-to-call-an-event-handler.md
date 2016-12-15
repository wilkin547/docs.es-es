---
title: "C&#243;mo: Llamar a un controlador de eventos en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "controladores de eventos"
  - "controladores de eventos, llamar"
  - "procedimientos, llamar"
  - "procedimientos, controladores de eventos"
  - "código de Visual Basic, procedimientos"
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Llamar a un controlador de eventos en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Un *evento* es una acción o un suceso \(por ejemplo, cuando se hace clic con el mouse o cuando se supera un límite de crédito\) que reconoce algún componente del programa y para el cual puede escribirse un código de respuesta.  Un *controlador de eventos* es el código que se escribe para responder a un evento.  
  
 En [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], un controlador de eventos es un procedimiento `Sub`.  Sin embargo, normalmente no se llama a este procedimiento del mismo modo que a otros procedimientos `Sub`;  sino que se identifica el procedimiento como un controlador del evento.  Esto puede hacerse con una cláusula [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) y una variable [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) o con una instrucción [AddHandler \(Instrucción\)](../../../../visual-basic/language-reference/statements/addhandler-statement.md).  En [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], de manera predeterminada se utiliza una cláusula `Handles` para declarar un controlador de eventos.  Ésta es la técnica que utilizan los diseñadores para escribir los controladores de eventos cuando programan en el entorno de desarrollo integrado \(IDE\).  La instrucción `AddHandler` resulta conveniente para desencadenar eventos de forma dinámica en tiempo de ejecución.  
  
 Cuando se produce el evento, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] llama automáticamente al procedimiento del controlador de eventos.  Cualquier código que tenga acceso al evento puede hacer que éste se desencadene ejecutando [RaiseEvent \(Instrucción\)](../../../../visual-basic/language-reference/statements/raiseevent-statement.md).  
  
 Puede asociar más de un controlador de eventos al mismo evento.  En algunos casos, puede desasociar un controlador de un evento.  Para obtener más información, vea [Eventos](../../../../visual-basic/programming-guide/language-features/events/events.md).  
  
### Para llamar a un controlador de eventos utilizando Handles y WithEvents  
  
1.  Asegúrese de que el evento se declara con una instrucción [Event \(Instrucción\)](../../../../visual-basic/language-reference/statements/event-statement.md).  
  
2.  Declare una variable de objeto en el nivel de módulo o de clase utilizando la palabra clave [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).  La cláusula `As` de esta variable debe especificar la clase que produce el evento.  
  
3.  En la declaración del procedimiento `Sub` de control de eventos, agregue una cláusula [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) que especifique la variable `WithEvents` y el nombre del evento.  
  
4.  Cuando se produce el evento, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] llama automáticamente al procedimiento `Sub`.  El código puede utilizar una instrucción `RaiseEvent` para desencadenar el evento.  
  
     En el ejemplo siguiente se define un evento y una variable `WithEvents` que hace referencia a la clase que desencadena el evento.  El procedimiento `Sub` de control de eventos utiliza una cláusula `Handles` para especificar la clase y el evento que ésta controla.  
  
     [!code-vb[VbVbcnProcedures#4](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]  
  
### Para llamar a un controlador de eventos utilizando AddHandler  
  
1.  Asegúrese de que el evento se declara con una instrucción `Event`.  
  
2.  Ejecute una instrucción [AddHandler \(Instrucción\)](../../../../visual-basic/language-reference/statements/addhandler-statement.md) para conectar de forma dinámica el procedimiento `Sub` de control de eventos con el evento.  
  
3.  Cuando se produce el evento, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] llama automáticamente al procedimiento `Sub`.  El código puede utilizar una instrucción `RaiseEvent` para desencadenar el evento.  
  
     En el ejemplo siguiente se define un procedimiento `Sub` que controla el evento <xref:System.Windows.Forms.Form.Closing> de un formulario.  A continuación, utiliza la instrucción [AddHandler \(Instrucción\)](../../../../visual-basic/language-reference/statements/addhandler-statement.md) para asociar el procedimiento `catchClose` como un controlador del evento <xref:System.Windows.Forms.Form.Closing>.  
  
     [!code-vb[VbVbcnProcedures#5](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]  
  
     Puede desasociar un controlador de eventos de un evento ejecutando [RemoveHandler \(Instrucción\)](../../../../visual-basic/language-reference/statements/removehandler-statement.md).  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedimientos Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Sub \(Instrucción\)](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [AddressOf \(Operador\)](../../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Cómo: crear un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure.md)   
 [Cómo: Llamar a un procedimiento que no devuelve un valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-does-not-return-a-value.md)