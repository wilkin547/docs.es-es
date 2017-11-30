---
title: "Tabla de conversiones numéricas implícitas (Referencia de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f6b1705dca357fd2a155fc1ea9c7fe0f65bad8a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="0b60a-102">Tabla de conversiones numéricas implícitas (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0b60a-102">Implicit Numeric Conversions Table (C# Reference)</span></span>
<span data-ttu-id="0b60a-103">En la tabla siguiente se muestran las conversiones numéricas implícitas predefinidas.</span><span class="sxs-lookup"><span data-stu-id="0b60a-103">The following table shows the predefined implicit numeric conversions.</span></span> <span data-ttu-id="0b60a-104">Las conversiones implícitas pueden ocurrir en muchas situaciones, incluidas las instrucciones de asignación y de invocación de método.</span><span class="sxs-lookup"><span data-stu-id="0b60a-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
|<span data-ttu-id="0b60a-105">De</span><span class="sxs-lookup"><span data-stu-id="0b60a-105">From</span></span>|<span data-ttu-id="0b60a-106">En</span><span class="sxs-lookup"><span data-stu-id="0b60a-106">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="0b60a-107">sbyte</span><span class="sxs-lookup"><span data-stu-id="0b60a-107">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="0b60a-108">`short`, `int`, `long`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="0b60a-108">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="0b60a-109">byte</span><span class="sxs-lookup"><span data-stu-id="0b60a-109">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="0b60a-110">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="0b60a-110">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="0b60a-111">short</span><span class="sxs-lookup"><span data-stu-id="0b60a-111">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="0b60a-112">`int`, `long`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="0b60a-112">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="0b60a-113">ushort</span><span class="sxs-lookup"><span data-stu-id="0b60a-113">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="0b60a-114">`int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="0b60a-114">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="0b60a-115">int</span><span class="sxs-lookup"><span data-stu-id="0b60a-115">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="0b60a-116">`long`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="0b60a-116">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="0b60a-117">uint</span><span class="sxs-lookup"><span data-stu-id="0b60a-117">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="0b60a-118">`long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="0b60a-118">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="0b60a-119">long</span><span class="sxs-lookup"><span data-stu-id="0b60a-119">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="0b60a-120">`float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="0b60a-120">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="0b60a-121">char</span><span class="sxs-lookup"><span data-stu-id="0b60a-121">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="0b60a-122">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="0b60a-122">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="0b60a-123">float</span><span class="sxs-lookup"><span data-stu-id="0b60a-123">float</span></span>](../../../csharp/language-reference/keywords/float.md)|`double`|  
|[<span data-ttu-id="0b60a-124">ulong</span><span class="sxs-lookup"><span data-stu-id="0b60a-124">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="0b60a-125">`float`, `double` o `decimal`</span><span class="sxs-lookup"><span data-stu-id="0b60a-125">`float`, `double`, or `decimal`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b60a-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0b60a-126">Remarks</span></span>  
  
-   <span data-ttu-id="0b60a-127">Es posible que en las conversiones de `int`, `uint`, `long` o `ulong` a `float` y de `long` o `ulong` a `double` se pierda la precisión pero no la magnitud.</span><span class="sxs-lookup"><span data-stu-id="0b60a-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`,  `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
-   <span data-ttu-id="0b60a-128">No hay ninguna conversión implícita al tipo `char`.</span><span class="sxs-lookup"><span data-stu-id="0b60a-128">There are no implicit conversions to the `char` type.</span></span>  
  
-   <span data-ttu-id="0b60a-129">No hay ninguna conversión implícita entre tipos de punto flotante y el tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="0b60a-129">There are no implicit conversions between floating-point types and the `decimal` type.</span></span>  
  
-   <span data-ttu-id="0b60a-130">Una expresión constante de tipo `int` se puede convertir a `sbyte`, `byte`, `short`, `ushort`, `uint` o `ulong`, siempre que el valor de la expresión constante esté dentro del intervalo del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="0b60a-130">A constant expression of type `int` can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided the value of the constant expression is within the range of the destination type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0b60a-131">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="0b60a-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0b60a-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b60a-132">See Also</span></span>  
 [<span data-ttu-id="0b60a-133">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="0b60a-133">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0b60a-134">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0b60a-134">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0b60a-135">Tabla de tipos enteros</span><span class="sxs-lookup"><span data-stu-id="0b60a-135">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="0b60a-136">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="0b60a-136">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="0b60a-137">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="0b60a-137">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
 [<span data-ttu-id="0b60a-138">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="0b60a-138">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)
