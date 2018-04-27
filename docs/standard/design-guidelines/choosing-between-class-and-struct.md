---
title: Elegir entre clases y structs
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- class library design guidelines [.NET Framework], classes
- structures [.NET Framework], vs. classes
- classes [.NET Framework], design guidelines
- type design guidelines, structures
- structures [.NET Framework], design guidelines
- classes [.NET Framework], vs. structures
- type design guidelines, classes
ms.assetid: f8b8ec9b-0ba7-4dea-aadf-a93395cd804f
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d7b7a0b290b97966894b9fa7d3b5597e68037cb0
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="choosing-between-class-and-struct"></a><span data-ttu-id="dbf59-102">Elegir entre clases y structs</span><span class="sxs-lookup"><span data-stu-id="dbf59-102">Choosing Between Class and Struct</span></span>
<span data-ttu-id="dbf59-103">Una de las decisiones de diseño básico que se enfrenta a cada diseñador framework es si va a diseñar un tipo como una clase (un tipo de referencia) o como un struct (un tipo de valor).</span><span class="sxs-lookup"><span data-stu-id="dbf59-103">One of the basic design decisions every framework designer faces is whether to design a type as a class (a reference type) or as a struct (a value type).</span></span> <span data-ttu-id="dbf59-104">Buena comprensión de las diferencias en el comportamiento de los tipos de referencia y tipos de valor es fundamental en la creación de esta opción.</span><span class="sxs-lookup"><span data-stu-id="dbf59-104">Good understanding of the differences in the behavior of reference types and value types is crucial in making this choice.</span></span>  
  
 <span data-ttu-id="dbf59-105">La primera diferencia entre los tipos de referencia y tipos de valor se tendrá en cuenta es que los tipos de referencia se asignan en el montón y recolección, mientras que los tipos de valor se asignan en la pila o en línea en que contiene los tipos y se desasigna cuando la pila desenreda o cuando obtiene cancela la asignación de su tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="dbf59-105">The first difference between reference types and value types we will consider is that reference types are allocated on the heap and garbage-collected, whereas value types are allocated either on the stack or inline in containing types and deallocated when the stack unwinds or when their containing type gets deallocated.</span></span> <span data-ttu-id="dbf59-106">Por lo tanto, las asignaciones y cancelaciones de asignación de tipos de valor son en general más económico que las asignaciones y cancelaciones de asignación de tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="dbf59-106">Therefore, allocations and deallocations of value types are in general cheaper than allocations and deallocations of reference types.</span></span>  
  
 <span data-ttu-id="dbf59-107">A continuación, matrices de tipos de referencia asignan a fuera de línea, lo que significa que la matriz de elementos son simplemente las referencias a las instancias del tipo de referencia que residen en el montón.</span><span class="sxs-lookup"><span data-stu-id="dbf59-107">Next, arrays of reference types are allocated out-of-line, meaning the array elements are just references to instances of the reference type residing on the heap.</span></span> <span data-ttu-id="dbf59-108">Matrices de tipo de valor se asignan en línea, lo que significa que los elementos de matriz son las instancias reales de tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="dbf59-108">Value type arrays are allocated inline, meaning that the array elements are the actual instances of the value type.</span></span> <span data-ttu-id="dbf59-109">Por lo tanto, las asignaciones y desasignaciones de matrices de tipo de valor son mucho más baratas que las asignaciones y desasignaciones de matrices de tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="dbf59-109">Therefore, allocations and deallocations of value type arrays are much cheaper than allocations and deallocations of reference type arrays.</span></span> <span data-ttu-id="dbf59-110">Además, en la mayoría de casos de matrices de tipo de valor exhiben mucho mejor grado de emplazamiento de referencia.</span><span class="sxs-lookup"><span data-stu-id="dbf59-110">In addition, in a majority of cases value type arrays exhibit much better locality of reference.</span></span>  
  
 <span data-ttu-id="dbf59-111">La diferencia siguiente está relacionado con el uso de memoria.</span><span class="sxs-lookup"><span data-stu-id="dbf59-111">The next difference is related to memory usage.</span></span> <span data-ttu-id="dbf59-112">Tipos de valor obtengan conversión boxing cuando se convierte en un tipo de referencia o una de las interfaces que implementan.</span><span class="sxs-lookup"><span data-stu-id="dbf59-112">Value types get boxed when cast to a reference type or one of the interfaces they implement.</span></span> <span data-ttu-id="dbf59-113">Obtienen conversión unboxing cuando se convierte al tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="dbf59-113">They get unboxed when cast back to the value type.</span></span> <span data-ttu-id="dbf59-114">Dado que cuadros son objetos que se asignan en el montón y son recolección, demasiado conversión boxing y unboxing puede tener un impacto negativo en el montón, el recolector de elementos no utilizados y, en última instancia, el rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dbf59-114">Because boxes are objects that are allocated on the heap and are garbage-collected, too much boxing and unboxing can have a negative impact on the heap, the garbage collector, and ultimately the performance of the application.</span></span>  <span data-ttu-id="dbf59-115">En cambio, se produce ninguna conversión boxing tal como tipos de referencia se convierten.</span><span class="sxs-lookup"><span data-stu-id="dbf59-115">In contrast, no such boxing occurs as reference types are cast.</span></span>  
  
 <span data-ttu-id="dbf59-116">A continuación, las asignaciones de tipo de referencia copiar la referencia, mientras que las asignaciones del tipo de valor copie el valor completo.</span><span class="sxs-lookup"><span data-stu-id="dbf59-116">Next, reference type assignments copy the reference, whereas value type assignments copy the entire value.</span></span> <span data-ttu-id="dbf59-117">Por lo tanto, las asignaciones de tipos de referencia de gran tamaño son más baratas que las asignaciones de tipos de valor grande.</span><span class="sxs-lookup"><span data-stu-id="dbf59-117">Therefore, assignments of large reference types are cheaper than assignments of large value types.</span></span>  
  
 <span data-ttu-id="dbf59-118">Por último, los tipos de referencia se pasan por referencia, mientras que los tipos de valor se pasan por valor.</span><span class="sxs-lookup"><span data-stu-id="dbf59-118">Finally, reference types are passed by reference, whereas value types are passed by value.</span></span> <span data-ttu-id="dbf59-119">Cambios en una instancia de un tipo de referencia afectan a todas las referencias que señalan a la instancia.</span><span class="sxs-lookup"><span data-stu-id="dbf59-119">Changes to an instance of a reference type affect all references pointing to the instance.</span></span> <span data-ttu-id="dbf59-120">Instancias del tipo de valor se copian cuando se pasan por valor.</span><span class="sxs-lookup"><span data-stu-id="dbf59-120">Value type instances are copied when they are passed by value.</span></span> <span data-ttu-id="dbf59-121">Cuando se cambia una instancia de un tipo de valor, evidentemente no afecta a cualquiera de sus copias.</span><span class="sxs-lookup"><span data-stu-id="dbf59-121">When an instance of a value type is changed, it of course does not affect any of its copies.</span></span> <span data-ttu-id="dbf59-122">Dado que las copias no se crean explícitamente por el usuario, pero se crean de forma implícita cuando los argumentos se pasan o devuelven los valores se devuelven, los tipos de valor que se pueden cambiar pueden ser confusos para muchos usuarios.</span><span class="sxs-lookup"><span data-stu-id="dbf59-122">Because the copies are not created explicitly by the user but are implicitly created when arguments are passed or return values are returned, value types that can be changed can be confusing to many users.</span></span> <span data-ttu-id="dbf59-123">Por lo tanto, los tipos de valor deben ser inmutables.</span><span class="sxs-lookup"><span data-stu-id="dbf59-123">Therefore, value types should be immutable.</span></span>  
  
 <span data-ttu-id="dbf59-124">Como regla general, la mayoría de los tipos en un marco de trabajo debe ser clases.</span><span class="sxs-lookup"><span data-stu-id="dbf59-124">As a rule of thumb, the majority of types in a framework should be classes.</span></span> <span data-ttu-id="dbf59-125">Sin embargo, existen algunas situaciones en que las características de un tipo de valor que sea más adecuado usar structs.</span><span class="sxs-lookup"><span data-stu-id="dbf59-125">There are, however, some situations in which the characteristics of a value type make it more appropriate to use structs.</span></span>  
  
 <span data-ttu-id="dbf59-126">**✓ Considere la posibilidad de** definir una estructura en lugar de una clase si instancias del tipo son pequeñas y normalmente corta duración o suelen estar incrustadas en otros objetos.</span><span class="sxs-lookup"><span data-stu-id="dbf59-126">**✓ CONSIDER** defining a struct instead of a class if instances of the type are small and commonly short-lived or are commonly embedded in other objects.</span></span>  
  
 <span data-ttu-id="dbf59-127">**X evitar** definir un struct a menos que el tipo tenga todas las características siguientes:</span><span class="sxs-lookup"><span data-stu-id="dbf59-127">**X AVOID** defining a struct unless the type has all of the following characteristics:</span></span>  
  
