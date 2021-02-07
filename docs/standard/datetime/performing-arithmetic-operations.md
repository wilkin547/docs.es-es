---
description: Más información acerca de cómo realizar operaciones aritméticas con fechas y horas
title: Efectuar operaciones aritméticas con fechas y horas
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- times [.NET], arithmetic operations
- dates [.NET], arithmetic operations
- time zones [.NET], arithmetic operations
- arithmetic operations [.NET], dates and times
- dates [.NET], comparing
- DateTime structure, arithmetic operations
- DateTimeOffset structure, arithmetic operations
ms.assetid: 87c7ddf2-f15e-48af-8602-b3642237e6d0
ms.openlocfilehash: 7b39a6dec3abc2206c8eef7566f74aab6614aae6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99702566"
---
# <a name="performing-arithmetic-operations-with-dates-and-times"></a>Efectuar operaciones aritméticas con fechas y horas

Aunque las <xref:System.DateTime> <xref:System.DateTimeOffset> estructuras y proporcionan miembros que realizan operaciones aritméticas en sus valores, los resultados de las operaciones aritméticas son muy diferentes. En este tema se examinan estas diferencias, se relacionan con los grados de reconocimiento de la zona horaria en los datos de fecha y hora, y se explica cómo realizar operaciones con reconocimiento completo de la zona horaria mediante datos de fecha y hora.

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>Comparaciones y operaciones aritméticas con valores DateTime

La <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> propiedad permite <xref:System.DateTimeKind> asignar un valor a la fecha y hora para indicar si representa la hora local, la hora universal coordinada (UTC) o la hora de una zona horaria no especificada. Sin embargo, esta información limitada de zona horaria se omite al comparar o realizar operaciones aritméticas de fecha y hora en <xref:System.DateTimeKind> valores. Esto se muestra en el ejemplo siguiente, que compara la hora local actual con la hora UTC actual.

[!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]

El <xref:System.DateTime.CompareTo%28System.DateTime%29> método informa de que la hora local es anterior a (o menor que) la hora UTC, y la operación de resta indica que la diferencia entre la hora UTC y la hora local de un sistema de la zona horaria estándar del Pacífico de EE. UU. es de siete horas. Sin embargo, dado que estos dos valores proporcionan representaciones diferentes de un único punto en el tiempo, en este caso es evidente que el intervalo de tiempo es totalmente atribuible a la diferencia horaria de la zona horaria local con respecto a la hora UTC.

En general, la <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> propiedad no afecta a los resultados devueltos por <xref:System.DateTime.Kind> los métodos aritméticos y de comparación (como se indica en la comparación de dos puntos idénticos en el tiempo), aunque puede afectar a la interpretación de los resultados. Por ejemplo:

- El resultado de cualquier operación aritmética realizada en dos valores de fecha y hora cuyas <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> propiedades son iguales <xref:System.DateTimeKind> refleja el intervalo de tiempo real entre los dos valores. Del mismo modo, la comparación de estos dos valores de fecha y hora refleja con exactitud la relación entre los tiempos.

- El resultado de cualquier operación aritmética o de comparación realizada en dos valores de fecha y hora cuyas <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> propiedades sean iguales <xref:System.DateTimeKind> o en dos valores de fecha y hora con diferentes <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> valores de propiedad refleja la diferencia en el tiempo de reloj entre los dos valores.

- Las operaciones aritméticas o de comparación en valores de fecha y hora local no tienen en cuenta si un valor concreto es ambiguo o no válido, ni tienen en cuenta el efecto de las reglas de ajuste que son consecuencia de la transición de la zona horaria local hacia o desde el horario de verano.

- Las operaciones que comparen o calculen la diferencia entre la hora UTC y una hora local incluyen en el resultado un intervalo de tiempo igual a la diferencia horaria de la zona horaria local respecto de la hora UTC.

- Las operaciones que comparen o calculen la diferencia entre una hora no especificada y la hora UTC o la hora local reflejan la hora de reloj simple. No se consideran las diferencias de zona horaria y el resultado no refleja la aplicación de reglas de ajuste de zona horaria.

- Las operaciones que comparen o calculen la diferencia entre dos horas no especificadas pueden incluir un intervalo desconocido que refleje la diferencia entre la hora de dos zonas horarias diferentes.

Hay muchos escenarios en los que las diferencias de zona horaria no afectan a los cálculos de fecha y hora (para obtener una explicación de algunos de ellos, vea [elegir entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo](choosing-between-datetime.md)) o en los que el contexto de los datos de fecha y hora define el significado de las operaciones aritméticas o de comparación.

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>Comparaciones y operaciones aritméticas con valores DateTimeOffset

