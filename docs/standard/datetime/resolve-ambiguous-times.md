---
title: 'Cómo: resolver horas ambiguas'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
ms.openlocfilehash: 0b5b28c588237fb2f7f069aaef06f3f73d5268bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122249"
---
# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="b1a0f-102">Cómo: resolver horas ambiguas</span><span class="sxs-lookup"><span data-stu-id="b1a0f-102">How to: Resolve ambiguous times</span></span>

<span data-ttu-id="b1a0f-103">Una hora ambigua es aquella que se asigna a más de una hora universal coordinada (UTC).</span><span class="sxs-lookup"><span data-stu-id="b1a0f-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="b1a0f-104">Esto sucede cuando la hora del reloj se atrasa, como durante la transición del horario de verano de una zona horaria al horario estándar.</span><span class="sxs-lookup"><span data-stu-id="b1a0f-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="b1a0f-105">Cuando se enfrente a una hora ambigua, puede realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b1a0f-105">When handling an ambiguous time, you can do one of the following:</span></span>

- <span data-ttu-id="b1a0f-106">Piense cómo se corresponde esa hora con la hora UTC.</span><span class="sxs-lookup"><span data-stu-id="b1a0f-106">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="b1a0f-107">Por ejemplo, puede dar por supuesto que una hora ambigua siempre se expresa en la hora estándar de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="b1a0f-107">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

- <span data-ttu-id="b1a0f-108">Si la hora ambigua es un dato introducido por el usuario, puede dejar que el usuario resuelva la ambigüedad.</span><span class="sxs-lookup"><span data-stu-id="b1a0f-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="b1a0f-109">En este tema se muestra cómo resolver una hora ambigua suponiendo que representa la hora estándar de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="b1a0f-109">This topic shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="b1a0f-110">Para asignar una hora ambigua a la hora estándar de una zona horaria</span><span class="sxs-lookup"><span data-stu-id="b1a0f-110">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="b1a0f-111">Llame al método <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> para determinar si la hora es ambigua.</span><span class="sxs-lookup"><span data-stu-id="b1a0f-111">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="b1a0f-112">Si la hora es ambigua, reste el tiempo del objeto <xref:System.TimeSpan> devuelto por la propiedad <xref:System.TimeZoneInfo.BaseUtcOffset%2A> de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="b1a0f-112">If the time is ambiguous, subtract the time from the <xref:System.TimeSpan> object returned by the time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span>

3. <span data-ttu-id="b1a0f-113">Llame al método de <xref:System.DateTime.SpecifyKind%2A> `static` (`Shared` en Visual Basic .NET) para establecer la propiedad <xref:System.DateTime.Kind%2A> del valor de fecha y hora UTC en <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b1a0f-113">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="b1a0f-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1a0f-114">Example</span></span>

<span data-ttu-id="b1a0f-115">En el ejemplo siguiente se muestra cómo convertir una hora ambigua a la hora UTC suponiendo que representa la hora estándar de la zona horaria local.</span><span class="sxs-lookup"><span data-stu-id="b1a0f-115">The following example illustrates how to convert an ambiguous time to UTC by assuming that it represents the local time zone's standard time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

<span data-ttu-id="b1a0f-116">El ejemplo consta de un método denominado `ResolveAmbiguousTime` que determina si el valor de <xref:System.DateTime> pasado es ambiguo.</span><span class="sxs-lookup"><span data-stu-id="b1a0f-116">The example consists of a method named `ResolveAmbiguousTime` that determines whether the <xref:System.DateTime> value passed to it is ambiguous.</span></span> <span data-ttu-id="b1a0f-117">Si el valor es ambiguo, el método devuelve un valor <xref:System.DateTime> que representa la hora UTC correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b1a0f-117">If the value is ambiguous, the method returns a <xref:System.DateTime> value that represents the corresponding UTC time.</span></span> <span data-ttu-id="b1a0f-118">El método controla esta conversión restando el valor de la propiedad <xref:System.TimeZoneInfo.BaseUtcOffset%2A> de la zona horaria local a la hora local.</span><span class="sxs-lookup"><span data-stu-id="b1a0f-118">The method handles this conversion by subtracting the value of the local time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property from the local time.</span></span>

<span data-ttu-id="b1a0f-119">Normalmente, se controla una hora ambigua llamando al método <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> para recuperar una matriz de objetos <xref:System.TimeSpan> que contengan los desplazamientos UTC posibles de la hora ambigua.</span><span class="sxs-lookup"><span data-stu-id="b1a0f-119">Ordinarily, an ambiguous time is handled by calling the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="b1a0f-120">Pero en este ejemplo se supone arbitrariamente que una hora ambigua siempre debe estar asignada a la hora estándar de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="b1a0f-120">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="b1a0f-121">La propiedad <xref:System.TimeZoneInfo.BaseUtcOffset%2A> devuelve el desplazamiento entre la hora UTC y la hora estándar de una zona horaria.</span><span class="sxs-lookup"><span data-stu-id="b1a0f-121">The <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property returns the offset between UTC and a time zone's standard time.</span></span>

<span data-ttu-id="b1a0f-122">En este ejemplo, todas las referencias a la zona horaria local se realizan a través de la propiedad <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>; la zona horaria local nunca se asigna a una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="b1a0f-122">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="b1a0f-123">Se trata de una práctica recomendada, ya que una llamada al método <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> invalida los objetos a los que está asignada la zona horaria local.</span><span class="sxs-lookup"><span data-stu-id="b1a0f-123">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="b1a0f-124">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="b1a0f-124">Compiling the code</span></span>

<span data-ttu-id="b1a0f-125">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="b1a0f-125">This example requires:</span></span>

- <span data-ttu-id="b1a0f-126">Que el espacio de nombres <xref:System> se importe con la instrucción `using` ( C# necesaria en el código).</span><span class="sxs-lookup"><span data-stu-id="b1a0f-126">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="b1a0f-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1a0f-127">See also</span></span>

- [<span data-ttu-id="b1a0f-128">Fechas, horas y zonas horarias</span><span class="sxs-lookup"><span data-stu-id="b1a0f-128">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="b1a0f-129">Permitir que los usuarios resuelvan horas ambiguas</span><span class="sxs-lookup"><span data-stu-id="b1a0f-129">How to: Let users resolve ambiguous times</span></span>](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
