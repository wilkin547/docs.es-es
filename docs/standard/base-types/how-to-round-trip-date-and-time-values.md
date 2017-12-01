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
# <a name="how-to-round-trip-date-and-time-values"></a>Cómo: Aplicar acciones de ida y vuelta a valores de fecha y hora
En muchas aplicaciones, un valor de fecha y hora sirve para identificar inequívocamente un único punto en el tiempo. Este tema muestra cómo guardar y restaurar un <xref:System.DateTime> valor, un <xref:System.DateTimeOffset> valor y un valor de fecha y hora con el tiempo de información de zona para que el valor restaurado identifique al mismo tiempo que el valor guardado.  
  
### <a name="to-round-trip-a-datetime-value"></a>Para un valor DateTime de ida y vuelta  
  
1.  Convertir el <xref:System.DateTime> valor en su representación de cadena mediante una llamada a la <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> método con el especificador de formato "o".  
  
2.  Guarde la representación de cadena de la <xref:System.DateTime> valor a un archivo, o se pasa a través de un proceso, el dominio de aplicación o el límite de la máquina.  
  
3.  Recuperar la cadena que representa el <xref:System.DateTime> valor.  
  
4.  Llame a la <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> método y pase <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> como el valor de la `styles` parámetro.  
  
 En el ejemplo siguiente se muestra cómo ida y vuelta un <xref:System.DateTime> valor.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
 [!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]  
  
 Cuando round-tripping un <xref:System.DateTime> valor, esta técnica mantiene correctamente la hora para todas las horas locales y universales. Por ejemplo, si una variable local <xref:System.DateTime> valor se guarda en un sistema de la zona horaria del Pacífico zona horaria estándar del Pacífico de Estados Unidos y se restaura en un sistema de la zona horaria estándar central de Estados Unidos, la fecha y hora restauradas serán dos horas posteriores a la hora original, lo que refleja la diferencia horaria entre las dos zonas. Pero esta técnica no es necesariamente precisa para horas no especificadas. Todos los <xref:System.DateTime> valores cuya <xref:System.DateTime.Kind%2A> propiedad es <xref:System.DateTimeKind.Unspecified> se tratan como si fueran horas locales. Si esto no es el caso, el <xref:System.DateTime> no identificará correctamente el punto correcto en el tiempo. La solución alternativa para esta limitación es acoplar estrechamente un valor de fecha y hora con su zona horaria para la operación de guardado y restauración.  
  
### <a name="to-round-trip-a-datetimeoffset-value"></a>Para un valor DateTimeOffset de ida y vuelta  
  
1.  Convertir el <xref:System.DateTimeOffset> valor en su representación de cadena mediante una llamada a la <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> método con el especificador de formato "o".  
  
2.  Guarde la representación de cadena de la <xref:System.DateTimeOffset> valor a un archivo, o se pasa a través de un proceso, el dominio de aplicación o el límite de la máquina.  
  
3.  Recuperar la cadena que representa el <xref:System.DateTimeOffset> valor.  
  
4.  Llame a la <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> método y pase <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> como el valor de la `styles` parámetro.  
  
 En el ejemplo siguiente se muestra cómo ida y vuelta un <xref:System.DateTimeOffset> valor.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
 [!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]  
  
 Esta técnica se identifica siempre de forma inequívoca un <xref:System.DateTimeOffset> valor como un único punto en el tiempo. El valor puede, a continuación, puede convertir en hora Universal coordinada (UTC) mediante una llamada a la <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> método, o bien puede convertirse en la hora de una zona horaria determinada llamando a la <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> o <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> método. La limitación principal de esta técnica es esa fecha y hora operadores aritméticos, cuando se realizan en un <xref:System.DateTimeOffset> valor que representa la hora en una zona horaria determinada, no puede producir resultados precisos para esa zona horaria. Esto es porque cuando un <xref:System.DateTimeOffset> se crea una instancia de valor, se desasocia de su zona horaria. Por lo tanto, ya no se pueden aplicar las reglas de ajuste de esa zona de horaria al realizar cálculos de fecha y hora. Para evitar este problema, puede definir un tipo personalizado que incluya tanto el valor de fecha y hora como la zona horaria correspondiente.  
  
### <a name="to-round-trip-a-date-and-time-value-with-its-time-zone"></a>Para un valor de fecha y hora con su zona horaria de ida y vuelta  
  
1.  Defina una clase o una estructura con dos campos. El primer campo sea un <xref:System.DateTime> o un <xref:System.DateTimeOffset> objeto y el segundo es un <xref:System.TimeZoneInfo> objeto. En el ejemplo siguiente es una versión simple de este tipo.  
  
     [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
     [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]  
  
2.  Marque la clase con la <xref:System.SerializableAttribute> atributo.  
  
3.  Serializar el objeto mediante el <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> método.  
  
4.  Restaurar el objeto utilizando el <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> método.  
  
5.  Convierta (en C#) o convertir el objeto deserializado (en Visual Basic) a un objeto del tipo adecuado.  
  
 En el ejemplo siguiente se muestra cómo al envío y recepción de un objeto que almacena la información de fecha y hora y zona horaria.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
 [!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]  
  
 Esta técnica debe reflejar siempre de forma inequívoca el punto correcto de tiempo ambos antes y después de se guarda y restaura, proporcionan que la implementación del objeto combinado de fecha y hora y zona horaria no permite el valor de fecha que dejen de estar sincronizados con el valor de zona horaria.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para estos ejemplos se necesita:  
  
-   Que se deben importar los siguientes espacios de nombres con C# `using` instrucciones o [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `Imports` instrucciones:  
  
    -   <xref:System>(Solo C#).  
  
    -   <xref:System.Globalization?displayProperty=nameWithType>.  
  
    -   <xref:System.IO?displayProperty=nameWithType>.  
  
    -   <xref:System.Runtime.Serialization?displayProperty=nameWithType>.  
  
    -   <xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.  
  
-   Una referencia a System.Core.dll.  
  
-   Cada ejemplo de código de, excepto el `DateInTimeZone` clase, debe ser incluido en una clase o módulo de Visual Basic, ajustado en métodos y llamar desde el `Main` método.  
  
## <a name="see-also"></a>Vea también  
 [Efectuar operaciones de formato](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [Elección entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)  
 [Standard Date and Time Format Strings](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)
