---
title: "Información general sobre zonas horarias"
description: "Información general sobre zonas horarias"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: e3a10f62-d403-4441-8621-adc964e32c07
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: 31a4582c28c208a7a3d86259b360e3472b851249

---

# <a name="time-zone-overview"></a>Información general sobre zonas horarias

La clase [System.TimeZoneInfo](xref:System.TimeZoneInfo) simplifica la creación de aplicaciones que tengan en cuenta la zona horaria. La clase [TimeZoneInfo](xref:System.TimeZoneInfo) permite trabajar con la zona horaria local y la hora universal coordinada (UTC), además de cualquier zona horaria cuya información esté predefinida en el registro. También puede usar [TimeZoneInfo](xref:System.TimeZoneInfo) para definir las zonas horarias personalizadas sobre las que el sistema no tiene información.

## <a name="time-zone-essentials"></a>Fundamentos de la zona horaria

Una zona horaria es una región geográfica en la que se usa la misma hora. Normalmente, pero no siempre, las zonas horarias adyacentes tienen una hora de diferencia. La hora de cualquier zona horaria del mundo se puede expresar como un desplazamiento a partir de la hora universal coordinada (UTC).

Muchas zonas horarias del mundo admiten el horario de verano. El horario de verano intenta maximizar las horas de luz diarias al adelantar la hora una hora en primavera o a principios de verano y regresar a la hora normal (o estándar) a finales de verano o en otoño. Estos cambios en relación con el horario estándar se conocen como reglas de ajuste.

El cambio al horario de verano o desde este en una zona horaria determinada puede definirse con una regla de ajuste fija o con una regla de ajuste flotante. Una regla de ajuste fija establece una fecha concreta en la que se produce la transición hacia o desde el horario de verano cada año. Por ejemplo, una transición desde el horario de verano hacia el horario estándar que se produce cada año el 25 de octubre sigue una regla de ajuste fija. Mucho más comunes son las reglas de ajuste flotantes, que establecen un día concreto de una semana concreta de un mes determinado para la transición hacia o desde el horario de verano. Por ejemplo, una transición desde el horario estándar hacia el horario de verano que se produce el tercer domingo de marzo sigue una regla de ajuste flotante.

Para las zonas horarias que admiten reglas de ajuste, el cambio de horario de verano crea dos tipos de horas anómalas: horas no válidas y horas ambiguas. Una hora no válida es una hora no existente creada por la transición desde el horario estándar hacia el horario de verano. Por ejemplo, si se produce esta transición en un día determinado a las 2:00 A.M. y hace que la hora cambie a las 3:00 A.M., cualquier intervalo de tiempo entre las 2:00 A.M. y las 2:59:99 A.M. es no válido. Una hora ambigua es aquella que se puede asignar a dos horas diferentes en una sola zona horaria. Se crea durante la transición del horario de verano hacia el horario estándar. Por ejemplo, si se produce esta transición en un día determinado a las 2:00 A.M. y hace que la hora cambie a la 1:00 A.M., cualquier intervalo de tiempo entre la 1:00 A.M. y la 1:59:99 A.M. se puede interpretar como correspondiente a la hora estándar o correspondiente al horario de verano. 

## <a name="time-zone-terminology"></a>Terminología de zona horaria

En la tabla siguiente se definen los términos usados comúnmente al trabajar con zonas horarias y desarrollar aplicaciones basadas en la zona horaria.

