---
title: "C&#243;mo: Aplicar acciones de ida y vuelta a valores de fecha y hora | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "valores de fecha y hora de ida y vuelta"
  - "fechas [.NET Framework], valores de ida y vuelta"
  - "zonas horarias [.NET Framework],valores de fecha y hora de ida y vuelta"
  - "hora [.NET Framework], valores de ida y vuelta"
  - "cadenas de formato [.NET Framework], valores de ida y vuelta"
ms.assetid: b609b277-edc6-4c74-b03e-ea73324ecbdb
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Aplicar acciones de ida y vuelta a valores de fecha y hora
En muchas aplicaciones, la finalidad de un valor de fecha y hora consiste en identificar de forma inequívoca un momento único.  En este tema se muestra cómo se  guarda y se restaura un valor <xref:System.DateTime>, un valor <xref:System.DateTimeOffset> y un valor de fecha y hora con información de la zona horaria de modo que el valor restaurado identifique el mismo momento que el valor guardado.  
  
### Para aplicar un viaje de ida y vuelta \(round trip\) a un valor DateTime  
  
1.  Convierta el valor <xref:System.DateTime> en su representación de cadena; para ello, llame al método <xref:System.DateTime.ToString%28System.String%29?displayProperty=fullName> con el especificador de formato "o".  
  
2.  Guarde la representación de cadena del valor <xref:System.DateTime> en un archivo o páselo a través de un proceso, del dominio de aplicación o del límite del equipo.  
  
3.  Recupere la cadena que representa el valor <xref:System.DateTime>.  
  
4.  Llame al método <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=fullName> y pase <xref:System.Globalization.DateTimeStyles?displayProperty=fullName> como valor del parámetro `styles`.  
  
 En el siguiente ejemplo se muestra cómo se aplican viajes de ida y vuelta \(round trip\) a un valor <xref:System.DateTime>.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
 [!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]  
  
 Cuando se aplican viajes de ida y vuelta \(round trip\) a un valor <xref:System.DateTime>, esta técnica mantiene correctamente la hora en todos los horarios locales y universales.  Por ejemplo, si un valor local de <xref:System.DateTime> se guarda en un sistema de la zona horaria estándar del Pacífico de EE.UU. y se restaura en un sistema de la zona horaria estándar de EE.UU. Central, fecha y hora restaurado tendrá dos horas posteriores a la hora original, que refleja la diferencia que existe entre las dos zonas horarias.  Sin embargo, esta técnica no resulta del todo precisa para los horarios no especificados.  Todos los valores <xref:System.DateTime> cuya propiedad <xref:System.DateTime.Kind%2A> es <xref:System.DateTimeKind> se tratan como si fueran horas locales.  Si éste no es el caso, <xref:System.DateTime> no identificará correctamente el momento en el tiempo preciso.  La solución alternativa para esta limitación consiste en acoplar de forma rigurosa un valor de fecha y hora con su zona horaria al guardar y restaurar.  
  
### Para aplicar un viaje de ida y vuelta \(round trip\) a un valor DateTimeOffset  
  
1.  Convierta el valor <xref:System.DateTimeOffset> en su representación de cadena; para ello, llame al método <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=fullName> con el especificador de formato "o".  
  
2.  Guarde la representación de cadena del valor <xref:System.DateTimeOffset> en un archivo o páselo a través de un proceso, del dominio de aplicación o del límite del equipo.  
  
3.  Recupere la cadena que representa el valor <xref:System.DateTimeOffset>.  
  
4.  Llame al método <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=fullName> y pase <xref:System.Globalization.DateTimeStyles?displayProperty=fullName> como valor del parámetro `styles`.  
  
 En el siguiente ejemplo se muestra cómo se aplican viajes de ida y vuelta \(round trip\) a un valor <xref:System.DateTimeOffset>.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
 [!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]  
  
 Esta técnica siempre identifica de forma inequívoca un valor <xref:System.DateTimeOffset> como un momento único.  El valor se puede convertir a continuación a la hora universal coordinada \(UTC\) llamando al método <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=fullName> o se puede convertir a la hora de una determinada zona horaria llamando al método <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=fullName> o <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=fullName>.  La limitación principal de esta técnica es que las operaciones aritméticas de fecha y hora, cuando se realizan sobre un valor <xref:System.DateTimeOffset> que representa la hora en una determinada zona horaria, no pueden generar resultados precisos para esa zona horaria.  Esto se debe a que cuando se crea una instancia de un valor <xref:System.DateTimeOffset>, se desasocia de su zona horaria.  Por tanto, estas reglas de ajuste ya no se pueden aplicar cuando se realizan cálculos de fecha y hora.  Para evitar este problema, defina un tipo personalizado que incluya un valor de fecha y hora y su zona horaria correspondiente.  
  
### Para aplicar viajes de ida y vuelta \(round trip\) a un valor de fecha y hora con su zona horaria  
  
1.  Defina una clase o una estructura con dos campos.  El primer campo es un objeto <xref:System.DateTime> o <xref:System.DateTimeOffset> y el segundo es un objeto <xref:System.TimeZoneInfo>.  En el ejemplo siguiente se muestra una versión sencilla de un tipo de estas características.  
  
     [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
     [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]  
  
2.  Marque la clase con el atributo <xref:System.SerializableAttribute>.  
  
3.  Serialice el objeto con el método <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=fullName>.  
  
4.  Restaure el objeto con el método <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A>.  
  
5.  Convierta el objeto deserializado en un objeto del tipo adecuado.  
  
 En el ejemplo siguiente se muestra cómo se aplican viajes de ida y vuelta \(round trip\) a un objeto que almacena información de fecha y hora e información de la zona horaria.  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
 [!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]  
  
 Esta técnica siempre debería reflejar de forma inequívoca el momento preciso tanto antes como después de que se haya guardado y restaurado, siempre que la implementación del objeto combinado de fecha y hora y zona horaria no permita que el valor de fecha y hora pierda su sincronía con el valor de zona horaria.  
  
## Compilar el código  
 Estos ejemplos necesitan:  
  
-   Que los espacios de nombres siguientes se importen con instrucciones `using` en C\# o instrucciones `Imports` en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]:  
  
    -   <xref:System> \(sólo en C\#\).  
  
    -   <xref:System.Globalization?displayProperty=fullName>.  
  
    -   <xref:System.IO?displayProperty=fullName>.  
  
    -   <xref:System.Runtime.Serialization?displayProperty=fullName>.  
  
    -   <xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=fullName>.  
  
-   Una referencia a System.Core.dll.  
  
-   Todos los ejemplos de código, excepto la clase `DateInTimeZone`, deberían estar incluidos en una clase o módulo de Visual Basic, ajustarse a los métodos y llamarse desde el método `Main`.  
  
## Vea también  
 [Efectuar operaciones de formato](../../../docs/standard/base-types/performing-formatting-operations.md)   
 [Elegir entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)   
 [Cadenas con formato de fecha y hora estándar](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)