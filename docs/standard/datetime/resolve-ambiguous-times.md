---
description: 'Más información acerca de cómo: resolver horas ambiguas'
title: Procedimiento para resolver horas ambiguas
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], ambiguous time
- ambiguous time [.NET]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
ms.openlocfilehash: 743aff3303669efcf20e233b1f5b2d520475d5f9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99702527"
---
# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="ada98-103">Procedimiento para resolver horas ambiguas</span><span class="sxs-lookup"><span data-stu-id="ada98-103">How to: Resolve ambiguous times</span></span>

<span data-ttu-id="ada98-104">Una hora ambigua es aquella que se asigna a más de una hora universal coordinada (UTC).</span><span class="sxs-lookup"><span data-stu-id="ada98-104">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="ada98-105">Esto sucede cuando la hora del reloj se atrasa, como durante la transición del horario de verano de una zona horaria al horario estándar.</span><span class="sxs-lookup"><span data-stu-id="ada98-105">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="ada98-106">Cuando se enfrente a una hora ambigua, puede realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ada98-106">When handling an ambiguous time, you can do one of the following:</span></span>

- <span data-ttu-id="ada98-107">Piense cómo se corresponde esa hora con la hora UTC.</span><span class="sxs-lookup"><span data-stu-id="ada98-107">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="ada98-108">Por ejemplo, puede dar por supuesto que una hora ambigua siempre se expresa en la hora estándar de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="ada98-108">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

- <span data-ttu-id="ada98-109">Si la hora ambigua es un dato introducido por el usuario, puede dejar que el usuario resuelva la ambigüedad.</span><span class="sxs-lookup"><span data-stu-id="ada98-109">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="ada98-110">En este tema se muestra cómo resolver una hora ambigua suponiendo que representa la hora estándar de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="ada98-110">This topic shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="ada98-111">Para asignar una hora ambigua a la hora estándar de una zona horaria</span><span class="sxs-lookup"><span data-stu-id="ada98-111">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="ada98-112">Llame al <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> método para determinar si la hora es ambigua.</span><span class="sxs-lookup"><span data-stu-id="ada98-112">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="ada98-113">Si la hora es ambigua, reste la hora del <xref:System.TimeSpan> objeto devuelto por la propiedad de la zona horaria <xref:System.TimeZoneInfo.BaseUtcOffset%2A> .</span><span class="sxs-lookup"><span data-stu-id="ada98-113">If the time is ambiguous, subtract the time from the <xref:System.TimeSpan> object returned by the time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span>

3. <span data-ttu-id="ada98-114">Llame al `static` `Shared` método (en Visual Basic .net) <xref:System.DateTime.SpecifyKind%2A> para establecer la propiedad del valor de fecha y hora UTC <xref:System.DateTime.Kind%2A> en <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="ada98-114">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="ada98-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ada98-115">Example</span></span>

<span data-ttu-id="ada98-116">En el ejemplo siguiente se muestra cómo convertir una hora ambigua a la hora UTC suponiendo que representa la hora estándar de la zona horaria local.</span><span class="sxs-lookup"><span data-stu-id="ada98-116">The following example illustrates how to convert an ambiguous time to UTC by assuming that it represents the local time zone's standard time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

<span data-ttu-id="ada98-117">El ejemplo consta de un método denominado `ResolveAmbiguousTime` que determina si el <xref:System.DateTime> valor pasado a él es ambiguo.</span><span class="sxs-lookup"><span data-stu-id="ada98-117">The example consists of a method named `ResolveAmbiguousTime` that determines whether the <xref:System.DateTime> value passed to it is ambiguous.</span></span> <span data-ttu-id="ada98-118">Si el valor es ambiguo, el método devuelve un <xref:System.DateTime> valor que representa la hora UTC correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ada98-118">If the value is ambiguous, the method returns a <xref:System.DateTime> value that represents the corresponding UTC time.</span></span> <span data-ttu-id="ada98-119">El método controla esta conversión restando el valor de la propiedad de la zona horaria local <xref:System.TimeZoneInfo.BaseUtcOffset%2A> a la hora local.</span><span class="sxs-lookup"><span data-stu-id="ada98-119">The method handles this conversion by subtracting the value of the local time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property from the local time.</span></span>

<span data-ttu-id="ada98-120">Normalmente, se controla una hora ambigua llamando al <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> método para recuperar una matriz de <xref:System.TimeSpan> objetos que contienen los posibles desplazamientos de UTC de la hora ambigua.</span><span class="sxs-lookup"><span data-stu-id="ada98-120">Ordinarily, an ambiguous time is handled by calling the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="ada98-121">Pero en este ejemplo se supone arbitrariamente que una hora ambigua siempre debe estar asignada a la hora estándar de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="ada98-121">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="ada98-122">La <xref:System.TimeZoneInfo.BaseUtcOffset%2A> propiedad devuelve el desplazamiento entre la hora UTC y la hora estándar de una zona horaria.</span><span class="sxs-lookup"><span data-stu-id="ada98-122">The <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property returns the offset between UTC and a time zone's standard time.</span></span>

<span data-ttu-id="ada98-123">En este ejemplo, todas las referencias a la zona horaria local se realizan a través de la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> propiedad; la zona horaria local nunca se asigna a una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="ada98-123">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="ada98-124">Se trata de una práctica recomendada, ya que una llamada al <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> método invalida los objetos a los que está asignada la zona horaria local.</span><span class="sxs-lookup"><span data-stu-id="ada98-124">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="ada98-125">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="ada98-125">Compiling the code</span></span>

<span data-ttu-id="ada98-126">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="ada98-126">This example requires:</span></span>

- <span data-ttu-id="ada98-127">Que el <xref:System> espacio de nombres se debe importar con la `using` instrucción (necesaria en el código de C#).</span><span class="sxs-lookup"><span data-stu-id="ada98-127">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="ada98-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="ada98-128">See also</span></span>

- [<span data-ttu-id="ada98-129">Fechas, horas y zonas horarias</span><span class="sxs-lookup"><span data-stu-id="ada98-129">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="ada98-130">Cómo: permitir que los usuarios resuelvan horas ambiguas</span><span class="sxs-lookup"><span data-stu-id="ada98-130">How to: Let users resolve ambiguous times</span></span>](let-users-resolve-ambiguous-times.md)
