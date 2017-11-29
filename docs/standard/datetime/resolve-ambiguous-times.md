---
title: "Cómo: resolver horas ambiguas"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e3706747848dbcd29d4ed2e81d5b7447a127a653
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="301fb-102">Cómo: resolver horas ambiguas</span><span class="sxs-lookup"><span data-stu-id="301fb-102">How to: Resolve ambiguous times</span></span>

<span data-ttu-id="301fb-103">Una hora ambigua es aquella que se asigna a más de una hora universal coordinada (UTC).</span><span class="sxs-lookup"><span data-stu-id="301fb-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="301fb-104">Esto sucede cuando la hora del reloj se atrasa, como durante la transición del horario de verano de una zona horaria al horario estándar.</span><span class="sxs-lookup"><span data-stu-id="301fb-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="301fb-105">Cuando se enfrente a una hora ambigua, puede realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="301fb-105">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="301fb-106">Piense cómo se corresponde esa hora con la hora UTC.</span><span class="sxs-lookup"><span data-stu-id="301fb-106">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="301fb-107">Por ejemplo, puede dar por supuesto que una hora ambigua siempre se expresa en la hora estándar de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="301fb-107">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

* <span data-ttu-id="301fb-108">Si la hora ambigua es un dato introducido por el usuario, puede dejar que el usuario resuelva la ambigüedad.</span><span class="sxs-lookup"><span data-stu-id="301fb-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="301fb-109">Este tema muestra cómo resolver una hora ambigua suponiendo que representa la hora de la zona horaria estándar.</span><span class="sxs-lookup"><span data-stu-id="301fb-109">This topic shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="301fb-110">Para asignar una hora ambigua a la hora estándar de una zona horaria</span><span class="sxs-lookup"><span data-stu-id="301fb-110">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="301fb-111">Llame a la <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> método para determinar si la hora es ambigua.</span><span class="sxs-lookup"><span data-stu-id="301fb-111">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="301fb-112">Si la hora es ambigua, reste el tiempo desde el <xref:System.TimeSpan> objeto devuelto por la zona horaria <xref:System.TimeZoneInfo.BaseUtcOffset%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="301fb-112">If the time is ambiguous, subtract the time from the <xref:System.TimeSpan> object returned by the time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span>

3. <span data-ttu-id="301fb-113">Llame a la `static` (`Shared` en Visual Basic. NET) <xref:System.DateTime.SpecifyKind%2A> método para establecer la fecha y hora valor UTC <xref:System.DateTime.Kind%2A> propiedad <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="301fb-113">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="301fb-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="301fb-114">Example</span></span>

<span data-ttu-id="301fb-115">En el ejemplo siguiente se muestra cómo convertir una hora ambigua en una hora UTC suponiendo que representa la hora estándar de la zona horaria local.</span><span class="sxs-lookup"><span data-stu-id="301fb-115">The following example illustrates how to convert an ambiguous time to UTC by assuming that it represents the local time zone's standard time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

<span data-ttu-id="301fb-116">El ejemplo consta de un método denominado `ResolveAmbiguousTime` que determina si el <xref:System.DateTime> valor pasado es ambiguo.</span><span class="sxs-lookup"><span data-stu-id="301fb-116">The example consists of a method named `ResolveAmbiguousTime` that determines whether the <xref:System.DateTime> value passed to it is ambiguous.</span></span> <span data-ttu-id="301fb-117">Si el valor es ambiguo, el método devuelve un <xref:System.DateTime> valor que representa la hora UTC correspondiente.</span><span class="sxs-lookup"><span data-stu-id="301fb-117">If the value is ambiguous, the method returns a <xref:System.DateTime> value that represents the corresponding UTC time.</span></span> <span data-ttu-id="301fb-118">El método controla esta conversión restando el valor de la zona horaria local <xref:System.TimeZoneInfo.BaseUtcOffset%2A> propiedad desde la hora local.</span><span class="sxs-lookup"><span data-stu-id="301fb-118">The method handles this conversion by subtracting the value of the local time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property from the local time.</span></span>

<span data-ttu-id="301fb-119">Normalmente, una hora ambigua se controla mediante una llamada a la <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> método para recuperar una matriz de <xref:System.TimeSpan> desplazamientos de objetos que contienen posibles UTC la hora ambigua.</span><span class="sxs-lookup"><span data-stu-id="301fb-119">Ordinarily, an ambiguous time is handled by calling the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="301fb-120">Pero en este ejemplo se supone arbitrariamente que una hora ambigua siempre debe estar asignada a la hora estándar de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="301fb-120">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="301fb-121">El <xref:System.TimeZoneInfo.BaseUtcOffset%2A> propiedad devuelve la diferencia entre la hora UTC y la hora de una zona horaria estándar.</span><span class="sxs-lookup"><span data-stu-id="301fb-121">The <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property returns the offset between UTC and a time zone's standard time.</span></span>

<span data-ttu-id="301fb-122">En este ejemplo, todas las referencias a la zona horaria local se realizan a través del <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> propiedad; la hora local zona nunca se asigna a una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="301fb-122">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="301fb-123">Esto es una práctica recomendada porque una llamada a la <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> método invalida cualquier objeto asignado a la zona horaria local.</span><span class="sxs-lookup"><span data-stu-id="301fb-123">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="301fb-124">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="301fb-124">Compiling the code</span></span>

<span data-ttu-id="301fb-125">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="301fb-125">This example requires:</span></span>

* <span data-ttu-id="301fb-126">Que se agregará al proyecto una referencia a System.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="301fb-126">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="301fb-127">Que el <xref:System> espacio de nombres se importan con el `using` instrucción (obligatorio en el código de C#).</span><span class="sxs-lookup"><span data-stu-id="301fb-127">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="301fb-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="301fb-128">See also</span></span>

<span data-ttu-id="301fb-129">[Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
[Cómo: permitir que los usuarios a resolver horas ambiguas](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)</span><span class="sxs-lookup"><span data-stu-id="301fb-129">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[How to: Let users resolve ambiguous times](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)</span></span>
