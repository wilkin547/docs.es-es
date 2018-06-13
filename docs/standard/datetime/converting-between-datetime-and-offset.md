---
title: Conversión entre DateTime y DateTimeOffset
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DateTime structure, converting
- time zones [.NET Framework], conversions
- UTC times, converting
- DateTimeOffset structure, converting
- converting DateTimeOffset and DateTime values
- dates [.NET Framework], converting
- converting times
- Date data type, converting
- local time conversions
ms.assetid: b605ff97-0c45-4c24-833f-4c6a3e8be64c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dec0e5138ecf08783f11d21cd28d7291d27ea68d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578253"
---
# <a name="converting-between-datetime-and-datetimeoffset"></a>Conversión entre DateTime y DateTimeOffset

Aunque la <xref:System.DateTimeOffset> estructura proporciona un mayor grado de zona horaria que el <xref:System.DateTime> estructura, <xref:System.DateTime> parámetros se utilizan con más frecuencia en llamadas a métodos. Por este motivo, la capacidad de convertir <xref:System.DateTimeOffset> valores <xref:System.DateTime> valores y viceversa es especialmente importante. Este tema muestra cómo realizar estas conversiones de manera que se conserve tanta información de zona horaria como sea posible.

> [!NOTE]
> Tanto el <xref:System.DateTime> y <xref:System.DateTimeOffset> tipos tienen algunas limitaciones al representar horas en zonas horarias. Con su <xref:System.DateTime.Kind%2A> propiedad <xref:System.DateTime> puede reflejar solo la hora Universal coordinada (UTC) y la zona horaria local del sistema. <xref:System.DateTimeOffset> refleja la diferencia horaria de la hora UTC, pero no refleja la zona horaria real a la que esa diferencia horaria pertenece. Para obtener más información sobre valores de hora y la compatibilidad para las zonas horarias, vea [Choosing Between DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).

## <a name="conversions-from-datetime-to-datetimeoffset"></a>Conversiones entre DateTime y DateTimeOffset

El <xref:System.DateTimeOffset> estructura proporciona dos maneras equivalentes para realizar <xref:System.DateTime> a <xref:System.DateTimeOffset> conversión que son adecuados para la mayoría de las conversiones:

* El <xref:System.DateTimeOffset.%23ctor%2A> constructor, que crea un nuevo <xref:System.DateTimeOffset> objeto basado en un <xref:System.DateTime> valor.

* El operador de conversión implícita, que permite asignar un <xref:System.DateTime> valor a un <xref:System.DateTimeOffset> objeto.

Para la hora UTC y la local <xref:System.DateTime> valores, el <xref:System.DateTimeOffset.Offset%2A> propiedad del resultante <xref:System.DateTimeOffset> valor refleja con exactitud el ajuste de zona horaria local o UTC. Por ejemplo, el código siguiente convierte una hora UTC equivalente <xref:System.DateTimeOffset> valor.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

En este caso, la diferencia horaria de la variable `utcTime2` es 00:00. De forma similar, el código siguiente convierte una hora local equivalente <xref:System.DateTimeOffset> valor.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

Sin embargo, para <xref:System.DateTime> valores cuya <xref:System.DateTime.Kind%2A> propiedad es <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, estos dos métodos de conversión generan un <xref:System.DateTimeOffset> valor cuya diferencia es que la zona horaria local. Esto se muestra en el ejemplo siguiente, que se ejecuta en los EE. UU. Zona horaria estándar del Pacífico.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

Si el <xref:System.DateTime> valor refleja la fecha y hora en algo distinto de la zona horaria local o UTC, puede convertirlo a una <xref:System.DateTimeOffset> valor y a mantener su información de zona horaria llamando al método sobrecargado <xref:System.DateTimeOffset.%23ctor%2A> constructor. Por ejemplo, en el ejemplo siguiente se crea un <xref:System.DateTimeOffset> objeto que refleja la hora estándar Central.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

El segundo parámetro a esta sobrecarga del constructor, un <xref:System.TimeSpan> se debe recuperar el objeto que representa el desplazamiento de hora a la hora UTC, mediante una llamada a la <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> método de zona horaria correspondiente de la hora. Es el único parámetro del método la <xref:System.DateTime> valor que representa la fecha y hora que se va a convertir. Si la zona horaria admite el horario de verano, este parámetro permite al método determinar la diferencia horaria adecuada de esa fecha y hora concretas.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>Conversiones entre DateTimeOffset y DateTime

El <xref:System.DateTimeOffset.DateTime%2A> propiedad se utiliza normalmente para realizar <xref:System.DateTimeOffset> a <xref:System.DateTime> conversión. Sin embargo, devuelve un <xref:System.DateTime> cuyo valor <xref:System.DateTime.Kind%2A> propiedad es <xref:System.DateTimeKind.Unspecified>, como se muestra en el ejemplo siguiente.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

Esto significa que toda la información sobre la <xref:System.DateTimeOffset> se pierde la relación del valor en una hora UTC mediante la conversión cuando el <xref:System.DateTimeOffset.DateTime%2A> se utiliza la propiedad. Esto afecta a <xref:System.DateTimeOffset> valores que corresponden a la hora UTC o a la hora del sistema local porque la <xref:System.DateTimeOffset.DateTime%2A> estructura refleja esas dos zonas horarias en su <xref:System.DateTime.Kind%2A> propiedad.

