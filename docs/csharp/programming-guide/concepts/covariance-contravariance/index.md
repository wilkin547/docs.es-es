---
title: Covarianza y contravarianza (C#)
description: Obtenga información sobre la covarianza y la contravarianza, y sobre cómo afectan a la compatibilidad de las asignaciones. Consulte un ejemplo de código en el que se muestran las diferencias que existen entre ellas.
ms.date: 07/20/2015
ms.assetid: 066d9a3c-aab7-4ea6-826d-0b1a85399c74
ms.openlocfilehash: ad4b2a7d7925d7893eb5a8e1d2d7c9ee3dcbd527
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465668"
---
# <a name="covariance-and-contravariance-c"></a><span data-ttu-id="fa26f-104">Covarianza y contravarianza (C#)</span><span class="sxs-lookup"><span data-stu-id="fa26f-104">Covariance and Contravariance (C#)</span></span>
<span data-ttu-id="fa26f-105">En C#, la covarianza y la contravarianza habilitan la conversión de referencias implícita de tipos de matriz, tipos de delegado y argumentos de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="fa26f-105">In C#, covariance and contravariance enable implicit reference conversion for array types, delegate types, and generic type arguments.</span></span> <span data-ttu-id="fa26f-106">La covarianza conserva la compatibilidad de asignaciones y la contravarianza la invierte.</span><span class="sxs-lookup"><span data-stu-id="fa26f-106">Covariance preserves assignment compatibility and contravariance reverses it.</span></span>  
  
 <span data-ttu-id="fa26f-107">El siguiente código muestra la diferencia entre la compatibilidad de asignaciones, la covarianza y la contravarianza.</span><span class="sxs-lookup"><span data-stu-id="fa26f-107">The following code demonstrates the difference between assignment compatibility, covariance, and contravariance.</span></span>  
  
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
  
 <span data-ttu-id="fa26f-108">La covarianza de matrices permite la conversión implícita de una matriz de un tipo más derivado a una matriz de un tipo menos derivado.</span><span class="sxs-lookup"><span data-stu-id="fa26f-108">Covariance for arrays enables implicit conversion of an array of a more derived type to an array of a less derived type.</span></span> <span data-ttu-id="fa26f-109">Pero esta operación no es segura, tal como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="fa26f-109">But this operation is not type safe, as shown in the following code example.</span></span>  
  
```csharp  
object[] array = new String[10];  
// The following statement produces a run-time exception.  
// array[0] = 10;  
```  
  
 <span data-ttu-id="fa26f-110">La compatibilidad de la covarianza y la contravarianza con grupos de métodos permite hacer coincidir firmas de método con tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="fa26f-110">Covariance and contravariance support for method groups allows for matching method signatures with delegate types.</span></span> <span data-ttu-id="fa26f-111">Esto le permite asignar a los delegados no solo métodos con firmas coincidentes, sino métodos que devuelven tipos más derivados (covarianza) o que aceptan parámetros con tipos menos derivados (contravarianza) que el especificado por el tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="fa26f-111">This enables you to assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="fa26f-112">Para obtener más información, vea [Varianza en delegados (C#)](./variance-in-delegates.md) y [Usar varianza en delegados (C#)](./using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="fa26f-112">For more information, see [Variance in Delegates (C#)](./variance-in-delegates.md) and [Using Variance in Delegates (C#)](./using-variance-in-delegates.md).</span></span>  
  
 <span data-ttu-id="fa26f-113">En el ejemplo de código siguiente, se muestra la compatibilidad de covarianza y contravarianza con grupos de métodos.</span><span class="sxs-lookup"><span data-stu-id="fa26f-113">The following code example shows covariance and contravariance support for method groups.</span></span>  
  
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
  
 <span data-ttu-id="fa26f-114">En .NET Framework 4 o versiones posteriores, C# admite la covarianza y contravarianza en las interfaces genéricas y los delegados, y permite la conversión implícita de los parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="fa26f-114">In .NET Framework 4 and later versions, C# supports covariance and contravariance in generic interfaces and delegates and allows for implicit conversion of generic type parameters.</span></span> <span data-ttu-id="fa26f-115">Para obtener más información, vea [Varianza en interfaces genéricas (C#)](./variance-in-generic-interfaces.md) y [Varianza en delegados (C#)](./variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="fa26f-115">For more information, see [Variance in Generic Interfaces (C#)](./variance-in-generic-interfaces.md) and [Variance in Delegates (C#)](./variance-in-delegates.md).</span></span>  
  
 <span data-ttu-id="fa26f-116">En el ejemplo de código siguiente, se muestra la conversión implícita de referencias para interfaces genéricas.</span><span class="sxs-lookup"><span data-stu-id="fa26f-116">The following code example shows implicit reference conversion for generic interfaces.</span></span>  
  
```csharp  
IEnumerable<String> strings = new List<String>();  
IEnumerable<Object> objects = strings;  
```  
  
 <span data-ttu-id="fa26f-117">Un delegado o interfaz genéricos se denominan *variante* si sus parámetros genéricos se declaran como covariantes o contravariantes.</span><span class="sxs-lookup"><span data-stu-id="fa26f-117">A generic interface or delegate is called *variant* if its generic parameters are declared covariant or contravariant.</span></span> <span data-ttu-id="fa26f-118">C# le permite crear sus propias interfaces y delegados variantes.</span><span class="sxs-lookup"><span data-stu-id="fa26f-118">C# enables you to create your own variant interfaces and delegates.</span></span> <span data-ttu-id="fa26f-119">Para obtener más información, consulte [Crear interfaces genéricas variantes (C#)](./creating-variant-generic-interfaces.md) y [Varianza en delegados (C#)](./variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="fa26f-119">For more information, see [Creating Variant Generic Interfaces (C#)](./creating-variant-generic-interfaces.md) and [Variance in Delegates (C#)](./variance-in-delegates.md).</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="fa26f-120">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="fa26f-120">Related Topics</span></span>  
  
|<span data-ttu-id="fa26f-121">Title</span><span class="sxs-lookup"><span data-stu-id="fa26f-121">Title</span></span>|<span data-ttu-id="fa26f-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa26f-122">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="fa26f-123">Varianza en interfaces genéricas (C#)</span><span class="sxs-lookup"><span data-stu-id="fa26f-123">Variance in Generic Interfaces (C#)</span></span>](./variance-in-generic-interfaces.md)|<span data-ttu-id="fa26f-124">Describe la covarianza y contravarianza en las interfaces genéricas y proporciona una lista de interfaces genéricas variantes en .NET.</span><span class="sxs-lookup"><span data-stu-id="fa26f-124">Discusses covariance and contravariance in generic interfaces and provides a list of variant generic interfaces in .NET.</span></span>|  
|[<span data-ttu-id="fa26f-125">Crear interfaces genéricas variantes (C#)</span><span class="sxs-lookup"><span data-stu-id="fa26f-125">Creating Variant Generic Interfaces (C#)</span></span>](./creating-variant-generic-interfaces.md)|<span data-ttu-id="fa26f-126">Se muestra cómo crear interfaces variantes personalizadas.</span><span class="sxs-lookup"><span data-stu-id="fa26f-126">Shows how to create custom variant interfaces.</span></span>|  
|[<span data-ttu-id="fa26f-127">Usar la varianza en interfaces para las colecciones genéricas (C#)</span><span class="sxs-lookup"><span data-stu-id="fa26f-127">Using Variance in Interfaces for Generic Collections (C#)</span></span>](./using-variance-in-interfaces-for-generic-collections.md)|<span data-ttu-id="fa26f-128">Se muestra cómo la compatibilidad de covarianza y contravarianza en las interfaces <xref:System.Collections.Generic.IEnumerable%601> y <xref:System.IComparable%601> puede ayudarle a volver a usar el código.</span><span class="sxs-lookup"><span data-stu-id="fa26f-128">Shows how covariance and contravariance support in the <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601> interfaces can help you reuse code.</span></span>|  
|[<span data-ttu-id="fa26f-129">Varianza en delegados (C#)</span><span class="sxs-lookup"><span data-stu-id="fa26f-129">Variance in Delegates (C#)</span></span>](./variance-in-delegates.md)|<span data-ttu-id="fa26f-130">Se describe la covarianza y contravarianza en delegados genéricos y no genéricos y se proporciona una lista de delegados genéricos variantes en .NET.</span><span class="sxs-lookup"><span data-stu-id="fa26f-130">Discusses covariance and contravariance in generic and non-generic delegates and provides a list of variant generic delegates in .NET.</span></span>|  
|[<span data-ttu-id="fa26f-131">Usar varianza en delegados (C#)</span><span class="sxs-lookup"><span data-stu-id="fa26f-131">Using Variance in Delegates (C#)</span></span>](./using-variance-in-delegates.md)|<span data-ttu-id="fa26f-132">Se muestra cómo usar la compatibilidad de covarianza y contravarianza en los delegados no genéricos para que coincidan las firmas de método con los tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="fa26f-132">Shows how to use covariance and contravariance support in non-generic delegates to match method signatures with delegate types.</span></span>|  
|[<span data-ttu-id="fa26f-133">Usar varianza para los delegados genéricos Func y Action (C#)</span><span class="sxs-lookup"><span data-stu-id="fa26f-133">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)|<span data-ttu-id="fa26f-134">Se muestra cómo la compatibilidad de covarianza y contravarianza en los delegados `Func` y `Action` puede ayudarle a volver a usar el código.</span><span class="sxs-lookup"><span data-stu-id="fa26f-134">Shows how covariance and contravariance support in the `Func` and `Action` delegates can help you reuse code.</span></span>|
