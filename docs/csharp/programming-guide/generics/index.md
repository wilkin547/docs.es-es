---
title: "Genéricos (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 0dc2fcee3903b80816c98bab47e2b9a2e5ef78b0
ms.openlocfilehash: de81058173b0985577474e8601aa84d4e83336a5
ms.contentlocale: es-es
ms.lasthandoff: 08/28/2017

---
# <a name="generics-c-programming-guide"></a><span data-ttu-id="dc1bb-102">Genéricos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="dc1bb-102">Generics (C# Programming Guide)</span></span>
<span data-ttu-id="dc1bb-103">Los genéricos se han agregado a la versión 2.0 del lenguaje C# y Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="dc1bb-103">Generics were added to version 2.0 of the C# language and the common language runtime (CLR).</span></span> <span data-ttu-id="dc1bb-104">Los genéricos introducen en .NET Framework el concepto de parámetros de tipo, lo que le permite diseñar clases y métodos que aplazan la especificación de uno o varios tipos hasta que el código de cliente declare y cree una instancia de la clase o el método.</span><span class="sxs-lookup"><span data-stu-id="dc1bb-104">Generics introduce to the .NET Framework the concept of type parameters, which make it possible to design classes and methods that defer the specification of one or more types until the class or method is declared and instantiated by client code.</span></span> <span data-ttu-id="dc1bb-105">Por ejemplo, al usar un parámetro de tipo genérico T puede escribir una clase única que otro código de cliente puede usar sin incurrir en el costo o riesgo de conversiones en tiempo de ejecución u operaciones de conversión boxing, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="dc1bb-105">For example, by using a generic type parameter T you can write a single class that other client code can use without incurring the cost or risk of runtime casts or boxing operations, as shown here:</span></span>  
  
 <span data-ttu-id="dc1bb-106">[!code-cs[csProgGuideGenerics#1](../../../csharp/programming-guide/generics/codesnippet/CSharp/index_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="dc1bb-106">[!code-cs[csProgGuideGenerics#1](../../../csharp/programming-guide/generics/codesnippet/CSharp/index_1.cs)]</span></span>  
  
## <a name="generics-overview"></a><span data-ttu-id="dc1bb-107">Información general sobre los genéricos</span><span class="sxs-lookup"><span data-stu-id="dc1bb-107">Generics Overview</span></span>  
  
-   <span data-ttu-id="dc1bb-108">Use tipos genéricos para maximizar la reutilización del código, la seguridad de tipos y el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="dc1bb-108">Use generic types to maximize code reuse, type safety, and performance.</span></span>  
  
-   <span data-ttu-id="dc1bb-109">El uso más común de los genéricos es crear clases de colección.</span><span class="sxs-lookup"><span data-stu-id="dc1bb-109">The most common use of generics is to create collection classes.</span></span>  
  
-   <span data-ttu-id="dc1bb-110">La biblioteca de clases .NET Framework contiene varias clases de colección genéricas nuevas en el espacio de nombres <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="dc1bb-110">The .NET Framework class library contains several new generic collection classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="dc1bb-111">Estas se deberían usar siempre que sea posible en lugar de clases como <xref:System.Collections.ArrayList> en el espacio de nombres <xref:System.Collections>.</span><span class="sxs-lookup"><span data-stu-id="dc1bb-111">These should be used whenever possible instead of classes such as <xref:System.Collections.ArrayList> in the <xref:System.Collections> namespace.</span></span>  
  
-   <span data-ttu-id="dc1bb-112">Puede crear sus propias interfaces, clases, métodos, eventos y delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="dc1bb-112">You can create your own generic interfaces, classes, methods, events and delegates.</span></span>  
  
-   <span data-ttu-id="dc1bb-113">Puede limitar las clases genéricas para habilitar el acceso a métodos en tipos de datos determinados.</span><span class="sxs-lookup"><span data-stu-id="dc1bb-113">Generic classes may be constrained to enable access to methods on particular data types.</span></span>  
  
-   <span data-ttu-id="dc1bb-114">Puede obtener información sobre los tipos que se usan en un tipo de datos genérico en tiempo de ejecución mediante la reflexión.</span><span class="sxs-lookup"><span data-stu-id="dc1bb-114">Information on the types that are used in a generic data type may be obtained at run-time by using reflection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="dc1bb-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="dc1bb-115">Related Sections</span></span>  
 <span data-ttu-id="dc1bb-116">Para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="dc1bb-116">For more information:</span></span>  
  
-   [<span data-ttu-id="dc1bb-117">Introducción a los genéricos</span><span class="sxs-lookup"><span data-stu-id="dc1bb-117">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
  
-   [<span data-ttu-id="dc1bb-118">Ventajas de los genéricos</span><span class="sxs-lookup"><span data-stu-id="dc1bb-118">Benefits of Generics</span></span>](../../../csharp/programming-guide/generics/benefits-of-generics.md)  
  
-   [<span data-ttu-id="dc1bb-119">Parámetros de tipo genérico</span><span class="sxs-lookup"><span data-stu-id="dc1bb-119">Generic Type Parameters</span></span>](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
-   [<span data-ttu-id="dc1bb-120">Restricciones de tipos de parámetros</span><span class="sxs-lookup"><span data-stu-id="dc1bb-120">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
-   [<span data-ttu-id="dc1bb-121">Clases genéricas</span><span class="sxs-lookup"><span data-stu-id="dc1bb-121">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)  
  
-   [<span data-ttu-id="dc1bb-122">Interfaces genéricas</span><span class="sxs-lookup"><span data-stu-id="dc1bb-122">Generic Interfaces</span></span>](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
-   [<span data-ttu-id="dc1bb-123">Métodos genéricos</span><span class="sxs-lookup"><span data-stu-id="dc1bb-123">Generic Methods</span></span>](../../../csharp/programming-guide/generics/generic-methods.md)  
  
-   [<span data-ttu-id="dc1bb-124">Delegados genéricos</span><span class="sxs-lookup"><span data-stu-id="dc1bb-124">Generic Delegates</span></span>](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
-   [<span data-ttu-id="dc1bb-125">Diferencias entre plantillas de C++ y tipos genéricos de C#</span><span class="sxs-lookup"><span data-stu-id="dc1bb-125">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
-   [<span data-ttu-id="dc1bb-126">Genéricos y reflexión</span><span class="sxs-lookup"><span data-stu-id="dc1bb-126">Generics and Reflection</span></span>](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
-   [<span data-ttu-id="dc1bb-127">Genéricos en el motor en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="dc1bb-127">Generics in the Run Time</span></span>](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
-   [<span data-ttu-id="dc1bb-128">Tipos genéricos en la biblioteca de clases de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dc1bb-128">Generics in the .NET Framework Class Library</span></span>](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="dc1bb-129">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="dc1bb-129">C# Language Specification</span></span>  
 <span data-ttu-id="dc1bb-130">Para obtener más información, consulte la [Especificación del lenguaje C#](../../../csharp/language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="dc1bb-130">For more information, see the [C# Language Specification](../../../csharp/language-reference/language-specification/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc1bb-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc1bb-131">See Also</span></span>  
 <span data-ttu-id="dc1bb-132"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="dc1bb-132"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="dc1bb-133">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="dc1bb-133">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="dc1bb-134">[Tipos](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="dc1bb-134">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 <span data-ttu-id="dc1bb-135">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md) </span><span class="sxs-lookup"><span data-stu-id="dc1bb-135">[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md) </span></span>  
 [<span data-ttu-id="dc1bb-136">\<typeparamref></span><span class="sxs-lookup"><span data-stu-id="dc1bb-136">\<typeparamref></span></span>](../../../csharp/programming-guide/xmldoc/typeparamref.md)

