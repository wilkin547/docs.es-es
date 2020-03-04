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
ms.openlocfilehash: 5c19296f75e9e002e88263c5e5efa9917e185ebc
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156041"
---
# <a name="converting-between-datetime-and-datetimeoffset"></a>Conversión entre DateTime y DateTimeOffset

Aunque la estructura <xref:System.DateTimeOffset> proporciona un mayor grado de reconocimiento de la zona horaria que la estructura de <xref:System.DateTime>, los parámetros de <xref:System.DateTime> se utilizan con más frecuencia en las llamadas a métodos. Por este motivo, la capacidad de convertir valores <xref:System.DateTimeOffset> en <xref:System.DateTime> valores y viceversa es especialmente importante. En este tema se muestra cómo realizar estas conversiones de forma que conserve tanta información de zona horaria como sea posible.

> [!NOTE]
> Tanto el <xref:System.DateTime> como los tipos de <xref:System.DateTimeOffset> tienen algunas limitaciones cuando representan horas en zonas horarias. Con su propiedad <xref:System.DateTime.Kind%2A>, <xref:System.DateTime> solo puede reflejar la hora universal coordinada (UTC) y la zona horaria local del sistema. <xref:System.DateTimeOffset> refleja el desplazamiento de una hora con respecto a la hora UTC, pero no refleja la zona horaria real a la que pertenece ese desplazamiento. Para obtener más información sobre los valores de hora y la compatibilidad con las zonas horarias, vea [elegir entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).

## <a name="conversions-from-datetime-to-datetimeoffset"></a>Conversiones entre DateTime y DateTimeOffset

La estructura <xref:System.DateTimeOffset> proporciona dos maneras equivalentes de realizar <xref:System.DateTime> para <xref:System.DateTimeOffset> conversión que son adecuadas para la mayoría de las conversiones:

- El constructor <xref:System.DateTimeOffset.%23ctor%2A>, que crea un nuevo objeto <xref:System.DateTimeOffset> basado en un valor <xref:System.DateTime>.

- Operador de conversión implícita, que permite asignar un valor de <xref:System.DateTime> a un objeto <xref:System.DateTimeOffset>.

Para los valores de <xref:System.DateTime> UTC y local, la propiedad <xref:System.DateTimeOffset.Offset%2A> del valor de <xref:System.DateTimeOffset> resultante refleja con precisión la hora UTC o el ajuste de zona horaria local. Por ejemplo, el código siguiente convierte una hora UTC a su valor de <xref:System.DateTimeOffset> equivalente.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

En este caso, la diferencia horaria de la variable `utcTime2` es 00:00. Del mismo modo, el código siguiente convierte una hora local a su valor de <xref:System.DateTimeOffset> equivalente.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

Sin embargo, para <xref:System.DateTime> valores cuya propiedad <xref:System.DateTime.Kind%2A> se <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, estos dos métodos de conversión generan un valor <xref:System.DateTimeOffset> cuyo desplazamiento es el de la zona horaria local. Esto se muestra en el ejemplo siguiente, que se ejecuta en la zona horaria estándar del Pacífico de EE. UU.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

Si el valor de <xref:System.DateTime> refleja la fecha y hora en un valor distinto de la zona horaria local o UTC, puede convertirla en un valor <xref:System.DateTimeOffset> y conservar su información de zona horaria llamando al constructor de <xref:System.DateTimeOffset.%23ctor%2A> sobrecargado. Por ejemplo, en el ejemplo siguiente se crea una instancia de un objeto <xref:System.DateTimeOffset> que refleja la hora estándar central.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

El segundo parámetro de esta sobrecarga del constructor, un objeto <xref:System.TimeSpan> que representa la diferencia horaria con respecto a la hora UTC, se debe recuperar llamando al método <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> de la zona horaria correspondiente a la hora. El parámetro único del método es el valor de <xref:System.DateTime> que representa la fecha y hora que se van a convertir. Si la zona horaria admite el horario de verano, este parámetro permite al método determinar la diferencia horaria adecuada de esa fecha y hora concretas.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>Conversiones entre DateTimeOffset y DateTime

La propiedad <xref:System.DateTimeOffset.DateTime%2A> se usa normalmente para realizar <xref:System.DateTimeOffset> para <xref:System.DateTime> conversión. Sin embargo, devuelve un valor <xref:System.DateTime> cuya propiedad <xref:System.DateTime.Kind%2A> es <xref:System.DateTimeKind.Unspecified>, como se muestra en el ejemplo siguiente.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

Esto significa que la conversión pierde toda la información sobre la relación del valor <xref:System.DateTimeOffset> con la hora UTC cuando se utiliza la propiedad <xref:System.DateTimeOffset.DateTime%2A>. Esto afecta a <xref:System.DateTimeOffset> valores que corresponden a la hora UTC o a la hora local del sistema, ya que la estructura de <xref:System.DateTimeOffset.DateTime%2A> refleja solo esas dos zonas horarias en su propiedad <xref:System.DateTime.Kind%2A>.

