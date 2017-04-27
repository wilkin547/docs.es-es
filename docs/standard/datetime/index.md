---
title: Fechas, horas y zonas horarias | Microsoft Docs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-4.6
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- time zone objects [.NET Framework]
- date and time data [.NET Framework]
- time zones [.NET Framework]
- times [.NET Framework], time zones
- time [.NET Framework], time zones
ms.assetid: 295c16e0-641b-4771-94b3-39c1ffa98c13
caps.latest.revision: 22
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: c50b3e328998b65ec47efe6d7457b36116813c77
ms.openlocfilehash: 2445188fda029ddc0f673d4c81f99f7f46edb89b
ms.lasthandoff: 04/08/2017

---
# <a name="dates-times-and-time-zones"></a>Fechas, horas y zonas horarias
Además de la estructura básica <xref:System.DateTime>, [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proporciona las siguientes clases que permiten trabajar con zonas horarias:  
  
-   <xref:System.TimeZone>  
  
     Use esta clase para trabajar con la zona horaria local del sistema y la zona de la hora universal coordinada (UTC).  La clase <xref:System.TimeZoneInfo> reemplaza en gran medida la funcionalidad de la clase <xref:System.TimeZone>.  
  
-   <xref:System.TimeZoneInfo>  
  
     Use esta clase para trabajar con cualquier zona horaria predefinida en un sistema, para crear zonas horarias nuevas y para convertir fácilmente fechas y horas desde una zona horaria a otra. Para un desarrollo nuevo, use la clase <xref:System.TimeZoneInfo> en lugar de la clase <xref:System.TimeZone>.  
  
-   <xref:System.DateTimeOffset>  
  
     Use esta estructura para trabajar con fechas y horas cuyo desplazamiento (o diferencia) con respecto a la hora UTC es conocido. La estructura <xref:System.DateTimeOffset> combina un valor de fecha y hora con esa hora de desplazamiento de UTC. Debido a su relación con la hora UTC, un valor individual de fecha y hora identifica de forma inequívoca un punto temporal único. Esto hace que un valor de <xref:System.DateTimeOffset> sea más portátil de un equipo a otro que un valor de <xref:System.DateTime>.  
  
 Esta sección de la documentación proporciona la información que necesita para trabajar con zonas horarias y para crear aplicaciones basadas en la zona horaria que puedan convertir fechas y horas de una zona horaria a otra.  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md)  
 Describe la terminología, los conceptos y los problemas relacionados con la creación de aplicaciones basadas en la zona horaria.  
  
 [Elección entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)  
 Describe cuando usar los tipos <xref:System.DateTime>, <xref:System.DateTimeOffset> y <xref:System.TimeZoneInfo> cuando se trabaja con datos de fecha y hora.  
  
 [Buscar las zonas horarias definidas en un sistema local](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)  
 Describe cómo enumerar las zonas horarias que se encuentran en un sistema local.  
  
 [Enumerar zonas horarias presentes en un equipo](../../../docs/standard/datetime/enumerate-time-zones.md)  
 Proporciona ejemplos que enumeran las zonas horarias definidas en el registro de un equipo y que permiten a los usuarios seleccionar una zona horaria predefinida de una lista.  
  
 [Acceso a los objetos de zona horaria local y UTC predefinidos](../../../docs/standard/datetime/access-utc-and-local.md)  
 Describe cómo tener acceso a la hora universal coordinada y a la zona horaria local.  
  
 [Crear instancias de un objeto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md)  
 Describe cómo crear una instancia de un objeto <xref:System.TimeZoneInfo> desde el sistema local.  
  
 [Crear instancias de un objeto DateTimeOffset](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md)  
 Describe las formas en que pueden crearse instancias de un objeto <xref:System.DateTimeOffset> y las formas en que un valor <xref:System.DateTime> se puede convertir en un valor <xref:System.DateTimeOffset>.  
  
 [Creación de zonas horarias sin reglas de ajuste](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)  
 Describe cómo crear una zona horaria personalizada que no admite la transición al horario de verano o desde este.  
  
 [Creación de zonas horarias con reglas de ajuste](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)  
 Describe cómo crear una zona horaria personalizada que admite una o varias transiciones al horario de verano o desde este.  
  
 [Guardado y restauración de zonas horarias](../../../docs/standard/datetime/saving-and-restoring-time-zones.md)  
 Describe la compatibilidad de <xref:System.TimeZoneInfo> con la serialización y deserialización de datos de zona horaria y muestra algunos de los escenarios en que se pueden usar estas características.  
  
 [Guardado de zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)  
 Describe cómo crear una zona horaria personalizada y guardar su información en un archivo de recursos.  
  
 [Restauración de zonas horarias de un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)  
 Describe cómo crear instancias de zonas horarias personalizadas que se guardaron en un archivo de recursos incrustado.  
  
 [Efectuar operaciones aritméticas con fechas y horas](../../../docs/standard/datetime/performing-arithmetic-operations.md)  
 Describe los aspectos necesarios para agregar, sustraer y comparar los valores <xref:System.DateTime> y <xref:System.DateTimeOffset>.  
  
 [Usar zonas horarias en operaciones aritméticas de fecha y hora](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)  
 Describe cómo realizar la aritmética de fecha y hora que refleja las reglas de ajuste de una zona horaria.  
  
 [Conversión entre DateTime y DateTimeOffset](../../../docs/standard/datetime/converting-between-datetime-and-offset.md)  
 Describe cómo realizar la conversión entre los valores <xref:System.DateTime> y <xref:System.DateTimeOffset>.  
  
 [Conversión de horas entre zonas horarias](../../../docs/standard/datetime/converting-between-time-zones.md)  
 Describe cómo convertir las horas de una zona horaria a otra.  
  
 [Resolución de horas ambiguas](../../../docs/standard/datetime/resolve-ambiguous-times.md)  
 Describe cómo resolver una hora ambigua asignándola a la hora estándar de la zona horaria.  
  
 [Permitir que los usuarios resuelvan horas ambiguas](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)  
 Describe cómo permitir que los usuarios determinen la asignación entre una hora local ambigua y la hora universal coordinada.  
  
## <a name="reference"></a>Referencia  
 <xref:System.TimeZoneInfo?displayProperty=fullName>
