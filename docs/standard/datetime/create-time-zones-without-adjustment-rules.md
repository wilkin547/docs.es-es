---
title: Procedimiento para crear zonas horarias sin reglas de ajuste
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], adjustment rule
- time zones [.NET Framework], creating
- adjustment rule [.NET Framework]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb3ffc7b6f1f7baec7ce6beb5a50b706ff78bfa1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026554"
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a>Procedimiento para crear zonas horarias sin reglas de ajuste

La información de zona horaria exacta requerida por una aplicación puede no encontrarse en un sistema determinado por varias razones:

* Nunca se definió la zona horaria en el registro del sistema local.

* Datos sobre la zona horaria se ha modificado o quitado del registro.

* La zona horaria existe pero no tiene información precisa sobre los ajustes de zona horaria para un período histórico determinado.

En estos casos, puede llamar a la <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método para definir la zona horaria requerida por la aplicación. Puede utilizar las sobrecargas de este método para crear una zona horaria con o sin reglas de ajuste. Si la zona horaria admite el horario de verano, puede definir los ajustes con cualquier reglas de ajuste fija o flotante. (Para obtener definiciones de estos términos, vea la sección "Terminología de zona horaria" en [Introducción a zona horaria](../../../docs/standard/datetime/time-zone-overview.md).)

> [!IMPORTANT]
> Zonas horarias personalizadas creadas mediante una llamada a la <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método no se agregan al registro. En su lugar, puede obtenerse únicamente a través de la referencia de objeto devuelta por la <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> llamada al método.

En este tema se muestra cómo crear una zona horaria sin reglas de ajuste. Para crear una zona horaria que es compatible con las reglas de ajuste al horario de verano, vea [Cómo: Creación de zonas horarias con reglas de ajuste](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).

### <a name="to-create-a-time-zone-without-adjustment-rules"></a>Para crear una zona horaria sin reglas de ajuste

1. Definir el nombre para mostrar de la zona horaria.

   El nombre para mostrar sigue un formato bastante estándar en el que se encierra entre paréntesis el desplazamiento de la zona horaria de hora Universal coordinada (UTC) y seguido de una cadena que identifica la zona horaria, uno o más de las ciudades de la zona horaria o uno o varios de lo cou movimientos o regiones en la zona horaria.

2. Defina el nombre de la hora de la zona horaria estándar. Normalmente, esta cadena también se utiliza como identificador de la zona horaria.

3. Si desea utilizar un identificador diferente que el nombre de la zona horaria estándar, definir el identificador de zona horaria.

4. Crear una instancia de un <xref:System.TimeSpan> objeto que define el desplazamiento de la zona horaria a la hora UTC. Zonas horarias con horas posteriores a la hora UTC tienen una diferencia positiva. Zonas horarias con tiempos anteriores a la hora UTC tienen una diferencia negativa.

5. Llame a la <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> método para crear una instancia de la nueva zona horaria.

## <a name="example"></a>Ejemplo

El ejemplo siguiente define una zona horaria personalizada para Mawson, Antártida, que no tiene ninguna regla de ajuste.

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

La cadena asignada a la <xref:System.TimeZoneInfo.DisplayName%2A> propiedad sigue un formato estándar en que el desplazamiento de la zona horaria a la hora UTC va seguido de una descripción detallada de la zona horaria.

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

* Que se agregarán al proyecto una referencia a System.Core.dll.

* Que se importarán los espacios de nombres siguientes:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
- [Información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md)
- [Cómo: Creación de zonas horarias con reglas de ajuste](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)
