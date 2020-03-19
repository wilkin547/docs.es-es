---
title: 'Búferes de tamaño fijo: Guía de programación de C#'
ms.date: 04/20/2018
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.openlocfilehash: 6770497b23212f1786b4f4a620ed2b650079c44b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79157031"
---
# <a name="fixed-size-buffers-c-programming-guide"></a><span data-ttu-id="4e49e-102">Búferes de tamaño fijo (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="4e49e-102">Fixed Size Buffers (C# Programming Guide)</span></span>

<span data-ttu-id="4e49e-103">En C#, puede usar la instrucción [fixed](../../language-reference/keywords/fixed-statement.md) para crear un búfer con una matriz de tamaño fijo en una estructura de datos.</span><span class="sxs-lookup"><span data-stu-id="4e49e-103">In C#, you can use the [fixed](../../language-reference/keywords/fixed-statement.md) statement to create a buffer with a fixed size array in a data structure.</span></span> <span data-ttu-id="4e49e-104">Los búferes de tamaño fijo resultan útiles al escribir métodos que interoperan con orígenes de datos de otros lenguajes o plataformas.</span><span class="sxs-lookup"><span data-stu-id="4e49e-104">Fixed size buffers are useful when you write methods that interop with data sources from other languages or platforms.</span></span> <span data-ttu-id="4e49e-105">La matriz fija puede tomar cualquiera de los atributos o modificadores permitidos para los miembros de structs normales.</span><span class="sxs-lookup"><span data-stu-id="4e49e-105">The fixed array can take any attributes or modifiers that are allowed for regular struct members.</span></span> <span data-ttu-id="4e49e-106">La única restricción es que el tipo de matriz debe ser `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` o `double`.</span><span class="sxs-lookup"><span data-stu-id="4e49e-106">The only restriction is that the array type must be `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float`, or `double`.</span></span>

```csharp
private fixed char name[30];
```

## <a name="remarks"></a><span data-ttu-id="4e49e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4e49e-107">Remarks</span></span>

<span data-ttu-id="4e49e-108">En el código seguro, un struct de C# que contiene una matriz no contiene los elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="4e49e-108">In safe code, a C# struct that contains an array does not contain the array elements.</span></span> <span data-ttu-id="4e49e-109">En su lugar, el struct contiene una referencia a los elementos.</span><span class="sxs-lookup"><span data-stu-id="4e49e-109">Instead, the struct contains a reference to the elements.</span></span> <span data-ttu-id="4e49e-110">Puede insertar una matriz de tamaño fijo en un [struct](../../language-reference/builtin-types/struct.md) cuando se usa en un bloque de código [no seguro](../../language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="4e49e-110">You can embed an array of fixed size in a [struct](../../language-reference/builtin-types/struct.md) when it is used in an [unsafe](../../language-reference/keywords/unsafe.md) code block.</span></span>

<span data-ttu-id="4e49e-111">El tamaño del siguiente `struct` no depende del número de elementos en la matriz, ya que `pathName` es una referencia:</span><span class="sxs-lookup"><span data-stu-id="4e49e-111">Size of the following `struct` doesn't depend on the number of elements in the array, since `pathName` is a reference:</span></span>

