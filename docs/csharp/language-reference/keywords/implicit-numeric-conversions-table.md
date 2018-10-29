---
title: Tabla de conversiones numéricas implícitas (Referencia de C#)
ms.date: 09/05/2018
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: c3c0153a0ae3e07839822c8bb978b1a09277bd53
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188708"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="3a72d-102">Tabla de conversiones numéricas implícitas (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="3a72d-102">Implicit numeric conversions table (C# Reference)</span></span>

<span data-ttu-id="3a72d-103">En la tabla siguiente se muestran las conversiones implícitas predefinidas entre tipos numéricos de .NET.</span><span class="sxs-lookup"><span data-stu-id="3a72d-103">The following table shows the predefined implicit conversions between .NET numeric types.</span></span>
  
|<span data-ttu-id="3a72d-104">De</span><span class="sxs-lookup"><span data-stu-id="3a72d-104">From</span></span>|<span data-ttu-id="3a72d-105">En</span><span class="sxs-lookup"><span data-stu-id="3a72d-105">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="3a72d-106">sbyte</span><span class="sxs-lookup"><span data-stu-id="3a72d-106">sbyte</span></span>](sbyte.md)|<span data-ttu-id="3a72d-107">`short`, `int`, `long`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="3a72d-107">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="3a72d-108">byte</span><span class="sxs-lookup"><span data-stu-id="3a72d-108">byte</span></span>](byte.md)|<span data-ttu-id="3a72d-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="3a72d-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="3a72d-110">short</span><span class="sxs-lookup"><span data-stu-id="3a72d-110">short</span></span>](short.md)|<span data-ttu-id="3a72d-111">`int`, `long`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="3a72d-111">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="3a72d-112">ushort</span><span class="sxs-lookup"><span data-stu-id="3a72d-112">ushort</span></span>](ushort.md)|<span data-ttu-id="3a72d-113">`int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="3a72d-113">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="3a72d-114">int</span><span class="sxs-lookup"><span data-stu-id="3a72d-114">int</span></span>](int.md)|<span data-ttu-id="3a72d-115">`long`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="3a72d-115">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="3a72d-116">uint</span><span class="sxs-lookup"><span data-stu-id="3a72d-116">uint</span></span>](uint.md)|<span data-ttu-id="3a72d-117">`long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="3a72d-117">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="3a72d-118">long</span><span class="sxs-lookup"><span data-stu-id="3a72d-118">long</span></span>](long.md)|<span data-ttu-id="3a72d-119">`float`, `double`o `decimal`</span><span class="sxs-lookup"><span data-stu-id="3a72d-119">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="3a72d-120">char</span><span class="sxs-lookup"><span data-stu-id="3a72d-120">char</span></span>](char.md)|<span data-ttu-id="3a72d-121">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="3a72d-121">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="3a72d-122">float</span><span class="sxs-lookup"><span data-stu-id="3a72d-122">float</span></span>](float.md)|`double`|  
|[<span data-ttu-id="3a72d-123">ulong</span><span class="sxs-lookup"><span data-stu-id="3a72d-123">ulong</span></span>](ulong.md)|<span data-ttu-id="3a72d-124">`float`, `double`o `decimal`</span><span class="sxs-lookup"><span data-stu-id="3a72d-124">`float`, `double`, or `decimal`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a72d-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a72d-125">Remarks</span></span>  

- <span data-ttu-id="3a72d-126">Cualquier [tipo entero](integral-types-table.md) es implícitamente convertible en cualquier [tipo de punto flotante](floating-point-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="3a72d-126">Any [integral type](integral-types-table.md) is implicitly convertible to any [floating-point type](floating-point-types-table.md).</span></span>

- <span data-ttu-id="3a72d-127">Es posible que en las conversiones de `int`, `uint`, `long` o `ulong` en `float` y de `long` o `ulong` en `double` se pierda la precisión, pero no la magnitud.</span><span class="sxs-lookup"><span data-stu-id="3a72d-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`, `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
- <span data-ttu-id="3a72d-128">No hay ninguna conversión implícita al tipo `char`.</span><span class="sxs-lookup"><span data-stu-id="3a72d-128">There are no implicit conversions to the `char` type.</span></span>  
  
- <span data-ttu-id="3a72d-129">No hay ninguna conversión implícita entre los tipos `float` y `double` y el tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="3a72d-129">There are no implicit conversions between the `float` and `double` types and the `decimal` type.</span></span>  
  
- <span data-ttu-id="3a72d-130">Un valor de una expresión constante de tipo `int` (por ejemplo, un valor representado por un literal entero) se puede convertir en `sbyte`, `byte`, `short`, `ushort`, `uint` o `ulong`, siempre que esté dentro del intervalo del tipo de destino:</span><span class="sxs-lookup"><span data-stu-id="3a72d-130">A value of a constant expression of type `int` (for example, a value represented by an integral literal) can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided it's within the range of the destination type:</span></span>

  ```csharp
  byte a = 13;    // Compiles
  byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

<span data-ttu-id="3a72d-131">Para obtener más información sobre las conversiones implícitas, vea la sección [Conversiones implícitas](~/_csharplang/spec/conversions.md#implicit-conversions) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="3a72d-131">For more information about implicit conversions, see the [Implicit conversions](~/_csharplang/spec/conversions.md#implicit-conversions) section of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3a72d-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a72d-132">See also</span></span>

- [<span data-ttu-id="3a72d-133">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="3a72d-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3a72d-134">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3a72d-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3a72d-135">Tabla de tipos enteros</span><span class="sxs-lookup"><span data-stu-id="3a72d-135">Integral types table</span></span>](integral-types-table.md)
- [<span data-ttu-id="3a72d-136">Tabla de tipos de punto flotante</span><span class="sxs-lookup"><span data-stu-id="3a72d-136">Floating-point types table</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="3a72d-137">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="3a72d-137">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="3a72d-138">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="3a72d-138">Explicit numeric conversions table</span></span>](explicit-numeric-conversions-table.md)
- [<span data-ttu-id="3a72d-139">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="3a72d-139">Casting and type conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
