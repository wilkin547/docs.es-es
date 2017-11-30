---
title: "Cómo: Aplicar acciones de ida y vuelta a valores de fecha y hora"
ms.custom: 
ms.date: 03/30/2017
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
- round-trip date and time values
- dates [.NET Framework], round-trip values
- time zones [.NET Framework], round-trip date and time values
- time [.NET Framework], round-trip values
- formatting strings [.NET Framework], round-trip values
ms.assetid: b609b277-edc6-4c74-b03e-ea73324ecbdb
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 515a29e279cfa8fc100e0612fc19df7abc6a3b36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-round-trip-date-and-time-values"></a><span data-ttu-id="f6554-102">Cómo: Aplicar acciones de ida y vuelta a valores de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="f6554-102">How to: Round-trip Date and Time Values</span></span>
<span data-ttu-id="f6554-103">En muchas aplicaciones, un valor de fecha y hora sirve para identificar inequívocamente un único punto en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="f6554-103">In many applications, a date and time value is intended to unambiguously identify a single point in time.</span></span> <span data-ttu-id="f6554-104">Este tema muestra cómo guardar y restaurar un <xref:System.DateTime> valor, un <xref:System.DateTimeOffset> valor y un valor de fecha y hora con el tiempo de información de zona para que el valor restaurado identifique al mismo tiempo que el valor guardado.</span><span class="sxs-lookup"><span data-stu-id="f6554-104">This topic shows how to save and restore a <xref:System.DateTime> value, a <xref:System.DateTimeOffset> value, and a date and time value with time zone information so that the restored value identifies the same time as the saved value.</span></span>  
  
### <a name="to-round-trip-a-datetime-value"></a><span data-ttu-id="f6554-105">Para un valor DateTime de ida y vuelta</span><span class="sxs-lookup"><span data-stu-id="f6554-105">To round-trip a DateTime value</span></span>  
  
1.  <span data-ttu-id="f6554-106">Convertir el <xref:System.DateTime> valor en su representación de cadena mediante una llamada a la <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> método con el especificador de formato "o".</span><span class="sxs-lookup"><span data-stu-id="f6554-106">Convert the <xref:System.DateTime> value to its string representation by calling the <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> method with the "o" format specifier.</span></span>  
  
2.  <span data-ttu-id="f6554-107">Guarde la representación de cadena de la <xref:System.DateTime> valor a un archivo, o se pasa a través de un proceso, el dominio de aplicación o el límite de la máquina.</span><span class="sxs-lookup"><span data-stu-id="f6554-107">Save the string representation of the <xref:System.DateTime> value to a file, or pass it across a process, application domain, or machine boundary.</span></span>  
  
3.  <span data-ttu-id="f6554-108">Recuperar la cadena que representa el <xref:System.DateTime> valor.</span><span class="sxs-lookup"><span data-stu-id="f6554-108">Retrieve the string that represents the <xref:System.DateTime> value.</span></span>  
  
