---
title: "Convertir horas entre zonas horarias | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "convertir horas"
  - "conversiones de hora local"
  - "zonas horarias [.NET Framework], conversiones"
  - "horas [.NET Framework], convertir"
  - "horas UTC, convertir"
ms.assetid: a51e1a3b-c983-4320-b31a-1f9fa3cf824a
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Convertir horas entre zonas horarias
Cada vez es más importante que las aplicaciones que trabajan con fechas y horas controlen las diferencias entre zonas horarias.  Una aplicación ya no puede suponer que todas las horas se pueden expresar en la hora local, que es la hora disponible en la estructura <xref:System.DateTime>.  Por ejemplo, una página web que muestra la hora actual en la zona oriental de Estados Unidos no tendrá credibilidad para un cliente de Asia oriental.  En este tema se explica cómo convertir las horas de una zona horaria a otra, y cómo convertir los valores de <xref:System.DateTimeOffset> que tienen un conocimiento limitado de la zona horaria.  
  
## Convertir a hora universal coordinada  
 La hora universal coordinada \(UTC\) es una norma de hora atómica de gran precisión.  Las zonas horarias del mundo se expresan como diferencias positivas o negativas respecto a la hora UTC.  Así, la hora UTC proporciona una hora neutra o independiente de la zona horaria.  Se recomienda el uso de la hora UTC cuando sea importante la portabilidad de fecha y hora entre equipos. \(Para obtener información detallada y otros procedimientos recomendados con las fechas y horas, vea [Procedimientos recomendados Utilizar DateTime de codificación en .NET Framework](http://go.microsoft.com/fwlink/?LinkId=92342).\) La conversión de zonas horarias individuales a horas UTC facilita la comparación de horas.  
  
> [!NOTE]
>  También puede serializar una estructura <xref:System.DateTimeOffset> para representar inequívocamente un único punto en el tiempo.  Debido a que los objetos <xref:System.DateTimeOffset> almacenan un valor de fecha y hora junto con su diferencia respecto a la hora UTC, siempre representan un punto en el tiempo determinado en relación con la hora UTC.  
  
 El modo más sencillo de convertir una hora en la hora UTC es llamar al método `static` \(`Shared` en Visual Basic\) <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=fullName>.  La conversión exacta realizada por el método depende del valor de la propiedad <xref:System.DateTime.Kind%2A> del parámetro `dateTime`, como se muestra en la siguiente tabla.  
  
|Propiedad DateTime.Kind|Conversión|  
|-----------------------------|----------------|  
|<xref:System.DateTimeKind?displayProperty=fullName>|Convierte la hora local en hora UTC.|  
|<xref:System.DateTimeKind?displayProperty=fullName>|Supone que el parámetro `dateTime` es la hora local y la convierte en hora UTC.|  
|<xref:System.DateTimeKind?displayProperty=fullName>|Devuelve el parámetro `dateTime` sin modificar.|  
  
 El código siguiente convierte la hora local actual en hora UTC y muestra el resultado en la consola.  
  
 [!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
 [!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]  
  
> [!NOTE]
>  El método <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=fullName> no genera necesariamente los mismos resultados que los métodos <xref:System.TimeZone.ToUniversalTime%2A?displayProperty=fullName> y <xref:System.DateTime.ToUniversalTime%2A?displayProperty=fullName>.  Si la zona horaria local del sistema host incluye varias reglas de ajuste, <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=fullName> aplica la regla apropiada a un valor de fecha y hora concreto.  Los otros dos métodos siempre aplican la última regla de ajuste.  
  
 Si el valor de fecha y hora no representa una hora local ni una hora UTC, el método <xref:System.DateTime.ToUniversalTime%2A> devolverá probablemente un resultado erróneo.  Sin embargo, puede utilizar el método <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=fullName> para convertir el valor de fecha y hora de una zona horaria especificada. \(Para obtener información detallada sobre cómo recuperar un objeto <xref:System.TimeZoneInfo> que representa la zona horaria de destino, vea [Buscar las zonas horarias definidas en un sistema local](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)\). El código siguiente utiliza el método <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=fullName> para convertir la Hora estándar del Este en hora UTC.  
  
 [!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
 [!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]  
  
 Observe que este método produce una excepción <xref:System.ArgumentException> si la propiedad <xref:System.DateTime.Kind%2A> del objeto <xref:System.DateTime> y la zona horaria no coinciden.  Se produce un error de coincidencia si la propiedad <xref:System.DateTime.Kind%2A> es <xref:System.DateTimeKind?displayProperty=fullName> pero el objeto <xref:System.TimeZoneInfo> no representa la zona horaria local, o si la propiedad <xref:System.DateTime.Kind%2A> es <xref:System.DateTimeKind?displayProperty=fullName> pero el objeto <xref:System.TimeZoneInfo> no es igual a <xref:System.DateTimeKind?displayProperty=fullName>.  
  
 Todos estos métodos toman valores de <xref:System.DateTime> como parámetros y devuelven un valor de <xref:System.DateTime>.  Para los valores de <xref:System.DateTimeOffset>, la estructura <xref:System.DateTimeOffset> tiene un método de instancia <xref:System.DateTimeOffset.ToUniversalTime%2A> que convierte el valor de fecha y hora de la instancia actual a horario UTC.  En el ejemplo siguiente se llama al método <xref:System.DateTimeOffset.ToUniversalTime%2A> para convertir una hora local y otras horas a hora universal coordinada \(UTC\).  
  
 [!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
 [!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]  
  
## Convertir una hora UTC a la zona horaria designada  
 Para convertir una hora UTC en hora local, vea la sección "Convertir una hora UTC en hora local" que sigue a continuación.  Para convertir una hora UTC en la hora correspondiente a cualquier zona horaria designada, llame al método <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>.  El método toma dos parámetros:  
  
-   Hora UTC que se va a convertir.  Debe ser un valor <xref:System.DateTime> cuya propiedad <xref:System.DateTime.Kind%2A> esté establecida en <xref:System.DateTimeKind?displayProperty=fullName> o <xref:System.DateTimeKind?displayProperty=fullName>.  
  
-   Zona horaria a la que se va a convertir la hora UTC.  
  
 El código siguiente convierte una hora UTC en Hora estándar del Centro.  
  
 [!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
 [!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]  
  
## Convertir una hora UTC en hora local  
 Para convertir una hora UTC en hora local, llame al método <xref:System.DateTime.ToLocalTime%2A> del objeto <xref:System.DateTime> cuya hora desea convertir.  El comportamiento exacto del método depende del valor de la propiedad <xref:System.DateTime.Kind%2A> del objeto, como muestra la tabla siguiente.  
  
|Propiedad `DateTime.Kind`|Conversión|  
|-------------------------------|----------------|  
|`DateTimeKind.Local`|Devuelve el valor de <xref:System.DateTime> sin modificar.|  
|`DateTimeKind.Unspecified`|Supone que el valor de <xref:System.DateTime> es la hora UTC y la convierte en hora local.|  
|`DateTimeKind.Utc`|Convierte el valor de <xref:System.DateTime> en hora local.|  
  
 **Nota** El método <xref:System.TimeZone.ToLocalTime%2A?displayProperty=fullName> se comporta de forma idéntica al método `DateTime.ToLocalTime`.  Toma un único parámetro, que es el valor de fecha y hora que se va a convertir.  
  
 También puede convertir la hora de cualquier zona horaria designada en hora local utilizando el método <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=fullName> `static` \(`Shared` en Visual Basic\).  Esta técnica se describe en la sección siguiente.  
  
## Convertir entre dos zonas horarias  
 Puede realizar la conversión entre dos zonas horarias mediante uno de los dos métodos `static` \(`Shared` en Visual Basic\) siguientes de la clase <xref:System.TimeZoneInfo>:  
  
-   <xref:System.TimeZoneInfo.ConvertTime%2A>  
  
     Los parámetros de este método son el valor de fecha y hora que se va a convertir, un objeto `TimeZoneInfo` que representa la zona horaria del valor de fecha y hora, y un objeto `TimeZoneInfo` que representa la zona horaria a la que se va a convertir el valor de fecha y hora.  
  
-   <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>  
  
     Los parámetros de este método son el valor de fecha y hora que se va a convertir, el identificador de la zona horaria del valor de fecha y hora, y el identificador de la zona horaria a la que se va a convertir el valor de fecha y hora.  
  
 Ambos métodos requieren que la propiedad <xref:System.DateTime.Kind%2A> del valor de fecha y hora que se va a convertir y el objeto <xref:System.TimeZoneInfo> o el identificador que representa la zona horaria se correspondan entre sí.  De lo contrario, se produce una excepción <xref:System.ArgumentException>.  Por ejemplo, si la propiedad `Kind` del valor de fecha y hora es `DateTimeKind.Local`, se produce una excepción si el objeto `TimeZoneInfo` pasado como parámetro al método no es igual a `TimeZoneInfo.Local`.  También se produce una excepción si el identificador pasado como parámetro al método no es igual a `TimeZoneInfo.Local.Id`.  
  
 En el ejemplo siguiente se utiliza el método <xref:System.TimeZoneInfo.ConvertTime%2A> para convertir la Hora estándar de Hawai en hora local.  
  
 [!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
 [!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]  
  
## Convertir valores de DateTimeOffset  
 Los valores de fecha y hora representados por objetos <xref:System.DateTimeOffset> no tienen totalmente en cuenta la zona horaria porque el objeto no está asociado a su zona horaria en el momento de crearse la instancia.  Sin embargo, en muchos casos una aplicación solo necesita convertir un valor de fecha y hora en función de dos diferencias distintas respecto a la hora UTC, en lugar de la hora de las zonas horarias concretas.  Para realizar esta conversión, puede llamar al método <xref:System.DateTimeOffset.ToOffset%2A> de la instancia actual.  El único parámetro del método es la diferencia del nuevo valor de fecha y hora que el método va a devolver.  
  
 Por ejemplo, si se conoce el valor de fecha y hora en que un usuario solicita una página web y se serializa como una cadena con el formato MM\/dd\/aaaa hh:mm:ss zzzz, el método `ReturnTimeOnServer` siguiente convierte este valor de fecha y hora en el valor de fecha y hora del servidor web.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
 [!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)]  
  
 Si el método se pasa la cadena “9\/1\/2007 5:32: 07 \-05:00”, que representa la fecha y hora de una zona horaria cinco horas de anterior a la hora UTC, devuelve 9\/1\/2007 3:32: 07 \-07:00 De la para un servidor ubicado en la zona horaria estándar del Pacífico de EE.UU.  
  
 La clase <xref:System.TimeZoneInfo> también incluye una sobrecarga del método <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=fullName> que realiza conversiones de zona horaria con valores <xref:System.DateTimeOffset>.  Los parámetros del método son un valor de <xref:System.DateTimeOffset> y una referencia a la zona horaria a la que se va a convertir la hora.  La llamada al método devuelve un valor de <xref:System.DateTimeOffset>.  Por ejemplo, el método `ReturnTimeOnServer` del ejemplo anterior se puede volver a escribir de la siguiente manera para llamar al método <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29>.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
 [!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]  
  
## Vea también  
 <xref:System.TimeZoneInfo>   
 [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)   
 [Buscar las zonas horarias definidas en un sistema local](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)