---
title: 'Genéricos: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: a3ed3aa412c7d9c9d6b705dba80b527057c647fa
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241674"
---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="09f3f-102">Genéricos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="09f3f-102">Generics (C# Programming Guide)</span></span>

<span data-ttu-id="09f3f-103">Los genéricos introducen el concepto de parámetros de tipo a .NET, lo que le permite diseñar clases y métodos que aplazan la especificación de uno o varios tipos hasta que el código de cliente declare y cree una instancia de la clase o el método.</span><span class="sxs-lookup"><span data-stu-id="09f3f-103">Generics introduce the concept of type parameters to .NET, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="09f3f-104">Por ejemplo, al usar un parámetro de tipo genérico `T`, puede escribir una clase única que otro código de cliente puede usar sin incurrir en el costo o riesgo de conversiones en tiempo de ejecución u operaciones de conversión boxing, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="09f3f-104">For example, by using a generic type parameter `T`, you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>

[!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]

<span data-ttu-id="09f3f-105">Las clases y métodos genéricos combinan reusabilidad, seguridad de tipos y eficacia de una manera en que sus homólogos no genéricos no pueden.</span><span class="sxs-lookup"><span data-stu-id="09f3f-105">Generic classes and methods combine reusability, type safety, and efficiency in a way that their non-generic counterparts cannot.</span></span> <span data-ttu-id="09f3f-106">Los genéricos se usan frecuentemente con colecciones y los métodos que funcionan en ellas.</span><span class="sxs-lookup"><span data-stu-id="09f3f-106">Generics are most frequently used with collections and the methods that operate on them.</span></span> <span data-ttu-id="09f3f-107">El espacio de nombres <xref:System.Collections.Generic> contiene varias clases de colecciones basadas en genéricos.</span><span class="sxs-lookup"><span data-stu-id="09f3f-107">The <xref:System.Collections.Generic> namespace contains several generic-based collection classes.</span></span> <span data-ttu-id="09f3f-108">No se recomiendan las colecciones no genéricas, como <xref:System.Collections.ArrayList>, y se mantienen por compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="09f3f-108">The non-generic collections, such as <xref:System.Collections.ArrayList> are not recommended and are maintained for compatibility purposes.</span></span> <span data-ttu-id="09f3f-109">Para más información, vea [Elementos genéricos en .NET](../../../standard/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="09f3f-109">For more information, see [Generics in .NET](../../../standard/generics/index.md).</span></span>

<span data-ttu-id="09f3f-110">Por supuesto, también se pueden crear tipos y métodos genéricos personalizados para proporcionar soluciones y patrones de diseño generalizados propios con seguridad de tipos y eficaces.</span><span class="sxs-lookup"><span data-stu-id="09f3f-110">Of course, you can also create custom generic types and methods to provide your own generalized solutions and design patterns that are type-safe and efficient.</span></span> <span data-ttu-id="09f3f-111">En el ejemplo de código siguiente se muestra una clase genérica simple de lista vinculada para fines de demostración.</span><span class="sxs-lookup"><span data-stu-id="09f3f-111">The following code example shows a simple generic linked-list class for demonstration purposes.</span></span> <span data-ttu-id="09f3f-112">(En la mayoría de los casos, debe usar la clase <xref:System.Collections.Generic.List%601> proporcionada por .NET en lugar de crear la suya propia). El parámetro de tipo `T` se usa en diversas ubicaciones donde normalmente se usaría un tipo concreto para indicar el tipo del elemento almacenado en la lista.</span><span class="sxs-lookup"><span data-stu-id="09f3f-112">(In most cases, you should use the <xref:System.Collections.Generic.List%601> class provided by .NET instead of creating your own.) The type parameter `T` is used in several locations where a concrete type would ordinarily be used to indicate the type of the item stored in the list.</span></span> <span data-ttu-id="09f3f-113">Se usa de estas formas:</span><span class="sxs-lookup"><span data-stu-id="09f3f-113">It is used in the following ways:</span></span>

- <span data-ttu-id="09f3f-114">Como el tipo de un parámetro de método en el método `AddHead`.</span><span class="sxs-lookup"><span data-stu-id="09f3f-114">As the type of a method parameter in the `AddHead` method.</span></span>
- <span data-ttu-id="09f3f-115">Como el tipo de valor devuelto de la propiedad `Data` en la clase anidada `Node`.</span><span class="sxs-lookup"><span data-stu-id="09f3f-115">As the return type of the `Data` property in the nested `Node` class.</span></span>
- <span data-ttu-id="09f3f-116">Como el tipo de miembro privado `data` de la clase anidada.</span><span class="sxs-lookup"><span data-stu-id="09f3f-116">As the type of the private member `data` in the nested class.</span></span>

 <span data-ttu-id="09f3f-117">Tenga en cuenta que `T` está disponible para la clase anidada `Node`.</span><span class="sxs-lookup"><span data-stu-id="09f3f-117">Note that `T` is available to the nested `Node` class.</span></span> <span data-ttu-id="09f3f-118">Cuando se crea una instancia de `GenericList<T>` con un tipo concreto, por ejemplo como un `GenericList<int>`, cada repetición de `T` se sustituye por `int`.</span><span class="sxs-lookup"><span data-stu-id="09f3f-118">When `GenericList<T>` is instantiated with a concrete type, for example as a `GenericList<int>`, each occurrence of `T` will be replaced with `int`.</span></span>

[!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)]

<span data-ttu-id="09f3f-119">En el ejemplo de código siguiente se muestra cómo el código de cliente usa la clase genérica `GenericList<T>` para crear una lista de enteros.</span><span class="sxs-lookup"><span data-stu-id="09f3f-119">The following code example shows how client code uses the generic `GenericList<T>` class to create a list of integers.</span></span> <span data-ttu-id="09f3f-120">Simplemente cambiando el argumento de tipo, el código siguiente puede modificarse fácilmente para crear listas de cadenas o cualquier otro tipo personalizado:</span><span class="sxs-lookup"><span data-stu-id="09f3f-120">Simply by changing the type argument, the following code could easily be modified to create lists of strings or any other custom type:</span></span>

[!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]

## <a name="generics-overview"></a><span data-ttu-id="09f3f-121">Introducción a los genéricos</span><span class="sxs-lookup"><span data-stu-id="09f3f-121">Generics overview</span></span>

- <span data-ttu-id="09f3f-122">Use tipos genéricos para maximizar la reutilización del código, la seguridad de tipos y el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="09f3f-122">Use generic types to maximize code reuse, type safety, and performance.</span></span>
- <span data-ttu-id="09f3f-123">El uso más común de los genéricos es crear clases de colección.</span><span class="sxs-lookup"><span data-stu-id="09f3f-123">The most common use of generics is to create collection classes.</span></span>
- <span data-ttu-id="09f3f-124">La biblioteca de clases de .NET contiene varias clases de colección genéricas en el espacio de nombres <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="09f3f-124">The .NET class library contains several generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="09f3f-125">Estas se deberían usar siempre que sea posible en lugar de clases como <xref:System.Collections.ArrayList> en el espacio de nombres <xref:System.Collections>.</span><span class="sxs-lookup"><span data-stu-id="09f3f-125">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>
- <span data-ttu-id="09f3f-126">Puede crear sus propias interfaces, clases, métodos, eventos y delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="09f3f-126">You can create your own generic interfaces, classes, methods, events, and delegates.</span></span>
- <span data-ttu-id="09f3f-127">Puede limitar las clases genéricas para habilitar el acceso a métodos en tipos de datos determinados.</span><span class="sxs-lookup"><span data-stu-id="09f3f-127">Generic classes may be constrained to enable access to methods on particular data types.</span></span>
- <span data-ttu-id="09f3f-128">Puede obtener información sobre los tipos que se usan en un tipo de datos genérico en tiempo de ejecución mediante la reflexión.</span><span class="sxs-lookup"><span data-stu-id="09f3f-128">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>

## <a name="related-sections"></a><span data-ttu-id="09f3f-129">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="09f3f-129">Related sections</span></span>

- [<span data-ttu-id="09f3f-130">Parámetros de tipo genérico</span><span class="sxs-lookup"><span data-stu-id="09f3f-130">Generic Type Parameters</span></span>](generic-type-parameters.md)
- [<span data-ttu-id="09f3f-131">Restricciones de tipos de parámetros</span><span class="sxs-lookup"><span data-stu-id="09f3f-131">Constraints on Type Parameters</span></span>](constraints-on-type-parameters.md)
- [<span data-ttu-id="09f3f-132">Clases genéricas</span><span class="sxs-lookup"><span data-stu-id="09f3f-132">Generic Classes</span></span>](generic-classes.md)
- [<span data-ttu-id="09f3f-133">Interfaces genéricas</span><span class="sxs-lookup"><span data-stu-id="09f3f-133">Generic Interfaces</span></span>](generic-interfaces.md)
- [<span data-ttu-id="09f3f-134">Métodos genéricos</span><span class="sxs-lookup"><span data-stu-id="09f3f-134">Generic Methods</span></span>](generic-methods.md)
- [<span data-ttu-id="09f3f-135">Delegados genéricos</span><span class="sxs-lookup"><span data-stu-id="09f3f-135">Generic Delegates</span></span>](generic-delegates.md)
- [<span data-ttu-id="09f3f-136">Diferencias entre plantillas de C++ y tipos genéricos de C#</span><span class="sxs-lookup"><span data-stu-id="09f3f-136">Differences Between C++ Templates and C# Generics</span></span>](differences-between-cpp-templates-and-csharp-generics.md)
- [<span data-ttu-id="09f3f-137">Genéricos y reflexión</span><span class="sxs-lookup"><span data-stu-id="09f3f-137">Generics and Reflection</span></span>](generics-and-reflection.md)
- [<span data-ttu-id="09f3f-138">Genéricos en el motor en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="09f3f-138">Generics in the Run Time</span></span>](generics-in-the-run-time.md)

## <a name="c-language-specification"></a><span data-ttu-id="09f3f-139">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="09f3f-139">C# language specification</span></span>

<span data-ttu-id="09f3f-140">Para obtener más información, consulte la [Especificación del lenguaje C#](~/_csharplang/spec/types.md#constructed-types).</span><span class="sxs-lookup"><span data-stu-id="09f3f-140">For more information, see the [C# Language Specification](~/_csharplang/spec/types.md#constructed-types).</span></span>

## <a name="see-also"></a><span data-ttu-id="09f3f-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="09f3f-141">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="09f3f-142">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="09f3f-142">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="09f3f-143">Tipos</span><span class="sxs-lookup"><span data-stu-id="09f3f-143">Types</span></span>](../types/index.md)
- [\<typeparam>](../xmldoc/typeparam.md)
- [\<typeparamref>](../xmldoc/typeparamref.md)
- [<span data-ttu-id="09f3f-144">Elementos genéricos en .NET</span><span class="sxs-lookup"><span data-stu-id="09f3f-144">Generics in .NET</span></span>](../../../standard/generics/index.md)
