---
title: Procedimiento para valores de fecha y hora de ida y vuelta
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- round-trip date and time values
- dates [.NET], round-trip values
- time zones [.NET], round-trip date and time values
- time [.NET], round-trip values
- formatting strings [.NET], round-trip values
ms.assetid: b609b277-edc6-4c74-b03e-ea73324ecbdb
ms.openlocfilehash: 243ed98972f834c207331770f9d0202ddb60d4e6
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821975"
---
# <a name="how-to-round-trip-date-and-time-values"></a><span data-ttu-id="b7253-102">Procedimiento para valores de fecha y hora de ida y vuelta</span><span class="sxs-lookup"><span data-stu-id="b7253-102">How to: Round-trip Date and Time Values</span></span>

<span data-ttu-id="b7253-103">En muchas aplicaciones, un valor de fecha y hora sirve para identificar inequívocamente un único punto en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="b7253-103">In many applications, a date and time value is intended to unambiguously identify a single point in time.</span></span> <span data-ttu-id="b7253-104">En este artículo se muestra cómo guardar y restaurar un valor <xref:System.DateTime>, <xref:System.DateTimeOffset> y de fecha y hora con información sobre la zona horaria, de manera que el valor restaurado identifique la misma hora que el guardado.</span><span class="sxs-lookup"><span data-stu-id="b7253-104">This article shows how to save and restore a <xref:System.DateTime> value, a <xref:System.DateTimeOffset> value, and a date and time value with time zone information so that the restored value identifies the same time as the saved value.</span></span>

## <a name="round-trip-a-datetime-value"></a><span data-ttu-id="b7253-105">Acción de ida y vuelta para un valor DateTime</span><span class="sxs-lookup"><span data-stu-id="b7253-105">Round-trip a DateTime value</span></span>

1. <span data-ttu-id="b7253-106">Convierta el valor <xref:System.DateTime> en su representación de cadena mediante una llamada al método <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> con el especificador de formato "o".</span><span class="sxs-lookup"><span data-stu-id="b7253-106">Convert the <xref:System.DateTime> value to its string representation by calling the <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> method with the "o" format specifier.</span></span>

2. <span data-ttu-id="b7253-107">Guarde la representación de cadena del valor <xref:System.DateTime> en un archivo o pásela a través de un límite de proceso, dominio de aplicación o máquina.</span><span class="sxs-lookup"><span data-stu-id="b7253-107">Save the string representation of the <xref:System.DateTime> value to a file, or pass it across a process, application domain, or machine boundary.</span></span>

3. <span data-ttu-id="b7253-108">Recupere la cadena que representa el valor <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="b7253-108">Retrieve the string that represents the <xref:System.DateTime> value.</span></span>

4. <span data-ttu-id="b7253-109">Llame al método <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> y pase <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> como el valor del parámetro `styles`.</span><span class="sxs-lookup"><span data-stu-id="b7253-109">Call the <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> method, and pass <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> as the value of the `styles` parameter.</span></span>

<span data-ttu-id="b7253-110">En el ejemplo siguiente se muestra cómo usar un valor <xref:System.DateTime> de ida y vuelta.</span><span class="sxs-lookup"><span data-stu-id="b7253-110">The following example illustrates how to round-trip a <xref:System.DateTime> value.</span></span>

