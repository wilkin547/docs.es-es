---
title: Información general sobre zonas horarias
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zones [.NET Framework], about time zones
- transition time [.NET Framework]
- TimeZoneInfo class, about TimeZoneInfo class
- time zones [.NET Framework], creating
- invalid time [.NET Framework]
- fixed rule [.NET Framework]
- ambiguous time [.NET Framework]
- floating rule [.NET Framework]
- daylight saving time [.NET Framework]
- adjustment rule [.NET Framework]
- time zones [.NET Framework], terminology
ms.assetid: c4b7ed01-5e38-4959-a3b6-ef9765d6ccf1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0eb24c7c4f2c60a9c16d903ab1e845b058e280f7
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2018
ms.locfileid: "46493417"
---
# <a name="time-zone-overview"></a>Información general sobre zonas horarias

La <xref:System.TimeZoneInfo> clase simplifica la creación de aplicaciones basadas en la zona horaria. La <xref:System.TimeZone> clase permite trabajar con la zona horaria local y la hora Universal coordinada (UTC). La <xref:System.TimeZoneInfo> clase es compatible con ambas de estas zonas así como cualquier zona horaria sobre qué información está predefinido en el registro. También puede usar <xref:System.TimeZoneInfo> para definir las zonas horarias personalizadas que el sistema no tiene ninguna información acerca de.

## <a name="time-zone-essentials"></a>Fundamentos de la zona horaria

Una zona horaria es una región geográfica en la que se usa la misma hora. Normalmente, pero no siempre, las zonas horarias adyacentes tienen una hora de diferencia. La hora de cualquier zona horaria del mundo se puede expresar como un desplazamiento a partir de la hora universal coordinada (UTC).

Muchas zonas horarias del mundo admiten el horario de verano. El horario de verano intenta maximizar las horas de luz diarias al adelantar la hora una hora en primavera o a principios de verano y regresar a la hora normal (o estándar) a finales de verano o en otoño. Estos cambios en relación con el horario estándar se conocen como reglas de ajuste.

El cambio al horario de verano o desde este en una zona horaria determinada puede definirse con una regla de ajuste fija o con una regla de ajuste flotante. Una regla de ajuste fija establece una fecha concreta en la que se produce la transición hacia o desde el horario de verano cada año. Por ejemplo, una transición desde el horario de verano hacia el horario estándar que se produce cada año el 25 de octubre sigue una regla de ajuste fija. Mucho más comunes son las reglas de ajuste flotantes, que establecen un día concreto de una semana concreta de un mes determinado para la transición hacia o desde el horario de verano. Por ejemplo, una transición desde el horario estándar hacia el horario de verano que se produce el tercer domingo de marzo sigue una regla de ajuste flotante.

Para las zonas horarias que admiten reglas de ajuste, el cambio de horario de verano crea dos tipos de horas anómalas: horas no válidas y horas ambiguas. Una hora no válida es una hora no existente creada por la transición desde el horario estándar hacia el horario de verano. Por ejemplo, si se produce esta transición en un día determinado a las 2:00 A.M. y hace que la hora cambie a las 3:00 A.M., cualquier intervalo de tiempo entre las 2:00 A.M. y las 2:59:99 A.M. es no válido. Una hora ambigua es aquella que se puede asignar a dos horas diferentes en una sola zona horaria. Se crea durante la transición del horario de verano hacia el horario estándar. Por ejemplo, si se produce esta transición en un día determinado a las 2:00 A.M. y hace que la hora cambie a la 1:00 A.M., cualquier intervalo de tiempo entre la 1:00 A.M. y la 1:59:99 A.M. se puede interpretar como correspondiente a la hora estándar o correspondiente al horario de verano.

## <a name="time-zone-terminology"></a>Terminología de zona horaria

En la tabla siguiente se definen los términos usados comúnmente al trabajar con zonas horarias y desarrollar aplicaciones basadas en la zona horaria.

| Término            | de esquema JSON |
| --------------- | ---------- |
| Regla de ajuste | Una regla que define cuándo se produce la transición desde el horario estándar hacia el horario de verano y desde el horario de verano hacia el horario estándar. Cada regla de ajuste tiene una fecha de inicio y finalización que define la regla está en su lugar (por ejemplo, la regla de ajuste está vigente desde el 1 de enero de 1986 al 31 de diciembre de 2006), un delta (la cantidad de tiempo por la que se cambia la hora estándar como resultado de la aplicación de th regla de ajuste e) e información acerca de la fecha y hora específicas que son las transiciones que se produzca durante el período de ajuste. Las transiciones pueden seguir una regla fija o una regla flotante. |
| Hora ambigua  | Una hora que se puede asignar a dos horas diferentes en una sola zona horaria. Esto sucede cuando la hora del reloj se atrasa, como durante la transición del horario de verano de una zona horaria al horario estándar. Por ejemplo, si se produce esta transición en un día determinado a las 2:00 A.M. y hace que la hora cambie a la 1:00 A.M., cualquier intervalo de tiempo entre la 1:00 A.M. y la 1:59:99 A.M. se puede interpretar como correspondiente a la hora estándar o correspondiente al horario de verano. |
| Regla fija      | Regla de ajuste que establece una fecha concreta para la transición hacia o desde el horario de verano. Por ejemplo, una transición desde el horario de verano hacia el horario estándar que se produce cada año el 25 de octubre sigue una regla de ajuste fija. |
| Regla flotante   | Regla de ajuste que establece un día concreto de una semana concreta de un mes determinado para la transición hacia o desde el horario de verano. Por ejemplo, una transición desde el horario estándar hacia el horario de verano que se produce el tercer domingo de marzo sigue una regla de ajuste flotante. |
| Hora no válida    | Hora no existente que resulta de la transición desde el horario estándar hacia el horario de verano. Esto sucede cuando la hora del reloj se adelanta, como durante la transición en una zona horaria desde el horario estándar hacia el horario de verano. Por ejemplo, si se produce esta transición en un día determinado a las 2:00 A.M. y hace que la hora cambie a las 3:00 A.M., cualquier intervalo de tiempo entre las 2:00 A.M. y las 2:59:99 A.M. es no válido. |
| Tiempo de transición | Información sobre un cambio horario concreto, como el cambio desde el horario de verano hacia el horario estándar o viceversa, en una zona horaria determinada. |

