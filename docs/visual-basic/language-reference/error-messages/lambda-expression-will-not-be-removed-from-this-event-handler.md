---
description: 'Más información sobre: BC42326: la expresión lambda no se quitará de este controlador de eventos'
title: La expresión lambda no se quitará de este controlador de eventos
ms.date: 07/20/2015
f1_keywords:
- bc42326
- vbc42326
helpviewer_keywords:
- BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
ms.openlocfilehash: 6feb8733a6413caa564d2c930b4d35dc5697b4fe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795955"
---
# <a name="bc42326-lambda-expression-will-not-be-removed-from-this-event-handler"></a><span data-ttu-id="77e53-103">BC42326: la expresión lambda no se quitará de este controlador de eventos</span><span class="sxs-lookup"><span data-stu-id="77e53-103">BC42326: Lambda expression will not be removed from this event handler</span></span>

<span data-ttu-id="77e53-104">La expresión lambda no se quitará de este controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="77e53-104">Lambda expression will not be removed from this event handler.</span></span> <span data-ttu-id="77e53-105">Asigne la expresión lambda a una variable y use la variable para agregar y quitar el evento.</span><span class="sxs-lookup"><span data-stu-id="77e53-105">Assign the lambda expression to a variable and use the variable to add and remove the event.</span></span>

<span data-ttu-id="77e53-106">Cuando se usan expresiones lambda con controladores de eventos, es posible que no vea el comportamiento que espera.</span><span class="sxs-lookup"><span data-stu-id="77e53-106">When lambda expressions are used with event handlers, you may not see the behavior you expect.</span></span> <span data-ttu-id="77e53-107">El compilador genera un nuevo método para cada definición de expresión lambda, incluso si son idénticos.</span><span class="sxs-lookup"><span data-stu-id="77e53-107">The compiler generates a new method for each lambda expression definition, even if they are identical.</span></span> <span data-ttu-id="77e53-108">Por lo tanto, se muestra el código siguiente `False` .</span><span class="sxs-lookup"><span data-stu-id="77e53-108">Therefore, the following code displays `False`.</span></span>

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

<span data-ttu-id="77e53-109">Cuando se usan expresiones lambda con controladores de eventos, esto puede provocar resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="77e53-109">When lambda expressions are used with event handlers, this may cause unexpected results.</span></span> <span data-ttu-id="77e53-110">En el siguiente ejemplo, la expresión lambda agregada por `AddHandler` no se quita mediante la `RemoveHandler` instrucción.</span><span class="sxs-lookup"><span data-stu-id="77e53-110">In the following example, the lambda expression added by `AddHandler` is not removed by the `RemoveHandler` statement.</span></span>

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

<span data-ttu-id="77e53-111">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="77e53-111">By default, this message is a warning.</span></span> <span data-ttu-id="77e53-112">Para más información sobre cómo ocultar las advertencias o tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="77e53-112">For more information about how to hide warnings or treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

<span data-ttu-id="77e53-113">**Identificador de error:** BC42326</span><span class="sxs-lookup"><span data-stu-id="77e53-113">**Error ID:** BC42326</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="77e53-114">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="77e53-114">To correct this error</span></span>

<span data-ttu-id="77e53-115">Para evitar la advertencia y quitar la expresión lambda, asigne la expresión lambda a una variable y use la variable en las `AddHandler` instrucciones y `RemoveHandler` , tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="77e53-115">To avoid the warning and remove the lambda expression, assign the lambda expression to a variable and use the variable in both the `AddHandler` and `RemoveHandler` statements, as shown in the following example.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="77e53-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="77e53-116">See also</span></span>

- [<span data-ttu-id="77e53-117">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="77e53-117">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="77e53-118">Conversión de delegado flexible</span><span class="sxs-lookup"><span data-stu-id="77e53-118">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="77e53-119">Eventos</span><span class="sxs-lookup"><span data-stu-id="77e53-119">Events</span></span>](../../programming-guide/language-features/events/index.md)
