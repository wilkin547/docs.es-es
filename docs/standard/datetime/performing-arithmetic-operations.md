---
title: Efectuar operaciones aritméticas con fechas y horas
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- times [.NET Framework], arithmetic operations
- dates [.NET Framework], arithmetic operations
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], comparing
- DateTime structure, arithmetic operations
- DateTimeOffset structure, arithmetic operations
ms.assetid: 87c7ddf2-f15e-48af-8602-b3642237e6d0
ms.openlocfilehash: 0db0331620da8337930bfacf5d1bbd9913647afa
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344171"
---
# <a name="performing-arithmetic-operations-with-dates-and-times"></a>Efectuar operaciones aritméticas con fechas y horas

Aunque las <xref:System.DateTime> estructuras y las <xref:System.DateTimeOffset> proporcionan miembros que realizan operaciones aritméticas en sus valores, los resultados de las operaciones aritméticas son muy diferentes. En este tema se examinan esas diferencias, se relacionan con grados de reconocimiento de zona horaria en los datos de fecha y hora y se describe cómo realizar operaciones de reconocimiento de zona horaria completa mediante datos de fecha y hora.

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>Comparaciones y operaciones aritméticas con valores DateTime

La <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> propiedad <xref:System.DateTimeKind> permite asignar un valor a la fecha y hora para indicar si representa la hora local, la hora universal coordinada (UTC) o la hora en una zona horaria no especificada. Sin embargo, esta información de zona horaria limitada se <xref:System.DateTimeKind> omite al comparar o realizar la aritmética de fecha y hora en los valores. Esto se muestra en el ejemplo siguiente, que compara la hora local actual con la hora UTC actual.

[!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]

El <xref:System.DateTime.CompareTo%28System.DateTime%29> método informa de que la hora local es anterior (o menor que) la hora UTC y la operación de resta indica que la diferencia entre UTC y la hora local para un sistema en la zona horaria estándar del Pacífico de EE. UU. es de siete horas. Pero debido a que estos dos valores proporcionan diferentes representaciones de un solo punto en el tiempo, está claro en este caso que el intervalo de tiempo es completamente atribuible al desplazamiento de la zona horaria local de UTC.

En términos <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> más generales, la propiedad <xref:System.DateTime.Kind> no afecta a los resultados devueltos por métodos de comparación y aritméticos (como indica la comparación de dos puntos idénticos en el tiempo), aunque puede afectar a la interpretación de esos resultados. Por ejemplo:

- El resultado de cualquier operación aritmética <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> realizada <xref:System.DateTimeKind> en dos valores de fecha y hora cuyas propiedades sean iguales refleja el intervalo de tiempo real entre los dos valores. Del mismo modo, la comparación de estos dos valores de fecha y hora refleja con exactitud la relación entre los tiempos.

- El resultado de cualquier operación aritmética o <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> de <xref:System.DateTimeKind> comparación realizada en dos <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> valores de fecha y hora cuyas propiedades sean iguales o en dos valores de fecha y hora con valores de propiedad diferentes refleja la diferencia en el tiempo de reloj entre los dos valores.

- Las operaciones aritméticas o de comparación en valores de fecha y hora local no tienen en cuenta si un valor concreto es ambiguo o no válido, ni tienen en cuenta el efecto de las reglas de ajuste que son consecuencia de la transición de la zona horaria local hacia o desde el horario de verano.

- Las operaciones que comparen o calculen la diferencia entre la hora UTC y una hora local incluyen en el resultado un intervalo de tiempo igual a la diferencia horaria de la zona horaria local respecto de la hora UTC.

- Las operaciones que comparen o calculen la diferencia entre una hora no especificada y la hora UTC o la hora local reflejan la hora de reloj simple. No se consideran las diferencias de zona horaria y el resultado no refleja la aplicación de reglas de ajuste de zona horaria.

- Las operaciones que comparen o calculen la diferencia entre dos horas no especificadas pueden incluir un intervalo desconocido que refleje la diferencia entre la hora de dos zonas horarias diferentes.

Hay muchos escenarios en los que las diferencias de zona horaria no afectan a los cálculos de fecha y hora (para una explicación de algunos de estos, vea [Elegir entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)) o en los que el contexto de los datos de fecha y hora define el significado de las operaciones de comparación o aritméticas.

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>Comparaciones y operaciones aritméticas con valores DateTimeOffset

