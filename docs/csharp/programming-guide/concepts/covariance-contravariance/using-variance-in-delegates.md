---
title: Usar varianza en delegados (C#)
ms.date: 07/20/2015
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
ms.openlocfilehash: 00e11d4ce755c8c75b73023fec14d95ebc96b4fe
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69595264"
---
# <a name="using-variance-in-delegates-c"></a><span data-ttu-id="b9389-102">Usar varianza en delegados (C#)</span><span class="sxs-lookup"><span data-stu-id="b9389-102">Using Variance in Delegates (C#)</span></span>
<span data-ttu-id="b9389-103">Al asignar un método a un delegado, la *covarianza* y la *contravarianza* proporcionan flexibilidad para hacer coincidir un tipo de delegado con una firma de método.</span><span class="sxs-lookup"><span data-stu-id="b9389-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="b9389-104">La covarianza permite que un método tenga un tipo de valor devuelto más derivado que el definido en el delegado.</span><span class="sxs-lookup"><span data-stu-id="b9389-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="b9389-105">La contravarianza permite un método que tiene tipos de parámetro menos derivados que los del tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="b9389-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="b9389-106">Ejemplo 1: Covarianza</span><span class="sxs-lookup"><span data-stu-id="b9389-106">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="b9389-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b9389-107">Description</span></span>  
 <span data-ttu-id="b9389-108">En este ejemplo se muestra cómo se pueden usar delegados con métodos que tienen tipos de valor devuelto derivados del tipo de valor devuelto en la firma del delegado.</span><span class="sxs-lookup"><span data-stu-id="b9389-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="b9389-109">El tipo de datos devuelto por `DogsHandler` es de tipo `Dogs`, que se deriva del tipo `Mammals` definido en el delegado.</span><span class="sxs-lookup"><span data-stu-id="b9389-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b9389-110">Código</span><span class="sxs-lookup"><span data-stu-id="b9389-110">Code</span></span>  
  
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
  
## <a name="example-2-contravariance"></a><span data-ttu-id="b9389-111">Ejemplo 2: Contravarianza</span><span class="sxs-lookup"><span data-stu-id="b9389-111">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="b9389-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b9389-112">Description</span></span>  
 <span data-ttu-id="b9389-113">En este ejemplo se muestra cómo se pueden usar delegados con métodos que tienen parámetros de un tipo que son tipos base del tipo de parámetro de la firma del delegado.</span><span class="sxs-lookup"><span data-stu-id="b9389-113">This example demonstrates how delegates can be used with methods that have parameters of a type that are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="b9389-114">Con la contravarianza, puede usar un controlador de eventos en lugar de controladores independientes.</span><span class="sxs-lookup"><span data-stu-id="b9389-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="b9389-115">Por ejemplo, puede crear un controlador de eventos que acepta un parámetro de entrada `EventArgs` y usarlo con un evento `Button.MouseClick` que envía un tipo `MouseEventArgs` como parámetro, pero también con un evento `TextBox.KeyDown` que envía un parámetro `KeyEventArgs`.</span><span class="sxs-lookup"><span data-stu-id="b9389-115">For example, you can create an event handler that accepts an `EventArgs` input parameter and use it with a `Button.MouseClick` event that sends a `MouseEventArgs` type as a parameter, and also with a `TextBox.KeyDown` event that sends a `KeyEventArgs` parameter.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b9389-116">Código</span><span class="sxs-lookup"><span data-stu-id="b9389-116">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b9389-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9389-117">See also</span></span>

- [<span data-ttu-id="b9389-118">Varianza en delegados (C#)</span><span class="sxs-lookup"><span data-stu-id="b9389-118">Variance in Delegates (C#)</span></span>](./variance-in-delegates.md)
- [<span data-ttu-id="b9389-119">Usar varianza para los delegados genéricos Func y Action (C#)</span><span class="sxs-lookup"><span data-stu-id="b9389-119">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)
