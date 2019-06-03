---
title: 'Palabra clave stackalloc: Referencia de C#'
ms.custom: seodec18
ms.date: 04/10/2019
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.openlocfilehash: c72daa58d2fceb05d9cc9c388a9d2e5dbe062796
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422431"
---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="1cdf2-102">stackalloc (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="1cdf2-102">stackalloc (C# Reference)</span></span>

<span data-ttu-id="1cdf2-103">La palabra clave `stackalloc` se usa para asignar un bloque de memoria en la pila.</span><span class="sxs-lookup"><span data-stu-id="1cdf2-103">The `stackalloc` keyword is used to allocate a block of memory on the stack.</span></span>

```csharp
Span<int> block = stackalloc int[100];
```

<span data-ttu-id="1cdf2-104">La asignación del bloque asignado a un <xref:System.Span%601?displayName=nameWithType> en lugar de un `int*` permite las asignaciones de pila en un bloque seguro.</span><span class="sxs-lookup"><span data-stu-id="1cdf2-104">Assigning the allocated block to a <xref:System.Span%601?displayName=nameWithType> instead of an `int*` allows stack allocations in a safe block.</span></span> <span data-ttu-id="1cdf2-105">No es necesario el contexto `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="1cdf2-105">The `unsafe` context is not required.</span></span>

## <a name="remarks"></a><span data-ttu-id="1cdf2-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1cdf2-106">Remarks</span></span>

<span data-ttu-id="1cdf2-107">La palabra clave solo es válida en inicializadores de variables locales.</span><span class="sxs-lookup"><span data-stu-id="1cdf2-107">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="1cdf2-108">El código siguiente genera errores del compilador.</span><span class="sxs-lookup"><span data-stu-id="1cdf2-108">The following code causes compiler errors.</span></span>

```csharp
int* block;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
block = stackalloc int[100];
Span<int> span;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
span = stackalloc int[100];
```

<span data-ttu-id="1cdf2-109">A partir de C# 7.3, puede usar la sintaxis de inicializador de matriz para matrices `stackalloc`.</span><span class="sxs-lookup"><span data-stu-id="1cdf2-109">Beginning with C# 7.3, you can use array initializer syntax for `stackalloc` arrays.</span></span> <span data-ttu-id="1cdf2-110">Todas las declaraciones siguientes declaran una matriz con tres elementos cuyos valores son los enteros `1`, `2` y `3`.</span><span class="sxs-lookup"><span data-stu-id="1cdf2-110">All the following declarations declare an array with three elements whose values are the integers `1`, `2`, and `3`.</span></span> <span data-ttu-id="1cdf2-111">La segunda inicialización asigna la memoria a un <xref:System.ReadOnlySpan%601>, lo que indica que no se puede modificar la memoria.</span><span class="sxs-lookup"><span data-stu-id="1cdf2-111">The second initialization assigns the memory to a <xref:System.ReadOnlySpan%601>, indicating that the memory cannot be modified.</span></span>

```csharp
// Valid starting with C# 7.3
Span<int> first = stackalloc int[3] { 1, 2, 3 };
ReadOnlySpan<int> second = stackalloc int[] { 1, 2, 3 };
Span<int> third = stackalloc[] { 1, 2, 3 };
```

<span data-ttu-id="1cdf2-112">Cuando se implican tipos de puntero, `stackalloc` requiere un contexto [unsafe](unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="1cdf2-112">When pointer types are involved, `stackalloc` requires an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="1cdf2-113">Para obtener más información, vea [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md) (Código no seguro y punteros [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="1cdf2-113">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>

<span data-ttu-id="1cdf2-114">`stackalloc` es como [_alloca](/cpp/c-runtime-library/reference/alloca) en la biblioteca en tiempo de ejecución de C.</span><span class="sxs-lookup"><span data-stu-id="1cdf2-114">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>

## <a name="examples"></a><span data-ttu-id="1cdf2-115">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="1cdf2-115">Examples</span></span>

<span data-ttu-id="1cdf2-116">En el ejemplo siguiente se calculan y muestran los 20 primeros números de la secuencia de Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="1cdf2-116">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="1cdf2-117">Cada número es la suma de los dos números anteriores.</span><span class="sxs-lookup"><span data-stu-id="1cdf2-117">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="1cdf2-118">En el código, se asigna a la pila, no al montón, un bloque de memoria de tamaño suficiente para contener 20 elementos del tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="1cdf2-118">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="1cdf2-119">La dirección del bloque se almacena en el `Span` `fib`.</span><span class="sxs-lookup"><span data-stu-id="1cdf2-119">The address of the block is stored in the `Span` `fib`.</span></span> <span data-ttu-id="1cdf2-120">Esta memoria no está sujeta a la recolección de elementos no utilizados y, por tanto, no necesita fijarse (mediante [fixed](fixed-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="1cdf2-120">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](fixed-statement.md)).</span></span> <span data-ttu-id="1cdf2-121">La duración del bloque de memoria se limita a la duración del método que lo define.</span><span class="sxs-lookup"><span data-stu-id="1cdf2-121">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="1cdf2-122">No se puede liberar la memoria antes de que el método vuelva.</span><span class="sxs-lookup"><span data-stu-id="1cdf2-122">You cannot free the memory before the method returns.</span></span>

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#1)]

<span data-ttu-id="1cdf2-123">En el ejemplo siguiente, se inicializa una matriz `stackalloc` de enteros en una máscara de bits con un bit establecido en cada elemento.</span><span class="sxs-lookup"><span data-stu-id="1cdf2-123">The following example initializes a `stackalloc` array of integers to a bit mask with one bit set in each element.</span></span> <span data-ttu-id="1cdf2-124">Esto demuestra la nueva sintaxis de inicializador disponible a partir de C# 7.3:</span><span class="sxs-lookup"><span data-stu-id="1cdf2-124">This demonstrates the new initializer syntax available starting in C# 7.3:</span></span>

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#2)]

## <a name="security"></a><span data-ttu-id="1cdf2-125">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1cdf2-125">Security</span></span>

<span data-ttu-id="1cdf2-126">Debe usar <xref:System.Span%601> o <xref:System.ReadOnlySpan%601> cuando sea posible porque el código no administrado es menos seguro que las alternativas seguras.</span><span class="sxs-lookup"><span data-stu-id="1cdf2-126">You should use <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> when possible because unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="1cdf2-127">Incluso cuando se usa con punteros, el uso de `stackalloc` habilita automática las características de detección del búfer en el entorno Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="1cdf2-127">Even when used with pointers, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="1cdf2-128">Si se detecta saturación del búfer, se finaliza el proceso lo antes posible para minimizar el riesgo de que se ejecute código malintencionado.</span><span class="sxs-lookup"><span data-stu-id="1cdf2-128">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1cdf2-129">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="1cdf2-129">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="1cdf2-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="1cdf2-130">See also</span></span>

- [<span data-ttu-id="1cdf2-131">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="1cdf2-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1cdf2-132">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1cdf2-132">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1cdf2-133">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="1cdf2-133">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="1cdf2-134">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="1cdf2-134">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
