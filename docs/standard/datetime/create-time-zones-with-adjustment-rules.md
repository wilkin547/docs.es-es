---
title: Procedimiento para crear zonas horarias con reglas de ajuste
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
ms.openlocfilehash: 6ae739d3c5dd233c2129950666846979edfba370
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106676"
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a>Procedimiento para crear zonas horarias con reglas de ajuste

La información precisa de zona horaria requerida por una aplicación puede no estar presente en un sistema determinado por varias razones:

- La zona horaria nunca se ha definido en el registro del sistema local.

- Los datos sobre la zona horaria se han modificado o eliminado del registro.

- La zona horaria no tiene información precisa sobre los ajustes de zona horaria para un determinado período histórico.

En estos casos, puede llamar <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> al método para definir la zona horaria requerida por la aplicación. Puede usar las sobrecargas de este método para crear una zona horaria con o sin reglas de ajuste. Si la zona horaria admite el horario de verano, puede definir ajustes con reglas de ajuste fijas o flotantes. (Para obtener definiciones de estos términos, consulte la sección "terminología de zona horaria" en [información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md)).

> [!IMPORTANT]
> Las zonas horarias personalizadas creadas <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> llamando al método no se agregan al registro. En su lugar, solo se puede tener acceso a ellos a través de la referencia <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> de objeto devuelta por la llamada al método.

En este tema se muestra cómo crear una zona horaria con reglas de ajuste. Para crear una zona horaria que no admita reglas de ajuste del horario de verano, [consulte How to: Cree zonas horarias sin reglas](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)de ajuste.

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a>Para crear una zona horaria con reglas de ajuste flotante

1. Para cada ajuste (es decir, para cada transición desde y hacia atrás a la hora estándar en un intervalo de tiempo determinado), haga lo siguiente:

    1. Defina el tiempo de transición inicial para el ajuste de zona horaria.

       Debe llamar al <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> método y pasarle un <xref:System.DateTime> valor que defina la hora de la transición, un valor entero que define el mes de la transición, un valor entero que define la semana en la que se produce la transición y un <xref:System.DayOfWeek> valor que define el día de la semana en el que se produce la transición. Esta llamada al método crea una <xref:System.TimeZoneInfo.TransitionTime> instancia de un objeto.

    2. Defina el tiempo de transición final para el ajuste de zona horaria. Esto requiere otra llamada al <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> método. Esta llamada al método crea una instancia <xref:System.TimeZoneInfo.TransitionTime> de un segundo objeto.

    3. Llame al <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> método y pásele las fechas de inicio y finalización vigentes del ajuste, <xref:System.TimeSpan> un objeto que define la cantidad de tiempo de la transición y los dos <xref:System.TimeZoneInfo.TransitionTime> objetos que definen Cuándo se realiza la transición hacia y desde el horario de verano. tiempo de espera. Esta llamada al método crea una <xref:System.TimeZoneInfo.AdjustmentRule> instancia de un objeto.

    4. Asigne el <xref:System.TimeZoneInfo.AdjustmentRule> objeto a una matriz de <xref:System.TimeZoneInfo.AdjustmentRule> objetos.

2. Defina el nombre para mostrar de la zona horaria. El nombre para mostrar sigue un formato bastante estándar en el que el desplazamiento de la zona horaria de la hora universal coordinada (UTC) se escribe entre paréntesis y va seguido de una cadena que identifica la zona horaria, una o varias de las ciudades de la zona horaria, o una o varias de las COU movimientos o regiones de la zona horaria.

3. Defina el nombre de la hora estándar de la zona horaria. Normalmente, esta cadena también se usa como identificador de la zona horaria.

4. Defina el nombre de la hora de verano de la zona horaria.

5. Si desea usar un identificador diferente del nombre estándar de la zona horaria, defina el identificador de zona horaria.

6. Cree una instancia <xref:System.TimeSpan> de un objeto que defina el desplazamiento de la zona horaria con respecto a la hora UTC. Las zonas horarias con horas que son posteriores a la hora UTC tienen un desplazamiento positivo. Las zonas horarias con horas anteriores a la hora UTC tienen un desplazamiento negativo.

7. Llame al <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> método para crear una instancia de la nueva zona horaria.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se define una zona horaria estándar central para el Estados Unidos que incluye reglas de ajuste para una variedad de intervalos de tiempo de 1918 a la presente.

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

La zona horaria creada en este ejemplo tiene varias reglas de ajuste. Se debe tener cuidado para asegurarse de que las fechas de inicio y finalización vigentes de cualquier regla de ajuste no se superpongan con las fechas de otra regla de ajuste. Si hay una superposición, se <xref:System.InvalidTimeZoneException> produce una excepción.

En el caso de las reglas de ajuste flotantes, se `week` pasa el valor <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> 5 al parámetro del método para indicar que la transición se produce en la última semana de un mes determinado.

Al crear la matriz de <xref:System.TimeZoneInfo.AdjustmentRule> objetos que se va a <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> usar en la llamada al método, el código podría inicializar la matriz con el tamaño requerido por el número de ajustes que se va a crear para la zona horaria. En su lugar, en este ejemplo de <xref:System.Collections.Generic.List%601.Add%2A> código se llama al método para agregar cada regla <xref:System.Collections.Generic.List%601> de ajuste <xref:System.TimeZoneInfo.AdjustmentRule> a una colección genérica de objetos. A continuación, el código <xref:System.Collections.Generic.List%601.CopyTo%2A> llama al método para copiar los miembros de esta colección en la matriz.

En el ejemplo también se <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> usa el método para definir los ajustes de fecha fija. Esto es similar a llamar al <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> método, con la salvedad de que solo requiere la hora, el mes y el día de los parámetros de transición.

El ejemplo se puede probar mediante código como el siguiente:

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

- Que se importen los espacios de nombres siguientes:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
- [Información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md)
- [Cómo: Crear zonas horarias sin reglas de ajuste](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)