Para conservar tanta información de zona horaria como sea posible al convertir un <xref:System.DateTimeOffset> en un valor <xref:System.DateTime>, puede usar las propiedades <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> y <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType>.

### <a name="converting-a-utc-time"></a>Convertir una hora UTC

Para indicar que un valor de <xref:System.DateTimeOffset.DateTime%2A> convertido es la hora UTC, puede recuperar el valor de la propiedad <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType>. Difiere de la propiedad <xref:System.DateTimeOffset.DateTime%2A> de dos maneras:

- Devuelve un valor <xref:System.DateTime> cuya propiedad <xref:System.DateTime.Kind%2A> es <xref:System.DateTimeKind.Utc>.

- Si el valor de la propiedad <xref:System.DateTimeOffset.Offset%2A> no es igual a <xref:System.TimeSpan.Zero?displayProperty=nameWithType>, convierte la hora a UTC.

> [!NOTE]
> Si la aplicación requiere que los valores de <xref:System.DateTime> convertidos identifiquen de forma inequívoca un único punto en el tiempo, debería considerar la posibilidad de usar la propiedad <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> para controlar todos los <xref:System.DateTimeOffset> a <xref:System.DateTime> conversiones.

En el código siguiente se usa la propiedad <xref:System.DateTimeOffset.UtcDateTime%2A> para convertir un valor de <xref:System.DateTimeOffset> cuyo desplazamiento es igual a <xref:System.TimeSpan.Zero?displayProperty=nameWithType> en un valor de <xref:System.DateTime>.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

En el código siguiente se usa la propiedad <xref:System.DateTimeOffset.UtcDateTime%2A> para realizar una conversión de zona horaria y una conversión de tipos en un valor <xref:System.DateTimeOffset>.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a>Conversión de una hora local

Para indicar que un valor de <xref:System.DateTimeOffset> representa la hora local, puede pasar el <xref:System.DateTime> valor devuelto por la propiedad <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> al método`Shared` `static` (Visual Basic en <xref:System.DateTime.SpecifyKind%2A>). El método devuelve la fecha y la hora que se le pasaron como su primer parámetro, pero establece la propiedad <xref:System.DateTime.Kind%2A> en el valor especificado por su segundo parámetro. En el código siguiente se usa el método <xref:System.DateTime.SpecifyKind%2A> al convertir un valor <xref:System.DateTimeOffset> cuyo desplazamiento corresponde al de la zona horaria local.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

También puede usar la propiedad <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> para convertir un valor <xref:System.DateTimeOffset> en un valor <xref:System.DateTime> local. La propiedad <xref:System.DateTime.Kind%2A> del valor de <xref:System.DateTime> devuelto es <xref:System.DateTimeKind.Local>. En el código siguiente se usa la propiedad <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> al convertir un valor <xref:System.DateTimeOffset> cuyo desplazamiento corresponde al de la zona horaria local.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

Cuando se recupera un valor de <xref:System.DateTime> mediante la propiedad <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType>, el descriptor de acceso `get` de la propiedad convierte primero el valor <xref:System.DateTimeOffset> en UTC y, a continuación, lo convierte en la hora local llamando al método <xref:System.DateTimeOffset.ToLocalTime%2A>. Esto significa que puede recuperar un valor de la propiedad <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> para realizar una conversión de zona horaria al mismo tiempo que realiza una conversión de tipos. También significa que se aplican las reglas de ajuste de zona horaria local para realizar la conversión. En el código siguiente se muestra el uso de la propiedad <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> para realizar un tipo y una conversión de zona horaria.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a>Un método de conversión de uso general

En el ejemplo siguiente se define un método denominado `ConvertFromDateTimeOffset` que convierte los valores de <xref:System.DateTimeOffset> en valores <xref:System.DateTime>. En función de su desplazamiento, determina si el valor de <xref:System.DateTimeOffset> es una hora UTC, una hora local o alguna otra, y define la propiedad <xref:System.DateTime.Kind%2A> del valor de fecha y hora devuelto en consecuencia.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

En el ejemplo siguiente se llama al método `ConvertFromDateTimeOffset` para convertir <xref:System.DateTimeOffset> valores que representan una hora UTC, una hora local y una hora en la zona horaria estándar del centro de EE. UU.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

Tenga en cuenta que este código hace dos suposiciones que, según la aplicación y el origen de sus valores de fecha y hora, pueden no ser siempre válidas:

- Se supone que un valor de fecha y hora cuyo desplazamiento es <xref:System.TimeSpan.Zero?displayProperty=nameWithType> representa la hora UTC. De hecho, la hora UTC no es una hora de una zona horaria determinada, sino la hora con respecto a la que se estandarizan las horas de las zonas horarias del mundo. Las zonas horarias también pueden tener un desplazamiento de <xref:System.TimeSpan.Zero>.

- Supone que una fecha y hora cuya diferencia horaria es igual que la de la zona horaria local representa la zona horaria local. Dado que los valores de fecha y hora se desasocian de su zona horaria original, este podría no ser el caso; la fecha y la hora pueden haberse originado en otra zona horaria con la misma diferencia horaria.

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