Para conservar la tanta información de zona horaria como sea posible al convertir un <xref:System.DateTimeOffset> a una <xref:System.DateTime> valor, puede utilizar el <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> y <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedades.

### <a name="converting-a-utc-time"></a>Convertir una hora UTC

Para indicar que un convertido <xref:System.DateTimeOffset.DateTime%2A> valor es la hora UTC, puede recuperar el valor de la <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> propiedad. Difiere de la <xref:System.DateTimeOffset.DateTime%2A> propiedad de dos maneras:

* Devuelve un <xref:System.DateTime> cuyo valor <xref:System.DateTime.Kind%2A> propiedad es <xref:System.DateTimeKind.Utc>.

* Si el <xref:System.DateTimeOffset.Offset%2A> valor de propiedad no es igual a <xref:System.TimeSpan.Zero?displayProperty=nameWithType>, convierte la hora en UTC.

> [!NOTE]
> Si la aplicación requiere que convertir <xref:System.DateTime> valores identifican inequívocamente un único punto en el tiempo, puede utilizar el <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> propiedad para administrar todas <xref:System.DateTimeOffset> a <xref:System.DateTime> conversiones.

El siguiente código utiliza el <xref:System.DateTimeOffset.UtcDateTime%2A> propiedad que se va a convertir un <xref:System.DateTimeOffset> valor cuya diferencia horaria es igual a <xref:System.TimeSpan.Zero?displayProperty=nameWithType> a una <xref:System.DateTime> valor.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

El siguiente código utiliza el <xref:System.DateTimeOffset.UtcDateTime%2A> propiedad para realizar una conversión de zona horaria y una conversión de tipos en un <xref:System.DateTimeOffset> valor.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a>Convertir una hora local

Para indicar que un <xref:System.DateTimeOffset> valor representa la hora local, puede pasar el <xref:System.DateTime> valor devuelto por la <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> propiedad a la `static` (`Shared` en Visual Basic) <xref:System.DateTime.SpecifyKind%2A> método. El método devuelve la fecha y hora que se pasa como primer parámetro, pero establece el <xref:System.DateTime.Kind%2A> en el valor especificado por su segundo parámetro. El siguiente código utiliza el <xref:System.DateTime.SpecifyKind%2A> método al convertir un <xref:System.DateTimeOffset> valor cuya diferencia horaria corresponde a la de la zona horaria local.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

También puede usar el <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedad que se va a convertir un <xref:System.DateTimeOffset> valor a una variable local <xref:System.DateTime> valor. El <xref:System.DateTime.Kind%2A> propiedad de devuelto <xref:System.DateTime> valor es <xref:System.DateTimeKind.Local>. El siguiente código utiliza el <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedad al convertir un <xref:System.DateTimeOffset> valor cuya diferencia horaria corresponde a la de la zona horaria local. 

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

Cuando se recupera un <xref:System.DateTime> valor mediante la <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedad, la propiedad `get` descriptor de acceso en primer lugar convierte el <xref:System.DateTimeOffset> valor a UTC, a continuación, lo convierte a la hora local mediante una llamada a la <xref:System.DateTimeOffset.ToLocalTime%2A> método. Esto significa que puede recuperar un valor de la <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedad que se va a realizar una conversión de zona horaria al mismo tiempo que lleva a cabo una conversión de tipos. También significa que se aplican las reglas de ajuste de zona horaria local para realizar la conversión. El código siguiente muestra el uso de la <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedad para realizar un tipo y una conversión de zona horaria.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a>Un método de conversión de uso general

En el ejemplo siguiente se define un método denominado `ConvertFromDateTimeOffset` que convierte <xref:System.DateTimeOffset> valores <xref:System.DateTime> valores. En función de su desplazamiento, determina si el <xref:System.DateTimeOffset> valor es una hora UTC, una hora local o algún otro momento y define la fecha devuelta y el valor de hora <xref:System.DateTime.Kind%2A> propiedad según corresponda.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

El ejemplo siguiente se llama el `ConvertFromDateTimeOffset` método para convertir <xref:System.DateTimeOffset> valores que representan una hora UTC, una hora local y un tiempo de la zona horaria del Pacífico Zona horaria estándar central.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

Tenga en cuenta que este código hace dos suposiciones que, según la aplicación y el origen de sus valores de fecha y hora, pueden no ser siempre válidas:

* Se supone que una fecha y hora valor cuya diferencia horaria es <xref:System.TimeSpan.Zero?displayProperty=nameWithType> representa la hora UTC. De hecho, la hora UTC no es una hora de una zona horaria determinada, sino la hora con respecto a la que se estandarizan las horas de las zonas horarias del mundo. Zonas horarias también pueden tener un desplazamiento de <xref:System.TimeSpan.Zero>.

* Supone que una fecha y hora cuya diferencia horaria es igual que la de la zona horaria local representa la zona horaria local. Dado que los valores de fecha y hora se desasocian de su zona horaria original, este podría no ser el caso; la fecha y la hora pueden haberse originado en otra zona horaria con la misma diferencia horaria.

## <a name="see-also"></a>Vea también

[Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