## <a name="time-zones-and-the-timezoneinfo-class"></a>Las zonas horarias y la clase TimeZoneInfo

En. NET, un <xref:System.TimeZoneInfo> objeto representa una zona horaria. El <xref:System.TimeZoneInfo> clase incluye un <xref:System.TimeZoneInfo.GetAdjustmentRules%2A> método que devuelve una matriz de <xref:System.TimeZoneInfo.AdjustmentRule> objetos. Cada elemento de esta matriz proporciona información sobre la transición al horario de verano para un período de tiempo determinado. (Para las zonas horarias que no admiten el horario de verano, el método devuelve una matriz vacía). Cada <xref:System.TimeZoneInfo.AdjustmentRule> objeto tiene un <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionStart%2A> y un <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionEnd%2A> propiedad que define la fecha y hora concretas de la transición hacia y desde el horario de verano. El <xref:System.TimeZoneInfo.TransitionTime.IsFixedDateRule%2A> propiedad indica si esa transición es fijo o flotante.

.NET se basa en información de zona horaria proporcionada por el sistema operativo de Windows y almacena en el registro. Debido al número de zonas horarias del mundo, no todas las zonas horarias existentes se representan en el registro. Además, dado que el registro es una estructura dinámica, zonas horarias predefinidas puede sumar o quita de ésta. Por último, el registro no contiene necesariamente los datos históricos de zona horaria. Por ejemplo, en Windows XP, el registro contiene datos sobre un solo conjunto de ajustes de zona horaria. Windows Vista es compatible con los datos de zona horaria dinámica, lo que significa que una sola zona horaria puede tener varias reglas de ajuste que se aplican a intervalos específicos de años. Sin embargo, la mayoría de las zonas horarias definidas en la Vista de Windows del registro y soporte técnico del horario de verano tener sólo uno o dos reglas de ajuste predefinidas.

La dependencia de la <xref:System.TimeZoneInfo> clase en el registro significa que una aplicación compatible con la zona horaria no puede estar seguro de que una zona horaria determinada se define en el registro. Por tanto, el intento de crear instancias de una zona horaria concreta (excepto la zona horaria local o la zona horaria que representa la hora UTC) debe usar el control de excepciones. Además, debe proporcionar algún método para permitir que la aplicación continúe si es necesaria <xref:System.TimeZoneInfo> no pueden crearse instancias de objeto del registro.

Para controlar la ausencia de una zona horaria necesaria, el <xref:System.TimeZoneInfo> clase incluye un <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método, que puede usar para crear zonas horarias personalizadas que no se encuentran en el registro. Para obtener más información sobre la creación de una zona horaria personalizada, vea [Cómo: crear zonas horarias sin reglas de ajuste](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) y [Cómo: crear zonas horarias con reglas de ajuste](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md). Además, puede usar el <xref:System.TimeZoneInfo.ToSerializedString%2A> método para convertir una zona horaria recién creada en una cadena y guardarla en un almacén de datos (por ejemplo, una base de datos, un archivo de texto, el registro o un recurso de aplicación). A continuación, puede usar el <xref:System.TimeZoneInfo.FromSerializedString%2A> nuevo método para convertir esta cadena a un <xref:System.TimeZoneInfo> objeto. Para obtener más información, consulte [Cómo: guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) y [Cómo: restaurar zonas horarias de un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).

Dado que cada zona horaria se caracteriza por un desplazamiento desde la hora UTC base, así como por un desplazamiento desde la hora UTC que refleja las reglas de ajuste existentes, la hora de una zona horaria se puede convertir fácilmente en la hora de otra zona horaria. Para este propósito, el <xref:System.TimeZoneInfo> objeto incluye varios métodos de conversión, como:

* <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>, que convierte la hora UTC a la hora de una zona horaria designada.

* <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>, que convierte la hora de una zona horaria designada en la hora UTC.

* <xref:System.TimeZoneInfo.ConvertTime%2A>, que convierte la hora de una zona horaria designada en la hora de otra zona horaria designada.

* <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>, que usa identificadores de zona horaria (en lugar de <xref:System.TimeZoneInfo> objetos) como parámetros para convertir la hora de una zona horaria designada en la hora de otra zona horaria designada.

Para obtener más información sobre cómo convertir horas entre zonas horarias, consulte [Convertir horas entre zonas horarias](../../../docs/standard/datetime/converting-between-time-zones.md).

## <a name="see-also"></a>Vea también

* [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
