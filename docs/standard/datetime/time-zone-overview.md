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
ms.openlocfilehash: 9cb50357931cb22fd2862ba7558154a4782e4557
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281042"
---
# <a name="time-zone-overview"></a>Información general sobre zonas horarias

La <xref:System.TimeZoneInfo> clase simplifica la creación de aplicaciones que tienen en cuenta la zona horaria. La <xref:System.TimeZone> clase permite trabajar con la zona horaria local y la hora universal coordinada (UTC). La <xref:System.TimeZoneInfo> clase admite ambas zonas y cualquier zona horaria sobre la que la información está predefinida en el registro. También puede utilizar <xref:System.TimeZoneInfo> para definir zonas horarias personalizadas en las que el sistema no tiene información.

## <a name="time-zone-essentials"></a>Aspectos básicos de la zona horaria

Una zona horaria es una región geográfica en la que se usa la misma hora. Normalmente, pero no siempre, las zonas horarias adyacentes tienen una hora de diferencia. La hora de cualquier zona horaria del mundo se puede expresar como un desplazamiento a partir de la hora universal coordinada (UTC).

Muchas zonas horarias del mundo admiten el horario de verano. El horario de verano intenta maximizar las horas de luz diarias al adelantar la hora una hora en primavera o a principios de verano y regresar a la hora normal (o estándar) a finales de verano o en otoño. Estos cambios en relación con el horario estándar se conocen como reglas de ajuste.

El cambio al horario de verano o desde este en una zona horaria determinada puede definirse con una regla de ajuste fija o con una regla de ajuste flotante. Una regla de ajuste fija establece una fecha concreta en la que se produce la transición hacia o desde el horario de verano cada año. Por ejemplo, una transición desde el horario de verano hacia el horario estándar que se produce cada año el 25 de octubre sigue una regla de ajuste fija. Mucho más comunes son las reglas de ajuste flotantes, que establecen un día concreto de una semana concreta de un mes determinado para la transición hacia o desde el horario de verano. Por ejemplo, una transición desde el horario estándar hacia el horario de verano que se produce el tercer domingo de marzo sigue una regla de ajuste flotante.

Para las zonas horarias que admiten reglas de ajuste, el cambio de horario de verano crea dos tipos de horas anómalas: horas no válidas y horas ambiguas. Una hora no válida es una hora no existente creada por la transición desde el horario estándar hacia el horario de verano. Por ejemplo, si se produce esta transición en un día determinado a las 2:00 A.M. y hace que la hora cambie a las 3:00 A.M., cualquier intervalo de tiempo entre las 2:00 A.M. y las 2:59:99 A.M. es no válido. Una hora ambigua es aquella que se puede asignar a dos horas diferentes en una sola zona horaria. Se crea durante la transición del horario de verano hacia el horario estándar. Por ejemplo, si se produce esta transición en un día determinado a las 2:00 A.M. y hace que la hora cambie a la 1:00 A.M., cualquier intervalo de tiempo entre la 1:00 A.M. y la 1:59:99 A.M. se puede interpretar como correspondiente a la hora estándar o correspondiente al horario de verano.

## <a name="time-zone-terminology"></a>Terminología de zona horaria

En la tabla siguiente se definen los términos usados comúnmente al trabajar con zonas horarias y desarrollar aplicaciones basadas en la zona horaria.

| Término            | Definición |
| --------------- | ---------- |
| Regla de ajuste | Una regla que define cuándo se produce la transición desde el horario estándar hacia el horario de verano y desde el horario de verano hacia el horario estándar. Cada regla de ajuste tiene una fecha de inicio y de finalización que define cuándo se aplica la regla (por ejemplo, la regla de ajuste está en vigor desde el 1 de enero de 1986 hasta el 31 de diciembre de 2006), un delta (la cantidad de tiempo que cambia la hora estándar como resultado de la aplicación de la regla de ajuste) e información sobre la fecha y hora específicas que las transiciones tienen lugar durante el período de ajuste. Las transiciones pueden seguir una regla fija o una regla flotante. |
| Hora ambigua  | Una hora que se puede asignar a dos horas diferentes en una sola zona horaria. Esto sucede cuando la hora del reloj se atrasa, como durante la transición del horario de verano de una zona horaria al horario estándar. Por ejemplo, si se produce esta transición en un día determinado a las 2:00 A.M. y hace que la hora cambie a la 1:00 A.M., cualquier intervalo de tiempo entre la 1:00 A.M. y la 1:59:99 A.M. se puede interpretar como correspondiente a la hora estándar o correspondiente al horario de verano. |
| Regla fija      | Regla de ajuste que establece una fecha concreta para la transición hacia o desde el horario de verano. Por ejemplo, una transición desde el horario de verano hacia el horario estándar que se produce cada año el 25 de octubre sigue una regla de ajuste fija. |
| Regla flotante   | Regla de ajuste que establece un día concreto de una semana concreta de un mes determinado para la transición hacia o desde el horario de verano. Por ejemplo, una transición desde el horario estándar hacia el horario de verano que se produce el tercer domingo de marzo sigue una regla de ajuste flotante. |
| Hora no válida    | Hora no existente que resulta de la transición desde el horario estándar hacia el horario de verano. Esto sucede cuando la hora del reloj se adelanta, como durante la transición en una zona horaria desde el horario estándar hacia el horario de verano. Por ejemplo, si se produce esta transición en un día determinado a las 2:00 A.M. y hace que la hora cambie a las 3:00 A.M., cualquier intervalo de tiempo entre las 2:00 A.M. y las 2:59:99 A.M. es no válido. |
| Tiempo de transición | Información sobre un cambio horario concreto, como el cambio desde el horario de verano hacia el horario estándar o viceversa, en una zona horaria determinada. |

