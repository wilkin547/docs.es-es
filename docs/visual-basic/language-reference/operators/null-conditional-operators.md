---
title: Operadores condicionales null
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: 003f579a7128bbe2462b7fbe7057de03e61bfbe6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348285"
---
# <a name="-and--null-conditional-operators-visual-basic"></a><span data-ttu-id="b1674-102">?.</span><span class="sxs-lookup"><span data-stu-id="b1674-102">?.</span></span> <span data-ttu-id="b1674-103">etc? () operadores condicionales null (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1674-103">and ?() null-conditional operators (Visual Basic)</span></span>

<span data-ttu-id="b1674-104">Comprueba el valor del operando izquierdo para null (`Nothing`) antes de realizar una operación de acceso a miembros (`?.`) o de índice (`?()`). Devuelve `Nothing` si el operando izquierdo se evalúa como `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="b1674-104">Tests the value of the left-hand operand for null (`Nothing`) before performing a member access (`?.`) or index (`?()`) operation; returns `Nothing` if the left-hand operand evaluates to `Nothing`.</span></span> <span data-ttu-id="b1674-105">Tenga en cuenta que, en las expresiones que normalmente devuelven tipos de valor, el operador condicional null devuelve un <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="b1674-105">Note that in expressions that ordinarily return value types, the null-conditional operator returns a <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="b1674-106">Estos operadores le ayudan a escribir menos código para controlar las comprobaciones de valores NULL, especialmente cuando desciende en estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="b1674-106">These operators help you write less code to handle null checks, especially when descending into data structures.</span></span> <span data-ttu-id="b1674-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b1674-107">For example:</span></span>

```vb
' Nothing if customers is Nothing
Dim length As Integer? = customers?.Length

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()
```

<span data-ttu-id="b1674-108">Para la comparación, el código alternativo para la primera de estas expresiones sin un operador condicional NULL es:</span><span class="sxs-lookup"><span data-stu-id="b1674-108">For comparison, the alternative code for the first of these expressions without a null-conditional operator is:</span></span>

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

<span data-ttu-id="b1674-109">A veces es necesario realizar una acción en un objeto que puede ser null, en función del valor de un miembro booleano en ese objeto (como la propiedad booleana `IsAllowedFreeShipping` en el ejemplo siguiente):</span><span class="sxs-lookup"><span data-stu-id="b1674-109">Sometimes you need to take an action on an object that may be null, based on the value of a Boolean member on that object (like the Boolean property `IsAllowedFreeShipping` in the following example):</span></span>

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer IsNot Nothing AndAlso customer.IsAllowedFreeShipping Then
  ApplyFreeShippingToOrders(customer)
End If
```

<span data-ttu-id="b1674-110">Puede acortar el código y evitar comprobar manualmente si hay valores NULL mediante el operador condicional null de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b1674-110">You can shorten your code and avoid manually checking for null by using the null-conditional operator as follows:</span></span>

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer?.IsAllowedFreeShipping Then ApplyFreeShippingToOrders(customer)
```

<span data-ttu-id="b1674-111">Los operadores de condición NULL se cortocircuitan.</span><span class="sxs-lookup"><span data-stu-id="b1674-111">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="b1674-112">Si una operación de una cadena de operaciones de índice y acceso a miembros condicionales devuelve `Nothing`, se detiene el resto de la ejecución de la cadena.</span><span class="sxs-lookup"><span data-stu-id="b1674-112">If one operation in a chain of conditional member access and index operations returns `Nothing`, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="b1674-113">En el ejemplo siguiente, `C(E)` no se evalúa si `A`, `B`o `C` se evalúan como `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="b1674-113">In the following example, `C(E)` isn't evaluated if `A`, `B`, or `C` evaluates to `Nothing`.</span></span>

```vb
A?.B?.C?(E)
```

<span data-ttu-id="b1674-114">Otro uso para el acceso de miembro condicional NULL es invocar delegados de una manera segura para subprocesos con mucho menos código.</span><span class="sxs-lookup"><span data-stu-id="b1674-114">Another use for null-conditional member access is to invoke delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="b1674-115">En el ejemplo siguiente se definen dos tipos, un `NewsBroadcaster` y un `NewsReceiver`.</span><span class="sxs-lookup"><span data-stu-id="b1674-115">The following example defines two types, a `NewsBroadcaster` and a `NewsReceiver`.</span></span> <span data-ttu-id="b1674-116">El delegado de `NewsBroadcaster.SendNews` envía los elementos de noticias al receptor.</span><span class="sxs-lookup"><span data-stu-id="b1674-116">News items are sent to the receiver by the `NewsBroadcaster.SendNews` delegate.</span></span>

```vb
Public Module NewsBroadcaster
   Dim SendNews As Action(Of String)

   Public Sub Main()
      Dim rec As New NewsReceiver()
      Dim rec2 As New NewsReceiver()
      SendNews?.Invoke("Just in: A newsworthy item...")
   End Sub

   Public Sub Register(client As Action(Of String))
      SendNews = SendNews.Combine({SendNews, client})
   End Sub
End Module

Public Class NewsReceiver
   Public Sub New()
      NewsBroadcaster.Register(AddressOf Me.DisplayNews)
   End Sub

   Public Sub DisplayNews(newsItem As String)
      Console.WriteLine(newsItem)
   End Sub
End Class
```

<span data-ttu-id="b1674-117">Si no hay ningún elemento en la lista de invocación de `SendNews`, el delegado de `SendNews` produce una <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="b1674-117">If there are no elements in the `SendNews` invocation list, the `SendNews` delegate throws a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="b1674-118">Antes de los operadores condicionales null, el código como el siguiente garantiza que la lista de invocación de delegado no se `Nothing`:</span><span class="sxs-lookup"><span data-stu-id="b1674-118">Before null conditional operators, code like the following ensured that the delegate invocation list was not `Nothing`:</span></span>

```vb
SendNews = SendNews.Combine({SendNews, client})
If SendNews IsNot Nothing Then
   SendNews("Just in...")
End If
```

<span data-ttu-id="b1674-119">La nueva manera es mucho más sencilla:</span><span class="sxs-lookup"><span data-stu-id="b1674-119">The new way is much simpler:</span></span>

```vb
SendNews = SendNews.Combine({SendNews, client})
SendNews?.Invoke("Just in...")
```

<span data-ttu-id="b1674-120">La nueva forma de hacerlo es segura para los subprocesos porque el compilador genera código para evaluar `SendNews` solo una vez, manteniendo el resultado en una variable temporal.</span><span class="sxs-lookup"><span data-stu-id="b1674-120">The new way is thread-safe because the compiler generates code to evaluate `SendNews` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="b1674-121">Debe llamar explícitamente al método `Invoke` porque no hay ninguna sintaxis de invocación del delegado null condicional `SendNews?(String)`.</span><span class="sxs-lookup"><span data-stu-id="b1674-121">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `SendNews?(String)`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1674-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1674-122">See also</span></span>

- [<span data-ttu-id="b1674-123">Operadores (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1674-123">Operators (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="b1674-124">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b1674-124">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="b1674-125">Referencia del lenguaje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b1674-125">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)