4.  <span data-ttu-id="f6554-109">Llame a la <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> método y pase <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> como el valor de la `styles` parámetro.</span><span class="sxs-lookup"><span data-stu-id="f6554-109">Call the <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> method, and pass <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> as the value of the `styles` parameter.</span></span>  
  
 <span data-ttu-id="f6554-110">En el ejemplo siguiente se muestra cómo ida y vuelta un <xref:System.DateTime> valor.</span><span class="sxs-lookup"><span data-stu-id="f6554-110">The following example illustrates how to round-trip a <xref:System.DateTime> value.</span></span>  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
 [!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]  
  
 <span data-ttu-id="f6554-111">Cuando round-tripping un <xref:System.DateTime> valor, esta técnica mantiene correctamente la hora para todas las horas locales y universales.</span><span class="sxs-lookup"><span data-stu-id="f6554-111">When round-tripping a <xref:System.DateTime> value, this technique successfully preserves the time for all local and universal times.</span></span> <span data-ttu-id="f6554-112">Por ejemplo, si una variable local <xref:System.DateTime> valor se guarda en un sistema de la zona horaria del Pacífico zona horaria estándar del Pacífico de Estados Unidos y se restaura en un sistema de la zona horaria estándar central de Estados Unidos, la fecha y hora restauradas serán dos horas posteriores a la hora original, lo que refleja la diferencia horaria entre las dos zonas.</span><span class="sxs-lookup"><span data-stu-id="f6554-112">For example, if a local <xref:System.DateTime> value is saved on a system in the U.S. Pacific Standard Time zone and is restored on a system in the U.S. Central Standard Time zone, the restored date and time will be two hours later than the original time, which reflects the time difference between the two time zones.</span></span> <span data-ttu-id="f6554-113">Pero esta técnica no es necesariamente precisa para horas no especificadas.</span><span class="sxs-lookup"><span data-stu-id="f6554-113">However, this technique is not necessarily accurate for unspecified times.</span></span> <span data-ttu-id="f6554-114">Todos los <xref:System.DateTime> valores cuya <xref:System.DateTime.Kind%2A> propiedad es <xref:System.DateTimeKind.Unspecified> se tratan como si fueran horas locales.</span><span class="sxs-lookup"><span data-stu-id="f6554-114">All <xref:System.DateTime> values whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Unspecified> are treated as if they are local times.</span></span> <span data-ttu-id="f6554-115">Si esto no es el caso, el <xref:System.DateTime> no identificará correctamente el punto correcto en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="f6554-115">If this is not the case, the <xref:System.DateTime> will not successfully identify the correct point in time.</span></span> <span data-ttu-id="f6554-116">La solución alternativa para esta limitación es acoplar estrechamente un valor de fecha y hora con su zona horaria para la operación de guardado y restauración.</span><span class="sxs-lookup"><span data-stu-id="f6554-116">The workaround for this limitation is to tightly couple a date and time value with its time zone for the save and restore operation.</span></span>  
  
### <a name="to-round-trip-a-datetimeoffset-value"></a><span data-ttu-id="f6554-117">Para un valor DateTimeOffset de ida y vuelta</span><span class="sxs-lookup"><span data-stu-id="f6554-117">To round-trip a DateTimeOffset value</span></span>  
  
1.  <span data-ttu-id="f6554-118">Convertir el <xref:System.DateTimeOffset> valor en su representación de cadena mediante una llamada a la <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> método con el especificador de formato "o".</span><span class="sxs-lookup"><span data-stu-id="f6554-118">Convert the <xref:System.DateTimeOffset> value to its string representation by calling the <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> method with the "o" format specifier.</span></span>  
  
2.  <span data-ttu-id="f6554-119">Guarde la representación de cadena de la <xref:System.DateTimeOffset> valor a un archivo, o se pasa a través de un proceso, el dominio de aplicación o el límite de la máquina.</span><span class="sxs-lookup"><span data-stu-id="f6554-119">Save the string representation of the <xref:System.DateTimeOffset> value to a file, or pass it across a process, application domain, or machine boundary.</span></span>  
  
3.  <span data-ttu-id="f6554-120">Recuperar la cadena que representa el <xref:System.DateTimeOffset> valor.</span><span class="sxs-lookup"><span data-stu-id="f6554-120">Retrieve the string that represents the <xref:System.DateTimeOffset> value.</span></span>  
  
