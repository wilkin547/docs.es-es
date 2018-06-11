---
title: fixed (Instrucción, Referencia de C#)
ms.date: 05/10/2018
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.openlocfilehash: 28c8e9bd078e07a185f541214aa5b5ff79018ff5
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2018
ms.locfileid: "34826999"
---
# <a name="fixed-statement-c-reference"></a><span data-ttu-id="21839-102">fixed (Instrucción, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="21839-102">fixed Statement (C# Reference)</span></span>

<span data-ttu-id="21839-103">La instrucción `fixed` evita que el recolector de elementos no utilizados reubique una variable móvil.</span><span class="sxs-lookup"><span data-stu-id="21839-103">The `fixed` statement prevents the garbage collector from relocating a movable variable.</span></span> <span data-ttu-id="21839-104">La instrucción `fixed` solo se permite en un contexto de [unsafe](unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="21839-104">The `fixed` statement is only permitted in an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="21839-105">`fixed` también puede usarse para crear [búferes de tamaño fijo](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span><span class="sxs-lookup"><span data-stu-id="21839-105">`fixed` can also be used to create [fixed size buffers](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>

<span data-ttu-id="21839-106">La instrucción `fixed` establece un puntero a una variable administrada y "ancla" esa variable durante su ejecución.</span><span class="sxs-lookup"><span data-stu-id="21839-106">The `fixed` statement sets a pointer to a managed variable and "pins" that variable during the execution of the statement.</span></span> <span data-ttu-id="21839-107">Los punteros a variables administradas móviles solo son útiles en un contexto `fixed`.</span><span class="sxs-lookup"><span data-stu-id="21839-107">Pointers to movable managed variables are useful only in a `fixed` context.</span></span> <span data-ttu-id="21839-108">Sin un contexto `fixed`, la recolección de elementos no utilizados podría reubicar las variables de forma impredecible.</span><span class="sxs-lookup"><span data-stu-id="21839-108">Without a `fixed` context, garbage collection could relocate the variables unpredictably.</span></span> <span data-ttu-id="21839-109">El compilador de C# solo permite asignar un puntero a una variable administrada en una instrucción `fixed`.</span><span class="sxs-lookup"><span data-stu-id="21839-109">The C# compiler only lets you assign a pointer to a managed variable in a `fixed` statement.</span></span>

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#1)]

<span data-ttu-id="21839-110">Puede inicializar un puntero mediante una matriz, una cadena, un búfer de tamaño fijo o la dirección de una variable.</span><span class="sxs-lookup"><span data-stu-id="21839-110">You can initialize a pointer by using an array, a string, a fixed-size buffer, or the address of a variable.</span></span> <span data-ttu-id="21839-111">En el ejemplo siguiente se muestra el uso de direcciones, matrices y cadenas de variables.</span><span class="sxs-lookup"><span data-stu-id="21839-111">The following example illustrates the use of variable addresses, arrays, and strings.</span></span> <span data-ttu-id="21839-112">Para obtener más información sobre los búferes de tamaño fijo, consulte [Fixed Size Buffers](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md) (Búferes de tamaño fijo).</span><span class="sxs-lookup"><span data-stu-id="21839-112">For more information about fixed-size buffers, see [Fixed Size Buffers](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>

[!code-csharp[Initializing fixed size buffers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#2)]

<span data-ttu-id="21839-113">A partir de C# 7.3, la instrucción `fixed` funciona en tipos adicionales más allá de matrices, cadenas, búferes de tamaño fijo o variables no administradas.</span><span class="sxs-lookup"><span data-stu-id="21839-113">Starting with C# 7.3, the `fixed` statement operates on additional types beyond arrays, strings, fixed-size buffers, or unmanaged variables.</span></span> <span data-ttu-id="21839-114">Cualquier tipo que implemente un método denominado `GetPinnableReference` se puede anclar.</span><span class="sxs-lookup"><span data-stu-id="21839-114">Any type that implements a method named `GetPinnableReference` can be pinned.</span></span> <span data-ttu-id="21839-115">`GetPinnableReference` debe devolver una variable `ref` a un tipo no administrado.</span><span class="sxs-lookup"><span data-stu-id="21839-115">The `GetPinnableReference` must return a `ref` variable to an unmanaged type.</span></span> <span data-ttu-id="21839-116">Consulte el tema sobre [tipos de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="21839-116">See the topic on [pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md) for more information.</span></span> <span data-ttu-id="21839-117">Los tipos de .NET <xref:System.Span%601?displayProperty=nameWithType> y <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> presentados en .NET Core 2.0 usan este patrón y se pueden anclar.</span><span class="sxs-lookup"><span data-stu-id="21839-117">The .NET types <xref:System.Span%601?displayProperty=nameWithType> and <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> introduced in .NET Core 2.0 make use of this pattern and can be pinned.</span></span> <span data-ttu-id="21839-118">Esto se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="21839-118">This is shown in the following example:</span></span>

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#FixedSpan)]

<span data-ttu-id="21839-119">Si crea tipos que deben participar en este patrón, consulta <xref:System.Span%601.GetPinnableReference?displayProperty=nameWithType> para ver un ejemplo de implementación del patrón.</span><span class="sxs-lookup"><span data-stu-id="21839-119">If you are creating types that should participate in this pattern, see <xref:System.Span%601.GetPinnableReference?displayProperty=nameWithType> for an example of implementing the pattern.</span></span>

<span data-ttu-id="21839-120">Es posible inicializar varios punteros en una sola instrucción si todos son del mismo tipo:</span><span class="sxs-lookup"><span data-stu-id="21839-120">Multiple pointers can be initialized in one statement if they are all the same type:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}
```

<span data-ttu-id="21839-121">Para inicializar punteros de tipos diferentes, simplemente anide instrucciones `fixed`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="21839-121">To initialize pointers of different types, simply nest `fixed` statements, as shown in the following example.</span></span>

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#3)]

<span data-ttu-id="21839-122">Después de ejecutar el código de la instrucción, las variables ancladas se desanclan y quedan sujetas a la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="21839-122">After the code in the statement is executed, any pinned variables are unpinned and subject to garbage collection.</span></span> <span data-ttu-id="21839-123">Por lo tanto, no debe apuntar a esas variables fuera de la instrucción `fixed`.</span><span class="sxs-lookup"><span data-stu-id="21839-123">Therefore, do not point to those variables outside the `fixed` statement.</span></span> <span data-ttu-id="21839-124">Las variables declaradas en la instrucción `fixed` se limitan a dicha instrucción, lo que simplifica esta tarea:</span><span class="sxs-lookup"><span data-stu-id="21839-124">The variables declared in the `fixed` statement are scoped to that statement, making this easier:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
   ...
}
// ps and pd are no longer in scope here.
```

<span data-ttu-id="21839-125">Los punteros inicializados en instrucciones `fixed` son variables de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="21839-125">Pointers initialized in `fixed` statements are readonly variables.</span></span> <span data-ttu-id="21839-126">Si quiere modificar el valor del puntero, debe declarar una segunda variable de puntero y modificarla.</span><span class="sxs-lookup"><span data-stu-id="21839-126">If you want to modify the pointer value, you must declare a second pointer variable, and modify that.</span></span> <span data-ttu-id="21839-127">La variable declarada en la instrucción `fixed` no se puede modificar:</span><span class="sxs-lookup"><span data-stu-id="21839-127">The variable declared in the `fixed` statement cannot be modified:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
    byte* pSourceCopy = ps;
    pSourceCopy++; // point to the next element.
    ps++; // invalid: cannot modify ps, as it is declared in the fixed statement.
}
```


<span data-ttu-id="21839-128">En el modo no seguro, puede asignar memoria en la pila, en la que no está sujeta a la recolección de elementos no utilizados y, por tanto, no necesita anclarse.</span><span class="sxs-lookup"><span data-stu-id="21839-128">In unsafe mode, you can allocate memory on the stack, where it is not subject to garbage collection and therefore does not need to be pinned.</span></span> <span data-ttu-id="21839-129">Para obtener más información, consulte [stackalloc](stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="21839-129">For more information, see [stackalloc](stackalloc.md).</span></span>

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="21839-130">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="21839-130">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="21839-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="21839-131">See Also</span></span>

 [<span data-ttu-id="21839-132">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="21839-132">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="21839-133">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="21839-133">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="21839-134">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="21839-134">C# Keywords</span></span>](index.md)  
 [<span data-ttu-id="21839-135">unsafe</span><span class="sxs-lookup"><span data-stu-id="21839-135">unsafe</span></span>](unsafe.md)  
 [<span data-ttu-id="21839-136">Búferes de tamaño fijo</span><span class="sxs-lookup"><span data-stu-id="21839-136">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
