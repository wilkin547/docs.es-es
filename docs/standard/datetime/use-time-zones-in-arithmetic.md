---
description: 'Más información acerca de cómo: usar zonas horarias en operaciones aritméticas de fecha y hora'
title: Procedimiento para usar zonas horarias en operaciones aritméticas de fecha y hora
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], arithmetic operations
- arithmetic operations [.NET], dates and times
- dates [.NET], adding and subtracting
ms.assetid: 83dd898d-1338-415d-8cd6-445377ab7871
ms.openlocfilehash: 74f878da85dc959114013d7296b738e8198fc992
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99702371"
---
# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a>Procedimiento para usar zonas horarias en operaciones aritméticas de fecha y hora

Normalmente, cuando se realizan operaciones aritméticas de fecha y hora con <xref:System.DateTime> <xref:System.DateTimeOffset> valores o, el resultado no refleja ninguna regla de ajuste de zona horaria. Esto ocurre incluso cuando la zona horaria del valor de fecha y hora es claramente identificable (por ejemplo, cuando la <xref:System.DateTime.Kind%2A> propiedad está establecida en <xref:System.DateTimeKind.Local> ). En este tema se muestra cómo realizar operaciones aritméticas en valores de fecha y hora que pertenecen a una zona horaria determinada. Los resultados de las operaciones aritméticas reflejarán las reglas de ajuste de la zona horaria.

### <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a>Para aplicar las reglas de ajuste a la fecha y hora aritmético

1. Implemente algún método para acoplar estrechamente un valor de fecha y hora con la zona horaria a la que pertenece. Por ejemplo, declare una estructura que incluya tanto el valor de fecha y hora como su zona horaria. En el ejemplo siguiente se usa este enfoque para vincular un <xref:System.DateTime> valor con su zona horaria.

   [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
   [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]

2. Convierta una hora en hora universal coordinada (UTC) llamando al <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> método o al <xref:System.TimeZoneInfo.ConvertTime%2A> método.

3. Realice la operación aritmética en la hora UTC.

4. Convierta la hora de la hora UTC a la zona horaria asociada a la hora original llamando al <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> método.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se agregan dos horas y treinta minutos al 9 de marzo de 2008, a la 1:30 A.M. zona horaria estándar central. La transición de esa zona horaria al horario de verano se produce treinta minutos más tarde, a las 2:00 A.M. del 9 de marzo de 2008. Puesto que el ejemplo sigue los cuatro pasos indicados en la sección anterior, se notifica correctamente la hora resultante como las 5:00 A.M. del 9 de marzo de 2008.

[!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]

Los <xref:System.DateTime> <xref:System.DateTimeOffset> valores y están desasociados de cualquier zona horaria a la que puedan pertenecer. Para realizar operaciones aritméticas de fecha y hora de tal manera que apliquen automáticamente las reglas de ajuste de una zona horaria, la zona horaria a la que pertenezca cualquier valor de fecha y hora debe ser identificable de forma inmediata. Esto significa que un valor de fecha y hora y su zona horaria asociada deben estar estrechamente acoplados. Hay varias maneras de hacer esto, que incluyen las siguientes:

- Suponer que todas las horas usadas en una aplicación pertenecen a una zona horaria determinada. Aunque es adecuado en algunos casos, este enfoque tiene una flexibilidad limitada y posiblemente, una portabilidad limitada.

- Definir un tipo que acople estrechamente una fecha y hora con su zona horaria asociada, incluyendo ambas como campos del tipo. Este enfoque es el que se usa en el ejemplo de código, que define una estructura para almacenar la fecha y hora y la zona horaria en dos campos de miembro.

En el ejemplo se muestra cómo realizar operaciones aritméticas en <xref:System.DateTime> valores para que se apliquen reglas de ajuste de zona horaria al resultado. Sin embargo, <xref:System.DateTimeOffset> los valores se pueden usar de la misma manera. En el ejemplo siguiente se muestra cómo el código del ejemplo original podría adaptarse para usar en <xref:System.DateTimeOffset> lugar de <xref:System.DateTime> los valores.

[!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]

Tenga en cuenta que si esta suma se realiza simplemente en el <xref:System.DateTimeOffset> valor sin convertirla primero a UTC, el resultado reflejará el punto en el tiempo correcto, pero su desplazamiento no reflejará el de la zona horaria designada en ese momento.

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

- Que el <xref:System> espacio de nombres se debe importar con la `using` instrucción (necesaria en el código de C#).

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](index.md)
- [Realizar operaciones aritméticas con fechas y horas](performing-arithmetic-operations.md)
