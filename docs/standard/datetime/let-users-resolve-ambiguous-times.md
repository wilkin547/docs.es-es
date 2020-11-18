---
title: Procedimiento para permitir que los usuarios resuelvan horas ambiguas
ms.date: 04/10/2017
helpviewer_keywords:
- time zones [.NET], ambiguous time
- ambiguous time [.NET]
ms.assetid: bca874ee-5b68-4654-8bbd-3711220ef332
ms.openlocfilehash: d543db20161057764749210533f35f7c2a1ec81d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817801"
---
# <a name="how-to-let-users-resolve-ambiguous-times"></a><span data-ttu-id="66525-102">Procedimiento para permitir que los usuarios resuelvan horas ambiguas</span><span class="sxs-lookup"><span data-stu-id="66525-102">How to: Let users resolve ambiguous times</span></span>

<span data-ttu-id="66525-103">Una hora ambigua es aquella que se asigna a más de una hora universal coordinada (UTC).</span><span class="sxs-lookup"><span data-stu-id="66525-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="66525-104">Esto sucede cuando la hora del reloj se atrasa, como durante la transición del horario de verano de una zona horaria al horario estándar.</span><span class="sxs-lookup"><span data-stu-id="66525-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="66525-105">Cuando se enfrente a una hora ambigua, puede realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="66525-105">When handling an ambiguous time, you can do one of the following:</span></span>

- <span data-ttu-id="66525-106">Si la hora ambigua es un dato introducido por el usuario, puede dejar que el usuario resuelva la ambigüedad.</span><span class="sxs-lookup"><span data-stu-id="66525-106">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

- <span data-ttu-id="66525-107">Piense cómo se corresponde esa hora con la hora UTC.</span><span class="sxs-lookup"><span data-stu-id="66525-107">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="66525-108">Por ejemplo, puede dar por supuesto que una hora ambigua siempre se expresa en la hora estándar de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="66525-108">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

<span data-ttu-id="66525-109">En este tema se muestra cómo permitir que un usuario resuelva una hora ambigua.</span><span class="sxs-lookup"><span data-stu-id="66525-109">This topic shows how to let a user resolve an ambiguous time.</span></span>

### <a name="to-let-a-user-resolve-an-ambiguous-time"></a><span data-ttu-id="66525-110">Para permitir que un usuario resuelva una hora ambigua</span><span class="sxs-lookup"><span data-stu-id="66525-110">To let a user resolve an ambiguous time</span></span>

1. <span data-ttu-id="66525-111">Obtenga la entrada de fecha y hora del usuario.</span><span class="sxs-lookup"><span data-stu-id="66525-111">Get the date and time input by the user.</span></span>

2. <span data-ttu-id="66525-112">Llame al <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> método para determinar si la hora es ambigua.</span><span class="sxs-lookup"><span data-stu-id="66525-112">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

3. <span data-ttu-id="66525-113">Si la hora es ambigua, llame al <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> método para recuperar una matriz de <xref:System.TimeSpan> objetos.</span><span class="sxs-lookup"><span data-stu-id="66525-113">If the time is ambiguous, call the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects.</span></span> <span data-ttu-id="66525-114">Cada elemento de la matriz contiene un desplazamiento UTC al que se puede asignar la hora ambigua.</span><span class="sxs-lookup"><span data-stu-id="66525-114">Each element in the array contains a UTC offset that the ambiguous time can map to.</span></span>

4. <span data-ttu-id="66525-115">Permita que el usuario seleccione la diferencia horaria que quiera.</span><span class="sxs-lookup"><span data-stu-id="66525-115">Let the user select the desired offset.</span></span>

5. <span data-ttu-id="66525-116">Para obtener la fecha y hora UTC, reste de la hora local la diferencia horaria que ha seleccionado el usuario.</span><span class="sxs-lookup"><span data-stu-id="66525-116">Get the UTC date and time by subtracting the offset selected by the user from the local time.</span></span>

6. <span data-ttu-id="66525-117">Llame al `static` `Shared` método (en Visual Basic .net) <xref:System.DateTime.SpecifyKind%2A> para establecer la propiedad del valor de fecha y hora UTC <xref:System.DateTime.Kind%2A> en <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="66525-117">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="66525-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="66525-118">Example</span></span>

<span data-ttu-id="66525-119">En el ejemplo siguiente se le pide al usuario que escriba un valor de fecha y hora y, si es ambiguo, se permite que el usuario seleccione la hora UTC con la que se corresponde dicha hora ambigua.</span><span class="sxs-lookup"><span data-stu-id="66525-119">The following example prompts the user to enter a date and time and, if it is ambiguous, lets the user select the UTC time that the ambiguous time maps to.</span></span>

[!code-csharp[System.TimeZone2.Concepts#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#11)]
[!code-vb[System.TimeZone2.Concepts#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#11)]

<span data-ttu-id="66525-120">En el núcleo del código de ejemplo se usa una matriz de <xref:System.TimeSpan> objetos para indicar posibles desplazamientos de la hora ambigua con respecto a la hora UTC.</span><span class="sxs-lookup"><span data-stu-id="66525-120">The core of the example code uses an array of <xref:System.TimeSpan> objects to indicate possible offsets of the ambiguous time from UTC.</span></span> <span data-ttu-id="66525-121">Pero es probable que estas diferencias horarias sean poco significativas para el usuario.</span><span class="sxs-lookup"><span data-stu-id="66525-121">However, these offsets are unlikely to be meaningful to the user.</span></span> <span data-ttu-id="66525-122">Para aclarar el significado de las diferencias horarias, el código también indica si una diferencia horaria representa la hora estándar o el horario de verano de la zona horaria local.</span><span class="sxs-lookup"><span data-stu-id="66525-122">To clarify the meaning of the offsets, the code also notes whether an offset represents the local time zone's standard time or its daylight saving time.</span></span> <span data-ttu-id="66525-123">El código determina qué hora es estándar y qué hora es el horario de verano comparando el desplazamiento con el valor de la <xref:System.TimeZoneInfo.BaseUtcOffset%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="66525-123">The code determines which time is standard and which time is daylight by comparing the offset with the value of the <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span> <span data-ttu-id="66525-124">Esta propiedad indica la diferencia entre la hora UTC y la hora estándar de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="66525-124">This property indicates the difference between the UTC and the time zone's standard time.</span></span>

<span data-ttu-id="66525-125">En este ejemplo, todas las referencias a la zona horaria local se realizan a través de la <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> propiedad; la zona horaria local nunca se asigna a una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="66525-125">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="66525-126">Se trata de una práctica recomendada, ya que una llamada al <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> método invalida los objetos a los que está asignada la zona horaria local.</span><span class="sxs-lookup"><span data-stu-id="66525-126">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="66525-127">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="66525-127">Compiling the code</span></span>

<span data-ttu-id="66525-128">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="66525-128">This example requires:</span></span>

- <span data-ttu-id="66525-129">Que el <xref:System> espacio de nombres se debe importar con la `using` instrucción (necesaria en el código de C#).</span><span class="sxs-lookup"><span data-stu-id="66525-129">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="66525-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="66525-130">See also</span></span>

- [<span data-ttu-id="66525-131">Fechas, horas y zonas horarias</span><span class="sxs-lookup"><span data-stu-id="66525-131">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="66525-132">Cómo: resolver horas ambiguas</span><span class="sxs-lookup"><span data-stu-id="66525-132">How to: Resolve ambiguous times</span></span>](resolve-ambiguous-times.md)
