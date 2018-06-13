---
title: La expresión lambda no se quitará de este controlador de eventos
ms.date: 07/20/2015
f1_keywords:
- bc42326
- vbc42326
helpviewer_keywords:
- BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
ms.openlocfilehash: 69228bbb5f659a8e500e85dea1ef87cb43b0356e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590172"
---
# <a name="lambda-expression-will-not-be-removed-from-this-event-handler"></a><span data-ttu-id="93728-102">La expresión lambda no se quitará de este controlador de eventos</span><span class="sxs-lookup"><span data-stu-id="93728-102">Lambda expression will not be removed from this event handler</span></span>
<span data-ttu-id="93728-103">Expresión lambda no se quitará de este controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="93728-103">Lambda expression will not be removed from this event handler.</span></span> <span data-ttu-id="93728-104">Asigne la expresión lambda a una variable y use la variable para agregar y quitar el evento.</span><span class="sxs-lookup"><span data-stu-id="93728-104">Assign the lambda expression to a variable and use the variable to add and remove the event.</span></span>  
  
 <span data-ttu-id="93728-105">Cuando se utilizan expresiones lambda con controladores de eventos, es podrán que no vea el comportamiento que espera.</span><span class="sxs-lookup"><span data-stu-id="93728-105">When lambda expressions are used with event handlers, you may not see the behavior you expect.</span></span> <span data-ttu-id="93728-106">El compilador genera un nuevo método para cada definición de la expresión lambda, incluso si son idénticos.</span><span class="sxs-lookup"><span data-stu-id="93728-106">The compiler generates a new method for each lambda expression definition, even if they are identical.</span></span> <span data-ttu-id="93728-107">Por lo tanto, el siguiente código muestra `False`.</span><span class="sxs-lookup"><span data-stu-id="93728-107">Therefore, the following code displays `False`.</span></span>  
  
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
  
 <span data-ttu-id="93728-108">Cuando se utilizan expresiones lambda con controladores de eventos, esto puede provocar resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="93728-108">When lambda expressions are used with event handlers, this may cause unexpected results.</span></span> <span data-ttu-id="93728-109">En el ejemplo siguiente, la expresión lambda agregados por `AddHandler` no quita el `RemoveHandler` instrucción.</span><span class="sxs-lookup"><span data-stu-id="93728-109">In the following example, the lambda expression added by `AddHandler` is not removed by the `RemoveHandler` statement.</span></span>  
  
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
  
 <span data-ttu-id="93728-110">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="93728-110">By default, this message is a warning.</span></span> <span data-ttu-id="93728-111">Para obtener más información sobre cómo ocultar las advertencias o tratar advertencias como errores, vea [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="93728-111">For more information about how to hide warnings or treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="93728-112">**Id. de error:** BC42326</span><span class="sxs-lookup"><span data-stu-id="93728-112">**Error ID:** BC42326</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="93728-113">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="93728-113">To correct this error</span></span>  
  
-   <span data-ttu-id="93728-114">Para evitar la advertencia y quitar la expresión lambda, asigne la expresión lambda a una variable y use la variable tanto en el `AddHandler` y `RemoveHandler` instrucciones, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="93728-114">To avoid the warning and remove the lambda expression, assign the lambda expression to a variable and use the variable in both the `AddHandler` and `RemoveHandler` statements, as shown in the following example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="93728-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="93728-115">See Also</span></span>  
 [<span data-ttu-id="93728-116">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="93728-116">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="93728-117">Conversión de delegado flexible</span><span class="sxs-lookup"><span data-stu-id="93728-117">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [<span data-ttu-id="93728-118">Eventos</span><span class="sxs-lookup"><span data-stu-id="93728-118">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
