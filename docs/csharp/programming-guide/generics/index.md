---
title: 'Genéricos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: e32eb7c60e01ca72824ffb3a1e1269cf34650f5a
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423393"
---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="91f3b-102">Genéricos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="91f3b-102">Generics (C# Programming Guide)</span></span>
<span data-ttu-id="91f3b-103">Los genéricos se han agregado a la versión 2.0 del lenguaje C# y Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="91f3b-103">Generics were added to version 2.0 of the C# language and the common language runtime (CLR).</span></span> <span data-ttu-id="91f3b-104">Los genéricos introducen en .NET Framework el concepto de parámetros de tipo, lo que le permite diseñar clases y métodos que aplazan la especificación de uno o varios tipos hasta que el código de cliente declare y cree una instancia de la clase o el método.</span><span class="sxs-lookup"><span data-stu-id="91f3b-104">Generics introduce to the .NET Framework the concept of type parameters, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="91f3b-105">Por ejemplo, al usar un parámetro de tipo genérico T puede escribir una clase única que otro código de cliente puede usar sin incurrir en el costo o riesgo de conversiones en tiempo de ejecución u operaciones de conversión boxing, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="91f3b-105">For example, by using a generic type parameter T you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]  

<span data-ttu-id="91f3b-106">Las clases y métodos genéricos combinan reusabilidad, seguridad de tipos y eficacia de una manera en que sus homólogos no genéricos no pueden.</span><span class="sxs-lookup"><span data-stu-id="91f3b-106">Generic classes and methods combine reusability, type safety and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="91f3b-107">Los genéricos se usan frecuentemente con colecciones y los métodos que funcionan en ellas.</span><span class="sxs-lookup"><span data-stu-id="91f3b-107">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="91f3b-108">La versión 2.0 de la biblioteca de clases .NET Framework proporciona un nuevo espacio de nombres, <xref:System.Collections.Generic>, que contiene varias clases de colección nuevas basadas en genéricos.</span><span class="sxs-lookup"><span data-stu-id="91f3b-108">Version 2.0 of the .NET Framework class library provides a new namespace, <xref:System.Collections.Generic>, which contains several new generic-based collection classes.</span></span> <span data-ttu-id="91f3b-109">Se recomienda que todas las aplicaciones destinadas a .NET Framework 2.0 y versiones posteriores usen las nuevas clases de colección genéricas en lugar de sus homólogas no genéricas anteriores como <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="91f3b-109">It is recommended that all applications that target the .NET Framework 2.0 and later use the new generic collection classes instead of the older non-generic counterparts such as <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="91f3b-110">Para más información, vea [Elementos genéricos en .NET](../../../standard/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="91f3b-110">For more information, see [Generics in .NET](../../../standard/generics/index.md).</span></span>  
  
 <span data-ttu-id="91f3b-111">Por supuesto, también se pueden crear tipos y métodos genéricos personalizados para proporcionar soluciones y patrones de diseño generalizados propios con seguridad de tipos y eficaces.</span><span class="sxs-lookup"><span data-stu-id="91f3b-111">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="91f3b-112">En el ejemplo de código siguiente se muestra una clase genérica simple de lista vinculada para fines de demostración.</span><span class="sxs-lookup"><span data-stu-id="91f3b-112">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="91f3b-113">(En la mayoría de los casos, se debe usar la clase <xref:System.Collections.Generic.List%601> proporcionada por la biblioteca de clases .NET Framework en lugar de crear una propia). El parámetro de tipo `T` se usa en diversas ubicaciones donde normalmente se usaría un tipo concreto para indicar el tipo del elemento almacenado en la lista.</span><span class="sxs-lookup"><span data-stu-id="91f3b-113">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by the .NET Framework class library instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="91f3b-114">Se usa de estas formas:</span><span class="sxs-lookup"><span data-stu-id="91f3b-114">It is used in the following ways:</span></span>  
  
- <span data-ttu-id="91f3b-115">Como el tipo de un parámetro de método en el método `AddHead`.</span><span class="sxs-lookup"><span data-stu-id="91f3b-115">As the type of a method parameter in the `AddHead` method.</span></span>  
  
- <span data-ttu-id="91f3b-116">Como el tipo de valor devuelto de la propiedad `Data` en la clase anidada `Node`.</span><span class="sxs-lookup"><span data-stu-id="91f3b-116">As the return type of the `Data` property in the nested `Node` class.</span></span>  
  
- <span data-ttu-id="91f3b-117">Como el tipo de miembro privado `data` de la clase anidada.</span><span class="sxs-lookup"><span data-stu-id="91f3b-117">As the type of the private member `data` in the nested class.</span></span>  
  
 <span data-ttu-id="91f3b-118">Tenga en cuenta que T está disponible para la clase anidada `Node`.</span><span class="sxs-lookup"><span data-stu-id="91f3b-118">Note that T is available to the nested `Node` class.</span></span> <span data-ttu-id="91f3b-119">Cuando se crea una instancia de `GenericList<T>` con un tipo concreto, por ejemplo como un `GenericList<int>`, cada repetición de `T` se sustituye por `int`.</span><span class="sxs-lookup"><span data-stu-id="91f3b-119">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)]  
  
 <span data-ttu-id="91f3b-120">En el ejemplo de código siguiente se muestra cómo el código de cliente usa la clase genérica `GenericList<T>` para crear una lista de enteros.</span><span class="sxs-lookup"><span data-stu-id="91f3b-120">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="91f3b-121">Simplemente cambiando el argumento de tipo, el código siguiente puede modificarse fácilmente para crear listas de cadenas o cualquier otro tipo personalizado:</span><span class="sxs-lookup"><span data-stu-id="91f3b-121">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]  
  