## <a name="time-zones-and-the-timezoneinfo-class"></a>Zonas horarias y la clase TimeZoneInfo

En .NET, un <xref:System.TimeZoneInfo> objeto representa una zona horaria. La <xref:System.TimeZoneInfo> clase incluye un <xref:System.TimeZoneInfo.GetAdjustmentRules%2A> método que devuelve una matriz de <xref:System.TimeZoneInfo.AdjustmentRule> objetos. Cada elemento de esta matriz proporciona información sobre la transición hacia y desde el horario de verano durante un período de tiempo determinado. (En el caso de las zonas horarias que no admiten el horario de verano, el método devuelve una matriz vacía). Cada <xref:System.TimeZoneInfo.AdjustmentRule> objeto tiene un <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionStart%2A> y una <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionEnd%2A> propiedad que define la fecha y hora concretas de la transición hacia y desde el horario de verano. La <xref:System.TimeZoneInfo.TransitionTime.IsFixedDateRule%2A> propiedad indica si esa transición es fija o flotante.

.NET se basa en la información de zona horaria proporcionada por el sistema operativo Windows y almacenada en el registro. Debido al número de zonas horarias de la tierra, no todas las zonas horarias existentes se representan en el registro. Además, dado que el registro es una estructura dinámica, se pueden agregar o quitar zonas horarias predefinidas. Por último, el registro no contiene necesariamente datos históricos de zona horaria. Por ejemplo, en Windows XP el registro contiene datos sobre un solo conjunto de ajustes de zona horaria. Windows Vista admite los datos dinámicos de zona horaria, lo que significa que una sola zona horaria puede tener varias reglas de ajuste que se aplican a intervalos específicos de años. Sin embargo, la mayoría de las zonas horarias definidas en el registro de Windows Vista y admiten el horario de verano tienen solo una o dos reglas de ajuste predefinidas.

La dependencia de la <xref:System.TimeZoneInfo> clase en el registro significa que una aplicación que tiene en cuenta la zona horaria no puede estar seguro de que se ha definido una zona horaria determinada en el registro. Por tanto, el intento de crear instancias de una zona horaria concreta (excepto la zona horaria local o la zona horaria que representa la hora UTC) debe usar el control de excepciones. También debe proporcionar algún método para permitir que la aplicación continúe si no se pueden <xref:System.TimeZoneInfo> crear instancias de un objeto necesario desde el registro.

Para controlar la ausencia de una zona horaria necesaria, la <xref:System.TimeZoneInfo> clase incluye un <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método, que puede usar para crear zonas horarias personalizadas que no se encuentran en el registro. Para obtener más información sobre cómo crear una zona horaria personalizada, consulte [Cómo: crear zonas horarias sin reglas de ajuste](create-time-zones-without-adjustment-rules.md) y [Cómo: crear zonas horarias con reglas de ajuste](create-time-zones-with-adjustment-rules.md). Además, puede utilizar el <xref:System.TimeZoneInfo.ToSerializedString%2A> método para convertir una zona horaria recién creada en una cadena y guardarla en un almacén de datos (como una base de datos, un archivo de texto, el registro o un recurso de aplicación). Después, puede utilizar el <xref:System.TimeZoneInfo.FromSerializedString%2A> método para volver a convertir esta cadena en un <xref:System.TimeZoneInfo> objeto. Para obtener más información, consulte [Cómo: guardar zonas horarias en un recurso incrustado](save-time-zones-to-an-embedded-resource.md) y [Cómo: restaurar zonas horarias desde un recurso incrustado](restore-time-zones-from-an-embedded-resource.md).

Dado que cada zona horaria se caracteriza por un desplazamiento desde la hora UTC base, así como por un desplazamiento desde la hora UTC que refleja las reglas de ajuste existentes, la hora de una zona horaria se puede convertir fácilmente en la hora de otra zona horaria. Para este propósito, el <xref:System.TimeZoneInfo> objeto incluye varios métodos de conversión, entre los que se incluyen:

- <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>, que convierte la hora UTC a la hora de una zona horaria designada.

- <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>, que convierte la hora de una zona horaria designada en una hora UTC.

- <xref:System.TimeZoneInfo.ConvertTime%2A>, que convierte la hora de una zona horaria designada en la hora de otra zona horaria designada.

- <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>, que usa identificadores de zona horaria (en lugar de <xref:System.TimeZoneInfo> objetos) como parámetros para convertir la hora de una zona horaria designada en la hora de otra zona horaria designada.

Para obtener más información sobre cómo convertir horas entre zonas horarias, consulte [Convertir horas entre zonas horarias](converting-between-time-zones.md).

## <a name="see-also"></a>Consulte también

- [Fechas, horas y zonas horarias](index.md)
