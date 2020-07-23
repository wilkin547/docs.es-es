---
title: Conversión entre DateTime y DateTimeOffset
description: Convierta entre valores DateTimeOffset y valores DateTime en .NET. La estructura DateTimeOffset proporciona más reconocimiento de zona horaria que la estructura DateTime.
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
ms.openlocfilehash: 86f2c982d7f87e83102933d1de73d6e13086dc87
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86924908"
---
# <a name="converting-between-datetime-and-datetimeoffset"></a>Conversión entre DateTime y DateTimeOffset

Aunque la <xref:System.DateTimeOffset> estructura proporciona un mayor grado de reconocimiento de la zona horaria que la <xref:System.DateTime> estructura, los <xref:System.DateTime> parámetros se utilizan con más frecuencia en las llamadas a métodos. Por este motivo, la capacidad de convertir <xref:System.DateTimeOffset> valores en <xref:System.DateTime> valores y viceversa es especialmente importante. En este tema se muestra cómo realizar estas conversiones de forma que conserve tanta información de zona horaria como sea posible.

> [!NOTE]
> Los <xref:System.DateTime> <xref:System.DateTimeOffset> tipos y tienen algunas limitaciones cuando representan las horas de las zonas horarias. Con su <xref:System.DateTime.Kind%2A> propiedad, <xref:System.DateTime> solo puede reflejar la hora universal coordinada (UTC) y la zona horaria local del sistema. <xref:System.DateTimeOffset>refleja el desplazamiento de una hora con respecto a la hora UTC, pero no refleja la zona horaria real a la que pertenece ese desplazamiento. Para obtener más información sobre los valores de hora y la compatibilidad con las zonas horarias, vea [elegir entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo](choosing-between-datetime.md).

## <a name="conversions-from-datetime-to-datetimeoffset"></a>Conversiones entre DateTime y DateTimeOffset

La <xref:System.DateTimeOffset> estructura proporciona dos maneras equivalentes de realizar una <xref:System.DateTime> <xref:System.DateTimeOffset> conversión que son adecuadas para la mayoría de las conversiones:

- <xref:System.DateTimeOffset.%23ctor%2A>Constructor, que crea un nuevo <xref:System.DateTimeOffset> objeto basado en un <xref:System.DateTime> valor.

- Operador de conversión implícita, que permite asignar un <xref:System.DateTime> valor a un <xref:System.DateTimeOffset> objeto.

En el caso de <xref:System.DateTime> los valores UTC y local, la <xref:System.DateTimeOffset.Offset%2A> propiedad del <xref:System.DateTimeOffset> valor resultante refleja con precisión la hora UTC o el ajuste de zona horaria local. Por ejemplo, el código siguiente convierte una hora UTC en su valor equivalente <xref:System.DateTimeOffset> .

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

En este caso, la diferencia horaria de la variable `utcTime2` es 00:00. Del mismo modo, el código siguiente convierte una hora local en su <xref:System.DateTimeOffset> valor equivalente.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

Sin embargo, para <xref:System.DateTime> los valores cuya <xref:System.DateTime.Kind%2A> propiedad es <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType> , estos dos métodos de conversión generan un <xref:System.DateTimeOffset> valor cuyo desplazamiento es el de la zona horaria local. Esto se muestra en el ejemplo siguiente, que se ejecuta en la zona horaria estándar del Pacífico de EE. UU.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

Si el <xref:System.DateTime> valor refleja la fecha y la hora en algo distinto de la zona horaria local o la hora UTC, puede convertirla en un <xref:System.DateTimeOffset> valor y conservar su información de zona horaria llamando al constructor sobrecargado <xref:System.DateTimeOffset.%23ctor%2A> . Por ejemplo, en el ejemplo siguiente se crea una instancia de un <xref:System.DateTimeOffset> objeto que refleja la hora estándar central.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

El segundo parámetro de esta sobrecarga del constructor, un <xref:System.TimeSpan> objeto que representa la diferencia horaria con respecto a la hora UTC, se debe recuperar llamando al <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> método de la zona horaria correspondiente a la hora. El parámetro único del método es el <xref:System.DateTime> valor que representa la fecha y hora que se van a convertir. Si la zona horaria admite el horario de verano, este parámetro permite al método determinar la diferencia horaria adecuada de esa fecha y hora concretas.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>Conversiones entre DateTimeOffset y DateTime

La <xref:System.DateTimeOffset.DateTime%2A> propiedad se usa normalmente para realizar la <xref:System.DateTimeOffset> <xref:System.DateTime> conversión. Sin embargo, devuelve un <xref:System.DateTime> valor cuya <xref:System.DateTime.Kind%2A> propiedad es <xref:System.DateTimeKind.Unspecified> , como se muestra en el ejemplo siguiente.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

Esto significa que la conversión pierde toda la información sobre la <xref:System.DateTimeOffset> relación del valor con la hora UTC cuando <xref:System.DateTimeOffset.DateTime%2A> se usa la propiedad. Esto afecta a <xref:System.DateTimeOffset> los valores que corresponden a la hora UTC o a la hora local del sistema, porque la <xref:System.DateTimeOffset.DateTime%2A> estructura refleja únicamente esas dos zonas horarias en su <xref:System.DateTime.Kind%2A> propiedad.

