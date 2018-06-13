---
title: 'Cómo: crear zonas horarias con reglas de ajuste'
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
ms.openlocfilehash: c63b93e0dc587571605edb305979b8f97bf54cb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33576499"
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a>Cómo: crear zonas horarias con reglas de ajuste

La información de zona horaria exacta requerida por una aplicación no puede estar presente en un determinado sistema por varias razones:

* La zona horaria nunca se ha definido en el registro del sistema local.

* Datos sobre la zona horaria se ha modificado o quitado del registro.

* La zona horaria no tiene información precisa sobre los ajustes de zona horaria para un período histórico determinado.

En estos casos, puede llamar a la <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método para definir la zona horaria requerida por la aplicación. Puede utilizar las sobrecargas de este método para crear una zona horaria con o sin reglas de ajuste. Si la zona horaria admite el horario de verano, puede definir ajustes con cualquier reglas de ajuste fijas o flotantes. (Para obtener definiciones de estos términos, vea la sección "Terminología de zonas horarias" en [información general de la zona horaria](../../../docs/standard/datetime/time-zone-overview.md).)

> [!IMPORTANT]
> Zonas horarias personalizadas creadas mediante una llamada a la <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método no se agregan al registro. En su lugar, puede tener acceso solo mediante la referencia de objeto devuelta por la <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> llamada al método.

Este tema muestra cómo crear una zona horaria con reglas de ajuste. Para crear una zona horaria que no es compatible con las reglas de ajuste del horario de verano, vea [Cómo: crear zonas horarias sin reglas de ajuste](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md).

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a>Para crear una zona horaria con reglas de ajuste flotantes

1. Para cada ajuste (es decir, para cada transición fuera de y realizar copias al horario estándar en un intervalo de tiempo determinado), haga lo siguiente:

    1. Definir el tiempo de transición inicial para el ajuste de zona horaria.

       Debe llamar a la <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> método y pásele un <xref:System.DateTime> valor que define el tiempo de la transición, un valor entero que define el mes de la transición, un valor entero que define la semana en que se produce la transición, y un <xref:System.DayOfWeek> valor que define el día de la semana en que se produce la transición. Crea una instancia de esta llamada al método un <xref:System.TimeZoneInfo.TransitionTime> objeto.

    2. Definir el tiempo de transición final para el ajuste de zona horaria. Esto requiere otra llamada a la <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> método. Llamar a este método crea una instancia de un segundo <xref:System.TimeZoneInfo.TransitionTime> objeto.

    3. Llame a la <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> método y pásele el efectivo fechas inicial y final del ajuste, un <xref:System.TimeSpan> objeto que define la cantidad de tiempo en la transición y las dos <xref:System.TimeZoneInfo.TransitionTime> objetos que definen cuándo las transiciones a y desde el horario de verano se producen de tiempo. Crea una instancia de esta llamada al método un <xref:System.TimeZoneInfo.AdjustmentRule> objeto.

    4. Asigne el <xref:System.TimeZoneInfo.AdjustmentRule> objeto a una matriz de <xref:System.TimeZoneInfo.AdjustmentRule> objetos.

2. Definir nombre para mostrar de la zona horaria. El nombre para mostrar sigue un formato bastante estándar en el que se encierra entre paréntesis desplazamiento de la zona horaria de hora Universal coordinada (UTC) y va seguido de una cadena que identifica la zona horaria, uno o más de las ciudades de la zona horaria, o uno o varios de lo cou movimientos o regiones de la zona horaria.

3. Defina el nombre de hora estándar de la zona horaria. Normalmente, esta cadena también se utiliza como identificador de la zona horaria.

4. Defina el nombre del horario de verano de la zona horaria.

5. Si desea utilizar un identificador diferente que el nombre de la zona horaria estándar, defina el identificador de zona horaria.

6. Crear una instancia de un <xref:System.TimeSpan> objeto que define el desplazamiento de la zona horaria a la hora UTC. Zonas horarias con horas posteriores a la hora UTC tienen un desplazamiento positivo. Zonas horarias con tiempos anteriores a la hora UTC tienen una diferencia negativa.

7. Llame a la <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> método para crear una instancia de la nueva zona horaria.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se define una zona horaria estándar Central para los Estados Unidos que incluye reglas de ajuste para una amplia variedad de intervalos de tiempo desde 1918 hasta el presente.

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

La zona horaria creada en este ejemplo tiene varias reglas de ajuste. Debe tener cuidado para asegurarse de que el inicio efectiva y fechas de finalización de cualquier regla de ajuste no se superponen con las fechas de otra regla de ajuste. Si no hay una superposición, un <xref:System.InvalidTimeZoneException> se produce.

Para reglas de ajuste flotantes, se pasa el valor 5 a la `week` parámetro de la <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> método para indicar que tiene lugar la transición en la última semana de un mes determinado.

En la creación de la matriz de <xref:System.TimeZoneInfo.AdjustmentRule> objetos que se va a usar en el <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> llamada al método, el código podría inicializar la matriz al tamaño requerido por el número de los ajustes que deben crearse para la zona horaria. En su lugar, este ejemplo de código llama a la <xref:System.Collections.Generic.List%601.Add%2A> método para agregar cada regla de ajuste a un tipo genérico <xref:System.Collections.Generic.List%601> colección de <xref:System.TimeZoneInfo.AdjustmentRule> objetos. El código, a continuación, llama a la <xref:System.Collections.Generic.List%601.CopyTo%2A> método para copiar los miembros de esta colección en la matriz.

El ejemplo también usa el <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> método para definir los ajustes de fecha fija. Esto es similar a llamar a la <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> método, salvo que requiere el tiempo, mes y día de los parámetros de transición.

En el ejemplo se puede probar mediante código como el siguiente:

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

* Que se agregará al proyecto una referencia a System.Core.dll.

* Que se importarán los espacios de nombres siguientes:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>Vea también

[Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
[información general de la zona horaria](../../../docs/standard/datetime/time-zone-overview.md)
[Cómo: crear zonas horarias sin reglas de ajuste](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)
