---
title: Usar varianza en delegados (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 9f2128080d34e78733cec926e59ee5dbe9b98a0d
ms.openlocfilehash: 83bef688a9d40c08f7a8280309ea5b607a9b06f0
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2017

---
# <a name="using-variance-in-delegates-c"></a><span data-ttu-id="242cc-102">Usar varianza en delegados (C#)</span><span class="sxs-lookup"><span data-stu-id="242cc-102">Using Variance in Delegates (C#)</span></span>
<span data-ttu-id="242cc-103">Al asignar un método a un delegado, la *covarianza* y la *contravarianza* proporcionan flexibilidad para hacer coincidir un tipo de delegado con una firma de método.</span><span class="sxs-lookup"><span data-stu-id="242cc-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="242cc-104">La covarianza permite que un método tenga un tipo de valor devuelto más derivado que el definido en el delegado.</span><span class="sxs-lookup"><span data-stu-id="242cc-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="242cc-105">La contravarianza permite un método que tiene tipos de parámetro menos derivados que los del tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="242cc-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="242cc-106">Ejemplo 1: covarianza</span><span class="sxs-lookup"><span data-stu-id="242cc-106">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="242cc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="242cc-107">Description</span></span>  
 <span data-ttu-id="242cc-108">En este ejemplo se muestra cómo se pueden usar delegados con métodos que tienen tipos de valor devuelto derivados del tipo de valor devuelto en la firma del delegado.</span><span class="sxs-lookup"><span data-stu-id="242cc-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="242cc-109">El tipo de datos devuelto por `DogsHandler` es de tipo `Dogs`, que se deriva del tipo `Mammals` definido en el delegado.</span><span class="sxs-lookup"><span data-stu-id="242cc-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="242cc-110">Código</span><span class="sxs-lookup"><span data-stu-id="242cc-110">Code</span></span>  
  
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
  
## <a name="example-2-contravariance"></a><span data-ttu-id="242cc-111">Ejemplo 2: contravarianza</span><span class="sxs-lookup"><span data-stu-id="242cc-111">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="242cc-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="242cc-112">Description</span></span>  
 <span data-ttu-id="242cc-113">En este ejemplo se muestra cómo se pueden usar delegados con métodos que tienen parámetros de un tipo que son tipos base del tipo de parámetro de la firma del delegado.</span><span class="sxs-lookup"><span data-stu-id="242cc-113">This example demonstrates how delegates can be used with methods that have parameters of a type that are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="242cc-114">Con la contravarianza, puede usar un controlador de eventos en lugar de controladores independientes.</span><span class="sxs-lookup"><span data-stu-id="242cc-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="242cc-115">Por ejemplo, puede crear un controlador de eventos que acepta un parámetro de entrada `EventArgs` y usarlo con un evento `Button.MouseClick` que envía un tipo `MouseEventArgs` como parámetro, pero también con un evento `TextBox.KeyDown` que envía un parámetro `KeyEventArgs`.</span><span class="sxs-lookup"><span data-stu-id="242cc-115">For example, you can create an event handler that accepts an `EventArgs` input parameter and use it with a `Button.MouseClick` event that sends a `MouseEventArgs` type as a parameter, and also with a `TextBox.KeyDown` event that sends a `KeyEventArgs` parameter.</span></span>  
  
### <a name="code"></a><span data-ttu-id="242cc-116">Código</span><span class="sxs-lookup"><span data-stu-id="242cc-116">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="242cc-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="242cc-117">See Also</span></span>  
 <span data-ttu-id="242cc-118">[Varianza en delegados (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) </span><span class="sxs-lookup"><span data-stu-id="242cc-118">[Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) </span></span>  
 [<span data-ttu-id="242cc-119">Usar varianza para los delegados genéricos Func y Action (C#)</span><span class="sxs-lookup"><span data-stu-id="242cc-119">Using Variance for Func and Action Generic Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)

