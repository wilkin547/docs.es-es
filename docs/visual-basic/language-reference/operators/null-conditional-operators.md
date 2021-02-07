---
description: Más información acerca de:?. etc? () operadores condicionales null (Visual Basic)
title: Operadores condicionales null
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: 558b8921d0da4089505dd1035cb6039af24a2802
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665372"
---
# <a name="-and--null-conditional-operators-visual-basic"></a><span data-ttu-id="4a963-104">?.</span><span class="sxs-lookup"><span data-stu-id="4a963-104">?.</span></span> <span data-ttu-id="4a963-105">etc? () operadores condicionales null (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a963-105">and ?() null-conditional operators (Visual Basic)</span></span>

<span data-ttu-id="4a963-106">Comprueba el valor del operando izquierdo para null ( `Nothing` ) antes de realizar una operación de acceso a miembros ( `?.` ) o índice ( `?()` ); devuelve `Nothing` si el operando izquierdo se evalúa como `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="4a963-106">Tests the value of the left-hand operand for null (`Nothing`) before performing a member access (`?.`) or index (`?()`) operation; returns `Nothing` if the left-hand operand evaluates to `Nothing`.</span></span> <span data-ttu-id="4a963-107">Tenga en cuenta que en las expresiones que normalmente devuelven tipos de valor, el operador condicional null devuelve <xref:System.Nullable%601> .</span><span class="sxs-lookup"><span data-stu-id="4a963-107">Note that in expressions that ordinarily return value types, the null-conditional operator returns a <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="4a963-108">Estos operadores le ayudan a escribir menos código para controlar las comprobaciones de valores NULL, especialmente cuando desciende en estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="4a963-108">These operators help you write less code to handle null checks, especially when descending into data structures.</span></span> <span data-ttu-id="4a963-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4a963-109">For example:</span></span>

```vb
' Nothing if customers is Nothing
Dim length As Integer? = customers?.Length

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()
```

<span data-ttu-id="4a963-110">Para la comparación, el código alternativo para la primera de estas expresiones sin un operador condicional NULL es:</span><span class="sxs-lookup"><span data-stu-id="4a963-110">For comparison, the alternative code for the first of these expressions without a null-conditional operator is:</span></span>

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

<span data-ttu-id="4a963-111">A veces es necesario realizar una acción en un objeto que puede ser null, en función del valor de un miembro booleano en ese objeto (como la propiedad booleana `IsAllowedFreeShipping` en el ejemplo siguiente):</span><span class="sxs-lookup"><span data-stu-id="4a963-111">Sometimes you need to take an action on an object that may be null, based on the value of a Boolean member on that object (like the Boolean property `IsAllowedFreeShipping` in the following example):</span></span>

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer IsNot Nothing AndAlso customer.IsAllowedFreeShipping Then
  ApplyFreeShippingToOrders(customer)
End If
```

<span data-ttu-id="4a963-112">Puede acortar el código y evitar comprobar manualmente si hay valores NULL mediante el operador condicional null de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="4a963-112">You can shorten your code and avoid manually checking for null by using the null-conditional operator as follows:</span></span>

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer?.IsAllowedFreeShipping Then ApplyFreeShippingToOrders(customer)
```

<span data-ttu-id="4a963-113">Los operadores de condición NULL se cortocircuitan.</span><span class="sxs-lookup"><span data-stu-id="4a963-113">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="4a963-114">Si una operación de una cadena de operaciones de índice y de acceso a miembros condicionales se devuelve `Nothing` , se detiene el resto de la ejecución de la cadena.</span><span class="sxs-lookup"><span data-stu-id="4a963-114">If one operation in a chain of conditional member access and index operations returns `Nothing`, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="4a963-115">En el ejemplo siguiente, `C(E)` no se evalúa si `A` , `B` o `C` se evalúa como `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="4a963-115">In the following example, `C(E)` isn't evaluated if `A`, `B`, or `C` evaluates to `Nothing`.</span></span>

```vb
A?.B?.C?(E)
```

<span data-ttu-id="4a963-116">Otro uso para el acceso de miembro condicional NULL es invocar delegados de una manera segura para subprocesos con mucho menos código.</span><span class="sxs-lookup"><span data-stu-id="4a963-116">Another use for null-conditional member access is to invoke delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="4a963-117">En el ejemplo siguiente se definen dos tipos, `NewsBroadcaster` y `NewsReceiver` .</span><span class="sxs-lookup"><span data-stu-id="4a963-117">The following example defines two types, a `NewsBroadcaster` and a `NewsReceiver`.</span></span> <span data-ttu-id="4a963-118">El delegado envía los elementos de noticias al receptor `NewsBroadcaster.SendNews` .</span><span class="sxs-lookup"><span data-stu-id="4a963-118">News items are sent to the receiver by the `NewsBroadcaster.SendNews` delegate.</span></span>

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

<span data-ttu-id="4a963-119">Si no hay ningún elemento en la `SendNews` lista de invocación, el `SendNews` delegado produce una excepción <xref:System.NullReferenceException> .</span><span class="sxs-lookup"><span data-stu-id="4a963-119">If there are no elements in the `SendNews` invocation list, the `SendNews` delegate throws a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="4a963-120">Antes de los operadores condicionales null, el código como el siguiente garantiza que la lista de invocación de delegado no era `Nothing` :</span><span class="sxs-lookup"><span data-stu-id="4a963-120">Before null conditional operators, code like the following ensured that the delegate invocation list was not `Nothing`:</span></span>

```vb
SendNews = SendNews.Combine({SendNews, client})
If SendNews IsNot Nothing Then
   SendNews("Just in...")
End If
```

<span data-ttu-id="4a963-121">La nueva manera es mucho más sencilla:</span><span class="sxs-lookup"><span data-stu-id="4a963-121">The new way is much simpler:</span></span>

```vb
SendNews = SendNews.Combine({SendNews, client})
SendNews?.Invoke("Just in...")
```

<span data-ttu-id="4a963-122">La nueva forma de hacerlo es segura para los subprocesos porque el compilador genera código para evaluar `SendNews` solo una vez, manteniendo el resultado en una variable temporal.</span><span class="sxs-lookup"><span data-stu-id="4a963-122">The new way is thread-safe because the compiler generates code to evaluate `SendNews` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="4a963-123">Debe llamar explícitamente al método `Invoke` porque no hay ninguna sintaxis de invocación del delegado null condicional `SendNews?(String)`.</span><span class="sxs-lookup"><span data-stu-id="4a963-123">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `SendNews?(String)`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a963-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a963-124">See also</span></span>

- [<span data-ttu-id="4a963-125">Operadores (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a963-125">Operators (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="4a963-126">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4a963-126">Visual Basic Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4a963-127">Referencia del lenguaje Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4a963-127">Visual Basic Language Reference</span></span>](../index.md)
