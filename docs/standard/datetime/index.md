---
title: Fechas, horas y zonas horarias
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zone objects [.NET Framework]
- date and time data [.NET Framework]
- time zones [.NET Framework]
- times [.NET Framework], time zones
- time [.NET Framework], time zones
ms.assetid: 295c16e0-641b-4771-94b3-39c1ffa98c13
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03a5594b689a52b641ecece0f9a92fb6cdfe5735
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991288"
---
# <a name="dates-times-and-time-zones"></a>Fechas, horas y zonas horarias

Además de la estructura básica <xref:System.DateTime>, .NET proporciona las siguientes clases que permiten trabajar con zonas horarias:

* <xref:System.TimeZone>

  Use esta clase para trabajar con la zona horaria local del sistema y la zona de la hora universal coordinada (UTC). La <xref:System.TimeZoneInfo> clase reemplaza en <xref:System.TimeZone> gran medida la funcionalidad de la clase.

* <xref:System.TimeZoneInfo>

  Use esta clase para trabajar con cualquier zona horaria predefinida en un sistema, para crear zonas horarias nuevas y para convertir fácilmente fechas y horas desde una zona horaria a otra. Para desarrollo nuevo, debe usar la clase <xref:System.TimeZoneInfo>, en lugar de la clase <xref:System.TimeZone>.

* <xref:System.DateTimeOffset>

  Use esta estructura para trabajar con fechas y horas cuyo desplazamiento (o diferencia) con respecto a la hora UTC es conocido. La estructura <xref:System.DateTimeOffset> combina un valor de fecha y hora con ese desplazamiento de hora de UTC. Debido a su relación con la hora UTC, un valor individual de fecha y hora identifica de forma inequívoca un punto temporal único. Esto hace que un valor de <xref:System.DateTimeOffset> sea más portátil de un equipo a otro que un valor de <xref:System.DateTime>.

Esta sección de la documentación proporciona la información que necesita para trabajar con zonas horarias y para crear aplicaciones basadas en la zona horaria que puedan convertir fechas y horas de una zona horaria a otra.

## <a name="in-this-section"></a>En esta sección

En [Time zone overview](../../../docs/standard/datetime/time-zone-overview.md) (Información general sobre zonas horarias) se describe la terminología, los conceptos y los problemas relacionados con la creación de aplicaciones basadas en la zona horaria.

En [Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md) (Elegir entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo) se explica cuándo usar los tipos <xref:System.DateTime>, <xref:System.DateTimeOffset> y <xref:System.TimeZoneInfo> al trabajar con datos de fecha y hora.

En [Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) (Buscar las zonas horarias definidas en un sistema local) se describe cómo enumerar las zonas horarias que se encuentran en un sistema local.

[Procedimientos: Enumerar zonas horarias presentes en un](../../../docs/standard/datetime/enumerate-time-zones.md) equipo proporciona ejemplos que enumeran las zonas horarias definidas en el registro de un equipo y que permiten a los usuarios seleccionar una zona horaria predefinida de una lista.

[Cómo: Acceder a los objetos](../../../docs/standard/datetime/access-utc-and-local.md) de zona horaria local y UTC predefinidos describe cómo obtener acceso a la hora universal coordinada y a la zona horaria local.

[Procedimientos: Crear una instancia de un](../../../docs/standard/datetime/instantiate-time-zone-info.md) objeto TimeZoneInfo describe cómo crear una <xref:System.TimeZoneInfo> instancia de un objeto desde el registro del sistema local.

En [Instantiating a DateTimeOffset object](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md) (Crear instancias de un objeto DateTimeOffset) se describen las formas en que pueden crearse instancias de un objeto <xref:System.DateTimeOffset> y las formas en que un valor <xref:System.DateTime> se puede convertir en un valor <xref:System.DateTimeOffset>.

[Cómo: Crear zonas horarias sin reglas](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) de ajuste describe cómo crear una zona horaria personalizada que no admite la transición hacia y desde el horario de verano.

[Cómo: Crear zonas horarias con reglas](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) de ajuste describe cómo crear una zona horaria personalizada que admite una o más transiciones hacia y desde el horario de verano.

En [Saving and restoring time zones](../../../docs/standard/datetime/saving-and-restoring-time-zones.md) (Guardar y restaurar zonas horarias) se describe la compatibilidad de <xref:System.TimeZoneInfo> con la serialización y la deserialización de datos de zona horaria y muestra algunos de los escenarios en que se pueden usar estas características.

[Cómo: Guardar zonas horarias en un recurso](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) incrustado describe cómo crear una zona horaria personalizada y guardar su información en un archivo de recursos.

[Cómo: Restaurar zonas horarias de un recurso](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) incrustado describe cómo crear instancias de zonas horarias personalizadas que se han guardado en un archivo de recursos incrustado.

En [Performing arithmetic operations with dates and times](../../../docs/standard/datetime/performing-arithmetic-operations.md) (Efectuar operaciones aritméticas con fechas y horas) se describen los aspectos necesarios para agregar, sustraer y comparar los valores <xref:System.DateTime> y <xref:System.DateTimeOffset>.

[Procedimientos: Usar zonas horarias en aritmética](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md) de fecha y hora describe cómo realizar operaciones aritméticas de fecha y hora que reflejen las reglas de ajuste de una zona horaria.

En [Converting between DateTime and DateTimeOffset](../../../docs/standard/datetime/converting-between-datetime-and-offset.md) (Convertir entre DateTime y DateTimeOffset) se describe cómo convertir entre valores <xref:System.DateTime> y <xref:System.DateTimeOffset>.

En [Converting times between time zones](../../../docs/standard/datetime/converting-between-time-zones.md) (Convertir horas entre zonas horarias) se describe cómo convertir las horas de una zona horaria a otra.

[Procedimientos: Resolver horas](../../../docs/standard/datetime/resolve-ambiguous-times.md) ambiguas describe cómo resolver una hora ambigua asignándola a la hora estándar de la zona horaria.

[Procedimientos: Permitir a los usuarios resolver](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md) horas ambiguas describe cómo permitir a un usuario determinar la asignación entre una hora local ambigua y la hora universal coordinada.

## <a name="reference"></a>Referencia

<xref:System.TimeZoneInfo?displayProperty=nameWithType>
