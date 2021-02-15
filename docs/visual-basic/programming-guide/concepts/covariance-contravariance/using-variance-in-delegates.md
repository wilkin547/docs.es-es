---
description: Más información acerca de cómo usar la varianza en delegados (Visual Basic)
title: Uso de la varianza en delegados
ms.date: 07/20/2015
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
ms.openlocfilehash: d146460c515c1579a9a98d31aa48441f9584b83b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100482005"
---
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="1e74e-103">Usar varianza en delegados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e74e-103">Using Variance in Delegates (Visual Basic)</span></span>

<span data-ttu-id="1e74e-104">Al asignar un método a un delegado, la *covarianza* y la *contravarianza* proporcionan flexibilidad para hacer coincidir un tipo de delegado con una firma de método.</span><span class="sxs-lookup"><span data-stu-id="1e74e-104">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="1e74e-105">La covarianza permite que un método tenga un tipo de valor devuelto más derivado que el definido en el delegado.</span><span class="sxs-lookup"><span data-stu-id="1e74e-105">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="1e74e-106">La contravarianza permite un método que tiene tipos de parámetro menos derivados que los del tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="1e74e-106">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>

## <a name="example-1-covariance"></a><span data-ttu-id="1e74e-107">Ejemplo 1: Covarianza</span><span class="sxs-lookup"><span data-stu-id="1e74e-107">Example 1: Covariance</span></span>

### <a name="description"></a><span data-ttu-id="1e74e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e74e-108">Description</span></span>

<span data-ttu-id="1e74e-109">En este ejemplo se muestra cómo se pueden usar delegados con métodos que tienen tipos de valor devuelto derivados del tipo de valor devuelto en la firma del delegado.</span><span class="sxs-lookup"><span data-stu-id="1e74e-109">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="1e74e-110">El tipo de datos devuelto por `DogsHandler` es de tipo `Dogs`, que se deriva del tipo `Mammals` definido en el delegado.</span><span class="sxs-lookup"><span data-stu-id="1e74e-110">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>

### <a name="code"></a><span data-ttu-id="1e74e-111">Código</span><span class="sxs-lookup"><span data-stu-id="1e74e-111">Code</span></span>

```vb
Class Mammals
End Class

Class Dogs
    Inherits Mammals
End Class
Class Test
    Public Delegate Function HandlerMethod() As Mammals
    Public Shared Function MammalsHandler() As Mammals
        Return Nothing
    End Function
    Public Shared Function DogsHandler() As Dogs
        Return Nothing
    End Function
    Sub Test()
        Dim handlerMammals As HandlerMethod = AddressOf MammalsHandler
        ' Covariance enables this assignment.
        Dim handlerDogs As HandlerMethod = AddressOf DogsHandler
    End Sub
End Class
```

## <a name="example-2-contravariance"></a><span data-ttu-id="1e74e-112">Ejemplo 2: Contravarianza</span><span class="sxs-lookup"><span data-stu-id="1e74e-112">Example 2: Contravariance</span></span>

### <a name="description"></a><span data-ttu-id="1e74e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e74e-113">Description</span></span>

<span data-ttu-id="1e74e-114">En este ejemplo se muestra cómo se pueden usar delegados con métodos que tienen parámetros que son tipos base del tipo de parámetro de la firma del delegado.</span><span class="sxs-lookup"><span data-stu-id="1e74e-114">This example demonstrates how delegates can be used with methods that have parameters whose types are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="1e74e-115">Con la contravarianza, puede usar un controlador de eventos en lugar de controladores independientes.</span><span class="sxs-lookup"><span data-stu-id="1e74e-115">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="1e74e-116">En el ejemplo siguiente se usan dos delegados:</span><span class="sxs-lookup"><span data-stu-id="1e74e-116">The following example makes use of two delegates:</span></span>

- <span data-ttu-id="1e74e-117">Un delegado <xref:System.Windows.Forms.KeyEventHandler> que define la firma del evento [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown).</span><span class="sxs-lookup"><span data-stu-id="1e74e-117">A <xref:System.Windows.Forms.KeyEventHandler> delegate that defines the signature of the [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) event.</span></span> <span data-ttu-id="1e74e-118">Su firma es:</span><span class="sxs-lookup"><span data-stu-id="1e74e-118">Its signature is:</span></span>

   ```vb
   Public Delegate Sub KeyEventHandler(sender As Object, e As KeyEventArgs)
   ```

- <span data-ttu-id="1e74e-119">Un delegado <xref:System.Windows.Forms.MouseEventHandler> que define la firma del evento [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown).</span><span class="sxs-lookup"><span data-stu-id="1e74e-119">A <xref:System.Windows.Forms.MouseEventHandler> delegate that defines the signature of the [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) event.</span></span> <span data-ttu-id="1e74e-120">Su firma es:</span><span class="sxs-lookup"><span data-stu-id="1e74e-120">Its signature is:</span></span>

   ```vb
   Public Delegate Sub MouseEventHandler(sender As Object, e As MouseEventArgs)
   ```

<span data-ttu-id="1e74e-121">En el ejemplo se define un controlador de eventos con un parámetro <xref:System.EventArgs>, que se usa para controlar los eventos `Button.KeyDown` y `Button.MouseClick`.</span><span class="sxs-lookup"><span data-stu-id="1e74e-121">The example defines an event handler with an <xref:System.EventArgs> parameter and uses it to handle both the `Button.KeyDown` and `Button.MouseClick` events.</span></span> <span data-ttu-id="1e74e-122">Es posible hacer esto porque <xref:System.EventArgs> es un tipo base de <xref:System.Windows.Forms.KeyEventArgs> y <xref:System.Windows.Forms.MouseEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="1e74e-122">It can do this because <xref:System.EventArgs> is a base type of both <xref:System.Windows.Forms.KeyEventArgs>  and <xref:System.Windows.Forms.MouseEventArgs>.</span></span>

### <a name="code"></a><span data-ttu-id="1e74e-123">Código</span><span class="sxs-lookup"><span data-stu-id="1e74e-123">Code</span></span>

```vb
' Event handler that accepts a parameter of the EventArgs type.
Private Sub MultiHandler(ByVal sender As Object,
                         ByVal e As System.EventArgs)
    Label1.Text = DateTime.Now
End Sub

Private Sub Form1_Load(ByVal sender As System.Object,
    ByVal e As System.EventArgs) Handles MyBase.Load

    ' You can use a method that has an EventArgs parameter,
    ' although the event expects the KeyEventArgs parameter.
    AddHandler Button1.KeyDown, AddressOf MultiHandler

    ' You can use the same method
    ' for the event that expects the MouseEventArgs parameter.
    AddHandler Button1.MouseClick, AddressOf MultiHandler
End Sub
```

## <a name="see-also"></a><span data-ttu-id="1e74e-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e74e-124">See also</span></span>

- [<span data-ttu-id="1e74e-125">Varianza en delegados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e74e-125">Variance in Delegates (Visual Basic)</span></span>](variance-in-delegates.md)
- [<span data-ttu-id="1e74e-126">Usar la varianza para los delegados genéricos Func y Action (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e74e-126">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](using-variance-for-func-and-action-generic-delegates.md)
