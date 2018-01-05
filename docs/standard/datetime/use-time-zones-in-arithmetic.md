---
title: "Cómo: utilizar zonas horarias en fecha y hora aritmético"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], adding and subtracting
ms.assetid: 83dd898d-1338-415d-8cd6-445377ab7871
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: bcffc98d763c125ac44c1048a7c89c8f6a1e89f1
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a>Cómo: utilizar zonas horarias en fecha y hora aritmético

Normalmente, cuando se realice la fecha y una hora mediante aritméticos <xref:System.DateTime> o <xref:System.DateTimeOffset> valores, el resultado no refleja las reglas de ajuste de zona horaria. Esto es cierto incluso cuando la zona horaria del valor de fecha y hora es claramente identificable (por ejemplo, cuando la <xref:System.DateTime.Kind%2A> propiedad está establecida en <xref:System.DateTimeKind.Local>). Este tema muestra cómo realizar operaciones aritméticas en valores de fecha y hora que pertenecen a una zona horaria determinada. Los resultados de las operaciones aritméticas reflejarán las reglas de ajuste de la zona horaria.

### <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a>Para aplicar las reglas de ajuste a la fecha y hora aritmético

1. Implemente algún método para acoplar estrechamente un valor de fecha y hora con la zona horaria a la que pertenece. Por ejemplo, declare una estructura que incluya tanto el valor de fecha y hora como su zona horaria. En el ejemplo siguiente se usa este enfoque para vincular un <xref:System.DateTime> valor con su zona horaria.

   [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
   [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]

2. Convertir una hora en hora Universal coordinada (UTC) mediante una llamada a la <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> método o la <xref:System.TimeZoneInfo.ConvertTime%2A> método.

3. Realice la operación aritmética en la hora UTC.

4. Convertir la hora a la hora UTC a la zona horaria asociada de la hora original llamando a la <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> método.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se agregan dos horas y treinta minutos al 9 de marzo de 2008, a la 1:30 A.M. zona horaria estándar central. La transición de esa zona horaria al horario de verano se produce treinta minutos más tarde, a las 2:00 A.M. del 9 de marzo de 2008. Puesto que el ejemplo sigue los cuatro pasos indicados en la sección anterior, se notifica correctamente la hora resultante como las 5:00 A.M. del 9 de marzo de 2008.

[!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]

Ambos <xref:System.DateTime> y <xref:System.DateTimeOffset> valores se desasocie de cualquier zona horaria a la que podría pertenecer. Para realizar operaciones aritméticas de fecha y hora de tal manera que apliquen automáticamente las reglas de ajuste de una zona horaria, la zona horaria a la que pertenezca cualquier valor de fecha y hora debe ser identificable de forma inmediata. Esto significa que un valor de fecha y hora y su zona horaria asociada deben estar estrechamente acoplados. Hay varias maneras de hacer esto, que incluyen las siguientes:

* Suponer que todas las horas usadas en una aplicación pertenecen a una zona horaria determinada. Aunque es adecuado en algunos casos, este enfoque tiene una flexibilidad limitada y posiblemente, una portabilidad limitada.

* Definir un tipo que acople estrechamente una fecha y hora con su zona horaria asociada, incluyendo ambas como campos del tipo. Este enfoque es el que se usa en el ejemplo de código, que define una estructura para almacenar la fecha y hora y la zona horaria en dos campos de miembro.

El ejemplo muestra cómo realizar operaciones aritméticas en <xref:System.DateTime> los valores para que se aplican las reglas de ajuste de zona horaria al resultado. Sin embargo, <xref:System.DateTimeOffset> valores se pueden utilizar fácilmente. En el ejemplo siguiente se muestra cómo el código en el ejemplo original puede adaptarse para su uso <xref:System.DateTimeOffset> en lugar de <xref:System.DateTime> valores.

[!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]

Tenga en cuenta que si simplemente se realiza esta incorporación en la <xref:System.DateTimeOffset> valor sin primero convierte a UTC, el resultado refleja el punto correcto en el tiempo, pero su desplazamiento no refleja que la zona horaria designada para esa hora.

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

* Que se agregará al proyecto una referencia a System.Core.dll.

* Que el <xref:System> espacio de nombres se importan con el `using` instrucción (obligatorio en el código de C#).

## <a name="see-also"></a>Vea también

[Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
[realizar operaciones aritméticas con fechas y horas](../../../docs/standard/datetime/performing-arithmetic-operations.md)
