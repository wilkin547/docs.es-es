---
title: 'Operador stackalloc: Referencia de C#'
ms.custom: seodec18
ms.date: 06/10/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: f211acaa8c47ab42a1f7f06cff6c35570cd22b75
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433829"
---
# <a name="stackalloc-operator-c-reference"></a><span data-ttu-id="0e5fe-102">Operador stackalloc (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0e5fe-102">stackalloc operator (C# reference)</span></span>

<span data-ttu-id="0e5fe-103">El operador `stackalloc` asigna un bloque de memoria en la pila.</span><span class="sxs-lookup"><span data-stu-id="0e5fe-103">The `stackalloc` operator allocates a block of memory on the stack.</span></span> <span data-ttu-id="0e5fe-104">Un bloque de memoria asignado a la pila creado durante la ejecución del método se descarta automáticamente cuando se devuelva dicho método.</span><span class="sxs-lookup"><span data-stu-id="0e5fe-104">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="0e5fe-105">No puede liberar explícitamente memoria asignada con el operador `stackalloc`.</span><span class="sxs-lookup"><span data-stu-id="0e5fe-105">You cannot explicitly free memory allocated with the `stackalloc` operator.</span></span> <span data-ttu-id="0e5fe-106">Un bloque de memoria asignada a la pila no está sujeto a [recolección de elementos no utilizados](../../../standard/garbage-collection/index.md) y no tiene que fijarse con la instrucción [`fixed`](../keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0e5fe-106">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with the [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="0e5fe-107">En la expresión `stackalloc T[E]`, `T` debe ser un [tipo no administrado](../builtin-types/unmanaged-types.md) y `E` debe ser una expresión de tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="0e5fe-107">In expression `stackalloc T[E]`, `T` must be an [unmanaged type](../builtin-types/unmanaged-types.md) and `E` must be an expression of type `int`.</span></span>

<span data-ttu-id="0e5fe-108">Puede asignar el resultado del operador `stackalloc` a una variable de uno de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="0e5fe-108">You can assign the result of the `stackalloc` operator to a variable of one of the following types:</span></span>

- <span data-ttu-id="0e5fe-109">A partir de C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> o <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0e5fe-109">Starting with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="0e5fe-110">No tiene que usar un contexto [unsafe](../keywords/unsafe.md) al asignar un bloque de memoria asignado a la pila para una variable <xref:System.Span%601> o <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="0e5fe-110">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="0e5fe-111">Cuando se trabaja con esos tipos, puede usar una expresión `stackalloc` en expresiones [condicionales](conditional-operator.md) o de asignación, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0e5fe-111">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AsExpression)]

  > [!NOTE]
  > <span data-ttu-id="0e5fe-112">Se recomienda usar los tipos <xref:System.Span%601> o <xref:System.ReadOnlySpan%601> para trabajar con memoria asignada a la pila siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="0e5fe-112">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="0e5fe-113">Un [tipo de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0e5fe-113">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="0e5fe-114">Como se muestra en el ejemplo anterior, se debe utilizar un contexto `unsafe` cuando se trabaja con tipos de puntero.</span><span class="sxs-lookup"><span data-stu-id="0e5fe-114">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

<span data-ttu-id="0e5fe-115">El contenido de la memoria recién asignada está sin definir.</span><span class="sxs-lookup"><span data-stu-id="0e5fe-115">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="0e5fe-116">A partir de C# 7.3, puede usar la sintaxis de inicializador de matriz para definir el contenido de la memoria recién asignada.</span><span class="sxs-lookup"><span data-stu-id="0e5fe-116">Starting with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="0e5fe-117">En el ejemplo siguiente se muestran diversas formas de hacerlo:</span><span class="sxs-lookup"><span data-stu-id="0e5fe-117">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](~/samples/csharp/language-reference/operators/StackallocOperator.cs#StackallocInit)]

## <a name="security"></a><span data-ttu-id="0e5fe-118">Seguridad</span><span class="sxs-lookup"><span data-stu-id="0e5fe-118">Security</span></span>

<span data-ttu-id="0e5fe-119">El uso de `stackalloc` habilita automáticamente las características de detección de saturación del búfer en el entorno Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0e5fe-119">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="0e5fe-120">Si se detecta saturación del búfer, se finaliza el proceso lo antes posible para minimizar el riesgo de que se ejecute código malintencionado.</span><span class="sxs-lookup"><span data-stu-id="0e5fe-120">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0e5fe-121">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="0e5fe-121">C# language specification</span></span>

<span data-ttu-id="0e5fe-122">Para obtener más información, vea la sección sobre [asignación de pila](~/_csharplang/spec/unsafe-code.md#stack-allocation) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="0e5fe-122">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0e5fe-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e5fe-123">See also</span></span>

- [<span data-ttu-id="0e5fe-124">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="0e5fe-124">C# reference</span></span>](../index.md)
- [<span data-ttu-id="0e5fe-125">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="0e5fe-125">C# operators</span></span>](index.md)
- [<span data-ttu-id="0e5fe-126">Operadores relacionados con el puntero</span><span class="sxs-lookup"><span data-stu-id="0e5fe-126">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="0e5fe-127">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="0e5fe-127">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="0e5fe-128">Tipos relacionados con el intervalo y la memoria</span><span class="sxs-lookup"><span data-stu-id="0e5fe-128">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
