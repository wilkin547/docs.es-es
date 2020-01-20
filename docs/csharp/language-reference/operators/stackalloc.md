---
title: 'Operador stackalloc: Referencia de C#'
ms.date: 09/20/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: 5654cae622cd94c8dad7e58fbc8a99fcf48391a9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712629"
---
# <a name="stackalloc-operator-c-reference"></a><span data-ttu-id="8982f-102">Operador stackalloc (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="8982f-102">stackalloc operator (C# reference)</span></span>

<span data-ttu-id="8982f-103">El operador `stackalloc` asigna un bloque de memoria en la pila.</span><span class="sxs-lookup"><span data-stu-id="8982f-103">The `stackalloc` operator allocates a block of memory on the stack.</span></span> <span data-ttu-id="8982f-104">Un bloque de memoria asignado a la pila creado durante la ejecución del método se descarta automáticamente cuando se devuelva dicho método.</span><span class="sxs-lookup"><span data-stu-id="8982f-104">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="8982f-105">No puede liberar explícitamente memoria asignada con el operador `stackalloc`.</span><span class="sxs-lookup"><span data-stu-id="8982f-105">You cannot explicitly free memory allocated with the `stackalloc` operator.</span></span> <span data-ttu-id="8982f-106">Un bloque de memoria asignada a la pila no está sujeto a la [recolección de elementos no utilizados](../../../standard/garbage-collection/index.md) y no tiene que fijarse con una [instrucción `fixed`](../keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8982f-106">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with a [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="8982f-107">Puede asignar el resultado del operador `stackalloc` a una variable de uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="8982f-107">You can assign the result of the `stackalloc` operator to a variable of one of the following types:</span></span>

- <span data-ttu-id="8982f-108">A partir de C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> o <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8982f-108">Beginning with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="8982f-109">No tiene que usar un contexto [unsafe](../keywords/unsafe.md) al asignar un bloque de memoria asignado a la pila para una variable <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="8982f-109">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="8982f-110">Cuando se trabaja con esos tipos, puede usar una expresión `stackalloc` en expresiones [condicionales](conditional-operator.md) o de asignación, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8982f-110">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AsExpression)]

  <span data-ttu-id="8982f-111">A partir de C# 8.0, se puede usar una expresión `stackalloc` dentro de otras expresiones siempre que se permita una variable <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8982f-111">Beginning with C# 8.0, you can use a `stackalloc` expression inside other expressions whenever a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable is allowed, as the following example shows:</span></span>

  [!code-csharp[stackalloc in nested expressions](~/samples/csharp/language-reference/operators/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > <span data-ttu-id="8982f-112">Se recomienda usar los tipos <xref:System.Span%601> o <xref:System.ReadOnlySpan%601> para trabajar con memoria asignada a la pila siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="8982f-112">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="8982f-113">Un [tipo de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8982f-113">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="8982f-114">Como se muestra en el ejemplo anterior, se debe utilizar un contexto `unsafe` cuando se trabaja con tipos de puntero.</span><span class="sxs-lookup"><span data-stu-id="8982f-114">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

  <span data-ttu-id="8982f-115">En el caso de los tipos de puntero, solo se puede usar una expresión `stackalloc` en una declaración de variable local para inicializar la variable.</span><span class="sxs-lookup"><span data-stu-id="8982f-115">In the case of pointer types, you can use a `stackalloc` expression only in a local variable declaration to initialize the variable.</span></span>

<span data-ttu-id="8982f-116">El contenido de la memoria recién asignada está sin definir.</span><span class="sxs-lookup"><span data-stu-id="8982f-116">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="8982f-117">A partir de C# 7.3, puede usar la sintaxis de inicializador de matriz para definir el contenido de la memoria recién asignada.</span><span class="sxs-lookup"><span data-stu-id="8982f-117">Beginning with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="8982f-118">En el ejemplo siguiente se muestran diversas formas de hacerlo:</span><span class="sxs-lookup"><span data-stu-id="8982f-118">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](~/samples/csharp/language-reference/operators/StackallocOperator.cs#StackallocInit)]

<span data-ttu-id="8982f-119">En la expresión `stackalloc T[E]`, `T` debe ser un [tipo no administrado](../builtin-types/unmanaged-types.md) y `E` debe ser una expresión de tipo [int](../builtin-types/integral-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="8982f-119">In expression `stackalloc T[E]`, `T` must be an [unmanaged type](../builtin-types/unmanaged-types.md) and `E` must be an expression of type [int](../builtin-types/integral-numeric-types.md).</span></span>

## <a name="security"></a><span data-ttu-id="8982f-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="8982f-120">Security</span></span>

<span data-ttu-id="8982f-121">El uso de `stackalloc` habilita automáticamente las características de detección de saturación del búfer en el entorno Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8982f-121">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="8982f-122">Si se detecta saturación del búfer, se finaliza el proceso lo antes posible para minimizar el riesgo de que se ejecute código malintencionado.</span><span class="sxs-lookup"><span data-stu-id="8982f-122">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8982f-123">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="8982f-123">C# language specification</span></span>

<span data-ttu-id="8982f-124">Para más información, consulte la sección sobre [asignación de pila](~/_csharplang/spec/unsafe-code.md#stack-allocation) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md) y la nota de la característica [Permitir `stackalloc` en contextos anidados](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="8982f-124">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the [Permit `stackalloc` in nested contexts](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md) feature proposal note.</span></span>

## <a name="see-also"></a><span data-ttu-id="8982f-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="8982f-125">See also</span></span>

- [<span data-ttu-id="8982f-126">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="8982f-126">C# reference</span></span>](../index.md)
- [<span data-ttu-id="8982f-127">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="8982f-127">C# operators</span></span>](index.md)
- [<span data-ttu-id="8982f-128">Operadores relacionados con el puntero</span><span class="sxs-lookup"><span data-stu-id="8982f-128">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="8982f-129">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="8982f-129">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="8982f-130">Tipos relacionados con el intervalo y la memoria</span><span class="sxs-lookup"><span data-stu-id="8982f-130">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
