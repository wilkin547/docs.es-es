---
title: 'Tabla de conversiones numéricas implícitas: Referencia de C#'
ms.custom: seodec18
ms.date: 09/05/2018
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: ab6506e619c675ddd68237c4ddca870e9e14098f
ms.sourcegitcommit: deb9225a55485a5a6e6c7914deb30ccfceb69d3f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2019
ms.locfileid: "54058469"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="a57ee-102">Tabla de conversiones numéricas implícitas (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a57ee-102">Implicit numeric conversions table (C# Reference)</span></span>

<span data-ttu-id="a57ee-103">En la tabla siguiente se muestran las conversiones implícitas predefinidas entre tipos numéricos de .NET.</span><span class="sxs-lookup"><span data-stu-id="a57ee-103">The following table shows the predefined implicit conversions between .NET numeric types.</span></span>
  
|<span data-ttu-id="a57ee-104">De</span><span class="sxs-lookup"><span data-stu-id="a57ee-104">From</span></span>|<span data-ttu-id="a57ee-105">En</span><span class="sxs-lookup"><span data-stu-id="a57ee-105">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="a57ee-106">sbyte</span><span class="sxs-lookup"><span data-stu-id="a57ee-106">sbyte</span></span>](sbyte.md)|<span data-ttu-id="a57ee-107">`short`, `int`, `long`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="a57ee-107">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="a57ee-108">byte</span><span class="sxs-lookup"><span data-stu-id="a57ee-108">byte</span></span>](byte.md)|<span data-ttu-id="a57ee-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="a57ee-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="a57ee-110">char</span><span class="sxs-lookup"><span data-stu-id="a57ee-110">char</span></span>](char.md)|<span data-ttu-id="a57ee-111">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="a57ee-111">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="a57ee-112">short</span><span class="sxs-lookup"><span data-stu-id="a57ee-112">short</span></span>](short.md)|<span data-ttu-id="a57ee-113">`int`, `long`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="a57ee-113">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="a57ee-114">ushort</span><span class="sxs-lookup"><span data-stu-id="a57ee-114">ushort</span></span>](ushort.md)|<span data-ttu-id="a57ee-115">`int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="a57ee-115">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="a57ee-116">int</span><span class="sxs-lookup"><span data-stu-id="a57ee-116">int</span></span>](int.md)|<span data-ttu-id="a57ee-117">`long`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="a57ee-117">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="a57ee-118">uint</span><span class="sxs-lookup"><span data-stu-id="a57ee-118">uint</span></span>](uint.md)|<span data-ttu-id="a57ee-119">`long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="a57ee-119">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="a57ee-120">long</span><span class="sxs-lookup"><span data-stu-id="a57ee-120">long</span></span>](long.md)|<span data-ttu-id="a57ee-121">`float`, `double`o `decimal`</span><span class="sxs-lookup"><span data-stu-id="a57ee-121">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="a57ee-122">ulong</span><span class="sxs-lookup"><span data-stu-id="a57ee-122">ulong</span></span>](ulong.md)|<span data-ttu-id="a57ee-123">`float`, `double`o `decimal`</span><span class="sxs-lookup"><span data-stu-id="a57ee-123">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="a57ee-124">float</span><span class="sxs-lookup"><span data-stu-id="a57ee-124">float</span></span>](float.md)|`double`|  
  
## <a name="remarks"></a><span data-ttu-id="a57ee-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a57ee-125">Remarks</span></span>  

- <span data-ttu-id="a57ee-126">Cualquier [tipo entero](integral-types-table.md) es implícitamente convertible en cualquier [tipo de punto flotante](floating-point-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="a57ee-126">Any [integral type](integral-types-table.md) is implicitly convertible to any [floating-point type](floating-point-types-table.md).</span></span>

- <span data-ttu-id="a57ee-127">Es posible que en las conversiones de `int`, `uint`, `long` o `ulong` en `float` y de `long` o `ulong` en `double` se pierda la precisión, pero no la magnitud.</span><span class="sxs-lookup"><span data-stu-id="a57ee-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`, `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
- <span data-ttu-id="a57ee-128">No hay ninguna conversión implícita a los tipos `char`, `byte` y `sbyte`.</span><span class="sxs-lookup"><span data-stu-id="a57ee-128">There are no implicit conversions to the `char`, `byte` and `sbyte` types.</span></span>  

- <span data-ttu-id="a57ee-129">No hay ninguna conversión implícita de los tipos `char`, `double` y `decimal`.</span><span class="sxs-lookup"><span data-stu-id="a57ee-129">There are no implicit conversions from the `char`, `double` and `decimal` types.</span></span>
  
- <span data-ttu-id="a57ee-130">No hay ninguna conversión implícita entre el tipo `decimal` y el tipo `float` o `double`.</span><span class="sxs-lookup"><span data-stu-id="a57ee-130">There are no implicit conversions between the `decimal` type and the `float` or `double` types.</span></span>  
  
- <span data-ttu-id="a57ee-131">Un valor de una expresión constante de tipo `int` (por ejemplo, un valor representado por un literal entero) se puede convertir en `sbyte`, `byte`, `short`, `ushort`, `uint` o `ulong`, siempre que esté dentro del intervalo del tipo de destino:</span><span class="sxs-lookup"><span data-stu-id="a57ee-131">A value of a constant expression of type `int` (for example, a value represented by an integral literal) can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided it's within the range of the destination type:</span></span>

  ```csharp
  byte a = 13;    // Compiles
  byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

<span data-ttu-id="a57ee-132">Para obtener más información sobre las conversiones implícitas, vea la sección [Conversiones implícitas](~/_csharplang/spec/conversions.md#implicit-conversions) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="a57ee-132">For more information about implicit conversions, see the [Implicit conversions](~/_csharplang/spec/conversions.md#implicit-conversions) section of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a57ee-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="a57ee-133">See also</span></span>

- [<span data-ttu-id="a57ee-134">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a57ee-134">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a57ee-135">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a57ee-135">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a57ee-136">Tabla de tipos enteros</span><span class="sxs-lookup"><span data-stu-id="a57ee-136">Integral types table</span></span>](integral-types-table.md)
- [<span data-ttu-id="a57ee-137">Tabla de tipos de punto flotante</span><span class="sxs-lookup"><span data-stu-id="a57ee-137">Floating-point types table</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="a57ee-138">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="a57ee-138">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="a57ee-139">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="a57ee-139">Explicit numeric conversions table</span></span>](explicit-numeric-conversions-table.md)
- [<span data-ttu-id="a57ee-140">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="a57ee-140">Casting and type conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