Término | Definición
---- | ----------
Regla de ajuste | Una regla que define cuándo se produce la transición desde el horario estándar hacia el horario de verano y desde el horario de verano hacia el horario estándar. Cada regla de ajuste tiene una fecha de inicio y finalización que define cuándo está vigente la regla (por ejemplo, la regla de ajuste está vigente desde el 1 de enero de 1986 hasta el 31 de diciembre de 2020), un delta (la cantidad de tiempo que varía el horario estándar como resultado de la aplicación de la regla de ajuste) e información acerca de la fecha y hora específicas en las que se producen las transiciones durante el período de ajuste. Las transiciones pueden seguir una regla fija o una regla flotante.
Hora ambigua | Una hora que se puede asignar a dos horas diferentes en una sola zona horaria. Esto sucede cuando la hora del reloj se atrasa, como durante la transición del horario de verano de una zona horaria al horario estándar. Por ejemplo, si se produce esta transición en un día determinado a las 2:00 A.M. y hace que la hora cambie a la 1:00 A.M., cualquier intervalo de tiempo entre la 1:00 A.M. y la 1:59:99 A.M. se puede interpretar como correspondiente a la hora estándar o correspondiente al horario de verano. 
Regla fija | Regla de ajuste que establece una fecha concreta para la transición hacia o desde el horario de verano. Por ejemplo, una transición desde el horario de verano hacia el horario estándar que se produce cada año el 25 de octubre sigue una regla de ajuste fija.
Regla flotante | Regla de ajuste que establece un día concreto de una semana concreta de un mes determinado para la transición hacia o desde el horario de verano. Por ejemplo, una transición desde el horario estándar hacia el horario de verano que se produce el tercer domingo de marzo sigue una regla de ajuste flotante.
Hora no válida | Hora no existente que resulta de la transición desde el horario estándar hacia el horario de verano. Esto sucede cuando la hora del reloj se adelanta, como durante la transición en una zona horaria desde el horario estándar hacia el horario de verano. Por ejemplo, si se produce esta transición en un día determinado a las 2:00 A.M. y hace que la hora cambie a las 3:00 A.M., cualquier intervalo de tiempo entre las 2:00 A.M. y las 2:59:99 A.M. es no válido.
Tiempo de transición | Información sobre un cambio horario concreto, como el cambio desde el horario de verano hacia el horario estándar o viceversa, en una zona horaria determinada.

## <a name="time-zones-and-the-timezoneinfo-class"></a>Zonas horarias y la clase TimeZoneInfo

En. NET, un objeto [System.TimeZoneInfo](xref:System.TimeZoneInfo) representa una zona horaria que se basa en la información proporcionada por el sistema operativo. El que la clase [TimeZoneInfo](xref:System.TimeZoneInfo) dependa del sistema operativo significa que una aplicación que tenga en cuenta la zona horaria no puede dar por hecho que una zona horaria determinada se haya definido en todos los sistemas operativos. Por tanto, el intento de crear instancias de una zona horaria concreta (excepto la zona horaria local o la zona horaria que representa la hora UTC) debe usar el control de excepciones. También debe proporcionar algún método para permitir que la aplicación pueda continuar si no pueden crearse instancias del objeto [TimeZoneInfo](xref:System.TimeZoneInfo) requerido.

Dado que cada zona horaria se caracteriza por un desplazamiento desde la hora UTC base, así como por un desplazamiento desde la hora UTC que refleja las reglas de ajuste existentes, la hora de una zona horaria se puede convertir fácilmente en la hora de otra zona horaria. Con este propósito, el objeto [TimeZoneInfo](xref:System.TimeZoneInfo) incluye varios métodos de conversión, como los siguientes:

* [ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)), que convierte [System.DateTime](xref:System.DateTime) a la hora de una zona horaria determinada.

* [ConvertTime(DateTime, TimeZoneInfo, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo,System.TimeZoneInfo)), que convierte [DateTime](xref:System.DateTime) de una zona horaria a otra.

* [ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)), que convierte [System.DateTimeOffset](xref:System.DateTimeOffset) a la hora de una zona horaria determinada. 

Para obtener más información sobre cómo convertir horas entre zonas horarias, consulte [Convertir horas entre zonas horarias](converting-between-time-zones.md).

## <a name="see-also"></a>Vea también

[Fechas, horas y zonas horarias](index.md)


<!--HONumber=Nov16_HO1-->


