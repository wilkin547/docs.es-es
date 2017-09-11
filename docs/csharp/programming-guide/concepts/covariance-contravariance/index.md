---
title: Covarianza y contravarianza (C#)
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
ms.assetid: 066d9a3c-aab7-4ea6-826d-0b1a85399c74
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e1282f84171fa75db9656634a83f7cd5d4b9ac82
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="covariance-and-contravariance-c"></a><span data-ttu-id="cc9c9-102">Covarianza y contravarianza (C#)</span><span class="sxs-lookup"><span data-stu-id="cc9c9-102">Covariance and Contravariance (C#)</span></span>
<span data-ttu-id="cc9c9-103">En C#, la covarianza y la contravarianza habilitan la conversión de referencias implícita de tipos de matriz, tipos de delegado y argumentos de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-103">In C#, covariance and contravariance enable implicit reference conversion for array types, delegate types, and generic type arguments.</span></span> <span data-ttu-id="cc9c9-104">La covarianza conserva la compatibilidad de asignaciones y la contravarianza la invierte.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-104">Covariance preserves assignment compatibility and contravariance reverses it.</span></span>  
  
 <span data-ttu-id="cc9c9-105">El siguiente código muestra la diferencia entre la compatibilidad de asignaciones, la covarianza y la contravarianza.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-105">The following code demonstrates the difference between assignment compatibility, covariance, and contravariance.</span></span>  
  
```csharp  
// Assignment compatibility.   
string str = "test";  
// An object of a more derived type is assigned to an object of a less derived type.   
object obj = str;  
  
// Covariance.   
IEnumerable<string> strings = new List<string>();  
// An object that is instantiated with a more derived type argument   
// is assigned to an object instantiated with a less derived type argument.   
// Assignment compatibility is preserved.   
IEnumerable<object> objects = strings;  
  
// Contravariance.             
// Assume that the following method is in the class:   
// static void SetObject(object o) { }   
Action<object> actObject = SetObject;  
// An object that is instantiated with a less derived type argument   
// is assigned to an object instantiated with a more derived type argument.   
// Assignment compatibility is reversed.   
Action<string> actString = actObject;  
```  
  
 <span data-ttu-id="cc9c9-106">La covarianza de matrices permite la conversión implícita de una matriz de un tipo más derivado a una matriz de un tipo menos derivado.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-106">Covariance for arrays enables implicit conversion of an array of a more derived type to an array of a less derived type.</span></span> <span data-ttu-id="cc9c9-107">Pero esta operación no es segura, tal como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-107">But this operation is not type safe, as shown in the following code example.</span></span>  
  
```csharp  
object[] array = new String[10];  
// The following statement produces a run-time exception.  
// array[0] = 10;  
```  
  
 <span data-ttu-id="cc9c9-108">La compatibilidad de la covarianza y la contravarianza con grupos de métodos permite hacer coincidir firmas de método con tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-108">Covariance and contravariance support for method groups allows for matching method signatures with delegate types.</span></span> <span data-ttu-id="cc9c9-109">Esto le permite asignar a los delegados no solo métodos con firmas coincidentes, sino métodos que devuelven tipos más derivados (covarianza) o que aceptan parámetros con tipos menos derivados (contravarianza) que el especificado por el tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-109">This enables you to assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="cc9c9-110">Para obtener más información, vea [Varianza en delegados (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) y [Usar varianza en delegados (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="cc9c9-110">For more information, see [Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span>  
  
 <span data-ttu-id="cc9c9-111">En el ejemplo de código siguiente, se muestra la compatibilidad de covarianza y contravarianza con grupos de métodos.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-111">The following code example shows covariance and contravariance support for method groups.</span></span>  
  
```csharp  
static object GetObject() { return null; }  
static void SetObject(object obj) { }  
  
static string GetString() { return ""; }  
static void SetString(string str) { }  
  
static void Test()  
{  
    // Covariance. A delegate specifies a return type as object,  
    // but you can assign a method that returns a string.  
    Func<object> del = GetString;  
  
    // Contravariance. A delegate specifies a parameter type as string,  
    // but you can assign a method that takes an object.  
    Action<string> del2 = SetObject;  
}  
```  
  
 <span data-ttu-id="cc9c9-112">En .NET Framework 4 o versiones posteriores, C# admite la covarianza y contravarianza en las interfaces genéricas y los delegados, y permite la conversión implícita de los parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-112">In .NET Framework 4 or newer C# supports covariance and contravariance in generic interfaces and delegates and allows for implicit conversion of generic type parameters.</span></span> <span data-ttu-id="cc9c9-113">Para obtener más información, vea [Varianza en interfaces genéricas (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) y [Varianza en delegados (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="cc9c9-113">For more information, see [Variance in Generic Interfaces (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) and [Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span></span>  
  
 <span data-ttu-id="cc9c9-114">En el ejemplo de código siguiente, se muestra la conversión implícita de referencias para interfaces genéricas.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-114">The following code example shows implicit reference conversion for generic interfaces.</span></span>  
  
```csharp  
IEnumerable<String> strings = new List<String>();  
IEnumerable<Object> objects = strings;  
```  
  
 <span data-ttu-id="cc9c9-115">Un delegado o interfaz genéricos se denominan *variante* si sus parámetros genéricos se declaran como covariantes o contravariantes.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-115">A generic interface or delegate is called *variant* if its generic parameters are declared covariant or contravariant.</span></span> <span data-ttu-id="cc9c9-116">C# le permite crear sus propias interfaces y delegados variantes.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-116">C# enables you to create your own variant interfaces and delegates.</span></span> <span data-ttu-id="cc9c9-117">Para obtener más información, consulte [Crear interfaces genéricas variantes (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) y [Varianza en delegados (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="cc9c9-117">For more information, see [Creating Variant Generic Interfaces (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) and [Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="cc9c9-118">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="cc9c9-118">Related Topics</span></span>  
  
|<span data-ttu-id="cc9c9-119">Título</span><span class="sxs-lookup"><span data-stu-id="cc9c9-119">Title</span></span>|<span data-ttu-id="cc9c9-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc9c9-120">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="cc9c9-121">Varianza en interfaces genéricas (C#)</span><span class="sxs-lookup"><span data-stu-id="cc9c9-121">Variance in Generic Interfaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)|<span data-ttu-id="cc9c9-122">Describe la covarianza y contravarianza en las interfaces genéricas y proporciona una lista de interfaces genéricas variantes en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-122">Discusses covariance and contravariance in generic interfaces and provides a list of variant generic interfaces in the .NET Framework.</span></span>|  
|[<span data-ttu-id="cc9c9-123">Crear interfaces genéricas variantes (C#)</span><span class="sxs-lookup"><span data-stu-id="cc9c9-123">Creating Variant Generic Interfaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)|<span data-ttu-id="cc9c9-124">Se muestra cómo crear interfaces variantes personalizadas.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-124">Shows how to create custom variant interfaces.</span></span>|  
|[<span data-ttu-id="cc9c9-125">Usar la varianza en interfaces para las colecciones genéricas (C#)</span><span class="sxs-lookup"><span data-stu-id="cc9c9-125">Using Variance in Interfaces for Generic Collections (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)|<span data-ttu-id="cc9c9-126">Se muestra cómo la compatibilidad de covarianza y contravarianza en las interfaces <xref:System.Collections.Generic.IEnumerable%601> y <xref:System.IComparable%601> puede ayudarle a volver a usar el código.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-126">Shows how covariance and contravariance support in the <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601> interfaces can help you reuse code.</span></span>|  
|[<span data-ttu-id="cc9c9-127">Varianza en delegados (C#)</span><span class="sxs-lookup"><span data-stu-id="cc9c9-127">Variance in Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)|<span data-ttu-id="cc9c9-128">Se describe la covarianza y contravarianza en delegados genéricos y no genéricos y se proporciona una lista de delegados genéricos variantes en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-128">Discusses covariance and contravariance in generic and non-generic delegates and provides a list of variant generic delegates in the .NET Framework.</span></span>|  
|[<span data-ttu-id="cc9c9-129">Usar varianza en delegados (C#)</span><span class="sxs-lookup"><span data-stu-id="cc9c9-129">Using Variance in Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)|<span data-ttu-id="cc9c9-130">Se muestra cómo usar la compatibilidad de covarianza y contravarianza en los delegados no genéricos para que coincidan las firmas de método con los tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-130">Shows how to use covariance and contravariance support in non-generic delegates to match method signatures with delegate types.</span></span>|  
|<span data-ttu-id="cc9c9-131">[Using Variance for Func and Action Generic Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md) (Usar la varianza para los delegados genéricos Func y Action (C#))</span><span class="sxs-lookup"><span data-stu-id="cc9c9-131">[Using Variance for Func and Action Generic Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span></span>|<span data-ttu-id="cc9c9-132">Se muestra cómo la compatibilidad de covarianza y contravarianza en los delegados `Func` y `Action` puede ayudarle a volver a usar el código.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-132">Shows how covariance and contravariance support in the `Func` and `Action` delegates can help you reuse code.</span></span>|

