---
title: stackalloc (Referencia de C#)
ms.date: 04/12/2018
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.openlocfilehash: 5926550eea1f5a2f8fb74645f22ca54c2bed3136
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43508585"
---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="2668c-102">stackalloc (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="2668c-102">stackalloc (C# Reference)</span></span>
<span data-ttu-id="2668c-103">La palabra clave `stackalloc` se usa en un contexto de código no seguro para asignar un bloque de memoria a la pila.</span><span class="sxs-lookup"><span data-stu-id="2668c-103">The `stackalloc` keyword is used in an unsafe code context to allocate a block of memory on the stack.</span></span>

```csharp
int* block = stackalloc int[100];
```

## <a name="remarks"></a><span data-ttu-id="2668c-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2668c-104">Remarks</span></span>

<span data-ttu-id="2668c-105">La palabra clave solo es válida en inicializadores de variables locales.</span><span class="sxs-lookup"><span data-stu-id="2668c-105">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="2668c-106">El código siguiente genera errores del compilador.</span><span class="sxs-lookup"><span data-stu-id="2668c-106">The following code causes compiler errors.</span></span>

```csharp
int* block;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
block = stackalloc int[100];
```

<span data-ttu-id="2668c-107">A partir de C# 7.3, puede usar la sintaxis de inicializador de matriz para matrices `stackalloc`.</span><span class="sxs-lookup"><span data-stu-id="2668c-107">Beginning with C# 7.3, you can use array initializer syntax for `stackalloc` arrays.</span></span> <span data-ttu-id="2668c-108">Todas las declaraciones siguientes declaran una matriz con tres elementos cuyos valores son los enteros `1`, `2` y `3`:</span><span class="sxs-lookup"><span data-stu-id="2668c-108">All the following declarations declare an array with three elements whose values are the integers `1`, `2`, and `3`:</span></span>

```csharp
// Valid starting with C# 7.3
int* first = stackalloc int[3] { 1, 2, 3 };
int* second = stackalloc int[] { 1, 2, 3 };
int* third = stackalloc[] { 1, 2, 3 };
```

<span data-ttu-id="2668c-109">Como implica tipos de puntero, `stackalloc` requiere un contexto [unsafe](unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="2668c-109">Because pointer types are involved, `stackalloc` requires an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="2668c-110">Para obtener más información, vea [Código no seguro y punteros](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="2668c-110">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md)</span></span> 

<span data-ttu-id="2668c-111">`stackalloc` es como [_alloca](/cpp/c-runtime-library/reference/alloca) en la biblioteca en tiempo de ejecución de C.</span><span class="sxs-lookup"><span data-stu-id="2668c-111">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>

## <a name="examples"></a><span data-ttu-id="2668c-112">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2668c-112">Examples</span></span>

<span data-ttu-id="2668c-113">En el ejemplo siguiente se calculan y muestran los 20 primeros números de la secuencia de Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="2668c-113">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="2668c-114">Cada número es la suma de los dos números anteriores.</span><span class="sxs-lookup"><span data-stu-id="2668c-114">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="2668c-115">En el código, se asigna a la pila, no al montón, un bloque de memoria de tamaño suficiente para contener 20 elementos del tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="2668c-115">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="2668c-116">La dirección del bloque se almacena en el puntero `fib`.</span><span class="sxs-lookup"><span data-stu-id="2668c-116">The address of the block is stored in the pointer `fib`.</span></span> <span data-ttu-id="2668c-117">Esta memoria no está sujeta a la recolección de elementos no utilizados y, por tanto, no necesita fijarse (mediante [fixed](fixed-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="2668c-117">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](fixed-statement.md)).</span></span> <span data-ttu-id="2668c-118">La duración del bloque de memoria se limita a la duración del método que lo define.</span><span class="sxs-lookup"><span data-stu-id="2668c-118">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="2668c-119">No se puede liberar la memoria antes de que el método vuelva.</span><span class="sxs-lookup"><span data-stu-id="2668c-119">You cannot free the memory before the method returns.</span></span>

[!code-csharp[csrefKeywordsOperator#15](../../../../samples/snippets/csharp/keywords/StackAllocExamples.cs#1)]

<span data-ttu-id="2668c-120">En el ejemplo siguiente, se inicializa una matriz `stackalloc` de enteros en una máscara de bits con un bit establecido en cada elemento.</span><span class="sxs-lookup"><span data-stu-id="2668c-120">The following example initializes a `stackalloc` array of integers to a bit mask with one bit set in each element.</span></span> <span data-ttu-id="2668c-121">Esto demuestra la nueva sintaxis de inicializador disponible a partir de C# 7.3:</span><span class="sxs-lookup"><span data-stu-id="2668c-121">This demonstrates the new initializer syntax available starting in C# 7.3:</span></span>

[!code-csharp[csrefKeywordsOperator#15](../../../../samples/snippets/csharp/keywords/StackAllocExamples.cs#2)]

## <a name="security"></a><span data-ttu-id="2668c-122">Seguridad</span><span class="sxs-lookup"><span data-stu-id="2668c-122">Security</span></span>

<span data-ttu-id="2668c-123">El código no seguro es menos seguro que las alternativas seguras.</span><span class="sxs-lookup"><span data-stu-id="2668c-123">Unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="2668c-124">Pero el uso de `stackalloc` habilita automáticamente las características de detección de saturación del búfer en el entorno Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="2668c-124">However, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="2668c-125">Si se detecta saturación del búfer, se finaliza el proceso lo antes posible para minimizar el riesgo de que se ejecute código malintencionado.</span><span class="sxs-lookup"><span data-stu-id="2668c-125">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2668c-126">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="2668c-126">C# Language Specification</span></span>
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="2668c-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="2668c-127">See Also</span></span>

- [<span data-ttu-id="2668c-128">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="2668c-128">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="2668c-129">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2668c-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="2668c-130">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="2668c-130">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="2668c-131">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="2668c-131">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
- [<span data-ttu-id="2668c-132">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="2668c-132">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
