---
title: 'Tabla de tipos integrados: Referencia de C#'
ms.custom: seodec18
description: Palabras clave para tipos integrados de C#
ms.date: 08/17/2018
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: bd8c52cd798496a4df3086411dfe3be6241fbff5
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422349"
---
# <a name="built-in-types-table-c-reference"></a><span data-ttu-id="781f4-103">Tabla de tipos integrados (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="781f4-103">Built-in types table (C# Reference)</span></span>

<span data-ttu-id="781f4-104">En la siguiente tabla se muestran las palabras clave para los tipos de C# integrados, que son alias de los tipos predefinidos en el espacio de nombres <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="781f4-104">The following table shows the keywords for built-in C# types, which are aliases of predefined types in the <xref:System> namespace.</span></span>  
  
|<span data-ttu-id="781f4-105">Tipo de C#</span><span class="sxs-lookup"><span data-stu-id="781f4-105">C# type</span></span>|<span data-ttu-id="781f4-106">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="781f4-106">.NET type</span></span>|  
|--------------|-------------------------|  
|[<span data-ttu-id="781f4-107">bool</span><span class="sxs-lookup"><span data-stu-id="781f4-107">bool</span></span>](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|  
|[<span data-ttu-id="781f4-108">byte</span><span class="sxs-lookup"><span data-stu-id="781f4-108">byte</span></span>](byte.md)|<xref:System.Byte?displayProperty=nameWithType>|  
|[<span data-ttu-id="781f4-109">sbyte</span><span class="sxs-lookup"><span data-stu-id="781f4-109">sbyte</span></span>](sbyte.md)|<xref:System.SByte?displayProperty=nameWithType>|  
|[<span data-ttu-id="781f4-110">char</span><span class="sxs-lookup"><span data-stu-id="781f4-110">char</span></span>](char.md)|<xref:System.Char?displayProperty=nameWithType>|  
|[<span data-ttu-id="781f4-111">decimal</span><span class="sxs-lookup"><span data-stu-id="781f4-111">decimal</span></span>](decimal.md)|<xref:System.Decimal?displayProperty=nameWithType>|  
|[<span data-ttu-id="781f4-112">double</span><span class="sxs-lookup"><span data-stu-id="781f4-112">double</span></span>](double.md)|<xref:System.Double?displayProperty=nameWithType>|  
|[<span data-ttu-id="781f4-113">float</span><span class="sxs-lookup"><span data-stu-id="781f4-113">float</span></span>](float.md)|<xref:System.Single?displayProperty=nameWithType>|  
|[<span data-ttu-id="781f4-114">int</span><span class="sxs-lookup"><span data-stu-id="781f4-114">int</span></span>](int.md)|<xref:System.Int32?displayProperty=nameWithType>|  
|[<span data-ttu-id="781f4-115">uint</span><span class="sxs-lookup"><span data-stu-id="781f4-115">uint</span></span>](uint.md)|<xref:System.UInt32?displayProperty=nameWithType>|  
|[<span data-ttu-id="781f4-116">long</span><span class="sxs-lookup"><span data-stu-id="781f4-116">long</span></span>](long.md)|<xref:System.Int64?displayProperty=nameWithType>|  
|[<span data-ttu-id="781f4-117">ulong</span><span class="sxs-lookup"><span data-stu-id="781f4-117">ulong</span></span>](ulong.md)|<xref:System.UInt64?displayProperty=nameWithType>|  
|[<span data-ttu-id="781f4-118">object</span><span class="sxs-lookup"><span data-stu-id="781f4-118">object</span></span>](object.md)|<xref:System.Object?displayProperty=nameWithType>|  
|[<span data-ttu-id="781f4-119">short</span><span class="sxs-lookup"><span data-stu-id="781f4-119">short</span></span>](short.md)|<xref:System.Int16?displayProperty=nameWithType>|  
|[<span data-ttu-id="781f4-120">ushort</span><span class="sxs-lookup"><span data-stu-id="781f4-120">ushort</span></span>](ushort.md)|<xref:System.UInt16?displayProperty=nameWithType>|  
|[<span data-ttu-id="781f4-121">string</span><span class="sxs-lookup"><span data-stu-id="781f4-121">string</span></span>](string.md)|<xref:System.String?displayProperty=nameWithType>|  
  
## <a name="remarks"></a><span data-ttu-id="781f4-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="781f4-122">Remarks</span></span>

<span data-ttu-id="781f4-123">A todos los tipos de la tabla, excepto `object` y `string`, se les hace referencia como tipos simples.</span><span class="sxs-lookup"><span data-stu-id="781f4-123">All of the types in the table, except `object` and `string`, are referred to as simple types.</span></span>  
  
<span data-ttu-id="781f4-124">Las palabras clave de tipo de C# y sus alias son intercambiables.</span><span class="sxs-lookup"><span data-stu-id="781f4-124">The C# type keywords and their aliases are interchangeable.</span></span> <span data-ttu-id="781f4-125">Por ejemplo, puede declarar una variable de entero con cualquiera de las siguientes declaraciones:</span><span class="sxs-lookup"><span data-stu-id="781f4-125">For example, you can declare an integer variable by using either of the following declarations:</span></span>  

```csharp
int x = 123;
System.Int32 y = 123;
```

<span data-ttu-id="781f4-126">Use el operador [typeof](typeof.md) para obtener la instancia <xref:System.Type?displayProperty=nameWithType> que representa el tipo especificado:</span><span class="sxs-lookup"><span data-stu-id="781f4-126">Use the [typeof](typeof.md) operator to get the <xref:System.Type?displayProperty=nameWithType> instance that represents the specified type:</span></span>

```csharp
Type stringType = typeof(string);
Console.WriteLine(stringType.FullName);

Type doubleType = typeof(System.Double);
Console.WriteLine(doubleType.FullName);

// Output:
// System.String
// System.Double
```

## <a name="see-also"></a><span data-ttu-id="781f4-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="781f4-127">See also</span></span>

- [<span data-ttu-id="781f4-128">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="781f4-128">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="781f4-129">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="781f4-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="781f4-130">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="781f4-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="781f4-131">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="781f4-131">Value types</span></span>](value-types.md)
- [<span data-ttu-id="781f4-132">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="781f4-132">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="781f4-133">Tabla de valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="781f4-133">Default values table</span></span>](default-values-table.md)
- [<span data-ttu-id="781f4-134">dynamic</span><span class="sxs-lookup"><span data-stu-id="781f4-134">dynamic</span></span>](dynamic.md)
