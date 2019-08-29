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
ms.openlocfilehash: eb91ed8edd0c5cd3cb1d051157596f311718195d
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107060"
---
# <a name="converting-between-datetime-and-datetimeoffset"></a>Conversión entre DateTime y DateTimeOffset

Aunque la <xref:System.DateTimeOffset> estructura proporciona un mayor grado de reconocimiento de la zona horaria <xref:System.DateTime> que la <xref:System.DateTime> estructura, los parámetros se utilizan con más frecuencia en las llamadas a métodos. Por este motivo, la capacidad de convertir <xref:System.DateTimeOffset> valores en <xref:System.DateTime> valores y viceversa es especialmente importante. En este tema se muestra cómo realizar estas conversiones de forma que conserve tanta información de zona horaria como sea posible.

> [!NOTE]
> Los <xref:System.DateTime> tipos<xref:System.DateTimeOffset> y tienen algunas limitaciones cuando representan las horas de las zonas horarias. Con su <xref:System.DateTime.Kind%2A> propiedad, <xref:System.DateTime> solo puede reflejar la hora universal coordinada (UTC) y la zona horaria local del sistema. <xref:System.DateTimeOffset>refleja el desplazamiento de una hora con respecto a la hora UTC, pero no refleja la zona horaria real a la que pertenece ese desplazamiento. Para obtener más información sobre los valores de hora y la compatibilidad con las zonas horarias, vea [elegir entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).

## <a name="conversions-from-datetime-to-datetimeoffset"></a>Conversiones entre DateTime y DateTimeOffset

La <xref:System.DateTimeOffset> estructura proporciona dos maneras equivalentes de <xref:System.DateTime> <xref:System.DateTimeOffset> realizar una conversión que son adecuadas para la mayoría de las conversiones:

- Constructor, que crea un nuevo <xref:System.DateTimeOffset> objeto basado en un <xref:System.DateTime> valor. <xref:System.DateTimeOffset.%23ctor%2A>

- Operador de conversión implícita, que permite asignar un <xref:System.DateTime> valor a un <xref:System.DateTimeOffset> objeto.

En el caso de <xref:System.DateTime> los valores UTC <xref:System.DateTimeOffset.Offset%2A> y local, la <xref:System.DateTimeOffset> propiedad del valor resultante refleja con precisión la hora UTC o el ajuste de zona horaria local. Por ejemplo, el código siguiente convierte una hora UTC en su valor equivalente <xref:System.DateTimeOffset> .

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

En este caso, la diferencia horaria de la variable `utcTime2` es 00:00. Del mismo modo, el código siguiente convierte una hora local en su <xref:System.DateTimeOffset> valor equivalente.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

Sin embargo, <xref:System.DateTime> para los <xref:System.DateTime.Kind%2A> valores cuya <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>propiedad es, estos dos métodos de <xref:System.DateTimeOffset> conversión generan un valor cuyo desplazamiento es el de la zona horaria local. Esto se muestra en el ejemplo siguiente, que se ejecuta en los EE. UU. Zona horaria estándar del Pacífico.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

Si el <xref:System.DateTime> valor refleja la fecha y la hora en algo distinto de la zona horaria local o la hora UTC, puede convertirla <xref:System.DateTimeOffset> en un valor y conservar su información de zona horaria <xref:System.DateTimeOffset.%23ctor%2A> llamando al constructor sobrecargado. Por ejemplo, en el ejemplo siguiente se crea <xref:System.DateTimeOffset> una instancia de un objeto que refleja la hora estándar central.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

El segundo parámetro de esta sobrecarga del constructor, <xref:System.TimeSpan> un objeto que representa la diferencia horaria con respecto a la hora UTC, se debe <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> recuperar llamando al método de la zona horaria correspondiente a la hora. El parámetro único del método es el <xref:System.DateTime> valor que representa la fecha y hora que se van a convertir. Si la zona horaria admite el horario de verano, este parámetro permite al método determinar la diferencia horaria adecuada de esa fecha y hora concretas.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>Conversiones entre DateTimeOffset y DateTime

La <xref:System.DateTimeOffset.DateTime%2A> propiedad se usa normalmente para <xref:System.DateTime> realizar <xref:System.DateTimeOffset> la conversión. Sin embargo, devuelve un <xref:System.DateTime> valor cuya <xref:System.DateTime.Kind%2A> propiedad es <xref:System.DateTimeKind.Unspecified>, como se muestra en el ejemplo siguiente.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

Esto significa que la conversión pierde toda <xref:System.DateTimeOffset> la información sobre la relación del valor con la hora UTC cuando <xref:System.DateTimeOffset.DateTime%2A> se usa la propiedad. Esto afecta <xref:System.DateTimeOffset> a los valores que corresponden a la hora UTC o a la hora local del <xref:System.DateTimeOffset.DateTime%2A> sistema, porque la estructura refleja únicamente esas dos <xref:System.DateTime.Kind%2A> zonas horarias en su propiedad.

