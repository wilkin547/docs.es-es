---
title: Cómo llamar a un controlador de eventos
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
no-loc:
- WithEvents
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 3762c79dd3d883ae2ccfe76b335cf98ac87d4246
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "89464966"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Cómo llamar a un controlador de eventos en Visual Basic

Un *evento* es una acción o una repetición, como un clic del mouse o un límite de crédito superado, que es reconocido por algún componente del programa y para el que puede escribir código para responder. Un *controlador de eventos* es el código que se escribe para responder a un evento.

Un controlador de eventos en Visual Basic es un `Sub` procedimiento. Sin embargo, normalmente no se llama de la misma manera que otros `Sub` procedimientos. En su lugar, identifique el procedimiento como un controlador para el evento. Puede hacerlo con una [`Handles`](../../../language-reference/statements/handles-clause.md) cláusula y una [`WithEvents`](../../../language-reference/modifiers/withevents.md) variable, o con una [instrucción AddHandler](../../../language-reference/statements/addhandler-statement.md). El uso de una `Handles` cláusula es la forma predeterminada de declarar un controlador de eventos en Visual Basic. Esta es la forma en que los diseñadores escriben los controladores de eventos cuando se programa en el entorno de desarrollo integrado (IDE). La `AddHandler` instrucción es adecuada para generar eventos dinámicamente en tiempo de ejecución.

Cuando se produce el evento, Visual Basic llama automáticamente al procedimiento de controlador de eventos. Cualquier código que tenga acceso al evento puede hacer que se produzca ejecutando una [instrucción RaiseEvent](../../../language-reference/statements/raiseevent-statement.md).

Puede asociar más de un controlador de eventos con el mismo evento. En algunos casos, puede desasociar un controlador de un evento. Para más información, vea [Eventos](../events/index.md).

## <a name="call-an-event-handler-using-no-loc-texthandles-and-no-locwithevents"></a>Llamar a un controlador de eventos mediante :::no-loc text="Handles"::: y WithEvents

1. Asegúrese de que el evento se declara con una [instrucción de evento](../../../language-reference/statements/event-statement.md).

2. Declare una variable de objeto en el nivel de módulo o de clase, mediante la [`WithEvents`](../../../language-reference/modifiers/withevents.md) palabra clave. La `As` cláusula para esta variable debe especificar la clase que genera el evento.

3. En la declaración del procedimiento de control de eventos `Sub` , agregue una [`Handles`](../../../language-reference/statements/handles-clause.md) cláusula que especifique la `WithEvents` variable y el nombre del evento.

4. Cuando se produce el evento, Visual Basic llama automáticamente al `Sub` procedimiento. El código puede utilizar una `RaiseEvent` instrucción para que se produzca el evento.

    En el ejemplo siguiente se define un evento y una `WithEvents` variable que hace referencia a la clase que genera el evento. El procedimiento de control de eventos `Sub` utiliza una `Handles` cláusula para especificar la clase y el evento que administra.

    :::code language="vb" source="snippets/how-to-call-an-event-handler/SpecialForm.vb" id="4":::

## <a name="call-an-event-handler-using-addhandler"></a>Llamar a un controlador de eventos mediante AddHandler

1. Asegúrese de que el evento se declara con una `Event` instrucción.

2. Ejecute una [instrucción AddHandler](../../../language-reference/statements/addhandler-statement.md) para conectar dinámicamente el procedimiento de control de eventos `Sub` con el evento.

3. Cuando se produce el evento, Visual Basic llama automáticamente al `Sub` procedimiento. El código puede utilizar una `RaiseEvent` instrucción para que se produzca el evento.

    En el ejemplo siguiente se usa la [instrucción AddHandler](../../../language-reference/statements/addhandler-statement.md) en el constructor para asociar el `OnFormClosing` procedimiento como un controlador de eventos para <xref:System.Windows.Forms.Form.FormClosing> .

    :::code language="vb" source="snippets/how-to-call-an-event-handler/SpecialForm.vb" id="5":::

    Puede desasociar un controlador de eventos de un evento ejecutando la [instrucción RemoveHandler](../../../language-reference/statements/removehandler-statement.md).

## <a name="see-also"></a>Consulte también

- [Procedimientos](index.md)
- [Procedimientos Sub](sub-procedures.md)
- [Instrucción Sub](../../../language-reference/statements/sub-statement.md)
- [AddressOf (operador)](../../../language-reference/operators/addressof-operator.md)
- [Procedimiento para crear un procedimiento](how-to-create-a-procedure.md)
- [Procedimiento apara llamar a un procedimiento que no devuelve un valor](how-to-call-a-procedure-that-does-not-return-a-value.md)
