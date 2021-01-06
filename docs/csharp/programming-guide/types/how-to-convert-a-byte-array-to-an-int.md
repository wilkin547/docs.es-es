---
title: 'Procedimiento Convertir una matriz de bytes en un valor int: Guía de programación de C#'
description: Aprenda a convertir una matriz de bytes en un entero. Vea ejemplos de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], byte array to int
- byte arrays [C#], converting to int
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
ms.openlocfilehash: f6fb6ad907ecd668d59ca95b19218c19d378d83e
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513255"
---
# <a name="how-to-convert-a-byte-array-to-an-int-c-programming-guide"></a><span data-ttu-id="500d6-103">Procedimiento Convertir una matriz de bytes en un valor int (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="500d6-103">How to convert a byte array to an int (C# Programming Guide)</span></span>

<span data-ttu-id="500d6-104">En este ejemplo se muestra cómo usar la clase <xref:System.BitConverter> para convertir una matriz de bytes en un valor [int](../../language-reference/builtin-types/integral-numeric-types.md) y de nuevo en una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="500d6-104">This example shows you how to use the <xref:System.BitConverter> class to convert an array of bytes to an [int](../../language-reference/builtin-types/integral-numeric-types.md) and back to an array of bytes.</span></span> <span data-ttu-id="500d6-105">Por ejemplo, es posible que tenga que realizar una conversión de bytes a un tipo de datos integrado después de leer los bytes fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="500d6-105">You may have to convert from bytes to a built-in data type after you read bytes off the network, for example.</span></span> <span data-ttu-id="500d6-106">Además del método [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) del ejemplo, en la tabla siguiente se muestran los métodos de la clase <xref:System.BitConverter> que sirven para convertir bytes (de una matriz de bytes) en otros tipos integrados.</span><span class="sxs-lookup"><span data-stu-id="500d6-106">In addition to the [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) method in the example, the following table lists methods in the <xref:System.BitConverter> class that convert bytes (from an array of bytes) to other built-in types.</span></span>

|<span data-ttu-id="500d6-107">Tipo devuelto</span><span class="sxs-lookup"><span data-stu-id="500d6-107">Type returned</span></span>|<span data-ttu-id="500d6-108">Método</span><span class="sxs-lookup"><span data-stu-id="500d6-108">Method</span></span>|
|-------------------|------------|
|`bool`|<span data-ttu-id="500d6-109">[ToBoolean(Byte\[\], Int32)](xref:System.BitConverter.ToBoolean(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="500d6-109">[ToBoolean(Byte\[\], Int32)](xref:System.BitConverter.ToBoolean(System.Byte[],System.Int32))</span></span>|
|`char`|<span data-ttu-id="500d6-110">[ToChar(Byte\[\], Int32)](xref:System.BitConverter.ToChar(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="500d6-110">[ToChar(Byte\[\], Int32)](xref:System.BitConverter.ToChar(System.Byte[],System.Int32))</span></span>|
|`double`|<span data-ttu-id="500d6-111">[ToDouble(Byte\[\], Int32)](xref:System.BitConverter.ToDouble(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="500d6-111">[ToDouble(Byte\[\], Int32)](xref:System.BitConverter.ToDouble(System.Byte[],System.Int32))</span></span>|
|`short`|<span data-ttu-id="500d6-112">[ToInt16(Byte\[\], Int32)](xref:System.BitConverter.ToInt16(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="500d6-112">[ToInt16(Byte\[\], Int32)](xref:System.BitConverter.ToInt16(System.Byte[],System.Int32))</span></span>|
|`int`|<span data-ttu-id="500d6-113">[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="500d6-113">[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))</span></span>|
|`long`|<span data-ttu-id="500d6-114">[ToInt64(Byte\[\], Int32)](xref:System.BitConverter.ToInt64(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="500d6-114">[ToInt64(Byte\[\], Int32)](xref:System.BitConverter.ToInt64(System.Byte[],System.Int32))</span></span>|
|`float`|<span data-ttu-id="500d6-115">[ToSingle(Byte\[\], Int32)](xref:System.BitConverter.ToSingle(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="500d6-115">[ToSingle(Byte\[\], Int32)](xref:System.BitConverter.ToSingle(System.Byte[],System.Int32))</span></span>|
|`ushort`|<span data-ttu-id="500d6-116">[ToUInt16(Byte\[\], Int32)](xref:System.BitConverter.ToUInt16(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="500d6-116">[ToUInt16(Byte\[\], Int32)](xref:System.BitConverter.ToUInt16(System.Byte[],System.Int32))</span></span>|
|`uint`|<span data-ttu-id="500d6-117">[ToUInt32(Byte\[\], Int32)](xref:System.BitConverter.ToUInt32(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="500d6-117">[ToUInt32(Byte\[\], Int32)](xref:System.BitConverter.ToUInt32(System.Byte[],System.Int32))</span></span>|
|`ulong`|<span data-ttu-id="500d6-118">[ToUInt64(Byte\[\], Int32)](xref:System.BitConverter.ToUInt64(System.Byte[],System.Int32))</span><span class="sxs-lookup"><span data-stu-id="500d6-118">[ToUInt64(Byte\[\], Int32)](xref:System.BitConverter.ToUInt64(System.Byte[],System.Int32))</span></span>|

## <a name="example"></a><span data-ttu-id="500d6-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="500d6-119">Example</span></span>

<span data-ttu-id="500d6-120">En este ejemplo se inicializa una matriz de bytes, se invierte la matriz si la arquitectura de equipo es little-endian (es decir, en primer lugar se almacena el byte menos significativo) y, después, se llama al método [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) para convertir cuatro bytes de la matriz en `int`.</span><span class="sxs-lookup"><span data-stu-id="500d6-120">This example initializes an array of bytes, reverses the array if the computer architecture is little-endian (that is, the least significant byte is stored first), and then calls the [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) method to convert four bytes in the array to an `int`.</span></span> <span data-ttu-id="500d6-121">El segundo argumento de [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) especifica el índice de inicio de la matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="500d6-121">The second argument to [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) specifies the start index of the array of bytes.</span></span>

> [!NOTE]
> <span data-ttu-id="500d6-122">El resultado puede cambiar en función de los modos endian de la arquitectura del equipo.</span><span class="sxs-lookup"><span data-stu-id="500d6-122">The output may differ depending on the endianness of your computer's architecture.</span></span>

[!code-csharp[csProgGuideTypes#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#22)]

## <a name="example"></a><span data-ttu-id="500d6-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="500d6-123">Example</span></span>

<span data-ttu-id="500d6-124">En este ejemplo, el método <xref:System.BitConverter.GetBytes%28System.Int32%29> de la clase <xref:System.BitConverter> se llama para convertir `int` en una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="500d6-124">In this example, the <xref:System.BitConverter.GetBytes%28System.Int32%29> method of the <xref:System.BitConverter> class is called to convert an `int` to an array of bytes.</span></span>

> [!NOTE]
> <span data-ttu-id="500d6-125">El resultado puede cambiar en función de los modos endian de la arquitectura del equipo.</span><span class="sxs-lookup"><span data-stu-id="500d6-125">The output may differ depending on the endianness of your computer's architecture.</span></span>

[!code-csharp[csProgGuideTypes#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#23)]

## <a name="see-also"></a><span data-ttu-id="500d6-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="500d6-126">See also</span></span>

- <xref:System.BitConverter>
- <xref:System.BitConverter.IsLittleEndian>
- [<span data-ttu-id="500d6-127">Tipos</span><span class="sxs-lookup"><span data-stu-id="500d6-127">Types</span></span>](./index.md)