Para conservar tanta información de zona horaria como sea posible al convertir <xref:System.DateTimeOffset> un en <xref:System.DateTime> un valor, puede usar las <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> propiedades <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> y.

### <a name="converting-a-utc-time"></a>Convertir una hora UTC

Para indicar que un valor <xref:System.DateTimeOffset.DateTime%2A> convertido es la hora UTC, puede recuperar el valor de la <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> propiedad. Difiere de la <xref:System.DateTimeOffset.DateTime%2A> propiedad de dos maneras:

- Devuelve un <xref:System.DateTime> valor cuya <xref:System.DateTime.Kind%2A> propiedad es <xref:System.DateTimeKind.Utc>.

- Si el <xref:System.DateTimeOffset.Offset%2A> valor de la propiedad no <xref:System.TimeSpan.Zero?displayProperty=nameWithType>es igual a, convierte la hora a UTC.

> [!NOTE]
> Si la aplicación requiere que los <xref:System.DateTime> valores convertidos identifiquen inequívocamente un único punto en el tiempo, debería <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> considerar la posibilidad de utilizar <xref:System.DateTime> la propiedad para controlar todas las <xref:System.DateTimeOffset> conversiones.

En el código siguiente se <xref:System.DateTimeOffset.UtcDateTime%2A> usa la propiedad para <xref:System.DateTimeOffset> convertir un <xref:System.TimeSpan.Zero?displayProperty=nameWithType> valor cuyo desplazamiento es igual <xref:System.DateTime> a un valor.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

En el código siguiente se <xref:System.DateTimeOffset.UtcDateTime%2A> usa la propiedad para realizar una conversión de zona horaria y una conversión de <xref:System.DateTimeOffset> tipo en un valor.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a>Conversión de una hora local

Para indicar que un <xref:System.DateTimeOffset> valor representa la hora local, puede pasar el <xref:System.DateTime> valor devuelto `static` por la <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> propiedad al método (`Shared` en Visual Basic) <xref:System.DateTime.SpecifyKind%2A> . El método devuelve la fecha y la hora que se le pasaron como su primer parámetro, pero <xref:System.DateTime.Kind%2A> establece la propiedad en el valor especificado por su segundo parámetro. En el código siguiente se <xref:System.DateTime.SpecifyKind%2A> usa el método al <xref:System.DateTimeOffset> convertir un valor cuyo desplazamiento corresponde al de la zona horaria local.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

También puede utilizar la <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedad para convertir un <xref:System.DateTimeOffset> valor en un valor local <xref:System.DateTime> . La <xref:System.DateTime.Kind%2A> propiedad del valor devuelto <xref:System.DateTime> es <xref:System.DateTimeKind.Local>. El código siguiente usa la <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedad al convertir un <xref:System.DateTimeOffset> valor cuyo desplazamiento corresponde al de la zona horaria local. 

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

Cuando se recupera un <xref:System.DateTime> valor mediante la <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedad, el descriptor de acceso de `get` la <xref:System.DateTimeOffset> propiedad convierte primero el valor a UTC y, a continuación, lo convierte <xref:System.DateTimeOffset.ToLocalTime%2A> a la hora local llamando al método. Esto significa que puede recuperar un valor de la <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedad para realizar una conversión de zona horaria al mismo tiempo que realiza una conversión de tipos. También significa que se aplican las reglas de ajuste de zona horaria local para realizar la conversión. En el código siguiente se muestra el uso de <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> la propiedad para realizar una conversión de tipo y de zona horaria.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a>Un método de conversión de uso general

En el ejemplo siguiente se define un `ConvertFromDateTimeOffset` método denominado que <xref:System.DateTimeOffset> convierte valores <xref:System.DateTime> en valores. En función de su desplazamiento, determina si el <xref:System.DateTimeOffset> valor es una hora UTC, una hora local o alguna otra hora, y define la propiedad del valor de <xref:System.DateTime.Kind%2A> fecha y hora devuelto en consecuencia.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

En el ejemplo siguiente se `ConvertFromDateTimeOffset` llama al método <xref:System.DateTimeOffset> para convertir valores que representan una hora UTC, una hora local y una hora de la zona horaria del Pacífico de EE. UU. Zona horaria estándar central.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

Tenga en cuenta que este código hace dos suposiciones que, según la aplicación y el origen de sus valores de fecha y hora, pueden no ser siempre válidas:

- Se supone que un valor de fecha y hora cuya diferencia <xref:System.TimeSpan.Zero?displayProperty=nameWithType> horaria representa la hora UTC. De hecho, la hora UTC no es una hora de una zona horaria determinada, sino la hora con respecto a la que se estandarizan las horas de las zonas horarias del mundo. Las zonas horarias también pueden tener un <xref:System.TimeSpan.Zero>desplazamiento de.

- Supone que una fecha y hora cuya diferencia horaria es igual que la de la zona horaria local representa la zona horaria local. Dado que los valores de fecha y hora se desasocian de su zona horaria original, este podría no ser el caso; la fecha y la hora pueden haberse originado en otra zona horaria con la misma diferencia horaria.

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
