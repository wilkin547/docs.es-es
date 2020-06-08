---
title: 'Búferes de tamaño fijo: Guía de programación de C#'
ms.date: 04/23/2020
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.openlocfilehash: 932ff3d57995ce47c4b74e8e888a479f0d09d0ed
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397433"
---
# <a name="fixed-size-buffers-c-programming-guide"></a><span data-ttu-id="39280-102">Búferes de tamaño fijo (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="39280-102">Fixed Size Buffers (C# Programming Guide)</span></span>

<span data-ttu-id="39280-103">En C#, puede usar la instrucción [fixed](../../language-reference/keywords/fixed-statement.md) para crear un búfer con una matriz de tamaño fijo en una estructura de datos.</span><span class="sxs-lookup"><span data-stu-id="39280-103">In C#, you can use the [fixed](../../language-reference/keywords/fixed-statement.md) statement to create a buffer with a fixed size array in a data structure.</span></span> <span data-ttu-id="39280-104">Los búferes de tamaño fijo resultan útiles al escribir métodos que interoperan con orígenes de datos de otros lenguajes o plataformas.</span><span class="sxs-lookup"><span data-stu-id="39280-104">Fixed size buffers are useful when you write methods that interop with data sources from other languages or platforms.</span></span> <span data-ttu-id="39280-105">La matriz fija puede tomar cualquiera de los atributos o modificadores permitidos para los miembros de structs normales.</span><span class="sxs-lookup"><span data-stu-id="39280-105">The fixed array can take any attributes or modifiers that are allowed for regular struct members.</span></span> <span data-ttu-id="39280-106">La única restricción es que el tipo de matriz debe ser `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` o `double`.</span><span class="sxs-lookup"><span data-stu-id="39280-106">The only restriction is that the array type must be `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float`, or `double`.</span></span>

```csharp
private fixed char name[30];
```

## <a name="remarks"></a><span data-ttu-id="39280-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="39280-107">Remarks</span></span>

<span data-ttu-id="39280-108">En el código seguro, un struct de C# que contiene una matriz no contiene los elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="39280-108">In safe code, a C# struct that contains an array does not contain the array elements.</span></span> <span data-ttu-id="39280-109">En su lugar, el struct contiene una referencia a los elementos.</span><span class="sxs-lookup"><span data-stu-id="39280-109">Instead, the struct contains a reference to the elements.</span></span> <span data-ttu-id="39280-110">Puede insertar una matriz de tamaño fijo en un [struct](../../language-reference/builtin-types/struct.md) cuando se usa en un bloque de código [no seguro](../../language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="39280-110">You can embed an array of fixed size in a [struct](../../language-reference/builtin-types/struct.md) when it is used in an [unsafe](../../language-reference/keywords/unsafe.md) code block.</span></span>

<span data-ttu-id="39280-111">El tamaño del siguiente `struct` no depende del número de elementos en la matriz, ya que `pathName` es una referencia:</span><span class="sxs-lookup"><span data-stu-id="39280-111">Size of the following `struct` doesn't depend on the number of elements in the array, since `pathName` is a reference:</span></span>

