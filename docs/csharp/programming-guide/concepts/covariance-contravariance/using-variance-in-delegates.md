---
title: Usar varianza en delegados (C#)
description: Aprenda a usar la varianza en delegados con los ejemplos de código de covarianza y contravarianza incluidos.
ms.date: 07/20/2015
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
ms.openlocfilehash: 62b0555ee29c5e7d2ba0954a8949d61596122cc7
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105684"
---
# <a name="using-variance-in-delegates-c"></a><span data-ttu-id="955b5-103">Usar varianza en delegados (C#)</span><span class="sxs-lookup"><span data-stu-id="955b5-103">Using Variance in Delegates (C#)</span></span>
<span data-ttu-id="955b5-104">Al asignar un método a un delegado, la *covarianza* y la *contravarianza* proporcionan flexibilidad para hacer coincidir un tipo de delegado con una firma de método.</span><span class="sxs-lookup"><span data-stu-id="955b5-104">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="955b5-105">La covarianza permite que un método tenga un tipo de valor devuelto más derivado que el definido en el delegado.</span><span class="sxs-lookup"><span data-stu-id="955b5-105">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="955b5-106">La contravarianza permite un método que tiene tipos de parámetro menos derivados que los del tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="955b5-106">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="955b5-107">Ejemplo 1: Covarianza</span><span class="sxs-lookup"><span data-stu-id="955b5-107">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="955b5-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="955b5-108">Description</span></span>  
 <span data-ttu-id="955b5-109">En este ejemplo se muestra cómo se pueden usar delegados con métodos que tienen tipos de valor devuelto derivados del tipo de valor devuelto en la firma del delegado.</span><span class="sxs-lookup"><span data-stu-id="955b5-109">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="955b5-110">El tipo de datos devuelto por `DogsHandler` es de tipo `Dogs`, que se deriva del tipo `Mammals` definido en el delegado.</span><span class="sxs-lookup"><span data-stu-id="955b5-110">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="955b5-111">Código</span><span class="sxs-lookup"><span data-stu-id="955b5-111">Code</span></span>  
  
```csharp  
class Mammals {}  
class Dogs : Mammals {}  
  
class Program  
{  
    // Define the delegate.  
    public delegate Mammals HandlerMethod();  
  
    public static Mammals MammalsHandler()  
    {  
        return null;  
    }  
  
    public static Dogs DogsHandler()  
    {  
        return null;  
    }  
  
    static void Test()  
    {  
        HandlerMethod handlerMammals = MammalsHandler;  
  
        // Covariance enables this assignment.  
        HandlerMethod handlerDogs = DogsHandler;  
    }  
}  
```  
  
## <a name="example-2-contravariance"></a><span data-ttu-id="955b5-112">Ejemplo 2: Contravarianza</span><span class="sxs-lookup"><span data-stu-id="955b5-112">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="955b5-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="955b5-113">Description</span></span>

<span data-ttu-id="955b5-114">En este ejemplo se muestra cómo se pueden usar delegados con métodos que tienen parámetros que son tipos base del tipo de parámetro de la firma del delegado.</span><span class="sxs-lookup"><span data-stu-id="955b5-114">This example demonstrates how delegates can be used with methods that have parameters whose types are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="955b5-115">Con la contravarianza, puede usar un controlador de eventos en lugar de controladores independientes.</span><span class="sxs-lookup"><span data-stu-id="955b5-115">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="955b5-116">En el ejemplo siguiente se usan dos delegados:</span><span class="sxs-lookup"><span data-stu-id="955b5-116">The following example makes use of two delegates:</span></span>

- <span data-ttu-id="955b5-117">Un delegado <xref:System.Windows.Forms.KeyEventHandler> que define la firma del evento [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown).</span><span class="sxs-lookup"><span data-stu-id="955b5-117">A <xref:System.Windows.Forms.KeyEventHandler> delegate that defines the signature of the [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) event.</span></span> <span data-ttu-id="955b5-118">Su firma es:</span><span class="sxs-lookup"><span data-stu-id="955b5-118">Its signature is:</span></span>

   ```csharp
   public delegate void KeyEventHandler(object sender, KeyEventArgs e)
   ```

- <span data-ttu-id="955b5-119">Un delegado <xref:System.Windows.Forms.MouseEventHandler> que define la firma del evento [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown).</span><span class="sxs-lookup"><span data-stu-id="955b5-119">A <xref:System.Windows.Forms.MouseEventHandler> delegate that defines the signature of the [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) event.</span></span> <span data-ttu-id="955b5-120">Su firma es:</span><span class="sxs-lookup"><span data-stu-id="955b5-120">Its signature is:</span></span>

   ```csharp
   public delegate void MouseEventHandler(object sender, MouseEventArgs e)
   ```

<span data-ttu-id="955b5-121">En el ejemplo se define un controlador de eventos con un parámetro <xref:System.EventArgs>, que se usa para controlar los eventos `Button.KeyDown` y `Button.MouseClick`.</span><span class="sxs-lookup"><span data-stu-id="955b5-121">The example defines an event handler with an <xref:System.EventArgs> parameter and uses it to handle both the `Button.KeyDown` and `Button.MouseClick` events.</span></span> <span data-ttu-id="955b5-122">Es posible hacer esto porque <xref:System.EventArgs> es un tipo base de <xref:System.Windows.Forms.KeyEventArgs> y <xref:System.Windows.Forms.MouseEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="955b5-122">It can do this because <xref:System.EventArgs> is a base type of both <xref:System.Windows.Forms.KeyEventArgs>  and <xref:System.Windows.Forms.MouseEventArgs>.</span></span>
  
### <a name="code"></a><span data-ttu-id="955b5-123">Código</span><span class="sxs-lookup"><span data-stu-id="955b5-123">Code</span></span>  
  
```csharp  
// Event handler that accepts a parameter of the EventArgs type.  
private void MultiHandler(object sender, System.EventArgs e)  
{  
    label1.Text = System.DateTime.Now.ToString();  
}  
  
public Form1()  
{  
    InitializeComponent();  
  
    // You can use a method that has an EventArgs parameter,  
    // although the event expects the KeyEventArgs parameter.  
    this.button1.KeyDown += this.MultiHandler;  
  
    // You can use the same method
    // for an event that expects the MouseEventArgs parameter.  
    this.button1.MouseClick += this.MultiHandler;  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="955b5-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="955b5-124">See also</span></span>

- [<span data-ttu-id="955b5-125">Varianza en delegados (C#)</span><span class="sxs-lookup"><span data-stu-id="955b5-125">Variance in Delegates (C#)</span></span>](./variance-in-delegates.md)
- [<span data-ttu-id="955b5-126">Usar varianza para los delegados genéricos Func y Action (C#)</span><span class="sxs-lookup"><span data-stu-id="955b5-126">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)
