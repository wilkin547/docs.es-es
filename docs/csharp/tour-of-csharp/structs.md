---
title: 'Estructuras de C#: un paseo por el lenguaje C#'
description: "Aprenda los conceptos básicos de los tipos de valores de C #, llamados structs."
keywords: .NET, C#, struct, tipo de valor
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 88a74571-f741-4a31-a2b5-1ccf165535b8
ms.openlocfilehash: 9d435fd87a6103d505c14219499eeea9aee045fb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="structs"></a><span data-ttu-id="0ec38-104">Estructuras</span><span class="sxs-lookup"><span data-stu-id="0ec38-104">Structs</span></span>

<span data-ttu-id="0ec38-105">Al igual que las clases, los ***structs*** son estructuras de datos que pueden contener miembros de datos y miembros de función, pero a diferencia de las clases, los structs son tipos de valor y no requieren asignación del montón.</span><span class="sxs-lookup"><span data-stu-id="0ec38-105">Like classes, ***structs*** are data structures that can contain data members and function members, but unlike classes, structs are value types and do not require heap allocation.</span></span> <span data-ttu-id="0ec38-106">Una variable de un tipo de struct almacena directamente los datos del struct, mientras que una variable de un tipo de clase almacena una referencia a un objeto asignado dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="0ec38-106">A variable of a struct type directly stores the data of the struct, whereas a variable of a class type stores a reference to a dynamically allocated object.</span></span> <span data-ttu-id="0ec38-107">Los tipos struct no admiten la herencia especificada por el usuario y todos los tipos de struct se heredan implícitamente del tipo <xref:System.ValueType>, que a su vez se hereda implícitamente de `object`.</span><span class="sxs-lookup"><span data-stu-id="0ec38-107">Struct types do not support user-specified inheritance, and all struct types implicitly inherit from type <xref:System.ValueType>, which in turn implicitly inherits from `object`.</span></span>

<span data-ttu-id="0ec38-108">Los structs son particularmente útiles para estructuras de datos pequeñas que tengan semánticas de valor.</span><span class="sxs-lookup"><span data-stu-id="0ec38-108">Structs are particularly useful for small data structures that have value semantics.</span></span> <span data-ttu-id="0ec38-109">Los números complejos, los puntos de un sistema de coordenadas o los pares clave-valor de un diccionario son buenos ejemplos de structs.</span><span class="sxs-lookup"><span data-stu-id="0ec38-109">Complex numbers, points in a coordinate system, or key-value pairs in a dictionary are all good examples of structs.</span></span> <span data-ttu-id="0ec38-110">El uso de un struct en lugar de una clase para estructuras de datos pequeñas puede suponer una diferencia sustancial en el número de asignaciones de memoria que realiza una aplicación.</span><span class="sxs-lookup"><span data-stu-id="0ec38-110">The use of structs rather than classes for small data structures can make a large difference in the number of memory allocations an application performs.</span></span> <span data-ttu-id="0ec38-111">Por ejemplo, el siguiente programa crea e inicializa una matriz de 100 puntos.</span><span class="sxs-lookup"><span data-stu-id="0ec38-111">For example, the following program creates and initializes an array of 100 points.</span></span> <span data-ttu-id="0ec38-112">Si `Point` se implementa como una clase, se crean instancias de 101 objetos distintos: uno para la matriz y uno por cada uno de los 100 elementos.</span><span class="sxs-lookup"><span data-stu-id="0ec38-112">With `Point` implemented as a class, 101 separate objects are instantiated—one for the array and one each for the 100 elements.</span></span>

