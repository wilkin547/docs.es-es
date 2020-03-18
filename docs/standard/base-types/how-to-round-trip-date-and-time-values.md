---
title: Procedimiento para valores de fecha y hora de ida y vuelta
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 2e3a58ffe8332e0afec62461f6897d673e1da09f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73132003"
---
# <a name="how-to-round-trip-date-and-time-values"></a>Procedimiento para valores de fecha y hora de ida y vuelta

En muchas aplicaciones, un valor de fecha y hora sirve para identificar inequívocamente un único punto en el tiempo. Este tema muestra cómo guardar y restaurar un valor <xref:System.DateTime>, un valor <xref:System.DateTimeOffset> y un valor de fecha y hora con información sobre la zona horaria, de manera que el valor restaurado identifique la misma hora que el valor guardado.

### <a name="to-round-trip-a-datetime-value"></a>Para un valor DateTime de ida y vuelta

1. Convierta el valor <xref:System.DateTime> en su representación de cadena mediante una llamada al método <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> con el especificador de formato "o".

2. Guarde la representación de cadena del valor <xref:System.DateTime> en un archivo o pásela a través de un límite de proceso, dominio de aplicación o máquina.

3. Recupere la cadena que representa el valor <xref:System.DateTime>.

4. Llame al método <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> y pase <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> como el valor del parámetro `styles`.

En el ejemplo siguiente se muestra cómo usar un valor <xref:System.DateTime> de ida y vuelta.

[!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
[!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]

Cuando se usa un valor <xref:System.DateTime> de ida y vuelta, esta técnica mantiene correctamente la hora para todas las horas locales y universales. Por ejemplo, si un valor local <xref:System.DateTime> se guarda en un sistema de la zona horaria estándar del Pacífico de Estados Unidos y se restaura en un sistema de la zona horaria estándar central de Estados Unidos, la fecha y hora restauradas serán dos horas posteriores a la hora original, lo que refleja la diferencia horaria entre las dos zonas. Pero esta técnica no es necesariamente precisa para horas no especificadas. Todos los valores <xref:System.DateTime> cuya propiedad <xref:System.DateTime.Kind%2A> es <xref:System.DateTimeKind.Unspecified> se tratan como si fueran horas locales. Si no es el caso, <xref:System.DateTime> no identificará correctamente el punto en el tiempo. La solución alternativa para esta limitación es acoplar estrechamente un valor de fecha y hora con su zona horaria para la operación de guardado y restauración.

### <a name="to-round-trip-a-datetimeoffset-value"></a>Para un valor DateTimeOffset de ida y vuelta

1. Convierta el valor <xref:System.DateTimeOffset> en su representación de cadena mediante una llamada al método <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> con el especificador de formato "o".

2. Guarde la representación de cadena del valor <xref:System.DateTimeOffset> en un archivo o pásela a través de un límite de proceso, dominio de aplicación o máquina.

3. Recupere la cadena que representa el valor <xref:System.DateTimeOffset>.

4. Llame al método <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> y pase <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> como el valor del parámetro `styles`.

En el ejemplo siguiente se muestra cómo usar un valor <xref:System.DateTimeOffset> de ida y vuelta.

[!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
[!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]

Esta técnica identifica siempre de forma inequívoca un valor <xref:System.DateTimeOffset> como un único punto en el tiempo. El valor puede convertirse entonces en la hora universal coordinada (UTC) al llamar al método <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType>, o bien puede convertirse en la hora de una zona horaria concreta al llamar a los métodos <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> o <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>. La limitación principal de esta técnica está en que las operaciones aritméticas de fecha y hora, cuando se realizan en un valor <xref:System.DateTimeOffset> que representa la hora en una zona horaria determinada, podrían no generar resultados precisos para esa zona horaria. Esto se debe a que, cuando se crea una instancia de un valor <xref:System.DateTimeOffset>, se desasocia de su zona horaria. Por lo tanto, ya no se pueden aplicar las reglas de ajuste de esa zona de horaria al realizar cálculos de fecha y hora. Para evitar este problema, puede definir un tipo personalizado que incluya tanto el valor de fecha y hora como la zona horaria correspondiente.

### <a name="to-round-trip-a-date-and-time-value-with-its-time-zone"></a>Para un valor de fecha y hora de ida y vuelta con su zona horaria

1. Defina una clase o una estructura con dos campos. El primer campo es un objeto <xref:System.DateTime> o <xref:System.DateTimeOffset> y el segundo es un objeto <xref:System.TimeZoneInfo>. El ejemplo siguiente es una versión sencilla de ese tipo.

    [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
    [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]

2. Marque la clase con el atributo <xref:System.SerializableAttribute>.

3. Serialice el objeto con el método <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>.

4. Restaure el objeto con el método <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A>.

5. Convierta (en C# o en Visual Basic) el objeto deserializado en un objeto del tipo adecuado.

En el ejemplo siguiente se muestra cómo realizar un recorrido de ida y vuelta de un objeto que almacena la información de fecha y hora y de zona horaria.

[!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
[!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]

Esta técnica debe reflejar siempre de forma inequívoca el punto correcto de tiempo antes y después de guardar y restaurar, siempre que la implementación del objeto combinado de fecha y hora y de zona horaria no permita que el valor de fecha quede fuera de la sincronización con el valor de zona horaria.

## <a name="compiling-the-code"></a>Compilar el código

Para estos ejemplos se necesita:

- Que los espacios de nombres siguientes se importen con instrucciones `using` de C# o con instrucciones `Imports` de Visual Basic:

  - <xref:System> (solo C#).

  - <xref:System.Globalization?displayProperty=nameWithType>.

  - <xref:System.IO?displayProperty=nameWithType>.

  - <xref:System.Runtime.Serialization?displayProperty=nameWithType>.

  - <xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.

- Cada ejemplo de código, excepto la clase `DateInTimeZone`, debe incluirse en una clase o en módulo de Visual Basic, ajustado en métodos y con una llamada al método `Main`.

## <a name="see-also"></a>Vea también

- [Efectuar operaciones de formato](../../../docs/standard/base-types/performing-formatting-operations.md)
- [Elección entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)
- [Cadenas con formato de fecha y hora estándar](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)