4.  <span data-ttu-id="f6554-121">Llame a la <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> método y pase <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> como el valor de la `styles` parámetro.</span><span class="sxs-lookup"><span data-stu-id="f6554-121">Call the <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> method, and pass <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> as the value of the `styles` parameter.</span></span>  
  
 <span data-ttu-id="f6554-122">En el ejemplo siguiente se muestra cómo ida y vuelta un <xref:System.DateTimeOffset> valor.</span><span class="sxs-lookup"><span data-stu-id="f6554-122">The following example illustrates how to round-trip a <xref:System.DateTimeOffset> value.</span></span>  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
 [!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]  
  
 <span data-ttu-id="f6554-123">Esta técnica se identifica siempre de forma inequívoca un <xref:System.DateTimeOffset> valor como un único punto en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="f6554-123">This technique always unambiguously identifies a <xref:System.DateTimeOffset> value as a single point in time.</span></span> <span data-ttu-id="f6554-124">El valor puede, a continuación, puede convertir en hora Universal coordinada (UTC) mediante una llamada a la <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> método, o bien puede convertirse en la hora de una zona horaria determinada llamando a la <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> o <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="f6554-124">The value can then be converted to Coordinated Universal Time (UTC) by calling the <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> method, or it can be converted to the time in a particular time zone by calling the <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> or <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f6554-125">La limitación principal de esta técnica es esa fecha y hora operadores aritméticos, cuando se realizan en un <xref:System.DateTimeOffset> valor que representa la hora en una zona horaria determinada, no puede producir resultados precisos para esa zona horaria.</span><span class="sxs-lookup"><span data-stu-id="f6554-125">The major limitation of this technique is that date and time arithmetic, when performed on a <xref:System.DateTimeOffset> value that represents the time in a particular time zone, may not produce accurate results for that time zone.</span></span> <span data-ttu-id="f6554-126">Esto es porque cuando un <xref:System.DateTimeOffset> se crea una instancia de valor, se desasocia de su zona horaria.</span><span class="sxs-lookup"><span data-stu-id="f6554-126">This is because when a <xref:System.DateTimeOffset> value is instantiated, it is disassociated from its time zone.</span></span> <span data-ttu-id="f6554-127">Por lo tanto, ya no se pueden aplicar las reglas de ajuste de esa zona de horaria al realizar cálculos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="f6554-127">Therefore, that time zone's adjustment rules can no longer be applied when you perform date and time calculations.</span></span> <span data-ttu-id="f6554-128">Para evitar este problema, puede definir un tipo personalizado que incluya tanto el valor de fecha y hora como la zona horaria correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f6554-128">You can work around this problem by defining a custom type that includes both a date and time value and its accompanying time zone.</span></span>  
  
### <a name="to-round-trip-a-date-and-time-value-with-its-time-zone"></a><span data-ttu-id="f6554-129">Para un valor de fecha y hora con su zona horaria de ida y vuelta</span><span class="sxs-lookup"><span data-stu-id="f6554-129">To round-trip a date and time value with its time zone</span></span>  
  