[!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
[!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]

<span data-ttu-id="b7253-111">Cuando se usa un valor <xref:System.DateTime> de ida y vuelta, esta técnica mantiene correctamente la hora para todas las horas locales y universales.</span><span class="sxs-lookup"><span data-stu-id="b7253-111">When round-tripping a <xref:System.DateTime> value, this technique successfully preserves the time for all local and universal times.</span></span> <span data-ttu-id="b7253-112">Por ejemplo, si un valor local <xref:System.DateTime> se guarda en un sistema de la zona horaria estándar del Pacífico de Estados Unidos y se restaura en un sistema de la zona horaria estándar central de Estados Unidos, la fecha y hora restauradas serán dos horas posteriores a la hora original, lo que refleja la diferencia horaria entre las dos zonas.</span><span class="sxs-lookup"><span data-stu-id="b7253-112">For example, if a local <xref:System.DateTime> value is saved on a system in the U.S. Pacific Standard Time zone and is restored on a system in the U.S. Central Standard Time zone, the restored date and time will be two hours later than the original time, which reflects the time difference between the two time zones.</span></span> <span data-ttu-id="b7253-113">Pero esta técnica no es necesariamente precisa para horas no especificadas.</span><span class="sxs-lookup"><span data-stu-id="b7253-113">However, this technique is not necessarily accurate for unspecified times.</span></span> <span data-ttu-id="b7253-114">Todos los valores <xref:System.DateTime> cuya propiedad <xref:System.DateTime.Kind%2A> es <xref:System.DateTimeKind.Unspecified> se tratan como si fueran horas locales.</span><span class="sxs-lookup"><span data-stu-id="b7253-114">All <xref:System.DateTime> values whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Unspecified> are treated as if they are local times.</span></span> <span data-ttu-id="b7253-115">Si no es una hora local, <xref:System.DateTime> no identificará correctamente el punto en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="b7253-115">If it's not a local time, the <xref:System.DateTime> doesn't successfully identify the correct point in time.</span></span> <span data-ttu-id="b7253-116">La solución alternativa para esta limitación es acoplar estrechamente un valor de fecha y hora con su zona horaria para la operación de guardado y restauración.</span><span class="sxs-lookup"><span data-stu-id="b7253-116">The workaround for this limitation is to tightly couple a date and time value with its time zone for the save and restore operation.</span></span>

## <a name="round-trip-a-datetimeoffset-value"></a><span data-ttu-id="b7253-117">Acción de ida y vuelta para un valor DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="b7253-117">Round-trip a DateTimeOffset value</span></span>

1. <span data-ttu-id="b7253-118">Convierta el valor <xref:System.DateTimeOffset> en su representación de cadena mediante una llamada al método <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> con el especificador de formato "o".</span><span class="sxs-lookup"><span data-stu-id="b7253-118">Convert the <xref:System.DateTimeOffset> value to its string representation by calling the <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> method with the "o" format specifier.</span></span>

2. <span data-ttu-id="b7253-119">Guarde la representación de cadena del valor <xref:System.DateTimeOffset> en un archivo o pásela a través de un límite de proceso, dominio de aplicación o máquina.</span><span class="sxs-lookup"><span data-stu-id="b7253-119">Save the string representation of the <xref:System.DateTimeOffset> value to a file, or pass it across a process, application domain, or machine boundary.</span></span>

3. <span data-ttu-id="b7253-120">Recupere la cadena que representa el valor <xref:System.DateTimeOffset>.</span><span class="sxs-lookup"><span data-stu-id="b7253-120">Retrieve the string that represents the <xref:System.DateTimeOffset> value.</span></span>

4. <span data-ttu-id="b7253-121">Llame al método <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> y pase <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> como el valor del parámetro `styles`.</span><span class="sxs-lookup"><span data-stu-id="b7253-121">Call the <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> method, and pass <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> as the value of the `styles` parameter.</span></span>

<span data-ttu-id="b7253-122">En el ejemplo siguiente se muestra cómo usar un valor <xref:System.DateTimeOffset> de ida y vuelta.</span><span class="sxs-lookup"><span data-stu-id="b7253-122">The following example illustrates how to round-trip a <xref:System.DateTimeOffset> value.</span></span>

[!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
[!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]

<span data-ttu-id="b7253-123">Esta técnica identifica siempre de forma inequívoca un valor <xref:System.DateTimeOffset> como un único punto en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="b7253-123">This technique always unambiguously identifies a <xref:System.DateTimeOffset> value as a single point in time.</span></span> <span data-ttu-id="b7253-124">El valor puede convertirse entonces en la hora universal coordinada (UTC) al llamar al método <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType>, o bien puede convertirse en la hora de una zona horaria concreta al llamar a los métodos <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> o <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b7253-124">The value can then be converted to Coordinated Universal Time (UTC) by calling the <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> method, or it can be converted to the time in a particular time zone by calling the <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> or <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b7253-125">La limitación principal de esta técnica está en que las operaciones aritméticas de fecha y hora, cuando se realizan en un valor <xref:System.DateTimeOffset> que representa la hora en una zona horaria determinada, podrían no generar resultados precisos para esa zona horaria.</span><span class="sxs-lookup"><span data-stu-id="b7253-125">The major limitation of this technique is that date and time arithmetic, when performed on a <xref:System.DateTimeOffset> value that represents the time in a particular time zone, may not produce accurate results for that time zone.</span></span> <span data-ttu-id="b7253-126">Esto se debe a que, cuando se crea una instancia de un valor <xref:System.DateTimeOffset>, se desasocia de su zona horaria.</span><span class="sxs-lookup"><span data-stu-id="b7253-126">This is because when a <xref:System.DateTimeOffset> value is instantiated, it is disassociated from its time zone.</span></span> <span data-ttu-id="b7253-127">Por lo tanto, ya no se pueden aplicar las reglas de ajuste de esa zona de horaria al realizar cálculos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="b7253-127">Therefore, that time zone's adjustment rules can no longer be applied when you perform date and time calculations.</span></span> <span data-ttu-id="b7253-128">Para evitar este problema, puede definir un tipo personalizado que incluya tanto el valor de fecha y hora como la zona horaria correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b7253-128">You can work around this problem by defining a custom type that includes both a date and time value and its accompanying time zone.</span></span>

## <a name="round-trip-a-date-and-time-value-with-its-time-zone"></a><span data-ttu-id="b7253-129">Acción de ida y vuelta para un valor de fecha y hora con su zona horaria</span><span class="sxs-lookup"><span data-stu-id="b7253-129">Round-trip a date and time value with its time zone</span></span>

1. <span data-ttu-id="b7253-130">Defina una clase o una estructura con dos campos.</span><span class="sxs-lookup"><span data-stu-id="b7253-130">Define a class or a structure with two fields.</span></span> <span data-ttu-id="b7253-131">El primer campo es un objeto <xref:System.DateTime> o <xref:System.DateTimeOffset> y el segundo es un objeto <xref:System.TimeZoneInfo>.</span><span class="sxs-lookup"><span data-stu-id="b7253-131">The first field is either a <xref:System.DateTime> or a <xref:System.DateTimeOffset> object, and the second is a <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="b7253-132">El ejemplo siguiente es una versión sencilla de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="b7253-132">The following example is a simple version of such a type.</span></span>

    [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
    [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]

2. <span data-ttu-id="b7253-133">Marque la clase con el atributo <xref:System.SerializableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b7253-133">Mark the class with the <xref:System.SerializableAttribute> attribute.</span></span>

3. <span data-ttu-id="b7253-134">Serialice el objeto con el método <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b7253-134">Serialize the object using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="b7253-135">Restaure el objeto con el método <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A>.</span><span class="sxs-lookup"><span data-stu-id="b7253-135">Restore the object using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> method.</span></span>

5. <span data-ttu-id="b7253-136">Convierta (en C# o en Visual Basic) el objeto deserializado en un objeto del tipo adecuado.</span><span class="sxs-lookup"><span data-stu-id="b7253-136">Cast (in C#) or convert (in Visual Basic) the deserialized object to an object of the appropriate type.</span></span>

<span data-ttu-id="b7253-137">En el ejemplo siguiente se muestra cómo realizar una acción de ida y vuelta para un objeto que almacena información de zona horaria y de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="b7253-137">The following example illustrates how to round-trip an object that stores both time zone and date and time information.</span></span>

[!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
[!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]

<span data-ttu-id="b7253-138">Esta técnica debe reflejar siempre de forma inequívoca el punto correcto de tiempo antes y después de guardar y restaurar, siempre que la implementación del objeto combinado de fecha y hora y de zona horaria no permita que el valor de fecha quede fuera de la sincronización con el valor de zona horaria.</span><span class="sxs-lookup"><span data-stu-id="b7253-138">This technique should always unambiguously reflect the correct point of time both before and after it is saved and restored, provided that the implementation of the combined date and time and time zone object does not allow the date value to become out of sync with the time zone value.</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="b7253-139">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b7253-139">Compile the code</span></span>

<span data-ttu-id="b7253-140">Para estos ejemplos se necesita lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b7253-140">These examples require that:</span></span>

- <span data-ttu-id="b7253-141">Que los espacios de nombres siguientes se importen con directivas `using` de C# o con instrucciones `Imports` de Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="b7253-141">The following namespaces be imported with C# `using` directives or Visual Basic `Imports` statements:</span></span>

  - <span data-ttu-id="b7253-142"><xref:System> (solo C#)</span><span class="sxs-lookup"><span data-stu-id="b7253-142"><xref:System> (C# only)</span></span>

  - <xref:System.Globalization?displayProperty=nameWithType>

  - <xref:System.IO?displayProperty=nameWithType>

  - <xref:System.Runtime.Serialization?displayProperty=nameWithType>

  - <xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>

- <span data-ttu-id="b7253-143">Que cada ejemplo de código, excepto la clase `DateInTimeZone`, se incluyan en una clase o módulo de Visual Basic, encapsulado en métodos y llamado desde el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="b7253-143">Each code example, other than the `DateInTimeZone` class, be included in a class or Visual Basic module, wrapped in methods, and called from the `Main` method.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7253-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7253-144">See also</span></span>

- [<span data-ttu-id="b7253-145">Elección entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="b7253-145">Choosing Between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo</span></span>](../datetime/choosing-between-datetime.md)
- [<span data-ttu-id="b7253-146">Cadenas con formato de fecha y hora estándar</span><span class="sxs-lookup"><span data-stu-id="b7253-146">Standard Date and Time Format Strings</span></span>](standard-date-and-time-format-strings.md)
