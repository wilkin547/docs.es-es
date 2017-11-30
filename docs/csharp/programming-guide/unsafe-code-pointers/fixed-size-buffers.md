---
title: "Búferes de tamaño fijo (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.assetid: 6220d454-947c-4977-ac9d-9308c6ed5051
caps.latest.revision: "31"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3f99c2c6d477fca988fcca77de5ca5c2f8addd4d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="fixed-size-buffers-c-programming-guide"></a><span data-ttu-id="17c07-102">Búferes de tamaño fijo (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="17c07-102">Fixed Size Buffers (C# Programming Guide)</span></span>
<span data-ttu-id="17c07-103">En C#, puede usar la instrucción [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) para crear un búfer con una matriz de tamaño fijo en una estructura de datos.</span><span class="sxs-lookup"><span data-stu-id="17c07-103">In C#, you can use the [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) statement to create a buffer with a fixed size array in a data structure.</span></span> <span data-ttu-id="17c07-104">Esto es útil cuando se trabaja con código existente, como el código escrito en otros lenguajes, archivos DLL preexistentes o proyectos COM.</span><span class="sxs-lookup"><span data-stu-id="17c07-104">This is useful when you are working with existing code, such as code written in other languages, pre-existing DLLs or COM projects.</span></span> <span data-ttu-id="17c07-105">La matriz fija puede tomar cualquiera de los atributos o modificadores permitidos para los miembros de structs normales.</span><span class="sxs-lookup"><span data-stu-id="17c07-105">The fixed array can take any attributes or modifiers that are allowed for regular struct members.</span></span> <span data-ttu-id="17c07-106">La única restricción es que el tipo de matriz debe ser `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` o `double`.</span><span class="sxs-lookup"><span data-stu-id="17c07-106">The only restriction is that the array type must be `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float`, or `double`.</span></span>  
  
```  
private fixed char name[30];  
```  
  
## <a name="remarks"></a><span data-ttu-id="17c07-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="17c07-107">Remarks</span></span>  
 <span data-ttu-id="17c07-108">En las primeras versiones de C#, declarar una estructura de tamaño fijo con el estilo de C++ era difícil, porque un struct de C# que contiene una matriz no contiene los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="17c07-108">In early versions of C#, declaring a C++ style fixed-size structure was difficult because a C# struct that contains an array does not contain the array elements.</span></span> <span data-ttu-id="17c07-109">En su lugar, el struct contiene una referencia a los elementos.</span><span class="sxs-lookup"><span data-stu-id="17c07-109">Instead, the struct contains a reference to the elements.</span></span>  
  
 <span data-ttu-id="17c07-110">En C# 2.0 se ha agregado la capacidad de insertar una matriz de tamaño fijo en un [struct](../../../csharp/language-reference/keywords/struct.md) cuando se usa en un bloque de código [no seguro](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="17c07-110">C# 2.0 added the ability to embed an array of fixed size in a [struct](../../../csharp/language-reference/keywords/struct.md) when it is used in an [unsafe](../../../csharp/language-reference/keywords/unsafe.md) code block.</span></span>  
  
 <span data-ttu-id="17c07-111">Por ejemplo, antes de C# 2.0, los siguientes `struct` tendrían 8 bytes de tamaño.</span><span class="sxs-lookup"><span data-stu-id="17c07-111">For example, before C# 2.0, the following `struct` would be 8 bytes in size.</span></span> <span data-ttu-id="17c07-112">La matriz `pathName` es una referencia a la matriz asignada en el montón:</span><span class="sxs-lookup"><span data-stu-id="17c07-112">The `pathName` array is a reference to the heap-allocated array:</span></span>  
  
 [!code-csharp[csProgGuidePointers#19](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_1.cs)]  
  
 <span data-ttu-id="17c07-113">Comenzando con C# 2.0, un `struct` puede contener una matriz insertada.</span><span class="sxs-lookup"><span data-stu-id="17c07-113">Beginning with C# 2.0, a `struct` can contain an embedded array.</span></span> <span data-ttu-id="17c07-114">En el siguiente ejemplo, la matriz `fixedBuffer` tiene un tamaño fijo.</span><span class="sxs-lookup"><span data-stu-id="17c07-114">In the following example, the `fixedBuffer` array has a fixed size.</span></span> <span data-ttu-id="17c07-115">Para tener acceso a los elementos de la matriz, use una instrucción `fixed` para establecer un puntero al primer elemento.</span><span class="sxs-lookup"><span data-stu-id="17c07-115">To access the elements of the array, you use a `fixed` statement to establish a pointer to the first element.</span></span> <span data-ttu-id="17c07-116">La instrucción `fixed` ancla una instancia de `fixedBuffer` a una ubicación concreta de la memoria.</span><span class="sxs-lookup"><span data-stu-id="17c07-116">The `fixed` statement pins an instance of `fixedBuffer` to a specific location in memory.</span></span>  
  
 [!code-csharp[csProgGuidePointers#20](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_2.cs)]  
  
 <span data-ttu-id="17c07-117">El tamaño de la matriz `char` de 128 elementos es 256 bytes.</span><span class="sxs-lookup"><span data-stu-id="17c07-117">The size of the 128 element `char` array is 256 bytes.</span></span> <span data-ttu-id="17c07-118">Los búferes [char](../../../csharp/language-reference/keywords/char.md) de tamaño fijo siempre admiten dos bytes por carácter, independientemente de la codificación.</span><span class="sxs-lookup"><span data-stu-id="17c07-118">Fixed size [char](../../../csharp/language-reference/keywords/char.md) buffers always take two bytes per character, regardless of the encoding.</span></span> <span data-ttu-id="17c07-119">Esto es verdadero, incluso cuando se calculan las referencias de los búferes de caracteres a los métodos API o structs con `CharSet = CharSet.Auto` o `CharSet = CharSet.Ansi`.</span><span class="sxs-lookup"><span data-stu-id="17c07-119">This is true even when char buffers are marshaled to API methods or structs with `CharSet = CharSet.Auto` or `CharSet = CharSet.Ansi`.</span></span> <span data-ttu-id="17c07-120">Para obtener más información, consulta <xref:System.Runtime.InteropServices.CharSet>.</span><span class="sxs-lookup"><span data-stu-id="17c07-120">For more information, see <xref:System.Runtime.InteropServices.CharSet>.</span></span>  
  
 <span data-ttu-id="17c07-121">Otra matriz de tamaño fijo común es la matriz [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="17c07-121">Another common fixed-size array is the [bool](../../../csharp/language-reference/keywords/bool.md) array.</span></span> <span data-ttu-id="17c07-122">Los elementos de una matriz `bool` siempre tienen un byte de tamaño.</span><span class="sxs-lookup"><span data-stu-id="17c07-122">The elements in a `bool` array are always one byte in size.</span></span> <span data-ttu-id="17c07-123">Las matrices `bool` no son adecuadas para crear matrices de bits o búferes.</span><span class="sxs-lookup"><span data-stu-id="17c07-123">`bool` arrays are not appropriate for creating bit arrays or buffers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17c07-124">Con excepción de la memoria creada con [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md), el compilador de C# y Common Language Runtime (CLR) no realizan ninguna comprobación de saturación del búfer de seguridad.</span><span class="sxs-lookup"><span data-stu-id="17c07-124">Except for memory created by using [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md), the C# compiler and the common language runtime (CLR) do not perform any security buffer overrun checks.</span></span> <span data-ttu-id="17c07-125">Como sucede con todo código no seguro, se ha de tener precaución.</span><span class="sxs-lookup"><span data-stu-id="17c07-125">As with all unsafe code, use caution.</span></span>  
  
 <span data-ttu-id="17c07-126">Los búferes no seguros son diferentes de las matrices normales en los siguientes puntos:</span><span class="sxs-lookup"><span data-stu-id="17c07-126">Unsafe buffers differ from regular arrays in the following ways:</span></span>  
  
-   <span data-ttu-id="17c07-127">Solo se pueden usar búferes no seguros en un contexto no seguro.</span><span class="sxs-lookup"><span data-stu-id="17c07-127">You can only use unsafe buffers in an unsafe context.</span></span>  
  
-   <span data-ttu-id="17c07-128">Los búferes no seguros siempre son vectores o matrices unidimensionales.</span><span class="sxs-lookup"><span data-stu-id="17c07-128">Unsafe buffers are always vectors, or one-dimensional arrays.</span></span>  
  
-   <span data-ttu-id="17c07-129">La declaración de la matriz debe incluir un recuento, por ejemplo, `char id[8]`.</span><span class="sxs-lookup"><span data-stu-id="17c07-129">The declaration of the array should include a count, such as `char id[8]`.</span></span> <span data-ttu-id="17c07-130">No puede usar `char id[]` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="17c07-130">You cannot use `char id[]` instead.</span></span>  
  
-   <span data-ttu-id="17c07-131">Los búferes no seguros solo pueden ser campos de instancias de structs en un contexto no seguro.</span><span class="sxs-lookup"><span data-stu-id="17c07-131">Unsafe buffers can only be instance fields of structs in an unsafe context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17c07-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="17c07-132">See Also</span></span>  
 [<span data-ttu-id="17c07-133">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="17c07-133">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="17c07-134">Código no seguro y punteros</span><span class="sxs-lookup"><span data-stu-id="17c07-134">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="17c07-135">fixed (instrucción)</span><span class="sxs-lookup"><span data-stu-id="17c07-135">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="17c07-136">Interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="17c07-136">Interoperability</span></span>](../../../csharp/programming-guide/interop/index.md)
