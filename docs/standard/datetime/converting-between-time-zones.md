---
title: Convertir horas entre zonas horarias
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- times [.NET Framework], converting
- time zones [.NET Framework], conversions
- UTC times, converting
- converting times
- local time conversions
ms.assetid: a51e1a3b-c983-4320-b31a-1f9fa3cf824a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64b971e71019359cebc1493a410e748a1fd7b7cb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43734986"
---
# <a name="converting-times-between-time-zones"></a>Convertir horas entre zonas horarias

Para cualquier aplicación que trabaje con fechas y horas se está volviendo cada vez más importante controlar las diferencias entre zonas horarias. Una aplicación ya no puede suponer que todas las horas se pueden expresar en la hora local, que es el tiempo disponible en el <xref:System.DateTime> estructura. Por ejemplo, una página web que muestre la hora actual en la zona oriental de los Estados Unidos no tendrá credibilidad para un cliente de Asia oriental. Este tema explica cómo convertir las horas de una zona horaria a otra, así como cómo convertir <xref:System.DateTimeOffset> valores que tienen limitada la zona horaria.

## <a name="converting-to-coordinated-universal-time"></a>Conversión a la hora universal coordinada

La hora universal coordinada (UTC) es un estándar de hora atómica de alta precisión. Las zonas horarias del mundo se expresan como diferencias positivas o negativas con respecto a la hora UTC. Por lo tanto, UTC proporciona un tipo de hora libre o neutra de zona horaria. Se recomienda el uso de la hora UTC cuando importa la portabilidad de la fecha y la hora entre equipos. (Para obtener detalles y otras prácticas recomendadas con fechas y horas, vea [mediante DateTime en .NET Framework de recomendaciones de codificación](https://msdn.microsoft.com/library/ms973825.aspx).) La conversión de zonas horarias individuales a UTC facilita las comparaciones de hora.

> [!NOTE]
> También se puede serializar un <xref:System.DateTimeOffset> estructura para representar de forma inequívoca un único punto en el tiempo. Dado que <xref:System.DateTimeOffset> objetos almacenan un valor de fecha y hora junto con su desplazamiento a la hora UTC, siempre representan un punto concreto en el tiempo en relación a la hora UTC.

La manera más fácil de convertir una hora en UTC es llamar a la `static` (`Shared` en Visual Basic) <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> método. La conversión exacta realizada por el método depende del valor de la `dateTime` del parámetro <xref:System.DateTime.Kind%2A> propiedad, como se muestra en la tabla siguiente.

| `DateTime.Kind`            | Conversión                                                                     |
| -------------------------- | ------------------------------------------------------------------------------ |
| `DateTimeKind.Local`       | Convierte la hora local a UTC.                                                    |
| `DateTimeKind.Unspecified` | Supone que el parámetro `dateTime` es la hora local y la convierte a UTC. |
| `DateTimeKind.Utc`         | Devuelve el parámetro `dateTime` sin modificar.                                    |

El código siguiente convierte la hora local actual a UTC y muestra el resultado en la consola.

[!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
[!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]

> [!NOTE]
> El <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> método no produce necesariamente resultados idénticos a los <xref:System.TimeZone.ToUniversalTime%2A?displayProperty=nameWithType> y <xref:System.DateTime.ToUniversalTime%2A?displayProperty=nameWithType> métodos. Si local del sistema host zona horaria incluye varias reglas de ajuste, <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> se aplica la regla correspondiente a una determinada fecha y hora. Los otros dos métodos siempre aplican la última regla de ajuste.

Si el valor de fecha y hora no representa la hora local o UTC, la <xref:System.DateTime.ToUniversalTime%2A> método probablemente devolverá un resultado erróneo. Sin embargo, puede usar el <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> método para convertir la fecha y hora de una zona horaria especificada. (Para obtener más información sobre cómo recuperar un <xref:System.TimeZoneInfo> objeto que representa la zona horaria de destino, vea [buscar las zonas horarias definidas en un sistema local](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md).) El siguiente código utiliza el <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> método para convertir la hora estándar del este a UTC.

[!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
[!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]

Tenga en cuenta que este método produce una <xref:System.ArgumentException> si el <xref:System.DateTime> del objeto <xref:System.DateTime.Kind%2A> propiedad y la zona horaria no coinciden. Se produce un error de coincidencia si el <xref:System.DateTime.Kind%2A> propiedad es <xref:System.DateTimeKind.Local?displayProperty=nameWithType> pero el <xref:System.TimeZoneInfo> objeto no representa la zona horaria local, o si el <xref:System.DateTime.Kind%2A> propiedad es <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> pero la <xref:System.TimeZoneInfo> no es igual que objeto <xref:System.TimeZoneInfo.Utc?displayProperty=nameWithType>.

Todos estos métodos toman <xref:System.DateTime> valores como parámetros y devuelven un <xref:System.DateTime> valor. Para <xref:System.DateTimeOffset> valores, el <xref:System.DateTimeOffset> estructura tiene un <xref:System.DateTimeOffset.ToUniversalTime%2A> método que convierte la fecha y hora de la instancia actual en hora UTC de instancia. El ejemplo siguiente se llama el <xref:System.DateTimeOffset.ToUniversalTime%2A> método para convertir una hora local y otras horas en hora Universal coordinada (UTC).

[!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
[!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]

## <a name="converting-utc-to-a-designated-time-zone"></a>Conversión de una hora UTC a una zona horaria designada

Para convertir la hora UTC a la hora local, consulte la sección "conversión de hora UTC a Local" a continuación. Para convertir la hora UTC a la hora de cualquier zona horaria que designe, llame a la <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> método. El método toma dos parámetros:

* La hora UTC que se va a convertir. Esto debe ser un <xref:System.DateTime> cuyo valor <xref:System.DateTime.Kind%2A> propiedad está establecida en `Unspecified` o `Utc`.

* La zona horaria a la que se va a convertir la hora UTC.

El código siguiente convierte la hora UTC a la hora estándar central.

[!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
[!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]

## <a name="converting-utc-to-local-time"></a>Conversión de una hora UTC a la hora local

Para convertir la hora UTC a la hora local, llame a la <xref:System.DateTime.ToLocalTime%2A> método de la <xref:System.DateTime> objeto cuya hora que se va a convertir. El comportamiento del método exacto depende del valor del objeto <xref:System.DateTime.Kind%2A> propiedad, como se muestra en la tabla siguiente.

| `DateTime.Kind`            | Conversión                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------- |
| `DateTimeKind.Local`       | Devuelve el <xref:System.DateTime> valor sin modificar.                                      |
| `DateTimeKind.Unspecified` | Se da por supuesto que el <xref:System.DateTime> valor es la hora UTC y convierte la hora UTC a la hora local. |
| `DateTimeKind.Utc`         | Convierte el <xref:System.DateTime> valor a la hora local.                                 |

> [!NOTE]
> El <xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType> método se comporta igual que el `DateTime.ToLocalTime` método. Toma un único parámetro, que es el valor de fecha y hora para convertir.

También puede convertir la hora de cualquier zona horaria designada a la hora local mediante el `static` (`Shared` en Visual Basic) <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType> método. Esta técnica se describe en la sección siguiente.

## <a name="converting-between-any-two-time-zones"></a>Conversión entre dos zonas horarias cualquiera

Puede convertir entre dos zonas horarias mediante cualquiera de las dos siguientes `static` (`Shared` en Visual Basic) los métodos de la <xref:System.TimeZoneInfo> clase:

* <xref:System.TimeZoneInfo.ConvertTime%2A>

  Parámetros de este método son el valor de fecha y hora en que se convierten un `TimeZoneInfo` objeto que representa la zona horaria del valor de fecha y hora, y un `TimeZoneInfo` objeto que representa la zona horaria para convertir el valor de fecha y hora.

* <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>

  Parámetros de este método son la fecha y valor de tiempo para convertir el identificador de la fecha y zona horaria del valor de tiempo y el identificador de la zona horaria para convertir el valor de fecha y hora.

Ambos métodos requieren que el <xref:System.DateTime.Kind%2A> propiedad del valor de fecha y hora para convertir y <xref:System.TimeZoneInfo> identificador de objeto o la zona horaria que representa su zona horaria se corresponden entre sí. De lo contrario, se produce una excepción <xref:System.ArgumentException>. Por ejemplo, si la `Kind` es propiedad del valor de fecha y hora `DateTimeKind.Local`, se produce una excepción si el `TimeZoneInfo` no es igual al objeto pasado como parámetro al método `TimeZoneInfo.Local`. También se produce una excepción si no es igual que el identificador pasado como parámetro al método `TimeZoneInfo.Local.Id`.

En el ejemplo siguiente se usa el <xref:System.TimeZoneInfo.ConvertTime%2A> método para convertir la hora estándar de Hawai en hora local.

[!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
[!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]

## <a name="converting-datetimeoffset-values"></a>Conversión de valores DateTimeOffset

Los valores de fecha y hora representados por <xref:System.DateTimeOffset> objetos no son totalmente la zona horaria porque el objeto se desasocia de su zona horaria en el momento, tenga en cuenta se crea una instancia. Pero en muchos casos una aplicación simplemente necesita convertir una fecha y hora basada en dos diferencias horarias diferentes con respecto a la hora UTC en lugar de en la hora en zonas horarias determinadas. Para llevar a cabo esta conversión, puede llamar a la instancia actual <xref:System.DateTimeOffset.ToOffset%2A> método. El parámetro del método solo es el desplazamiento de la nueva fecha y el valor de tiempo que el método va a devolver.

Por ejemplo, si la fecha y hora de una solicitud de usuario de una página web se conoce y se serializa como una cadena con el formato MM/dd/aaaa hh: mm:ss zzzz, el siguiente método `ReturnTimeOnServer` convierte este valor de fecha y hora en la fecha y hora del servidor web.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)] 

Si se pasa al método la cadena "9/1/2007 5:32:07 -05:00", que representa la fecha y hora de una zona horaria cinco horas anterior a UTC, devuelve 9/1/2007 3:32:07 AM -07:00 para un servidor ubicado en los Estados Unidos. Zona horaria estándar del Pacífico.

El <xref:System.TimeZoneInfo> clase también incluye una sobrecarga de la <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> método que realiza las conversiones de zona horaria con <xref:System.DateTimeOffset.ToOffset(System.TimeSpan)> valores. Los parámetros del método son un <xref:System.DateTimeOffset> valor y una referencia a la zona horaria a la que el tiempo que se va a convertir. Devuelve la llamada al método un <xref:System.DateTimeOffset> valor. Por ejemplo, el `ReturnTimeOnServer` método en el ejemplo anterior se podría reescribir como sigue para llamar a la <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29> método.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]

## <a name="see-also"></a>Vea también

<xref:System.TimeZoneInfo>
[Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
[buscar las zonas horarias definidas en un sistema local](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
