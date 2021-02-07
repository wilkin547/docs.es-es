---
description: 'Más información acerca de cómo: crear zonas horarias sin reglas de ajuste'
title: Procedimiento para crear zonas horarias sin reglas de ajuste
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], adjustment rule
- time zones [.NET], creating
- adjustment rule [.NET]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
ms.openlocfilehash: c2d1f2d2ea21c53c6a3b41603be4f31ec5442a30
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99702735"
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a>Procedimiento para crear zonas horarias sin reglas de ajuste

La información precisa de zona horaria requerida por una aplicación puede no estar presente en un sistema determinado por varias razones:

- La zona horaria nunca se ha definido en el registro del sistema local.

- Los datos sobre la zona horaria se han modificado o eliminado del registro.

- La zona horaria existe pero no tiene información precisa sobre los ajustes de zona horaria para un determinado período histórico.

En estos casos, puede llamar al <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método para definir la zona horaria requerida por la aplicación. Puede usar las sobrecargas de este método para crear una zona horaria con o sin reglas de ajuste. Si la zona horaria admite el horario de verano, puede definir ajustes con reglas de ajuste fijas o flotantes. (Para obtener definiciones de estos términos, consulte la sección "terminología de zona horaria" en [información general sobre zonas horarias](time-zone-overview.md)).

> [!IMPORTANT]
> Las zonas horarias personalizadas creadas llamando al <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método no se agregan al registro. En su lugar, solo se puede tener acceso a ellos a través de la referencia de objeto devuelta por la <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> llamada al método.

En este tema se muestra cómo crear una zona horaria sin reglas de ajuste. Para crear una zona horaria que admita reglas de ajuste del horario de verano, consulte [Cómo: crear zonas horarias con reglas de ajuste](create-time-zones-with-adjustment-rules.md).

### <a name="to-create-a-time-zone-without-adjustment-rules"></a>Para crear una zona horaria sin reglas de ajuste

1. Defina el nombre para mostrar de la zona horaria.

   El nombre para mostrar sigue un formato bastante estándar en el que el desplazamiento de la zona horaria de la hora universal coordinada (UTC) se incluye entre paréntesis y va seguido de una cadena que identifica la zona horaria, una o varias de las ciudades de la zona horaria o uno o varios de los países o regiones de la zona horaria.

2. Defina el nombre de la hora estándar de la zona horaria. Normalmente, esta cadena también se usa como identificador de la zona horaria.

3. Si desea usar un identificador diferente del nombre estándar de la zona horaria, defina el identificador de zona horaria.

4. Cree una instancia <xref:System.TimeSpan> de un objeto que defina el desplazamiento de la zona horaria con respecto a la hora UTC. Las zonas horarias con horas que son posteriores a la hora UTC tienen un desplazamiento positivo. Las zonas horarias con horas anteriores a la hora UTC tienen un desplazamiento negativo.

5. Llame al <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> método para crear una instancia de la nueva zona horaria.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se define una zona horaria personalizada para Mawson, Antártida, que no tiene reglas de ajuste.

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

La cadena asignada a la <xref:System.TimeZoneInfo.DisplayName%2A> propiedad sigue un formato estándar en el que el desplazamiento de la zona horaria con respecto a la hora UTC va seguido de una descripción detallada de la zona horaria.

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

- Que se importen los espacios de nombres siguientes:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](index.md)
- [Información general sobre zonas horarias](time-zone-overview.md)
- [Cómo: crear zonas horarias con reglas de ajuste](create-time-zones-with-adjustment-rules.md)
