---
title: 'Cómo: llamar a un controlador de eventos'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 0c626a9ad92fe2cd0ea117a9abdd2965a09df2ea
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340424"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Cómo: Llamar a un controlador de eventos en Visual Basic

Un *evento* es una acción o una repetición, como un clic del mouse o un límite de crédito superado, que es reconocido por algún componente del programa y para el que puede escribir código para responder. Un *controlador de eventos* es el código que se escribe para responder a un evento.

 Un controlador de eventos en Visual Basic es un procedimiento `Sub`. Sin embargo, normalmente no se llama de la misma manera que otros procedimientos de `Sub`. En su lugar, identifique el procedimiento como un controlador para el evento. Puede hacerlo con una cláusula [Handles](../../../language-reference/statements/handles-clause.md) y una variable [WithEvents](../../../language-reference/modifiers/withevents.md) , o con una [instrucción AddHandler](../../../language-reference/statements/addhandler-statement.md). Usar una cláusula `Handles` es la forma predeterminada de declarar un controlador de eventos en Visual Basic. Esta es la forma en que los diseñadores escriben los controladores de eventos cuando se programa en el entorno de desarrollo integrado (IDE). La instrucción `AddHandler` es adecuada para generar eventos dinámicamente en tiempo de ejecución.

 Cuando se produce el evento, Visual Basic llama automáticamente al procedimiento de controlador de eventos. Cualquier código que tenga acceso al evento puede hacer que se produzca ejecutando una [instrucción RaiseEvent](../../../language-reference/statements/raiseevent-statement.md).

 Puede asociar más de un controlador de eventos con el mismo evento. En algunos casos, puede desasociar un controlador de un evento. Para obtener más información, consulta [Eventos](../events/index.md).

### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>Para llamar a un controlador de eventos mediante handles y WithEvents

1. Asegúrese de que el evento se declara con una [instrucción de evento](../../../language-reference/statements/event-statement.md).

2. Declare una variable de objeto en el nivel de módulo o de clase mediante la palabra clave [WithEvents](../../../language-reference/modifiers/withevents.md) . La cláusula `As` para esta variable debe especificar la clase que genera el evento.

3. En la declaración del procedimiento de `Sub` de control de eventos, agregue una cláusula [Handles](../../../language-reference/statements/handles-clause.md) que especifique la variable `WithEvents` y el nombre del evento.

4. Cuando se produce el evento, Visual Basic llama automáticamente al procedimiento `Sub`. El código puede utilizar una instrucción `RaiseEvent` para que se produzca el evento.

     En el ejemplo siguiente se define un evento y una variable `WithEvents` que hace referencia a la clase que genera el evento. El procedimiento de `Sub` de control de eventos utiliza una cláusula `Handles` para especificar la clase y el evento que administra.

     [!code-vb[VbVbcnProcedures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#4)]

### <a name="to-call-an-event-handler-using-addhandler"></a>Para llamar a un controlador de eventos mediante AddHandler

1. Asegúrese de que el evento se declara con una instrucción `Event`.

2. Ejecute una [instrucción AddHandler](../../../language-reference/statements/addhandler-statement.md) para conectar dinámicamente el procedimiento de `Sub` de control de eventos con el evento.

3. Cuando se produce el evento, Visual Basic llama automáticamente al procedimiento `Sub`. El código puede utilizar una instrucción `RaiseEvent` para que se produzca el evento.

     En el ejemplo siguiente se define un procedimiento `Sub` para controlar el evento de <xref:System.Windows.Forms.Form.Closing> de un formulario. A continuación, usa la [instrucción AddHandler](../../../language-reference/statements/addhandler-statement.md) para asociar el procedimiento `catchClose` como un controlador de eventos para <xref:System.Windows.Forms.Form.Closing>.

     [!code-vb[VbVbcnProcedures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#5)]

     Puede desasociar un controlador de eventos de un evento ejecutando la [instrucción RemoveHandler](../../../language-reference/statements/removehandler-statement.md).

## <a name="see-also"></a>Vea también

- [Procedimientos](index.md)
- [Subprocedimientos](sub-procedures.md)
- [Sub (instrucción)](../../../language-reference/statements/sub-statement.md)
- [AddressOf (operador)](../../../language-reference/operators/addressof-operator.md)
- [Crear un procedimiento](how-to-create-a-procedure.md)
- [Llamar a un procedimiento que no devuelve un valor](how-to-call-a-procedure-that-does-not-return-a-value.md)