[!code-csharp[Struct with embedded array](snippets/FixedKeywordExamples.cs#6)]

<span data-ttu-id="39280-112">Un `struct` puede contener una matriz insertada en el código no seguro.</span><span class="sxs-lookup"><span data-stu-id="39280-112">A `struct` can contain an embedded array in unsafe code.</span></span> <span data-ttu-id="39280-113">En el siguiente ejemplo, la matriz `fixedBuffer` tiene un tamaño fijo.</span><span class="sxs-lookup"><span data-stu-id="39280-113">In the following example, the `fixedBuffer` array has a fixed size.</span></span> <span data-ttu-id="39280-114">Se usa una instrucción `fixed` para establecer un puntero al primer elemento.</span><span class="sxs-lookup"><span data-stu-id="39280-114">You use a `fixed` statement to establish a pointer to the first element.</span></span> <span data-ttu-id="39280-115">Se accede a los elementos de la matriz mediante este puntero.</span><span class="sxs-lookup"><span data-stu-id="39280-115">You access the elements of the array through this pointer.</span></span> <span data-ttu-id="39280-116">La instrucción `fixed` ancla el campo de instancia `fixedBuffer` a una ubicación concreta en la memoria.</span><span class="sxs-lookup"><span data-stu-id="39280-116">The `fixed` statement pins the `fixedBuffer` instance field to a specific location in memory.</span></span>

[!code-csharp[Struct with embedded inline array](snippets/FixedKeywordExamples.cs#7)]

<span data-ttu-id="39280-117">El tamaño de la matriz `char` de 128 elementos es 256 bytes.</span><span class="sxs-lookup"><span data-stu-id="39280-117">The size of the 128 element `char` array is 256 bytes.</span></span> <span data-ttu-id="39280-118">Los búferes [char](../../language-reference/builtin-types/char.md) de tamaño fijo siempre admiten dos bytes por carácter, independientemente de la codificación.</span><span class="sxs-lookup"><span data-stu-id="39280-118">Fixed size [char](../../language-reference/builtin-types/char.md) buffers always take two bytes per character, regardless of the encoding.</span></span> <span data-ttu-id="39280-119">Esto es verdadero, incluso cuando se calculan las referencias de los búferes de caracteres a los métodos API o structs con `CharSet = CharSet.Auto` o `CharSet = CharSet.Ansi`.</span><span class="sxs-lookup"><span data-stu-id="39280-119">This is true even when char buffers are marshaled to API methods or structs with `CharSet = CharSet.Auto` or `CharSet = CharSet.Ansi`.</span></span> <span data-ttu-id="39280-120">Para obtener más información, vea <xref:System.Runtime.InteropServices.CharSet>.</span><span class="sxs-lookup"><span data-stu-id="39280-120">For more information, see <xref:System.Runtime.InteropServices.CharSet>.</span></span>

<span data-ttu-id="39280-121">En el ejemplo anterior se muestra cómo acceder a campos `fixed` sin anclar, lo que está disponible a partir de C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="39280-121">The  preceding example demonstrates accessing `fixed` fields without pinning, which is available starting with C# 7.3.</span></span>

<span data-ttu-id="39280-122">Otra matriz de tamaño fijo común es la matriz [bool](../../language-reference/builtin-types/bool.md).</span><span class="sxs-lookup"><span data-stu-id="39280-122">Another common fixed-size array is the [bool](../../language-reference/builtin-types/bool.md) array.</span></span> <span data-ttu-id="39280-123">Los elementos de una matriz `bool` siempre tienen un byte de tamaño.</span><span class="sxs-lookup"><span data-stu-id="39280-123">The elements in a `bool` array are always one byte in size.</span></span> <span data-ttu-id="39280-124">Las matrices `bool` no son adecuadas para crear matrices de bits o búferes.</span><span class="sxs-lookup"><span data-stu-id="39280-124">`bool` arrays are not appropriate for creating bit arrays or buffers.</span></span>

<span data-ttu-id="39280-125">Los búferes de tamaño fijo se compilan con el atributo <xref:System.Runtime.CompilerServices.UnsafeValueTypeAttribute?displayProperty=nameWithType>, que indica a Common Language Runtime (CLR) que un tipo contiene una matriz no administrada que puede provocar un desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="39280-125">Fixed size buffers are compiled with the <xref:System.Runtime.CompilerServices.UnsafeValueTypeAttribute?displayProperty=nameWithType>, which instructs the common language runtime (CLR) that a type contains an unmanaged array that can potentially overflow.</span></span> <span data-ttu-id="39280-126">Esto es similar a la memoria creada mediante [stackalloc](../../language-reference/operators/stackalloc.md), que habilita automáticamente las características de detección de saturación del búfer en CLR.</span><span class="sxs-lookup"><span data-stu-id="39280-126">This is similar to memory created using [stackalloc](../../language-reference/operators/stackalloc.md), which automatically enables buffer overrun detection features in the CLR.</span></span> <span data-ttu-id="39280-127">En el ejemplo anterior se muestra cómo podría existir un búfer de tamaño fijo en un `unsafe struct`.</span><span class="sxs-lookup"><span data-stu-id="39280-127">The previous example shows how a fixed size buffer could exist in an `unsafe struct`.</span></span>

```csharp
internal unsafe struct Buffer
{
    public fixed char fixedBuffer[128];
}
```

<span data-ttu-id="39280-128">El código de C# generado por el compilador para `Buffer` se atribuye de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="39280-128">The compiler generated C# for `Buffer`, is attributed as follows:</span></span>

```csharp
internal struct Buffer
{
    [StructLayout(LayoutKind.Sequential, Size = 256)]
    [CompilerGenerated]
    [UnsafeValueType]
    public struct <fixedBuffer>e__FixedBuffer
    {
        public char FixedElementField;
    }

    [FixedBuffer(typeof(char), 128)]
    public <fixedBuffer>e__FixedBuffer fixedBuffer;
}
```

<span data-ttu-id="39280-129">Los búferes de tamaño fijo son diferentes de las matrices normales en los siguientes puntos:</span><span class="sxs-lookup"><span data-stu-id="39280-129">Fixed size buffers differ from regular arrays in the following ways:</span></span>

- <span data-ttu-id="39280-130">Solo se pueden usar en un contexto [no seguro](../../language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="39280-130">May only be used in an [unsafe](../../language-reference/keywords/unsafe.md) context.</span></span>
- <span data-ttu-id="39280-131">Solo pueden ser campos de instancia de structs.</span><span class="sxs-lookup"><span data-stu-id="39280-131">May only be instance fields of structs.</span></span>
- <span data-ttu-id="39280-132">Siempre son vectores o matrices unidimensionales.</span><span class="sxs-lookup"><span data-stu-id="39280-132">They're always vectors, or one-dimensional arrays.</span></span>
- <span data-ttu-id="39280-133">La declaración debe incluir la longitud, como `fixed char id[8]`.</span><span class="sxs-lookup"><span data-stu-id="39280-133">The declaration should include the length, such as `fixed char id[8]`.</span></span> <span data-ttu-id="39280-134">No se puede usar `fixed char id[]`.</span><span class="sxs-lookup"><span data-stu-id="39280-134">You cannot use `fixed char id[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="39280-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="39280-135">See also</span></span>

- [<span data-ttu-id="39280-136">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="39280-136">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="39280-137">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="39280-137">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="39280-138">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="39280-138">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="39280-139">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="39280-139">Interoperability</span></span>](../interop/index.md)