Para conservar tanta información de zona horaria como sea posible al convertir un <xref:System.DateTimeOffset> en un <xref:System.DateTime> valor, puede usar las <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedades y.

### <a name="converting-a-utc-time"></a>Convertir una hora UTC

Para indicar que un <xref:System.DateTimeOffset.DateTime%2A> valor convertido es la hora UTC, puede recuperar el valor de la <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> propiedad. Difiere de la <xref:System.DateTimeOffset.DateTime%2A> propiedad de dos maneras:

- Devuelve un <xref:System.DateTime> valor cuya <xref:System.DateTime.Kind%2A> propiedad es <xref:System.DateTimeKind.Utc> .

- Si el <xref:System.DateTimeOffset.Offset%2A> valor de la propiedad no es igual <xref:System.TimeSpan.Zero?displayProperty=nameWithType> a, convierte la hora a UTC.

> [!NOTE]
> Si la aplicación requiere que <xref:System.DateTime> los valores convertidos identifiquen inequívocamente un único punto en el tiempo, debería considerar la posibilidad de utilizar la <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> propiedad para controlar todas las <xref:System.DateTimeOffset> <xref:System.DateTime> conversiones.

En el código siguiente se usa la <xref:System.DateTimeOffset.UtcDateTime%2A> propiedad para convertir un <xref:System.DateTimeOffset> valor cuyo desplazamiento es igual <xref:System.TimeSpan.Zero?displayProperty=nameWithType> a un <xref:System.DateTime> valor.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

En el código siguiente se usa la <xref:System.DateTimeOffset.UtcDateTime%2A> propiedad para realizar una conversión de zona horaria y una conversión de tipo en un <xref:System.DateTimeOffset> valor.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a>Conversión de una hora local

Para indicar que un <xref:System.DateTimeOffset> valor representa la hora local, puede pasar el <xref:System.DateTime> valor devuelto por la <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> propiedad al `static` método ( `Shared` en Visual Basic) <xref:System.DateTime.SpecifyKind%2A> . El método devuelve la fecha y la hora que se le pasaron como su primer parámetro, pero establece la <xref:System.DateTime.Kind%2A> propiedad en el valor especificado por su segundo parámetro. En el código siguiente se usa el <xref:System.DateTime.SpecifyKind%2A> método al convertir un <xref:System.DateTimeOffset> valor cuyo desplazamiento corresponde al de la zona horaria local.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

También puede utilizar la <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedad para convertir un <xref:System.DateTimeOffset> valor en un valor local <xref:System.DateTime> . La <xref:System.DateTime.Kind%2A> propiedad del valor devuelto <xref:System.DateTime> es <xref:System.DateTimeKind.Local> . El código siguiente usa la <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedad al convertir un <xref:System.DateTimeOffset> valor cuyo desplazamiento corresponde al de la zona horaria local.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

Cuando se recupera un <xref:System.DateTime> valor mediante la <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedad, el `get` descriptor de acceso de la propiedad convierte primero el <xref:System.DateTimeOffset> valor a UTC y, a continuación, lo convierte a la hora local llamando al <xref:System.DateTimeOffset.ToLocalTime%2A> método. Esto significa que puede recuperar un valor de la <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedad para realizar una conversión de zona horaria al mismo tiempo que realiza una conversión de tipos. También significa que se aplican las reglas de ajuste de zona horaria local para realizar la conversión. En el código siguiente se muestra el uso de la <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedad para realizar una conversión de tipo y de zona horaria. La salida de ejemplo es para una máquina establecida en la zona horaria del Pacífico (EE. UU. y Canadá). La fecha de noviembre es la hora estándar del Pacífico, que es UTC-8, mientras que la fecha de junio es el horario de verano, que es UTC-7.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a>Un método de conversión de uso general

En el ejemplo siguiente se define un método denominado `ConvertFromDateTimeOffset` que convierte <xref:System.DateTimeOffset> valores en <xref:System.DateTime> valores. En función de su desplazamiento, determina si el <xref:System.DateTimeOffset> valor es una hora UTC, una hora local o alguna otra hora, y define la propiedad del valor de fecha y hora devuelto en <xref:System.DateTime.Kind%2A> consecuencia.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

En el ejemplo siguiente se llama al `ConvertFromDateTimeOffset` método para convertir <xref:System.DateTimeOffset> valores que representan una hora UTC, una hora local y una hora en la zona horaria estándar del centro de EE. UU.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

Tenga en cuenta que este código hace dos suposiciones que, según la aplicación y el origen de sus valores de fecha y hora, pueden no ser siempre válidas:

- Se supone que un valor de fecha y hora cuya diferencia horaria <xref:System.TimeSpan.Zero?displayProperty=nameWithType> representa la hora UTC. De hecho, la hora UTC no es una hora de una zona horaria determinada, sino la hora con respecto a la que se estandarizan las horas de las zonas horarias del mundo. Las zonas horarias también pueden tener un desplazamiento de <xref:System.TimeSpan.Zero> .

- Supone que una fecha y hora cuya diferencia horaria es igual que la de la zona horaria local representa la zona horaria local. Dado que los valores de fecha y hora se desasocian de su zona horaria original, este podría no ser el caso; la fecha y la hora pueden haberse originado en otra zona horaria con la misma diferencia horaria.

## <a name="see-also"></a>Consulte también

- [Fechas, horas y zonas horarias](index.md)
