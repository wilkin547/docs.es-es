---
title: Usar varianza en delegados (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cb8512945fa7aefa9afce4f4f1f8e0200dc3e2b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="using-variance-in-delegates-c"></a><span data-ttu-id="b37ef-102">Usar varianza en delegados (C#)</span><span class="sxs-lookup"><span data-stu-id="b37ef-102">Using Variance in Delegates (C#)</span></span>
<span data-ttu-id="b37ef-103">Al asignar un método a un delegado, la *covarianza* y la *contravarianza* proporcionan flexibilidad para hacer coincidir un tipo de delegado con una firma de método.</span><span class="sxs-lookup"><span data-stu-id="b37ef-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="b37ef-104">La covarianza permite que un método tenga un tipo de valor devuelto más derivado que el definido en el delegado.</span><span class="sxs-lookup"><span data-stu-id="b37ef-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="b37ef-105">La contravarianza permite un método que tiene tipos de parámetro menos derivados que los del tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="b37ef-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="b37ef-106">Ejemplo 1: covarianza</span><span class="sxs-lookup"><span data-stu-id="b37ef-106">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="b37ef-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b37ef-107">Description</span></span>  
 <span data-ttu-id="b37ef-108">En este ejemplo se muestra cómo se pueden usar delegados con métodos que tienen tipos de valor devuelto derivados del tipo de valor devuelto en la firma del delegado.</span><span class="sxs-lookup"><span data-stu-id="b37ef-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="b37ef-109">El tipo de datos devuelto por `DogsHandler` es de tipo `Dogs`, que se deriva del tipo `Mammals` definido en el delegado.</span><span class="sxs-lookup"><span data-stu-id="b37ef-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b37ef-110">Código</span><span class="sxs-lookup"><span data-stu-id="b37ef-110">Code</span></span>  
  
```csharp  
class Mammals{}  
class Dogs : Mammals{}  
  
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
  
## <a name="example-2-contravariance"></a><span data-ttu-id="b37ef-111">Ejemplo 2: contravarianza</span><span class="sxs-lookup"><span data-stu-id="b37ef-111">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="b37ef-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b37ef-112">Description</span></span>  
 <span data-ttu-id="b37ef-113">En este ejemplo se muestra cómo se pueden usar delegados con métodos que tienen parámetros de un tipo que son tipos base del tipo de parámetro de la firma del delegado.</span><span class="sxs-lookup"><span data-stu-id="b37ef-113">This example demonstrates how delegates can be used with methods that have parameters of a type that are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="b37ef-114">Con la contravarianza, puede usar un controlador de eventos en lugar de controladores independientes.</span><span class="sxs-lookup"><span data-stu-id="b37ef-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="b37ef-115">Por ejemplo, puede crear un controlador de eventos que acepta un parámetro de entrada `EventArgs` y usarlo con un evento `Button.MouseClick` que envía un tipo `MouseEventArgs` como parámetro, pero también con un evento `TextBox.KeyDown` que envía un parámetro `KeyEventArgs`.</span><span class="sxs-lookup"><span data-stu-id="b37ef-115">For example, you can create an event handler that accepts an `EventArgs` input parameter and use it with a `Button.MouseClick` event that sends a `MouseEventArgs` type as a parameter, and also with a `TextBox.KeyDown` event that sends a `KeyEventArgs` parameter.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b37ef-116">Código</span><span class="sxs-lookup"><span data-stu-id="b37ef-116">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b37ef-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b37ef-117">See Also</span></span>  
 [<span data-ttu-id="b37ef-118">Varianza en delegados (C#)</span><span class="sxs-lookup"><span data-stu-id="b37ef-118">Variance in Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)  
 <span data-ttu-id="b37ef-119">[Using Variance for Func and Action Generic Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md) (Usar la varianza para los delegados genéricos Func y Action (C#))</span><span class="sxs-lookup"><span data-stu-id="b37ef-119">[Using Variance for Func and Action Generic Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span></span>
