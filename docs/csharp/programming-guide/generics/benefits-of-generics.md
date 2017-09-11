---
title: "Ventajas de los genéricos (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], benefits
ms.assetid: 80f037cd-9ea7-48be-bfc1-219bfb2d4277
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8b05a3a695064764618564293e6ccd92e2ce60be
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="benefits-of-generics-c-programming-guide"></a><span data-ttu-id="ddeb6-102">Ventajas de los genéricos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="ddeb6-102">Benefits of Generics (C# Programming Guide)</span></span>
<span data-ttu-id="ddeb6-103">Los genéricos proporcionan la solución a una limitación en versiones anteriores de Common Language Runtime y el lenguaje de C# en el que se obtiene la generalización mediante la conversión de tipos a y desde el tipo base universal <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="ddeb6-103">Generics provide the solution to a limitation in earlier versions of the common language runtime and the C# language in which generalization is accomplished by casting types to and from the universal base type <xref:System.Object>.</span></span> <span data-ttu-id="ddeb6-104">Mediante la creación de una clase genérica, puede crear una colección con seguridad de tipos en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="ddeb6-104">By creating a generic class, you can create a collection that is type-safe at compile-time.</span></span>  
  
 <span data-ttu-id="ddeb6-105">Las limitaciones de usar clases de colección no genéricas pueden mostrarse al escribir un programa corto que use la clase de colección <xref:System.Collections.ArrayList> desde la biblioteca de clases .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ddeb6-105">The limitations of using non-generic collection classes can be demonstrated by writing a short program that uses the <xref:System.Collections.ArrayList> collection class from the .NET Framework class library.</span></span> <span data-ttu-id="ddeb6-106"><xref:System.Collections.ArrayList> es una clase de colección muy conveniente que puede usarse sin modificaciones para almacenar cualquier tipo de valor o referencia.</span><span class="sxs-lookup"><span data-stu-id="ddeb6-106"><xref:System.Collections.ArrayList> is a highly convenient collection class that can be used without modification to store any reference or value type.</span></span>  
  
 <span data-ttu-id="ddeb6-107">[!code-cs[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ddeb6-107">[!code-cs[csProgGuideGenerics#4](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_1.cs)]</span></span>  
  
 <span data-ttu-id="ddeb6-108">Pero esta comodidad tiene un precio.</span><span class="sxs-lookup"><span data-stu-id="ddeb6-108">But this convenience comes at a cost.</span></span> <span data-ttu-id="ddeb6-109">Cualquier tipo de valor o referencia que se agregue a <xref:System.Collections.ArrayList> se convierte implícitamente a <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="ddeb6-109">Any reference or value type that is added to an <xref:System.Collections.ArrayList> is implicitly upcast to <xref:System.Object>.</span></span> <span data-ttu-id="ddeb6-110">Si los elementos son tipos de valor, se les debe aplicar la conversión boxing cuando se agregan a la lista, y se les debe aplicar la conversión unboxing cuando se recuperan.</span><span class="sxs-lookup"><span data-stu-id="ddeb6-110">If the items are value types, they must be boxed when they are added to the list, and unboxed when they are retrieved.</span></span> <span data-ttu-id="ddeb6-111">Las operaciones de conversión y de conversión boxing y unboxing disminuyen el rendimiento; el efecto de la conversión boxing y unboxing puede ser muy importante en escenarios donde debe recorrer en iteración colecciones grandes.</span><span class="sxs-lookup"><span data-stu-id="ddeb6-111">Both the casting and the boxing and unboxing operations decrease performance; the effect of boxing and unboxing can be very significant in scenarios where you must iterate over large collections.</span></span>  
  
 <span data-ttu-id="ddeb6-112">La otra limitación es la falta de comprobación de tipos en tiempo de compilación; como <xref:System.Collections.ArrayList> convierte todo en <xref:System.Object>, no existe ninguna manera en tiempo de compilación de evitar que el código de cliente realice algo como esto:</span><span class="sxs-lookup"><span data-stu-id="ddeb6-112">The other limitation is lack of compile-time type checking; because an <xref:System.Collections.ArrayList> casts everything to <xref:System.Object>, there is no way at compile-time to prevent client code from doing something such as this:</span></span>  
  
 <span data-ttu-id="ddeb6-113">[!code-cs[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="ddeb6-113">[!code-cs[csProgGuideGenerics#5](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_2.cs)]</span></span>  
  
 <span data-ttu-id="ddeb6-114">Aunque es perfectamente aceptable y a veces intencional si está creando una colección heterogénea, combinar cadenas y `ints` en un <xref:System.Collections.ArrayList> único probablemente se deba a un error de programación, y este error no se detectará hasta el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ddeb6-114">Although perfectly acceptable and sometimes intentional if you are creating a heterogeneous collection, combining strings and `ints` in a single <xref:System.Collections.ArrayList> is more likely to be a programming error, and this error will not be detected until runtime.</span></span>  
  
 <span data-ttu-id="ddeb6-115">En las versiones 1.0 y 1.1 del lenguaje de C#, puede evitar los peligros del código generalizado en las clases de colección de la biblioteca de clases base de .NET Framework solo escribiendo sus propias colecciones específicas de tipo.</span><span class="sxs-lookup"><span data-stu-id="ddeb6-115">In versions 1.0 and 1.1 of the C# language, you could avoid the dangers of generalized code in the .NET Framework base class library collection classes only by writing your own type specific collections.</span></span> <span data-ttu-id="ddeb6-116">Por supuesto, como dicha clase no es reutilizable para más de un tipo de datos, se pierden las ventajas de la generalización y tiene que volver a escribir la clase para cada tipo que se almacenará.</span><span class="sxs-lookup"><span data-stu-id="ddeb6-116">Of course, because such a class is not reusable for more than one data type, you lose the benefits of generalization, and you have to rewrite the class for each type that will be stored.</span></span>  
  
 <span data-ttu-id="ddeb6-117">Lo que <xref:System.Collections.ArrayList> y otras clases similares realmente necesitan es una manera de que el código de cliente especifique, en una base por instancia, el tipo de datos determinado que pretenden usar.</span><span class="sxs-lookup"><span data-stu-id="ddeb6-117">What <xref:System.Collections.ArrayList> and other similar classes really need is a way for client code to specify, on a per-instance basis, the particular data type that they intend to use.</span></span> <span data-ttu-id="ddeb6-118">Eso eliminaría la necesidad de la conversión a `T:System.Object` y también haría posible que el compilador realizara una comprobación de tipos.</span><span class="sxs-lookup"><span data-stu-id="ddeb6-118">That would eliminate the need for the upcast to `T:System.Object` and would also make it possible for the compiler to do type checking.</span></span> <span data-ttu-id="ddeb6-119">En otras palabras, <xref:System.Collections.ArrayList> necesita un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="ddeb6-119">In other words, <xref:System.Collections.ArrayList> needs a type parameter.</span></span> <span data-ttu-id="ddeb6-120">Eso es exactamente lo que proporcionan los genéricos.</span><span class="sxs-lookup"><span data-stu-id="ddeb6-120">That is exactly what generics provide.</span></span> <span data-ttu-id="ddeb6-121">En la colección <xref:System.Collections.Generic.List%601> genérica, en el espacio de nombres `N:System.Collections.Generic`, la misma operación de agregar elementos a la colección tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="ddeb6-121">In the generic <xref:System.Collections.Generic.List%601> collection, in the `N:System.Collections.Generic` namespace, the same operation of adding items to the collection resembles this:</span></span>  
  
 <span data-ttu-id="ddeb6-122">[!code-cs[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="ddeb6-122">[!code-cs[csProgGuideGenerics#6](../../../csharp/programming-guide/generics/codesnippet/CSharp/benefits-of-generics_3.cs)]</span></span>  
  
 <span data-ttu-id="ddeb6-123">Para el código de cliente, la única sintaxis agregada con <xref:System.Collections.Generic.List%601> en comparación con <xref:System.Collections.ArrayList> es el argumento de tipo en la declaración y creación de instancias.</span><span class="sxs-lookup"><span data-stu-id="ddeb6-123">For client code, the only added syntax with <xref:System.Collections.Generic.List%601> compared to <xref:System.Collections.ArrayList> is the type argument in the declaration and instantiation.</span></span> <span data-ttu-id="ddeb6-124">A cambio de esta complejidad de codificación ligeramente mayor, puede crear una lista que no solo es más segura que <xref:System.Collections.ArrayList>, sino también significativamente más rápida, especialmente cuando los elementos de lista son tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="ddeb6-124">In return for this slightly more coding complexity, you can create a list that is not only safer than <xref:System.Collections.ArrayList>, but also significantly faster, especially when the list items are value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddeb6-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddeb6-125">See Also</span></span>  
 <span data-ttu-id="ddeb6-126"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="ddeb6-126"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="ddeb6-127">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ddeb6-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ddeb6-128">[Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="ddeb6-128">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 <span data-ttu-id="ddeb6-129">[Conversión boxing y conversión unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md) </span><span class="sxs-lookup"><span data-stu-id="ddeb6-129">[Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md) </span></span>  
 [<span data-ttu-id="ddeb6-130">Procedimientos recomendados de colecciones</span><span class="sxs-lookup"><span data-stu-id="ddeb6-130">Collections Best Practices</span></span>](http://go.microsoft.com/fwlink/?LinkId=112403)