Un <xref:System.DateTimeOffset> valor incluye no solo una fecha y hora, sino también un desplazamiento que define inequívocamente esa fecha y hora en relación con UTC. Esto permite definir la igualdad de forma <xref:System.DateTimeOffset> algo diferente que para los valores. Mientras <xref:System.DateTime> que los valores son iguales si <xref:System.DateTimeOffset> tienen el mismo valor de fecha y hora, los valores son iguales si ambos hacen referencia al mismo punto en el tiempo. Esto hace <xref:System.DateTimeOffset> que un valor sea más preciso y menos necesita interpretación cuando se utiliza en comparaciones y en la mayoría de las operaciones aritméticas que determinan el intervalo entre dos fechas y horas. El ejemplo siguiente, <xref:System.DateTimeOffset> que es el equivalente al <xref:System.DateTimeOffset> ejemplo anterior que comparó los valores locales y UTC, ilustra esta diferencia de comportamiento.

[!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]

En este ejemplo, el <xref:System.DateTimeOffset.CompareTo%2A> método indica que la hora local actual y <xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)> la hora UTC actual son iguales, y la resta de valores indica que la diferencia entre las dos veces es <xref:System.TimeSpan.Zero?displayProperty=nameWithType>.

La principal limitación del uso <xref:System.DateTimeOffset> de valores <xref:System.DateTimeOffset> en la aritmética de fecha y hora es que aunque los valores tienen cierta conciencia de zona horaria, no son plenamente conscientes de la zona horaria. Aunque <xref:System.DateTimeOffset> el desplazamiento del valor refleja el desplazamiento de <xref:System.DateTimeOffset> una zona horaria de UTC cuando se asigna un valor a una variable por primera vez, se desasocia de la zona horaria a partir de entonces. Dado que ya no está directamente asociada con una hora identificable, la suma y resta de intervalos de fecha y hora no tiene en cuenta las reglas de ajuste de una zona horaria.

Para ilustrar, la transición al horario de verano en la zona horaria estándar central de EE. UU. se produce a las 2:00 a.m. del 9 de marzo de 2008. Esto significa que la suma de un intervalo de dos horas y media a la hora estándar central 1:30 a. m. del día 9 de marzo de 2008 debería generar la siguiente fecha y hora: 5:00 a. m. del 9 de marzo de 2008. Pero como se muestra en el ejemplo siguiente, el resultado de la suma es 4:00 a. m. del 9 de marzo de 2008. Tenga en cuenta que el resultado de esta operación representa el punto correcto en el tiempo, aunque no es la hora en la zona horaria en la que estamos interesados (es decir, no tiene el desplazamiento de zona horaria esperado).

[!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]

## <a name="arithmetic-operations-with-times-in-time-zones"></a>Operaciones aritméticas con horarios en zonas horarias

La <xref:System.TimeZoneInfo> clase incluye una serie de métodos de conversión que aplican ajustes automáticamente cuando convierten tiempos de una zona horaria a otra. Entre ellas, figuran:

- Los <xref:System.TimeZoneInfo.ConvertTime%2A> <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A> métodos y, que convierten los tiempos entre dos zonas horarias cualquiera.

- Los <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> métodos y, que convierten la hora de una zona horaria determinada a UTC, o convierten UTC a la hora en una zona horaria determinada.

Para obtener más información, consulte [Conversión de horas entre zonas horarias.](../../../docs/standard/datetime/converting-between-time-zones.md)

La <xref:System.TimeZoneInfo> clase no proporciona ningún método que aplique automáticamente reglas de ajuste al realizar la aritmética de fecha y hora. Para hacerlo, puede convertir la hora de una zona horaria a la hora UTC, realizar la operación aritmética y, después, convertir la hora UTC de nuevo a la hora de la zona horaria. Para obtener más información, consulte [Cómo: Usar zonas horarias en la aritmética](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)de fecha y hora .

Por ejemplo, el código siguiente se parece al código anterior que sumaba dos horas y media a la fecha y hora 2:00 a. m. del 9 de marzo de 2008. Pero, dado que convierte una hora estándar central a la hora UTC antes de realizar la operación aritmética de fecha y hora y, después, convierte el resultado en hora UTC de nuevo a la hora estándar central, la hora resultante refleja la transición de la zona de la hora estándar central al horario de verano.

[!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
- [Procedimiento para usar zonas horarias en operaciones aritméticas de fecha y hora](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)
