---
title: 'Introducción a los genéricos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], about generics
ms.assetid: a1ad761e-42f7-41dd-a62f-452a2de26b9d
ms.openlocfilehash: d09cc686e934f722193cb4671d25671f7f4ef5f7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978519"
---
# <a name="introduction-to-generics-c-programming-guide"></a><span data-ttu-id="92ebd-102">Introducción a los genéricos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="92ebd-102">Introduction to Generics (C# Programming Guide)</span></span>
<span data-ttu-id="92ebd-103">Las clases y métodos genéricos combinan reusabilidad, seguridad de tipos y eficacia de una manera en que sus homólogos no genéricos no pueden.</span><span class="sxs-lookup"><span data-stu-id="92ebd-103">Generic classes and methods combine reusability, type safety and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="92ebd-104">Los genéricos se usan frecuentemente con colecciones y los métodos que funcionan en ellas.</span><span class="sxs-lookup"><span data-stu-id="92ebd-104">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="92ebd-105">La versión 2.0 de la biblioteca de clases .NET Framework proporciona un nuevo espacio de nombres, <xref:System.Collections.Generic>, que contiene varias clases de colección nuevas basadas en genéricos.</span><span class="sxs-lookup"><span data-stu-id="92ebd-105">Version 2.0 of the .NET Framework class library provides a new namespace, <xref:System.Collections.Generic>, which contains several new generic-based collection classes.</span></span> <span data-ttu-id="92ebd-106">Se recomienda que todas las aplicaciones destinadas a .NET Framework 2.0 y versiones posteriores usen las nuevas clases de colección genéricas en lugar de sus homólogas no genéricas anteriores como <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="92ebd-106">It is recommended that all applications that target the .NET Framework 2.0 and later use the new generic collection classes instead of the older non-generic counterparts such as <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="92ebd-107">Para más información, vea [Elementos genéricos en .NET](../../../standard/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="92ebd-107">For more information, see [Generics in .NET](../../../standard/generics/index.md).</span></span>  
  
 <span data-ttu-id="92ebd-108">Por supuesto, también se pueden crear tipos y métodos genéricos personalizados para proporcionar soluciones y patrones de diseño generalizados propios con seguridad de tipos y eficaces.</span><span class="sxs-lookup"><span data-stu-id="92ebd-108">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="92ebd-109">En el ejemplo de código siguiente se muestra una clase genérica simple de lista vinculada para fines de demostración.</span><span class="sxs-lookup"><span data-stu-id="92ebd-109">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="92ebd-110">(En la mayoría de los casos, se debe usar la clase <xref:System.Collections.Generic.List%601> proporcionada por la biblioteca de clases .NET Framework en lugar de crear una propia). El parámetro de tipo `T` se usa en diversas ubicaciones donde normalmente se usaría un tipo concreto para indicar el tipo del elemento almacenado en la lista.</span><span class="sxs-lookup"><span data-stu-id="92ebd-110">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by the .NET Framework class library instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="92ebd-111">Se usa de estas formas:</span><span class="sxs-lookup"><span data-stu-id="92ebd-111">It is used in the following ways:</span></span>  
  
-   <span data-ttu-id="92ebd-112">Como el tipo de un parámetro de método en el método `AddHead`.</span><span class="sxs-lookup"><span data-stu-id="92ebd-112">As the type of a method parameter in the `AddHead` method.</span></span>  
  
-   <span data-ttu-id="92ebd-113">Como el tipo de valor devuelto de la propiedad `Data` en la clase anidada `Node`.</span><span class="sxs-lookup"><span data-stu-id="92ebd-113">As the return type of the `Data` property in the nested `Node` class.</span></span>  
  
-   <span data-ttu-id="92ebd-114">Como el tipo de miembro privado `data` de la clase anidada.</span><span class="sxs-lookup"><span data-stu-id="92ebd-114">As the type of the private member `data` in the nested class.</span></span>  
  
 <span data-ttu-id="92ebd-115">Tenga en cuenta que T está disponible para la clase anidada `Node`.</span><span class="sxs-lookup"><span data-stu-id="92ebd-115">Note that T is available to the nested `Node` class.</span></span> <span data-ttu-id="92ebd-116">Cuando se crea una instancia de `GenericList<T>` con un tipo concreto, por ejemplo como un `GenericList<int>`, cada repetición de `T` se sustituye por `int`.</span><span class="sxs-lookup"><span data-stu-id="92ebd-116">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)]  
  
 <span data-ttu-id="92ebd-117">En el ejemplo de código siguiente se muestra cómo el código de cliente usa la clase genérica `GenericList<T>` para crear una lista de enteros.</span><span class="sxs-lookup"><span data-stu-id="92ebd-117">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="92ebd-118">Simplemente cambiando el argumento de tipo, el código siguiente puede modificarse fácilmente para crear listas de cadenas o cualquier otro tipo personalizado:</span><span class="sxs-lookup"><span data-stu-id="92ebd-118">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="92ebd-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="92ebd-119">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="92ebd-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="92ebd-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="92ebd-121">Genéricos</span><span class="sxs-lookup"><span data-stu-id="92ebd-121">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