[!code-csharp[Struct with embedded array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#6)]

<span data-ttu-id="4e49e-112">Un `struct` puede contener una matriz insertada en el código no seguro.</span><span class="sxs-lookup"><span data-stu-id="4e49e-112">A `struct` can contain an embedded array in unsafe code.</span></span> <span data-ttu-id="4e49e-113">En el siguiente ejemplo, la matriz `fixedBuffer` tiene un tamaño fijo.</span><span class="sxs-lookup"><span data-stu-id="4e49e-113">In the following example, the `fixedBuffer` array has a fixed size.</span></span> <span data-ttu-id="4e49e-114">Se usa una instrucción `fixed` para establecer un puntero al primer elemento.</span><span class="sxs-lookup"><span data-stu-id="4e49e-114">You use a `fixed` statement to establish a pointer to the first element.</span></span> <span data-ttu-id="4e49e-115">Se accede a los elementos de la matriz mediante este puntero.</span><span class="sxs-lookup"><span data-stu-id="4e49e-115">You access the elements of the array through this pointer.</span></span> <span data-ttu-id="4e49e-116">La instrucción `fixed` ancla el campo de instancia `fixedBuffer` a una ubicación concreta en la memoria.</span><span class="sxs-lookup"><span data-stu-id="4e49e-116">The `fixed` statement pins the `fixedBuffer` instance field to a specific location in memory.</span></span>

[!code-csharp[Struct with embedded inline array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#7)]

<span data-ttu-id="4e49e-117">El tamaño de la matriz `char` de 128 elementos es 256 bytes.</span><span class="sxs-lookup"><span data-stu-id="4e49e-117">The size of the 128 element `char` array is 256 bytes.</span></span> <span data-ttu-id="4e49e-118">Los búferes [char](../../language-reference/builtin-types/char.md) de tamaño fijo siempre admiten dos bytes por carácter, independientemente de la codificación.</span><span class="sxs-lookup"><span data-stu-id="4e49e-118">Fixed size [char](../../language-reference/builtin-types/char.md) buffers always take two bytes per character, regardless of the encoding.</span></span> <span data-ttu-id="4e49e-119">Esto es verdadero, incluso cuando se calculan las referencias de los búferes de caracteres a los métodos API o structs con `CharSet = CharSet.Auto` o `CharSet = CharSet.Ansi`.</span><span class="sxs-lookup"><span data-stu-id="4e49e-119">This is true even when char buffers are marshaled to API methods or structs with `CharSet = CharSet.Auto` or `CharSet = CharSet.Ansi`.</span></span> <span data-ttu-id="4e49e-120">Para obtener más información, vea <xref:System.Runtime.InteropServices.CharSet>.</span><span class="sxs-lookup"><span data-stu-id="4e49e-120">For more information, see <xref:System.Runtime.InteropServices.CharSet>.</span></span>

<span data-ttu-id="4e49e-121">En el ejemplo anterior se muestra cómo acceder a campos `fixed` sin anclar, lo que está disponible a partir de C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="4e49e-121">The  preceding example demonstrates accessing `fixed` fields without pinning, which is available starting with C# 7.3.</span></span>

<span data-ttu-id="4e49e-122">Otra matriz de tamaño fijo común es la matriz [bool](../../language-reference/builtin-types/bool.md).</span><span class="sxs-lookup"><span data-stu-id="4e49e-122">Another common fixed-size array is the [bool](../../language-reference/builtin-types/bool.md) array.</span></span> <span data-ttu-id="4e49e-123">Los elementos de una matriz `bool` siempre tienen un byte de tamaño.</span><span class="sxs-lookup"><span data-stu-id="4e49e-123">The elements in a `bool` array are always one byte in size.</span></span> <span data-ttu-id="4e49e-124">Las matrices `bool` no son adecuadas para crear matrices de bits o búferes.</span><span class="sxs-lookup"><span data-stu-id="4e49e-124">`bool` arrays are not appropriate for creating bit arrays or buffers.</span></span>

> [!NOTE]
> <span data-ttu-id="4e49e-125">Con excepción de la memoria creada con [stackalloc](../../language-reference/operators/stackalloc.md), el compilador de C# y Common Language Runtime (CLR) no realizan ninguna comprobación de saturación del búfer de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4e49e-125">Except for memory created by using [stackalloc](../../language-reference/operators/stackalloc.md), the C# compiler and the common language runtime (CLR) do not perform any security buffer overrun checks.</span></span> <span data-ttu-id="4e49e-126">Como sucede con todo código no seguro, se ha de tener precaución.</span><span class="sxs-lookup"><span data-stu-id="4e49e-126">As with all unsafe code, use caution.</span></span>

<span data-ttu-id="4e49e-127">Los búferes no seguros son diferentes de las matrices normales en los siguientes puntos:</span><span class="sxs-lookup"><span data-stu-id="4e49e-127">Unsafe buffers differ from regular arrays in the following ways:</span></span>

- <span data-ttu-id="4e49e-128">Solo se pueden usar búferes no seguros en un contexto no seguro.</span><span class="sxs-lookup"><span data-stu-id="4e49e-128">You can only use unsafe buffers in an unsafe context.</span></span>
- <span data-ttu-id="4e49e-129">Los búferes no seguros siempre son vectores o matrices unidimensionales.</span><span class="sxs-lookup"><span data-stu-id="4e49e-129">Unsafe buffers are always vectors, or one-dimensional arrays.</span></span>
- <span data-ttu-id="4e49e-130">La declaración de la matriz debe incluir un recuento, por ejemplo, `char id[8]`.</span><span class="sxs-lookup"><span data-stu-id="4e49e-130">The declaration of the array should include a count, such as `char id[8]`.</span></span> <span data-ttu-id="4e49e-131">No se puede usar `char id[]`.</span><span class="sxs-lookup"><span data-stu-id="4e49e-131">You cannot use `char id[]`.</span></span>
- <span data-ttu-id="4e49e-132">Los búferes no seguros solo pueden ser campos de instancias de structs en un contexto no seguro.</span><span class="sxs-lookup"><span data-stu-id="4e49e-132">Unsafe buffers can only be instance fields of structs in an unsafe context.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e49e-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e49e-133">See also</span></span>

- [<span data-ttu-id="4e49e-134">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4e49e-134">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4e49e-135">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="4e49e-135">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="4e49e-136">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4e49e-136">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="4e49e-137">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="4e49e-137">Interoperability</span></span>](../interop/index.md)
