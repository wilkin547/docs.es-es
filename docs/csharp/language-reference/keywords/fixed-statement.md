---
title: 'fixed (Instrucción): Referencia de C#'
ms.date: 05/10/2018
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.openlocfilehash: e527e8a54a739391d18b180532372b5b70f34d37
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713519"
---
# <a name="fixed-statement-c-reference"></a><span data-ttu-id="6e554-102">fixed (Instrucción, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="6e554-102">fixed Statement (C# Reference)</span></span>

<span data-ttu-id="6e554-103">La instrucción `fixed` evita que el recolector de elementos no utilizados reubique una variable móvil.</span><span class="sxs-lookup"><span data-stu-id="6e554-103">The `fixed` statement prevents the garbage collector from relocating a movable variable.</span></span> <span data-ttu-id="6e554-104">La instrucción `fixed` solo se permite en un contexto de [unsafe](unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="6e554-104">The `fixed` statement is only permitted in an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="6e554-105">También puede usar la palabra clave `fixed` para crear [búferes de tamaño fijo](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span><span class="sxs-lookup"><span data-stu-id="6e554-105">You can also use the `fixed` keyword to create [fixed size buffers](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>

<span data-ttu-id="6e554-106">La instrucción `fixed` establece un puntero a una variable administrada y "ancla" esa variable durante su ejecución.</span><span class="sxs-lookup"><span data-stu-id="6e554-106">The `fixed` statement sets a pointer to a managed variable and "pins" that variable during the execution of the statement.</span></span> <span data-ttu-id="6e554-107">Los punteros a variables administradas móviles solo son útiles en un contexto `fixed`.</span><span class="sxs-lookup"><span data-stu-id="6e554-107">Pointers to movable managed variables are useful only in a `fixed` context.</span></span> <span data-ttu-id="6e554-108">Sin un contexto `fixed`, la recolección de elementos no utilizados podría reubicar las variables de forma impredecible.</span><span class="sxs-lookup"><span data-stu-id="6e554-108">Without a `fixed` context, garbage collection could relocate the variables unpredictably.</span></span> <span data-ttu-id="6e554-109">El compilador de C# solo permite asignar un puntero a una variable administrada en una instrucción `fixed`.</span><span class="sxs-lookup"><span data-stu-id="6e554-109">The C# compiler only lets you assign a pointer to a managed variable in a `fixed` statement.</span></span>

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#1)]

<span data-ttu-id="6e554-110">Puede inicializar un puntero mediante una matriz, una cadena, un búfer de tamaño fijo o la dirección de una variable.</span><span class="sxs-lookup"><span data-stu-id="6e554-110">You can initialize a pointer by using an array, a string, a fixed-size buffer, or the address of a variable.</span></span> <span data-ttu-id="6e554-111">En el ejemplo siguiente se muestra el uso de direcciones, matrices y cadenas de variable:</span><span class="sxs-lookup"><span data-stu-id="6e554-111">The following example illustrates the use of variable addresses, arrays, and strings:</span></span>

[!code-csharp[Initializing fixed size buffers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#2)]

<span data-ttu-id="6e554-112">A partir de C# 7.3, la instrucción `fixed` funciona en tipos adicionales más allá de matrices, cadenas, búferes de tamaño fijo o variables no administradas.</span><span class="sxs-lookup"><span data-stu-id="6e554-112">Starting with C# 7.3, the `fixed` statement operates on additional types beyond arrays, strings, fixed size buffers, or unmanaged variables.</span></span> <span data-ttu-id="6e554-113">Cualquier tipo que implemente un método denominado `GetPinnableReference` se puede anclar.</span><span class="sxs-lookup"><span data-stu-id="6e554-113">Any type that implements a method named `GetPinnableReference` can be pinned.</span></span> <span data-ttu-id="6e554-114">`GetPinnableReference` debe devolver una variable `ref` a un [tipo no administrado](../builtin-types/unmanaged-types.md).</span><span class="sxs-lookup"><span data-stu-id="6e554-114">The `GetPinnableReference` must return a `ref` variable of an [unmanaged type](../builtin-types/unmanaged-types.md).</span></span> <span data-ttu-id="6e554-115">Los tipos de .NET <xref:System.Span%601?displayProperty=nameWithType> y <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> presentados en .NET Core 2.0 usan este patrón y se pueden anclar.</span><span class="sxs-lookup"><span data-stu-id="6e554-115">The .NET types <xref:System.Span%601?displayProperty=nameWithType> and <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> introduced in .NET Core 2.0 make use of this pattern and can be pinned.</span></span> <span data-ttu-id="6e554-116">Esto se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6e554-116">This is shown in the following example:</span></span>

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#FixedSpan)]

<span data-ttu-id="6e554-117">Si crea tipos que deben participar en este patrón, consulte <xref:System.Span%601.GetPinnableReference?displayProperty=nameWithType> para ver un ejemplo de implementación del patrón.</span><span class="sxs-lookup"><span data-stu-id="6e554-117">If you are creating types that should participate in this pattern, see <xref:System.Span%601.GetPinnableReference?displayProperty=nameWithType> for an example of implementing the pattern.</span></span>

<span data-ttu-id="6e554-118">Es posible inicializar varios punteros en una sola instrucción si todos son del mismo tipo:</span><span class="sxs-lookup"><span data-stu-id="6e554-118">Multiple pointers can be initialized in one statement if they are all the same type:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}
```

<span data-ttu-id="6e554-119">Para inicializar punteros de tipos diferentes, simplemente anide instrucciones `fixed`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6e554-119">To initialize pointers of different types, simply nest `fixed` statements, as shown in the following example.</span></span>

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#3)]

<span data-ttu-id="6e554-120">Después de ejecutar el código de la instrucción, las variables ancladas se desanclan y quedan sujetas a la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="6e554-120">After the code in the statement is executed, any pinned variables are unpinned and subject to garbage collection.</span></span> <span data-ttu-id="6e554-121">Por lo tanto, no debe apuntar a esas variables fuera de la instrucción `fixed`.</span><span class="sxs-lookup"><span data-stu-id="6e554-121">Therefore, do not point to those variables outside the `fixed` statement.</span></span> <span data-ttu-id="6e554-122">Las variables declaradas en la instrucción `fixed` se limitan a dicha instrucción, lo que simplifica esta tarea:</span><span class="sxs-lookup"><span data-stu-id="6e554-122">The variables declared in the `fixed` statement are scoped to that statement, making this easier:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
   ...
}
// ps and pd are no longer in scope here.
```

<span data-ttu-id="6e554-123">Los punteros inicializados en instrucciones `fixed` son variables de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="6e554-123">Pointers initialized in `fixed` statements are readonly variables.</span></span> <span data-ttu-id="6e554-124">Si quiere modificar el valor del puntero, debe declarar una segunda variable de puntero y modificarla.</span><span class="sxs-lookup"><span data-stu-id="6e554-124">If you want to modify the pointer value, you must declare a second pointer variable, and modify that.</span></span> <span data-ttu-id="6e554-125">La variable declarada en la instrucción `fixed` no se puede modificar:</span><span class="sxs-lookup"><span data-stu-id="6e554-125">The variable declared in the `fixed` statement cannot be modified:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
    byte* pSourceCopy = ps;
    pSourceCopy++; // point to the next element.
    ps++; // invalid: cannot modify ps, as it is declared in the fixed statement.
}
```

<span data-ttu-id="6e554-126">Puede asignar memoria en la pila, donde no está sujeta a la recolección de elementos no utilizados y, por tanto, no necesita anclarse.</span><span class="sxs-lookup"><span data-stu-id="6e554-126">You can allocate memory on the stack, where it is not subject to garbage collection and therefore does not need to be pinned.</span></span> <span data-ttu-id="6e554-127">Para hacerlo, utilice el [operador `stackalloc`](../operators/stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="6e554-127">To do that use the [`stackalloc` operator](../operators/stackalloc.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6e554-128">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="6e554-128">C# language specification</span></span>

<span data-ttu-id="6e554-129">Para más información, consulte la sección [La declaración fixed](~/_csharplang/spec/unsafe-code.md#the-fixed-statement) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="6e554-129">For more information, see [The fixed statement](~/_csharplang/spec/unsafe-code.md#the-fixed-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6e554-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e554-130">See also</span></span>

- [<span data-ttu-id="6e554-131">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="6e554-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6e554-132">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6e554-132">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6e554-133">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="6e554-133">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="6e554-134">unsafe</span><span class="sxs-lookup"><span data-stu-id="6e554-134">unsafe</span></span>](unsafe.md)
- [<span data-ttu-id="6e554-135">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="6e554-135">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="6e554-136">Búferes de tamaño fijo</span><span class="sxs-lookup"><span data-stu-id="6e554-136">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
