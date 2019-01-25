---
title: Procedimiento Creación de zonas horarias con reglas de ajuste
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], creating
- time zones [.NET Framework], and adjustment rules
- adjustment rule [.NET Framework]
ms.assetid: c52ef192-13a9-435f-8015-3b12eae8c47c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83905c97f37a0e49f6219da47e2f640ecfb8edfb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721180"
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a>Procedimiento Creación de zonas horarias con reglas de ajuste

La información de zona horaria exacta requerida por una aplicación puede no encontrarse en un sistema determinado por varias razones:

* Nunca se definió la zona horaria en el registro del sistema local.

* Datos sobre la zona horaria se ha modificado o quitado del registro.

* La zona horaria no tiene información precisa sobre los ajustes de zona horaria para un período histórico determinado.

En estos casos, puede llamar a la <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método para definir la zona horaria requerida por la aplicación. Puede utilizar las sobrecargas de este método para crear una zona horaria con o sin reglas de ajuste. Si la zona horaria admite el horario de verano, puede definir los ajustes con cualquier reglas de ajuste fija o flotante. (Para obtener definiciones de estos términos, vea la sección "Terminología de zona horaria" en [Introducción a zona horaria](../../../docs/standard/datetime/time-zone-overview.md).)

> [!IMPORTANT]
> Zonas horarias personalizadas creadas mediante una llamada a la <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método no se agregan al registro. En su lugar, puede obtenerse únicamente a través de la referencia de objeto devuelta por la <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> llamada al método.

En este tema se muestra cómo crear una zona horaria con reglas de ajuste. Para crear una zona horaria que no es compatible con las reglas de ajuste al horario de verano, vea [Cómo: Crear zonas horarias sin reglas de ajuste](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md).

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a>Para crear una zona horaria con reglas de ajuste flotantes

1. Para cada ajuste (es decir, para cada transición fuera de y realizar una copia a la hora estándar en un intervalo de tiempo determinado), haga lo siguiente:

    1. Defina el tiempo de transición inicial para el ajuste de zona horaria.

       Debe llamar a la <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> método y pásele un <xref:System.DateTime> valor que define el tiempo de la transición, un valor entero que define el mes de la transición, un valor entero que define la semana en que se produce la transición, y un <xref:System.DayOfWeek> valor que define el día de la semana en que se produce la transición. Crea una instancia de esta llamada al método un <xref:System.TimeZoneInfo.TransitionTime> objeto.

    2. Defina el tiempo de transición final para el ajuste de zona horaria. Esto requiere otra llamada a la <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> método. Esta llamada al método crea una instancia de un segundo <xref:System.TimeZoneInfo.TransitionTime> objeto.

    3. Llame a la <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> método y pásele el eficaz fechas inicial y final del ajuste, un <xref:System.TimeSpan> objeto que define la cantidad de tiempo en la transición y las dos <xref:System.TimeZoneInfo.TransitionTime> objetos que definen cuándo las transiciones a y desde el horario de verano tiempo se producen. Crea una instancia de esta llamada al método un <xref:System.TimeZoneInfo.AdjustmentRule> objeto.

    4. Asignar el <xref:System.TimeZoneInfo.AdjustmentRule> objeto a una matriz de <xref:System.TimeZoneInfo.AdjustmentRule> objetos.

2. Definir el nombre para mostrar de la zona horaria. El nombre para mostrar sigue un formato bastante estándar en el que se encierra entre paréntesis el desplazamiento de la zona horaria de hora Universal coordinada (UTC) y seguido de una cadena que identifica la zona horaria, uno o más de las ciudades de la zona horaria o uno o varios de lo cou movimientos o regiones en la zona horaria.

3. Defina el nombre de la hora de la zona horaria estándar. Normalmente, esta cadena también se utiliza como identificador de la zona horaria.

4. Definir el nombre del horario de verano de la zona horaria.

5. Si desea utilizar un identificador diferente que el nombre de la zona horaria estándar, definir el identificador de zona horaria.

6. Crear una instancia de un <xref:System.TimeSpan> objeto que define el desplazamiento de la zona horaria a la hora UTC. Zonas horarias con horas posteriores a la hora UTC tienen una diferencia positiva. Zonas horarias con tiempos anteriores a la hora UTC tienen una diferencia negativa.

7. Llame a la <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> método para crear una instancia de la nueva zona horaria.

## <a name="example"></a>Ejemplo

El ejemplo siguiente define una zona horaria estándar Central de Estados Unidos que incluye reglas de ajuste para una variedad de intervalos de tiempo desde 1918 hasta la actual.

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

La zona horaria creada en este ejemplo tiene varias reglas de ajuste. Debe tener cuidado para asegurarse de que el eficaz fechas inicial y final de cualquier regla de ajuste no se superponen con las fechas de otra regla de ajuste. Si hay una superposición, un <xref:System.InvalidTimeZoneException> se produce.

Para reglas de ajuste flotantes, se pasa el valor 5 a la `week` parámetro de la <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> método para indicar que la transición se produce en la última semana de un mes determinado.

En la creación de la matriz de <xref:System.TimeZoneInfo.AdjustmentRule> objetos que se va a usar en el <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> llamada al método, el código podría inicializar la matriz al tamaño requerido por el número de los ajustes que deben crearse para la zona horaria. En su lugar, este ejemplo de código llama a la <xref:System.Collections.Generic.List%601.Add%2A> para agregar cada regla de ajuste a un tipo genérico <xref:System.Collections.Generic.List%601> colección de <xref:System.TimeZoneInfo.AdjustmentRule> objetos. El código, a continuación, llama a la <xref:System.Collections.Generic.List%601.CopyTo%2A> método para copiar los miembros de esta colección en la matriz.

El ejemplo también usa el <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> método para definir los ajustes de fecha fija. Esto es similar a llamar a la <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> método, salvo que requiere el tiempo, mes y día de los parámetros de la transición.

En el ejemplo se puede probar con código como el siguiente:

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

* Que se agregarán al proyecto una referencia a System.Core.dll.

* Que se importarán los espacios de nombres siguientes:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
- [Información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md)
- [Cómo: Crear zonas horarias sin reglas de ajuste](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)