-   <span data-ttu-id="dbf59-128">Representa lógicamente un valor único, de forma similar a los tipos primitivos (`int`, `double`, etcetera.).</span><span class="sxs-lookup"><span data-stu-id="dbf59-128">It logically represents a single value, similar to primitive types (`int`, `double`, etc.).</span></span>  
  
-   <span data-ttu-id="dbf59-129">Tiene un tamaño de instancia inferior a 16 bytes.</span><span class="sxs-lookup"><span data-stu-id="dbf59-129">It has an instance size under 16 bytes.</span></span>  
  
-   <span data-ttu-id="dbf59-130">Es inmutable.</span><span class="sxs-lookup"><span data-stu-id="dbf59-130">It is immutable.</span></span>  
  
-   <span data-ttu-id="dbf59-131">No tendrá que realizar la conversión boxing con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="dbf59-131">It will not have to be boxed frequently.</span></span>  
  
 <span data-ttu-id="dbf59-132">En todos los demás casos, debe definir los tipos como clases.</span><span class="sxs-lookup"><span data-stu-id="dbf59-132">In all other cases, you should define your types as classes.</span></span>  
  
 <span data-ttu-id="dbf59-133">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="dbf59-133">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="dbf59-134">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="dbf59-134">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbf59-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbf59-135">See Also</span></span>  
 [<span data-ttu-id="dbf59-136">Instrucciones de diseño de tipos</span><span class="sxs-lookup"><span data-stu-id="dbf59-136">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="dbf59-137">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dbf59-137">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