Un <xref:System.DateTimeOffset> valor incluye no solo una fecha y hora, sino también un desplazamiento que define sin ambigüedad esa fecha y hora con respecto a la hora UTC. Esto permite definir la igualdad de forma ligeramente distinta a la de <xref:System.DateTimeOffset> los valores. Mientras que <xref:System.DateTime> los valores son iguales si tienen el mismo valor de fecha y hora, <xref:System.DateTimeOffset> los valores son iguales si ambos hacen referencia al mismo punto en el tiempo. Esto hace que un <xref:System.DateTimeOffset> valor sea más preciso y menor que la necesidad de interpretación cuando se usa en comparaciones y en la mayoría de las operaciones aritméticas que determinan el intervalo entre dos fechas y horas. En el ejemplo siguiente, que es el <xref:System.DateTimeOffset> equivalente al ejemplo anterior que comparó valores locales y UTC <xref:System.DateTimeOffset> , se muestra esta diferencia de comportamiento.

[!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]

En este ejemplo, el <xref:System.DateTimeOffset.CompareTo%2A> método indica que la hora local actual y la hora UTC actual son iguales, y la resta de <xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)> valores indica que la diferencia entre las dos horas es <xref:System.TimeSpan.Zero?displayProperty=nameWithType> .

La principal limitación de usar <xref:System.DateTimeOffset> valores en las operaciones aritméticas de fecha y hora es que <xref:System.DateTimeOffset> , aunque los valores tienen algún reconocimiento de zona horaria, no son totalmente compatibles con la zona horaria. Aunque el <xref:System.DateTimeOffset> desplazamiento del valor refleja el desplazamiento de una zona horaria con respecto a la hora UTC cuando <xref:System.DateTimeOffset> se asigna por primera vez un valor a una variable, se desasocia de la zona horaria a partir de entonces. Dado que ya no está directamente asociada con una hora identificable, la suma y resta de intervalos de fecha y hora no tiene en cuenta las reglas de ajuste de una zona horaria.

Para ilustrar, la transición al horario de verano en la zona horaria estándar del centro de EE. UU. se produce a las 2:00 A.M. del 9 de marzo de 2008. Esto significa que la suma de un intervalo de dos horas y media a la hora estándar central 1:30 a. m. del día 9 de marzo de 2008 debería generar la siguiente fecha y hora: 5:00 a. m. del 9 de marzo de 2008. Pero como se muestra en el ejemplo siguiente, el resultado de la suma es 4:00 a. m. del 9 de marzo de 2008. Tenga en cuenta que el resultado de esta operación representa el punto correcto en el tiempo, aunque no es la hora de la zona horaria en la que nos interesa (es decir, no tiene el ajuste de zona horaria esperado).

[!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]

## <a name="arithmetic-operations-with-times-in-time-zones"></a>Operaciones aritméticas con horas en zonas horarias

La <xref:System.TimeZoneInfo> clase incluye una serie de métodos de conversión que aplican automáticamente los ajustes cuando convierten las horas de una zona horaria a otra. que incluyen la siguiente información:

- Los <xref:System.TimeZoneInfo.ConvertTime%2A> <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A> métodos y, que convierten las horas entre dos zonas horarias cualesquiera.

- Los <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> métodos y, que convierten la hora de una zona horaria determinada en una hora UTC o convierta la hora UTC a la hora de una zona horaria determinada.

Para obtener más información, consulte [convertir horas entre zonas horarias](converting-between-time-zones.md).

La <xref:System.TimeZoneInfo> clase no proporciona métodos que apliquen automáticamente reglas de ajuste al realizar operaciones aritméticas de fecha y hora. Para hacerlo, puede convertir la hora de una zona horaria a la hora UTC, realizar la operación aritmética y, después, convertir la hora UTC de nuevo a la hora de la zona horaria. Para obtener más información, consulte [Cómo: usar zonas horarias en operaciones aritméticas de fecha y hora](use-time-zones-in-arithmetic.md).

Por ejemplo, el código siguiente se parece al código anterior que sumaba dos horas y media a la fecha y hora 2:00 a. m. del 9 de marzo de 2008. Pero, dado que convierte una hora estándar central a la hora UTC antes de realizar la operación aritmética de fecha y hora y, después, convierte el resultado en hora UTC de nuevo a la hora estándar central, la hora resultante refleja la transición de la zona de la hora estándar central al horario de verano.

[!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](index.md)
- [Procedimiento para usar zonas horarias en operaciones aritméticas de fecha y hora](use-time-zones-in-arithmetic.md)