[!code-csharp[PointClassUse](../../../samples/snippets/csharp/tour/structs/Program.cs#L5-L13)]

<span data-ttu-id="0ec38-113">Una alternativa es convertir Point en un struct.</span><span class="sxs-lookup"><span data-stu-id="0ec38-113">An alternative is to make Point a struct.</span></span>

[!code-csharp[PointStruct](../../../samples/snippets/csharp/tour/structs/Point.cs#L3-L11)]

<span data-ttu-id="0ec38-114">Ahora, se crea la instancia de un solo objeto: la de la matriz, y las instancias de `Point` se asignan en línea dentro de la matriz.</span><span class="sxs-lookup"><span data-stu-id="0ec38-114">Now, only one object is instantiated—the one for the array—and the `Point` instances are stored in-line in the array.</span></span>

<span data-ttu-id="0ec38-115">Los structs se invocan con el nuevo operador, pero eso no implica que se asigne memoria.</span><span class="sxs-lookup"><span data-stu-id="0ec38-115">Struct constructors are invoked with the new operator, but that does not imply that memory is being allocated.</span></span> <span data-ttu-id="0ec38-116">En lugar de asignar dinámicamente un objeto y devolver una referencia a él, un constructor de structs simplemente devuelve el valor del struct propiamente dicho (normalmente en una ubicación temporal en la pila) y este valor se copia luego cuando es necesario.</span><span class="sxs-lookup"><span data-stu-id="0ec38-116">Instead of dynamically allocating an object and returning a reference to it, a struct constructor simply returns the struct value itself (typically in a temporary location on the stack), and this value is then copied as necessary.</span></span>

<span data-ttu-id="0ec38-117">Con las clases, es posible que dos variables hagan referencia al mismo objeto y, que por tanto, las operaciones en una variable afecten al objeto al que hace referencia la otra variable.</span><span class="sxs-lookup"><span data-stu-id="0ec38-117">With classes, it is possible for two variables to reference the same object and thus possible for operations on one variable to affect the object referenced by the other variable.</span></span> <span data-ttu-id="0ec38-118">Con los struct, cada variable tiene su propia copia de los datos y no es posible que las operaciones en una afecten a la otra.</span><span class="sxs-lookup"><span data-stu-id="0ec38-118">With structs, the variables each have their own copy of the data, and it is not possible for operations on one to affect the other.</span></span> <span data-ttu-id="0ec38-119">Por ejemplo, la salida producida por el fragmento de código siguiente depende de si Point es una clase o un struct.</span><span class="sxs-lookup"><span data-stu-id="0ec38-119">For example, the output produced by the following code fragment depends on whether Point is a class or a struct.</span></span>

[!code-csharp[PointUse](../../../samples/snippets/csharp/tour/structs/Program.cs#L19-L22)]

<span data-ttu-id="0ec38-120">Si `Point` es una clase, la salida es 20 porque a y b hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="0ec38-120">If `Point` is a class, the output is 20 because a and b reference the same object.</span></span> <span data-ttu-id="0ec38-121">Si Point es un struct, la salida es 10 porque la asignación de `a` a `b` crea una copia del valor, y esta copia no se ve afectada por la asignación posterior a `a.x`.</span><span class="sxs-lookup"><span data-stu-id="0ec38-121">If Point is a struct, the output is 10 because the assignment of `a` to `b` creates a copy of the value, and this copy is unaffected by the subsequent assignment to `a.x`.</span></span>

<span data-ttu-id="0ec38-122">En el ejemplo anterior se resaltan dos de las limitaciones de los structs.</span><span class="sxs-lookup"><span data-stu-id="0ec38-122">The previous example highlights two of the limitations of structs.</span></span> <span data-ttu-id="0ec38-123">En primer lugar, copiar un struct entero normalmente es menos eficaz que copiar una referencia a un objeto, por lo que el paso de parámetros de asignación y valor puede ser más costoso con structs que con tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="0ec38-123">First, copying an entire struct is typically less efficient than copying an object reference, so assignment and value parameter passing can be more expensive with structs than with reference types.</span></span> <span data-ttu-id="0ec38-124">En segundo lugar, a excepción de los parámetros `ref` y `out`, no es posible crear referencias a structs, que excluyen su uso en varias situaciones.</span><span class="sxs-lookup"><span data-stu-id="0ec38-124">Second, except for `ref` and `out` parameters, it is not possible to create references to structs, which rules out their usage in a number of situations.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="0ec38-125">[Anterior](classes-and-objects.md)
[Siguiente](arrays.md)</span><span class="sxs-lookup"><span data-stu-id="0ec38-125">[Previous](classes-and-objects.md)
[Next](arrays.md)</span></span>
