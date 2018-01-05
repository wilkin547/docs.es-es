---
title: "Cómo: crear zonas horarias sin reglas de ajuste"
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
- time zones [.NET Framework], adjustment rule
- time zones [.NET Framework], creating
- adjustment rule [.NET Framework]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 14c5e02ce5af03d063260af19e9dd1a970a93ab6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a>Cómo: crear zonas horarias sin reglas de ajuste

La información de zona horaria exacta requerida por una aplicación no puede estar presente en un determinado sistema por varias razones:

* La zona horaria nunca se ha definido en el registro del sistema local.

* Datos sobre la zona horaria se ha modificado o quitado del registro.

* La zona horaria existe pero no tiene información precisa sobre los ajustes de zona horaria para un período histórico determinado.

En estos casos, puede llamar a la <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método para definir la zona horaria requerida por la aplicación. Puede utilizar las sobrecargas de este método para crear una zona horaria con o sin reglas de ajuste. Si la zona horaria admite el horario de verano, puede definir ajustes con cualquier reglas de ajuste fijas o flotantes. (Para obtener definiciones de estos términos, vea la sección "Terminología de zonas horarias" en [información general de la zona horaria](../../../docs/standard/datetime/time-zone-overview.md).)

> [!IMPORTANT]
> Zonas horarias personalizadas creadas mediante una llamada a la <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método no se agregan al registro. En su lugar, puede tener acceso solo mediante la referencia de objeto devuelta por la <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> llamada al método.

Este tema muestra cómo crear una zona horaria sin reglas de ajuste. Para crear una zona horaria que es compatible con las reglas de ajuste del horario de verano, vea [Cómo: crear zonas horarias con reglas de ajuste](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).

### <a name="to-create-a-time-zone-without-adjustment-rules"></a>Para crear una zona horaria sin reglas de ajuste

1. Definir nombre para mostrar de la zona horaria.

   El nombre para mostrar sigue un formato bastante estándar en el que se encierra entre paréntesis desplazamiento de la zona horaria de hora Universal coordinada (UTC) y va seguido de una cadena que identifica la zona horaria, uno o más de las ciudades de la zona horaria, o uno o varios de lo cou movimientos o regiones de la zona horaria.

2. Defina el nombre de hora estándar de la zona horaria. Normalmente, esta cadena también se utiliza como identificador de la zona horaria.

3. Si desea utilizar un identificador diferente que el nombre de la zona horaria estándar, defina el identificador de zona horaria.

4. Crear una instancia de un <xref:System.TimeSpan> objeto que define el desplazamiento de la zona horaria a la hora UTC. Zonas horarias con horas posteriores a la hora UTC tienen un desplazamiento positivo. Zonas horarias con tiempos anteriores a la hora UTC tienen una diferencia negativa.

5. Llame a la <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> método para crear una instancia de la nueva zona horaria.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se define una zona horaria personalizada para Mawson, Antártida, que no tiene ninguna regla de ajuste.

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

La cadena asignada a la <xref:System.TimeZoneInfo.DisplayName%2A> propiedad sigue un formato estándar en el que el desplazamiento de la zona horaria a la hora UTC va seguido de una descripción de la zona horaria.

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

* Que se agregará al proyecto una referencia a System.Core.dll.

* Que se importarán los espacios de nombres siguientes:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>Vea también

[Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
[información general de la zona horaria](../../../docs/standard/datetime/time-zone-overview.md)
[Cómo: crear zonas horarias con reglas de ajuste](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)
