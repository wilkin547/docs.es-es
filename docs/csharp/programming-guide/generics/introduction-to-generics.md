---
title: 'Introducción a los genéricos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], about generics
ms.assetid: a1ad761e-42f7-41dd-a62f-452a2de26b9d
ms.openlocfilehash: 0d7ecb7f7fd0bb0985234cdc2cf8d37b53323c86
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64595485"
---
# <a name="introduction-to-generics-c-programming-guide"></a><span data-ttu-id="44cd4-102">Introducción a los genéricos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="44cd4-102">Introduction to Generics (C# Programming Guide)</span></span>
<span data-ttu-id="44cd4-103">Las clases y métodos genéricos combinan reusabilidad, seguridad de tipos y eficacia de una manera en que sus homólogos no genéricos no pueden.</span><span class="sxs-lookup"><span data-stu-id="44cd4-103">Generic classes and methods combine reusability, type safety and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="44cd4-104">Los genéricos se usan frecuentemente con colecciones y los métodos que funcionan en ellas.</span><span class="sxs-lookup"><span data-stu-id="44cd4-104">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="44cd4-105">La versión 2.0 de la biblioteca de clases .NET Framework proporciona un nuevo espacio de nombres, <xref:System.Collections.Generic>, que contiene varias clases de colección nuevas basadas en genéricos.</span><span class="sxs-lookup"><span data-stu-id="44cd4-105">Version 2.0 of the .NET Framework class library provides a new namespace, <xref:System.Collections.Generic>, which contains several new generic-based collection classes.</span></span> <span data-ttu-id="44cd4-106">Se recomienda que todas las aplicaciones destinadas a .NET Framework 2.0 y versiones posteriores usen las nuevas clases de colección genéricas en lugar de sus homólogas no genéricas anteriores como <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="44cd4-106">It is recommended that all applications that target the .NET Framework 2.0 and later use the new generic collection classes instead of the older non-generic counterparts such as <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="44cd4-107">Para más información, vea [Elementos genéricos en .NET](../../../standard/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="44cd4-107">For more information, see [Generics in .NET](../../../standard/generics/index.md).</span></span>  
  
 <span data-ttu-id="44cd4-108">Por supuesto, también se pueden crear tipos y métodos genéricos personalizados para proporcionar soluciones y patrones de diseño generalizados propios con seguridad de tipos y eficaces.</span><span class="sxs-lookup"><span data-stu-id="44cd4-108">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="44cd4-109">En el ejemplo de código siguiente se muestra una clase genérica simple de lista vinculada para fines de demostración.</span><span class="sxs-lookup"><span data-stu-id="44cd4-109">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="44cd4-110">(En la mayoría de los casos, se debe usar la clase <xref:System.Collections.Generic.List%601> proporcionada por la biblioteca de clases .NET Framework en lugar de crear una propia). El parámetro de tipo `T` se usa en diversas ubicaciones donde normalmente se usaría un tipo concreto para indicar el tipo del elemento almacenado en la lista.</span><span class="sxs-lookup"><span data-stu-id="44cd4-110">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by the .NET Framework class library instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="44cd4-111">Se usa de estas formas:</span><span class="sxs-lookup"><span data-stu-id="44cd4-111">It is used in the following ways:</span></span>  
  
- <span data-ttu-id="44cd4-112">Como el tipo de un parámetro de método en el método `AddHead`.</span><span class="sxs-lookup"><span data-stu-id="44cd4-112">As the type of a method parameter in the `AddHead` method.</span></span>  
  
- <span data-ttu-id="44cd4-113">Como el tipo de valor devuelto de la propiedad `Data` en la clase anidada `Node`.</span><span class="sxs-lookup"><span data-stu-id="44cd4-113">As the return type of the `Data` property in the nested `Node` class.</span></span>  
  
- <span data-ttu-id="44cd4-114">Como el tipo de miembro privado `data` de la clase anidada.</span><span class="sxs-lookup"><span data-stu-id="44cd4-114">As the type of the private member `data` in the nested class.</span></span>  
  
 <span data-ttu-id="44cd4-115">Tenga en cuenta que T está disponible para la clase anidada `Node`.</span><span class="sxs-lookup"><span data-stu-id="44cd4-115">Note that T is available to the nested `Node` class.</span></span> <span data-ttu-id="44cd4-116">Cuando se crea una instancia de `GenericList<T>` con un tipo concreto, por ejemplo como un `GenericList<int>`, cada repetición de `T` se sustituye por `int`.</span><span class="sxs-lookup"><span data-stu-id="44cd4-116">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)]  
  
 <span data-ttu-id="44cd4-117">En el ejemplo de código siguiente se muestra cómo el código de cliente usa la clase genérica `GenericList<T>` para crear una lista de enteros.</span><span class="sxs-lookup"><span data-stu-id="44cd4-117">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="44cd4-118">Simplemente cambiando el argumento de tipo, el código siguiente puede modificarse fácilmente para crear listas de cadenas o cualquier otro tipo personalizado:</span><span class="sxs-lookup"><span data-stu-id="44cd4-118">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="44cd4-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="44cd4-119">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="44cd4-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="44cd4-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="44cd4-121">Genéricos</span><span class="sxs-lookup"><span data-stu-id="44cd4-121">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
