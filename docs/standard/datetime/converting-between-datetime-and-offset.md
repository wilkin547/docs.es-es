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
ms.openlocfilehash: 830e3e6e98be2eaaff2af6c0bdac650732833ab7
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864431"
---
# <a name="converting-between-datetime-and-datetimeoffset"></a>Conversión entre DateTime y DateTimeOffset

Aunque el <xref:System.DateTimeOffset> estructura proporciona un mayor grado de zona horaria que el <xref:System.DateTime> estructura, <xref:System.DateTime> parámetros se usan con más frecuencia en las llamadas a métodos. Por este motivo, la capacidad de convertir <xref:System.DateTimeOffset> valores <xref:System.DateTime> valores y viceversa es especialmente importante. En este tema se muestra cómo realizar estas conversiones de manera que se conserve tanta información de zona horaria como sea posible.

> [!NOTE]
> Tanto el <xref:System.DateTime> y <xref:System.DateTimeOffset> tipos tienen algunas limitaciones al representar horas de zonas horarias. Con su <xref:System.DateTime.Kind%2A> propiedad <xref:System.DateTime> es capaz de reflejar solo la hora Universal coordinada (UTC) y la zona horaria local del sistema. <xref:System.DateTimeOffset> refleja la diferencia horaria de la hora UTC, pero no refleja la zona horaria real a la que esa diferencia horaria pertenece. Para obtener más información acerca de los valores de hora y soporte técnico para las zonas horarias, consulte [Choosing Between DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).

## <a name="conversions-from-datetime-to-datetimeoffset"></a>Conversiones entre DateTime y DateTimeOffset

El <xref:System.DateTimeOffset> estructura proporciona dos maneras equivalentes de realizar <xref:System.DateTime> a <xref:System.DateTimeOffset> conversión que son adecuados para la mayoría de las conversiones:

* El <xref:System.DateTimeOffset.%23ctor%2A> constructor, que crea un nuevo <xref:System.DateTimeOffset> objeto según un <xref:System.DateTime> valor.

* El operador de conversión implícita, que le permite asignar un <xref:System.DateTime> valor a un <xref:System.DateTimeOffset> objeto.

UTC y local <xref:System.DateTime> valores, el <xref:System.DateTimeOffset.Offset%2A> propiedad del resultante <xref:System.DateTimeOffset> valor refleja con exactitud el desplazamiento de zona de hora UTC o local. Por ejemplo, el código siguiente convierte una hora UTC equivalente <xref:System.DateTimeOffset> valor.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

En este caso, la diferencia horaria de la variable `utcTime2` es 00:00. De forma similar, el código siguiente convierte una hora local equivalente <xref:System.DateTimeOffset> valor.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

Sin embargo, para <xref:System.DateTime> valores cuya <xref:System.DateTime.Kind%2A> propiedad es <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, estos dos métodos de conversión generan un <xref:System.DateTimeOffset> valor cuya diferencia horaria es la de la zona horaria local. Esto se muestra en el ejemplo siguiente, que se ejecuta en los EE. UU. Zona horaria estándar del Pacífico.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

Si el <xref:System.DateTime> valor refleja la fecha y hora en algo distinto de la zona horaria local o UTC, puede convertirlo a un <xref:System.DateTimeOffset> de valor y conservar su información de zona horaria llamando al método sobrecargado <xref:System.DateTimeOffset.%23ctor%2A> constructor. Por ejemplo, en el ejemplo siguiente se crea un <xref:System.DateTimeOffset> objeto que refleja la hora estándar Central.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

El segundo parámetro a esta sobrecarga del constructor, un <xref:System.TimeSpan> se debe recuperar el objeto que representa la diferencia horaria respecto a UTC, mediante una llamada a la <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> método de zona horaria correspondiente de la hora. Es el único parámetro del método la <xref:System.DateTime> valor que representa la fecha y hora que se va a convertir. Si la zona horaria admite el horario de verano, este parámetro permite al método determinar la diferencia horaria adecuada de esa fecha y hora concretas.

## <a name="conversions-from-datetimeoffset-to-datetime"></a>Conversiones entre DateTimeOffset y DateTime

El <xref:System.DateTimeOffset.DateTime%2A> propiedad se usa con más frecuencia para realizar <xref:System.DateTimeOffset> a <xref:System.DateTime> conversión. Sin embargo, devuelve un <xref:System.DateTime> cuyo valor <xref:System.DateTime.Kind%2A> propiedad es <xref:System.DateTimeKind.Unspecified>, tal y como se muestra en el ejemplo siguiente.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

Esto significa que toda la información sobre la <xref:System.DateTimeOffset> relación del valor a la hora UTC se pierde durante la conversión cuando el <xref:System.DateTimeOffset.DateTime%2A> se utiliza la propiedad. Esto afecta a <xref:System.DateTimeOffset> valores que corresponden a la hora UTC o a la hora del sistema local porque el <xref:System.DateTimeOffset.DateTime%2A> estructura refleja únicamente esas dos zonas horarias en su <xref:System.DateTime.Kind%2A> propiedad.