1.  <span data-ttu-id="f6554-130">Defina una clase o una estructura con dos campos.</span><span class="sxs-lookup"><span data-stu-id="f6554-130">Define a class or a structure with two fields.</span></span> <span data-ttu-id="f6554-131">El primer campo sea un <xref:System.DateTime> o un <xref:System.DateTimeOffset> objeto y el segundo es un <xref:System.TimeZoneInfo> objeto.</span><span class="sxs-lookup"><span data-stu-id="f6554-131">The first field is either a <xref:System.DateTime> or a <xref:System.DateTimeOffset> object, and the second is a <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="f6554-132">En el ejemplo siguiente es una versión simple de este tipo.</span><span class="sxs-lookup"><span data-stu-id="f6554-132">The following example is a simple version of such a type.</span></span>  
  
     [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
     [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]  
  
2.  <span data-ttu-id="f6554-133">Marque la clase con la <xref:System.SerializableAttribute> atributo.</span><span class="sxs-lookup"><span data-stu-id="f6554-133">Mark the class with the <xref:System.SerializableAttribute> attribute.</span></span>  
  
3.  <span data-ttu-id="f6554-134">Serializar el objeto mediante el <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="f6554-134">Serialize the object using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> method.</span></span>  
  
4.  <span data-ttu-id="f6554-135">Restaurar el objeto utilizando el <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> método.</span><span class="sxs-lookup"><span data-stu-id="f6554-135">Restore the object using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> method.</span></span>  
  
5.  <span data-ttu-id="f6554-136">Convierta (en C#) o convertir el objeto deserializado (en Visual Basic) a un objeto del tipo adecuado.</span><span class="sxs-lookup"><span data-stu-id="f6554-136">Cast (in C#) or convert (in Visual Basic) the deserialized object to an object of the appropriate type.</span></span>  
  
 <span data-ttu-id="f6554-137">En el ejemplo siguiente se muestra cómo al envío y recepción de un objeto que almacena la información de fecha y hora y zona horaria.</span><span class="sxs-lookup"><span data-stu-id="f6554-137">The following example illustrates how to round-trip an object that stores both date and time and time zone information.</span></span>  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
 [!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]  
  
 <span data-ttu-id="f6554-138">Esta técnica debe reflejar siempre de forma inequívoca el punto correcto de tiempo ambos antes y después de se guarda y restaura, proporcionan que la implementación del objeto combinado de fecha y hora y zona horaria no permite el valor de fecha que dejen de estar sincronizados con el valor de zona horaria.</span><span class="sxs-lookup"><span data-stu-id="f6554-138">This technique should always unambiguously reflect the correct point of time both before and after it is saved and restored, provided that the implementation of the combined date and time and time zone object does not allow the date value to become out of sync with the time zone value.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f6554-139">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="f6554-139">Compiling the Code</span></span>  
 <span data-ttu-id="f6554-140">Para estos ejemplos se necesita:</span><span class="sxs-lookup"><span data-stu-id="f6554-140">These examples require:</span></span>  
  
-   <span data-ttu-id="f6554-141">Que se deben importar los siguientes espacios de nombres con C# `using` instrucciones o [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="f6554-141">That the following namespaces be imported with C# `using` statements or [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `Imports` statements:</span></span>  
  
    -   <span data-ttu-id="f6554-142"><xref:System>(Solo C#).</span><span class="sxs-lookup"><span data-stu-id="f6554-142"><xref:System> (C# only).</span></span>  
  
    -   <span data-ttu-id="f6554-143"><xref:System.Globalization?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f6554-143"><xref:System.Globalization?displayProperty=nameWithType>.</span></span>  
  
    -   <span data-ttu-id="f6554-144"><xref:System.IO?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f6554-144"><xref:System.IO?displayProperty=nameWithType>.</span></span>  
  
    -   <span data-ttu-id="f6554-145"><xref:System.Runtime.Serialization?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f6554-145"><xref:System.Runtime.Serialization?displayProperty=nameWithType>.</span></span>  
  
    -   <span data-ttu-id="f6554-146"><xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f6554-146"><xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="f6554-147">Una referencia a System.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="f6554-147">A reference to System.Core.dll.</span></span>  
  
-   <span data-ttu-id="f6554-148">Cada ejemplo de código de, excepto el `DateInTimeZone` clase, debe ser incluido en una clase o módulo de Visual Basic, ajustado en métodos y llamar desde el `Main` método.</span><span class="sxs-lookup"><span data-stu-id="f6554-148">Each code example, other than the `DateInTimeZone` class, should be included in a class or Visual Basic module, wrapped in methods, and called from the `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6554-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6554-149">See Also</span></span>  
 [<span data-ttu-id="f6554-150">Efectuar operaciones de formato</span><span class="sxs-lookup"><span data-stu-id="f6554-150">Performing Formatting Operations</span></span>](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [<span data-ttu-id="f6554-151">Elección entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="f6554-151">Choosing Between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo</span></span>](../../../docs/standard/datetime/choosing-between-datetime.md)  
 [<span data-ttu-id="f6554-152">Standard Date and Time Format Strings</span><span class="sxs-lookup"><span data-stu-id="f6554-152">Standard Date and Time Format Strings</span></span>](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)
