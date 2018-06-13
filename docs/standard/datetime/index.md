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
ms.openlocfilehash: 5355666b95d75fc18d0188c978c186690ee9ccca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575432"
---
# <a name="dates-times-and-time-zones"></a>Fechas, horas y zonas horarias

Además de la estructura básica <xref:System.DateTime>, .NET proporciona las siguientes clases que permiten trabajar con zonas horarias:

* <xref:System.TimeZone>

  Use esta clase para trabajar con la zona horaria local del sistema y la zona de la hora universal coordinada (UTC). La clase <xref:System.TimeZoneInfo> reemplaza en gran medida la funcionalidad de la clase <xref:System.TimeZone>.

* <xref:System.TimeZoneInfo>

  Use esta clase para trabajar con cualquier zona horaria predefinida en un sistema, para crear zonas horarias nuevas y para convertir fácilmente fechas y horas desde una zona horaria a otra. Para desarrollo nuevo, debe usar la clase <xref:System.TimeZoneInfo>, en lugar de la clase <xref:System.TimeZone>.

* <xref:System.DateTimeOffset>

  Use esta estructura para trabajar con fechas y horas cuyo desplazamiento (o diferencia) con respecto a la hora UTC es conocido. La estructura <xref:System.DateTimeOffset> combina un valor de fecha y hora con ese desplazamiento de hora de UTC. Debido a su relación con la hora UTC, un valor individual de fecha y hora identifica de forma inequívoca un punto temporal único. Esto hace que un valor de <xref:System.DateTimeOffset> sea más portátil de un equipo a otro que un valor de <xref:System.DateTime>.

Esta sección de la documentación proporciona la información que necesita para trabajar con zonas horarias y para crear aplicaciones basadas en la zona horaria que puedan convertir fechas y horas de una zona horaria a otra.

## <a name="in-this-section"></a>En esta sección

En [Time zone overview](../../../docs/standard/datetime/time-zone-overview.md) (Información general sobre zonas horarias) se describe la terminología, los conceptos y los problemas relacionados con la creación de aplicaciones basadas en la zona horaria.

En [Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md) (Elegir entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo) se explica cuándo usar los tipos <xref:System.DateTime>, <xref:System.DateTimeOffset> y <xref:System.TimeZoneInfo> al trabajar con datos de fecha y hora.

En [Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) (Buscar las zonas horarias definidas en un sistema local) se describe cómo enumerar las zonas horarias que se encuentran en un sistema local.

En [How to: Enumerate time zones present on a computer](../../../docs/standard/datetime/enumerate-time-zones.md) (Cómo: enumerar zonas horarias presentes en un equipo) se proporcionan ejemplos que enumeran las zonas horarias definidas en el Registro de un equipo y que permiten a los usuarios seleccionar una zona horaria predefinida de una lista.

En [How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md) (Cómo: obtener acceso a los objetos de zona horaria local y UTC predefinidos) se describe cómo tener acceso a la hora universal coordinada y a la zona horaria local.

En [How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md) (Cómo: crear instancias de un objeto TimeZoneInfo) se describe cómo crear una instancia de un objeto <xref:System.TimeZoneInfo> desde el Registro del sistema local.

En [Instantiating a DateTimeOffset object](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md) (Crear instancias de un objeto DateTimeOffset) se describen las formas en que pueden crearse instancias de un objeto <xref:System.DateTimeOffset> y las formas en que un valor <xref:System.DateTime> se puede convertir en un valor <xref:System.DateTimeOffset>.

En [How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) (Cómo: crear zonas horarias sin reglas de ajuste) se describe cómo crear una zona horaria personalizada que no admite la transición al horario de verano o desde este.

En [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) (Cómo: crear zonas horarias con reglas de ajuste) se describe cómo crear una zona horaria personalizada que admite una o más transiciones al horario de verano o desde este.

En [Saving and restoring time zones](../../../docs/standard/datetime/saving-and-restoring-time-zones.md) (Guardar y restaurar zonas horarias) se describe la compatibilidad de <xref:System.TimeZoneInfo> con la serialización y la deserialización de datos de zona horaria y muestra algunos de los escenarios en que se pueden usar estas características.

En [How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) (Cómo: guardar zonas horarias en un recurso insertado) se describe cómo crear una zona horaria personalizada y guardar su información en un archivo de recursos.

En [How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) (Cómo: restaurar zonas horarias de un recurso insertado) se describe cómo crear instancias de zonas horarias personalizadas que se han guardado en un archivo de recursos insertado.

En [Performing arithmetic operations with dates and times](../../../docs/standard/datetime/performing-arithmetic-operations.md) (Efectuar operaciones aritméticas con fechas y horas) se describen los aspectos necesarios para agregar, sustraer y comparar los valores <xref:System.DateTime> y <xref:System.DateTimeOffset>.

En [How to: Use time zones in date and time arithmetic](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md) (Cómo: usar zonas horarias en aritmética de fecha y hora) se describe cómo realizar la aritmética de fecha y hora que refleja las reglas de ajuste de una zona horaria.

En [Converting between DateTime and DateTimeOffset](../../../docs/standard/datetime/converting-between-datetime-and-offset.md) (Convertir entre DateTime y DateTimeOffset) se describe cómo convertir entre valores <xref:System.DateTime> y <xref:System.DateTimeOffset>.

En [Converting times between time zones](../../../docs/standard/datetime/converting-between-time-zones.md) (Convertir horas entre zonas horarias) se describe cómo convertir las horas de una zona horaria a otra.

En [How to: Resolve ambiguous times](../../../docs/standard/datetime/resolve-ambiguous-times.md) (Cómo: resolver horas ambiguas) se describe cómo resolver una hora ambigua mediante su asignación a la hora estándar de la zona horaria.

En [How to: Let users resolve ambiguous times](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md) (Cómo: permitir que los usuarios resuelvan horas ambiguas) se describe cómo permitir que los usuarios determinen la asignación entre una hora local ambigua y la hora universal coordinada.

## <a name="reference"></a>Referencia

<xref:System.TimeZoneInfo?displayProperty=nameWithType>