Para conservar tanta información de zona horaria como sea posible al convertir un <xref:System.DateTimeOffset> a un <xref:System.DateTime> valor, puede usar el <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> y <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedades.

### <a name="converting-a-utc-time"></a>Convertir una hora UTC

Para indicar que un convertido <xref:System.DateTimeOffset.DateTime%2A> valor es la hora UTC, puede recuperar el valor de la <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> propiedad. Difiere de la <xref:System.DateTimeOffset.DateTime%2A> propiedad de dos maneras:

* Devuelve un <xref:System.DateTime> cuyo valor <xref:System.DateTime.Kind%2A> propiedad es <xref:System.DateTimeKind.Utc>.

* Si el <xref:System.DateTimeOffset.Offset%2A> el valor de propiedad no es igual <xref:System.TimeSpan.Zero?displayProperty=nameWithType>, convierte la hora a la hora UTC.

> [!NOTE]
> Si la aplicación requiere que se puede convertir <xref:System.DateTime> valores identifican inequívocamente un único punto en el tiempo, debería considerar el uso de la <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> propiedad para controlar todo <xref:System.DateTimeOffset> a <xref:System.DateTime> conversiones.

El siguiente código utiliza el <xref:System.DateTimeOffset.UtcDateTime%2A> propiedad que se va a convertir un <xref:System.DateTimeOffset> valor cuya diferencia horaria es igual a <xref:System.TimeSpan.Zero?displayProperty=nameWithType> a un <xref:System.DateTime> valor.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

El siguiente código utiliza el <xref:System.DateTimeOffset.UtcDateTime%2A> propiedad para realizar una conversión de zona horaria y una conversión de tipos en un <xref:System.DateTimeOffset> valor.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a>Convertir una hora local

Para indicar que un <xref:System.DateTimeOffset> valor representa la hora local, puede pasar el <xref:System.DateTime> valor devuelto por la <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> propiedad a la `static` (`Shared` en Visual Basic) <xref:System.DateTime.SpecifyKind%2A> método. El método devuelve la fecha y hora que se pasa a él como su primer parámetro, pero establece el <xref:System.DateTime.Kind%2A> propiedad en el valor especificado por su segundo parámetro. El siguiente código utiliza el <xref:System.DateTime.SpecifyKind%2A> método al convertir un <xref:System.DateTimeOffset> valor cuya diferencia horaria corresponde a la de la zona horaria local.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

También puede usar el <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedad que se va a convertir un <xref:System.DateTimeOffset> valor a una variable local <xref:System.DateTime> valor. El <xref:System.DateTime.Kind%2A> propiedad devuelto del <xref:System.DateTime> valor es <xref:System.DateTimeKind.Local>. El siguiente código utiliza el <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedad al convertir un <xref:System.DateTimeOffset> valor cuya diferencia horaria corresponde a la de la zona horaria local. 

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

Al recuperar un <xref:System.DateTime> valor mediante el <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedad, la propiedad `get` descriptor de acceso se convierte primero el <xref:System.DateTimeOffset> valor a la hora UTC, a continuación, lo convierte a la hora local mediante una llamada a la <xref:System.DateTimeOffset.ToLocalTime%2A> método. Esto significa que puede recuperar un valor de la <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedad para realizar una conversión de zona horaria al mismo tiempo que realizar una conversión de tipos. También significa que se aplican las reglas de ajuste de zona horaria local para realizar la conversión. El código siguiente muestra el uso de la <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> propiedad para realizar una conversión de zona horaria y un tipo.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a>Un método de conversión de uso general

En el ejemplo siguiente se define un método denominado `ConvertFromDateTimeOffset` que convierte <xref:System.DateTimeOffset> valores <xref:System.DateTime> valores. En función de su diferencia horaria, determina si el <xref:System.DateTimeOffset> valor es una hora UTC, una hora local o algún otro momento y define la fecha devuelta y el valor de hora <xref:System.DateTime.Kind%2A> propiedad según corresponda.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

El ejemplo siguiente llama el `ConvertFromDateTimeOffset` método para convertir <xref:System.DateTimeOffset> valores que representan una hora UTC, una hora local y una hora en los Estados Unidos. Zona horaria estándar central.

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

Tenga en cuenta que este código hace dos suposiciones que, según la aplicación y el origen de sus valores de fecha y hora, pueden no ser siempre válidas:

* Se supone que el valor de una fecha y hora cuya diferencia horaria es <xref:System.TimeSpan.Zero?displayProperty=nameWithType> representa la hora UTC. De hecho, la hora UTC no es una hora de una zona horaria determinada, sino la hora con respecto a la que se estandarizan las horas de las zonas horarias del mundo. Zonas horarias también pueden tener un desplazamiento de <xref:System.TimeSpan.Zero>.

* Supone que una fecha y hora cuya diferencia horaria es igual que la de la zona horaria local representa la zona horaria local. Dado que los valores de fecha y hora se desasocian de su zona horaria original, este podría no ser el caso; la fecha y la hora pueden haberse originado en otra zona horaria con la misma diferencia horaria.

## <a name="see-also"></a>Vea también

* [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
