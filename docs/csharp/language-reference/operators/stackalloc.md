---
title: 'Expresión stackalloc: referencia de C#'
ms.date: 03/13/2020
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc expression [C#]
ms.openlocfilehash: 2e99ce8b1e44dfa040c1acac799a3a55b375bd91
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546606"
---
# <a name="stackalloc-expression-c-reference"></a><span data-ttu-id="77405-102">Expresión stackalloc (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="77405-102">stackalloc expression (C# reference)</span></span>

<span data-ttu-id="77405-103">La expresión `stackalloc` asigna un bloque de memoria en la pila.</span><span class="sxs-lookup"><span data-stu-id="77405-103">A `stackalloc` expression allocates a block of memory on the stack.</span></span> <span data-ttu-id="77405-104">Un bloque de memoria asignado a la pila creado durante la ejecución del método se descarta automáticamente cuando se devuelva dicho método.</span><span class="sxs-lookup"><span data-stu-id="77405-104">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="77405-105">No puede liberar explícitamente memoria asignada con `stackalloc`.</span><span class="sxs-lookup"><span data-stu-id="77405-105">You cannot explicitly free the memory allocated with `stackalloc`.</span></span> <span data-ttu-id="77405-106">Un bloque de memoria asignada a la pila no está sujeto a la [recolección de elementos no utilizados](../../../standard/garbage-collection/index.md) y no tiene que fijarse con una [instrucción `fixed`](../keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="77405-106">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with a [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="77405-107">Puede asignar el resultado de una expresión `stackalloc` a una variable de uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="77405-107">You can assign the result of a `stackalloc` expression to a variable of one of the following types:</span></span>

- <span data-ttu-id="77405-108">A partir de C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> o <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="77405-108">Beginning with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](snippets/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="77405-109">No tiene que usar un contexto [unsafe](../keywords/unsafe.md) al asignar un bloque de memoria asignado a la pila para una variable <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="77405-109">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="77405-110">Cuando se trabaja con esos tipos, puede usar una expresión `stackalloc` en expresiones [condicionales](conditional-operator.md) o de asignación, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="77405-110">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](snippets/StackallocOperator.cs#AsExpression)]

  <span data-ttu-id="77405-111">A partir de C# 8.0, se puede usar una expresión `stackalloc` dentro de otras expresiones siempre que se permita una variable <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="77405-111">Beginning with C# 8.0, you can use a `stackalloc` expression inside other expressions whenever a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable is allowed, as the following example shows:</span></span>

  [!code-csharp[stackalloc in nested expressions](snippets/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > <span data-ttu-id="77405-112">Se recomienda usar los tipos <xref:System.Span%601> o <xref:System.ReadOnlySpan%601> para trabajar con memoria asignada a la pila siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="77405-112">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="77405-113">Un [tipo de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="77405-113">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](snippets/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="77405-114">Como se muestra en el ejemplo anterior, se debe utilizar un contexto `unsafe` cuando se trabaja con tipos de puntero.</span><span class="sxs-lookup"><span data-stu-id="77405-114">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

  <span data-ttu-id="77405-115">En el caso de los tipos de puntero, solo se puede usar una expresión `stackalloc` en una declaración de variable local para inicializar la variable.</span><span class="sxs-lookup"><span data-stu-id="77405-115">In the case of pointer types, you can use a `stackalloc` expression only in a local variable declaration to initialize the variable.</span></span>

<span data-ttu-id="77405-116">La cantidad de memoria disponible en la pila es limitada.</span><span class="sxs-lookup"><span data-stu-id="77405-116">The amount of memory available on the stack is limited.</span></span> <span data-ttu-id="77405-117">Si asigna demasiada memoria en la pila, se produce una excepción <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="77405-117">If you allocate too much memory on the stack, a <xref:System.StackOverflowException> is thrown.</span></span> <span data-ttu-id="77405-118">Para evitarlo, siga estas reglas:</span><span class="sxs-lookup"><span data-stu-id="77405-118">To avoid that, follow the rules below:</span></span>

- <span data-ttu-id="77405-119">Limite la cantidad de memoria asignada con `stackalloc`:</span><span class="sxs-lookup"><span data-stu-id="77405-119">Limit the amount of memory you allocate with `stackalloc`:</span></span>

  [!code-csharp[limit stackalloc](snippets/StackallocOperator.cs#LimitStackalloc)]

  <span data-ttu-id="77405-120">Como la cantidad de memoria disponible en la pila depende del entorno en el que se ejecuta el código, debe ser conservador al definir el valor límite real.</span><span class="sxs-lookup"><span data-stu-id="77405-120">Because the amount of memory available on the stack depends on the environment in which the code is executed, be conservative when you define the actual limit value.</span></span>

- <span data-ttu-id="77405-121">Evite el uso de `stackalloc` dentro de bucles.</span><span class="sxs-lookup"><span data-stu-id="77405-121">Avoid using `stackalloc` inside loops.</span></span> <span data-ttu-id="77405-122">Asigne el bloque de memoria fuera de un bucle y vuelva a usarlo dentro del bucle.</span><span class="sxs-lookup"><span data-stu-id="77405-122">Allocate the memory block outside a loop and reuse it inside the loop.</span></span>

<span data-ttu-id="77405-123">El contenido de la memoria recién asignada está sin definir.</span><span class="sxs-lookup"><span data-stu-id="77405-123">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="77405-124">Debe inicializarlo antes del uso.</span><span class="sxs-lookup"><span data-stu-id="77405-124">You should initialize it before the use.</span></span> <span data-ttu-id="77405-125">Por ejemplo, puede usar el método <xref:System.Span%601.Clear%2A?displayProperty=nameWithType> que establece todos los elementos en el valor predeterminado de tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="77405-125">For example, you can use the <xref:System.Span%601.Clear%2A?displayProperty=nameWithType> method that sets all the items to the default value of type `T`.</span></span>

<span data-ttu-id="77405-126">A partir de C# 7.3, puede usar la sintaxis de inicializador de matriz para definir el contenido de la memoria recién asignada.</span><span class="sxs-lookup"><span data-stu-id="77405-126">Beginning with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="77405-127">En el ejemplo siguiente se muestran diversas formas de hacerlo:</span><span class="sxs-lookup"><span data-stu-id="77405-127">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](snippets/StackallocOperator.cs#StackallocInit)]

<span data-ttu-id="77405-128">En la expresión `stackalloc T[E]`, `T` debe ser un [tipo no administrado](../builtin-types/unmanaged-types.md) y `E` debe evaluarse como un valor [int](../builtin-types/integral-numeric-types.md) no negativo.</span><span class="sxs-lookup"><span data-stu-id="77405-128">In expression `stackalloc T[E]`, `T` must be an [unmanaged type](../builtin-types/unmanaged-types.md) and `E` must evaluate to a non-negative [int](../builtin-types/integral-numeric-types.md) value.</span></span>

## <a name="security"></a><span data-ttu-id="77405-129">Seguridad</span><span class="sxs-lookup"><span data-stu-id="77405-129">Security</span></span>

<span data-ttu-id="77405-130">El uso de `stackalloc` habilita automáticamente las características de detección de saturación del búfer en el entorno Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="77405-130">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="77405-131">Si se detecta saturación del búfer, se finaliza el proceso lo antes posible para minimizar el riesgo de que se ejecute código malintencionado.</span><span class="sxs-lookup"><span data-stu-id="77405-131">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="77405-132">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="77405-132">C# language specification</span></span>

<span data-ttu-id="77405-133">Para más información, consulte la sección sobre [asignación de pila](~/_csharplang/spec/unsafe-code.md#stack-allocation) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md) y la nota de la característica [Permitir `stackalloc` en contextos anidados](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="77405-133">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the [Permit `stackalloc` in nested contexts](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md) feature proposal note.</span></span>

## <a name="see-also"></a><span data-ttu-id="77405-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="77405-134">See also</span></span>

- [<span data-ttu-id="77405-135">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="77405-135">C# reference</span></span>](../index.md)
- [<span data-ttu-id="77405-136">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="77405-136">C# operators</span></span>](index.md)
- [<span data-ttu-id="77405-137">Operadores relacionados con el puntero</span><span class="sxs-lookup"><span data-stu-id="77405-137">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="77405-138">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="77405-138">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="77405-139">Tipos relacionados con el intervalo y la memoria</span><span class="sxs-lookup"><span data-stu-id="77405-139">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="77405-140">Qué hacer y qué no hacer de stackalloc</span><span class="sxs-lookup"><span data-stu-id="77405-140">Dos and Don'ts of stackalloc</span></span>](https://vcsjones.dev/2020/02/24/stackalloc/)
