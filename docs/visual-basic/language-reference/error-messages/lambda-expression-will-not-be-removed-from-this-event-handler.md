---
title: La expresión lambda no se quitará de este controlador de eventos
ms.date: 07/20/2015
f1_keywords:
- bc42326
- vbc42326
helpviewer_keywords:
- BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
ms.openlocfilehash: 07ace3f1b9c5e512227dc1f718ef768b631c8303
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397381"
---
# <a name="lambda-expression-will-not-be-removed-from-this-event-handler"></a>La expresión lambda no se quitará de este controlador de eventos

La expresión lambda no se quitará de este controlador de eventos. Asigne la expresión lambda a una variable y use la variable para agregar y quitar el evento.

Cuando se usan expresiones lambda con controladores de eventos, es posible que no vea el comportamiento que espera. El compilador genera un nuevo método para cada definición de expresión lambda, incluso si son idénticos. Por lo tanto, se muestra el código siguiente `False` .

```vb
Module Module1

    Sub Main()
        Dim fun1 As ChangeInteger = Function(p As Integer) p + 1
        Dim fun2 As ChangeInteger = Function(p As Integer) p + 1
        Console.WriteLine(fun1 = fun2)
    End Sub

    Delegate Function ChangeInteger(ByVal x As Integer) As Integer

End Module
```

Cuando se usan expresiones lambda con controladores de eventos, esto puede provocar resultados inesperados. En el siguiente ejemplo, la expresión lambda agregada por `AddHandler` no se quita mediante la `RemoveHandler` instrucción.

```vb
Module Module1

    Event ProcessInteger(ByVal x As Integer)

    Sub Main()

        ' The following line adds one listener to the event.
        AddHandler ProcessInteger, Function(m As Integer) m

        ' The following statement searches the current listeners
        ' for a match to remove. However, this lambda is not the same
        ' as the previous one, so nothing is removed.
        RemoveHandler ProcessInteger, Function(m As Integer) m

    End Sub
End Module
```

De forma predeterminada, este mensaje es una advertencia. Para más información sobre cómo ocultar las advertencias o tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

**Identificador de error:** BC42326

## <a name="to-correct-this-error"></a>Para corregir este error

Para evitar la advertencia y quitar la expresión lambda, asigne la expresión lambda a una variable y use la variable en las `AddHandler` instrucciones y `RemoveHandler` , tal y como se muestra en el ejemplo siguiente.

```vb
Module Module1

    Event ProcessInteger(ByVal x As Integer)

    Dim PrintHandler As ProcessIntegerEventHandler

    Sub Main()

        ' Assign the lambda expression to a variable.
        PrintHandler = Function(m As Integer) m

        ' Use the variable to add the listener.
        AddHandler ProcessInteger, PrintHandler

        ' Use the variable again when you want to remove the listener.
        RemoveHandler ProcessInteger, PrintHandler

    End Sub
End Module
```

## <a name="see-also"></a>Consulte también

- [Expresiones lambda](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [Conversión de delegado flexible](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Eventos](../../programming-guide/language-features/events/index.md)
