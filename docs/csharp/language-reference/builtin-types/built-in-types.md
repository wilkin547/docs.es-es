---
title: 'Tipos integrados: referencia de C#'
description: Información sobre los tipos de referencia y de valor integrados de C#
ms.date: 02/04/2020
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: bf8823c6674b1ff3f0028a50df8ce8d0f803cfc1
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389490"
---
# <a name="built-in-types-c-reference"></a><span data-ttu-id="c3a8a-103">Tipos integrados (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c3a8a-103">Built-in types (C# reference)</span></span>

<span data-ttu-id="c3a8a-104">En la siguiente tabla se muestran los tipos de [valor](value-types.md) de C#:</span><span class="sxs-lookup"><span data-stu-id="c3a8a-104">The following table lists the C# built-in [value](value-types.md) types:</span></span>

|<span data-ttu-id="c3a8a-105">Palabra clave de tipo de C#</span><span class="sxs-lookup"><span data-stu-id="c3a8a-105">C# type keyword</span></span>|<span data-ttu-id="c3a8a-106">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="c3a8a-106">.NET type</span></span>|
|--------------|-------------------------|
|[`bool`](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|
|[`byte`](integral-numeric-types.md)|<xref:System.Byte?displayProperty=nameWithType>|
|[`sbyte`](integral-numeric-types.md)|<xref:System.SByte?displayProperty=nameWithType>|
|[`char`](char.md)|<xref:System.Char?displayProperty=nameWithType>|
|[`decimal`](floating-point-numeric-types.md)|<xref:System.Decimal?displayProperty=nameWithType>|
|[`double`](floating-point-numeric-types.md)|<xref:System.Double?displayProperty=nameWithType>|
|[`float`](floating-point-numeric-types.md)|<xref:System.Single?displayProperty=nameWithType>|
|[`int`](integral-numeric-types.md)|<xref:System.Int32?displayProperty=nameWithType>|
|[`uint`](integral-numeric-types.md)|<xref:System.UInt32?displayProperty=nameWithType>|
|[`long`](integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|
|[`ulong`](integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|
|[`short`](integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|
|[`ushort`](integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|

<span data-ttu-id="c3a8a-107">En la siguiente tabla se muestran los tipos de [referencia](../keywords/reference-types.md) integrados de C#:</span><span class="sxs-lookup"><span data-stu-id="c3a8a-107">The following table lists the C# built-in [reference](../keywords/reference-types.md) types:</span></span>

|<span data-ttu-id="c3a8a-108">Palabra clave de tipo de C#</span><span class="sxs-lookup"><span data-stu-id="c3a8a-108">C# type keyword</span></span>|<span data-ttu-id="c3a8a-109">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="c3a8a-109">.NET type</span></span>|
|--------------|-------------------------|
|[`object`](reference-types.md#the-object-type)|<xref:System.Object?displayProperty=nameWithType>|
|[`string`](reference-types.md#the-string-type)|<xref:System.String?displayProperty=nameWithType>|

<span data-ttu-id="c3a8a-110">En las tablas anteriores, cada palabra clave de tipo de C# de la columna ubicada a la izquierda es un alias del tipo de .NET correspondiente.</span><span class="sxs-lookup"><span data-stu-id="c3a8a-110">In the preceding tables, each C# type keyword from the left column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="c3a8a-111">Son intercambiables.</span><span class="sxs-lookup"><span data-stu-id="c3a8a-111">They are interchangeable.</span></span> <span data-ttu-id="c3a8a-112">Por ejemplo, en las declaraciones siguientes se declaran variables del mismo tipo:</span><span class="sxs-lookup"><span data-stu-id="c3a8a-112">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="c3a8a-113">La palabra clave [`void`](void.md) representa la ausencia de un tipo.</span><span class="sxs-lookup"><span data-stu-id="c3a8a-113">The [`void`](void.md) keyword represents the absence of a type.</span></span> <span data-ttu-id="c3a8a-114">Se usa como el tipo de valor devuelto de un método que no devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="c3a8a-114">You use it as the return type of a method that doesn't return a value.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3a8a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3a8a-115">See also</span></span>

- [<span data-ttu-id="c3a8a-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c3a8a-116">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c3a8a-117">Valores predeterminados de los tipos de C#</span><span class="sxs-lookup"><span data-stu-id="c3a8a-117">Default values of C# types</span></span>](default-values.md)
- [<span data-ttu-id="c3a8a-118">Palabra clave `dynamic`</span><span class="sxs-lookup"><span data-stu-id="c3a8a-118">`dynamic` keyword</span></span>](reference-types.md#the-dynamic-type)