## <a name="generics-overview"></a><span data-ttu-id="91f3b-122">Información general sobre los genéricos</span><span class="sxs-lookup"><span data-stu-id="91f3b-122">Generics Overview</span></span>  
  
- <span data-ttu-id="91f3b-123">Use tipos genéricos para maximizar la reutilización del código, la seguridad de tipos y el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="91f3b-123">Use generic types to maximize code reuse, type safety, and performance.</span></span>  
  
- <span data-ttu-id="91f3b-124">El uso más común de los genéricos es crear clases de colección.</span><span class="sxs-lookup"><span data-stu-id="91f3b-124">The most common use of generics is to create collection classes.</span></span>  
  
- <span data-ttu-id="91f3b-125">La biblioteca de clases .NET Framework contiene varias clases de colección genéricas nuevas en el espacio de nombres <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="91f3b-125">The .NET Framework class library contains several new generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="91f3b-126">Estas se deberían usar siempre que sea posible en lugar de clases como <xref:System.Collections.ArrayList> en el espacio de nombres <xref:System.Collections>.</span><span class="sxs-lookup"><span data-stu-id="91f3b-126">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>  
  
- <span data-ttu-id="91f3b-127">Puede crear sus propias interfaces, clases, métodos, eventos y delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="91f3b-127">You can create your own generic interfaces, classes, methods, events and delegates.</span></span>  
  
- <span data-ttu-id="91f3b-128">Puede limitar las clases genéricas para habilitar el acceso a métodos en tipos de datos determinados.</span><span class="sxs-lookup"><span data-stu-id="91f3b-128">Generic classes may be constrained to enable access to methods on particular data types.</span></span>  
  
- <span data-ttu-id="91f3b-129">Puede obtener información sobre los tipos que se usan en un tipo de datos genérico en tiempo de ejecución mediante la reflexión.</span><span class="sxs-lookup"><span data-stu-id="91f3b-129">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="91f3b-130">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="91f3b-130">Related Sections</span></span>  
 <span data-ttu-id="91f3b-131">Para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="91f3b-131">For more information:</span></span>  
  
- [<span data-ttu-id="91f3b-132">Parámetros de tipo genérico</span><span class="sxs-lookup"><span data-stu-id="91f3b-132">Generic Type Parameters</span></span>](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
- [<span data-ttu-id="91f3b-133">Restricciones de tipos de parámetros</span><span class="sxs-lookup"><span data-stu-id="91f3b-133">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
- [<span data-ttu-id="91f3b-134">Clases genéricas</span><span class="sxs-lookup"><span data-stu-id="91f3b-134">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)  
  
- [<span data-ttu-id="91f3b-135">Interfaces genéricas</span><span class="sxs-lookup"><span data-stu-id="91f3b-135">Generic Interfaces</span></span>](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
- [<span data-ttu-id="91f3b-136">Métodos genéricos</span><span class="sxs-lookup"><span data-stu-id="91f3b-136">Generic Methods</span></span>](../../../csharp/programming-guide/generics/generic-methods.md)  
  
- [<span data-ttu-id="91f3b-137">Delegados genéricos</span><span class="sxs-lookup"><span data-stu-id="91f3b-137">Generic Delegates</span></span>](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
- [<span data-ttu-id="91f3b-138">Diferencias entre plantillas de C++ y tipos genéricos de C#</span><span class="sxs-lookup"><span data-stu-id="91f3b-138">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
- [<span data-ttu-id="91f3b-139">Genéricos y reflexión</span><span class="sxs-lookup"><span data-stu-id="91f3b-139">Generics and Reflection</span></span>](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
- [<span data-ttu-id="91f3b-140">Genéricos en el motor en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="91f3b-140">Generics in the Run Time</span></span>](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="91f3b-141">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="91f3b-141">C# Language Specification</span></span>  
 <span data-ttu-id="91f3b-142">Para obtener más información, consulte la [Especificación del lenguaje C#](~/_csharplang/spec/types.md#constructed-types).</span><span class="sxs-lookup"><span data-stu-id="91f3b-142">For more information, see the [C# Language Specification](~/_csharplang/spec/types.md#constructed-types).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91f3b-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="91f3b-143">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="91f3b-144">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="91f3b-144">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="91f3b-145">Tipos</span><span class="sxs-lookup"><span data-stu-id="91f3b-145">Types</span></span>](../../../csharp/programming-guide/types/index.md)
- [<span data-ttu-id="91f3b-146">\<typeparam></span><span class="sxs-lookup"><span data-stu-id="91f3b-146">\<typeparam></span></span>](../../../csharp/programming-guide/xmldoc/typeparam.md)
- [<span data-ttu-id="91f3b-147">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="91f3b-147">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)
- [<span data-ttu-id="91f3b-148">Elementos genéricos en .NET</span><span class="sxs-lookup"><span data-stu-id="91f3b-148">Generics in .NET</span></span>](../../../standard/generics/index.md)
