---
title: Fechas, horas y zonas horarias
description: Fechas, horas y zonas horarias
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/22/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 76e6cacc-1c0c-4a71-8cb8-018c112385ba
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: a4d0a68ac32c3d722a1479ca2b067892fd88bf52

---

# <a name="dates-times-and-time-zones"></a>Fechas, horas y zonas horarias

Además de la estructura básica [System.DateTime](xref:System.DateTime), .NET proporciona las siguientes clases que permiten trabajar con zonas horarias:

* [System.TimeZoneInfo](xref:System.TimeZoneInfo)
    
  Use esta clase para trabajar con la zona horaria local del sistema y la zona de la hora universal coordinada (UTC).
  
* [System.DateTimeOffset](xref:System.DateTimeOffset)  

  Use esta estructura para trabajar con fechas y horas cuyo desplazamiento (o diferencia) con respecto a la hora UTC es conocido. La estructura [DateTimeOffset](xref:System.DateTimeOffset)] combina un valor de fecha y hora con esa hora de desplazamiento de UTC. Debido a su relación con la hora UTC, un valor individual de fecha y hora identifica de forma inequívoca un punto temporal único. Esto hace que un valor de [DateTimeOffset](xref:System.DateTimeOffset)] sea más portátil de un equipo a otro que un valor de [DateTime](xref:System.DateTime)]. 
  
Esta sección de la documentación proporciona la información que necesita para trabajar con zonas horarias y para crear aplicaciones basadas en la zona horaria que puedan convertir fechas y horas de una zona horaria a otra.

## <a name="in-this-section"></a>En esta sección

[Información general sobre zonas horarias](time-zone-overview.md): describe la terminología, los conceptos y los problemas relacionados con la creación de aplicaciones basadas en la zona horaria.
    
[Elegir entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo](choosing-between-datetime.md): explica cuándo usar los tipos [System.DateTime](xref:System.DateTime), [System.DateTimeOffset](xref:System.DateTimeOffset) y [System.TimeZoneInfo](xref:System.TimeZoneInfo) al trabajar con datos de fecha y hora.
    
[Buscar las zonas horarias definidas en un sistema local](finding-the-time-zones-on-local-system.md): describe cómo enumerar las zonas horarias que se encuentran en un sistema local.

[Crear instancias de un objeto DateTimeOffset](instantiating-a-datetimeoffset-object.md): describe las formas en que pueden crearse instancias de un objeto [System.DateTimeOffset](xref:System.DateTimeOffset) y las formas en que un valor [System.DateTime](xref:System.DateTime) se puede convertir en un valor [System.DateTimeOffset](xref:System.DateTimeOffset).

[Efectuar operaciones aritméticas con fechas y horas](performing-arithmetic-operations.md): describe los aspectos necesarios para agregar, sustraer y comparar los valores [System.DateTime](xref:System.DateTime) y [System.DateTimeOffset](xref:System.DateTimeOffset).

[Convertir entre DateTime y DateTimeOffset](converting-between-datetime-and-offset.md): describe cómo convertir entre valores [System.DateTime](xref:System.DateTime) y [System.DateTimeOffset](xref:System.DateTimeOffset).

[Convertir horas entre zonas horarias:](converting-between-time-zones.md) describe cómo convertir las horas de una zona horaria a otra.

[Cómo: Enumerar zonas horarias presentes en un equipo](enumerate-time-zones.md): proporciona ejemplos que enumeran las zonas horarias definidas en el registro de un equipo y que permiten a los usuarios seleccionar una zona horaria predefinida de una lista.

[Cómo: Obtener acceso a los objetos de zona horaria local y UTC predefinidos](access-utc-and-local.md): describe cómo tener acceso a la hora universal coordinada y a la zona horaria local.

[Cómo: Crear instancias de un objeto TimeZoneInfo](instantiate-time-zone-info.md): describe cómo crear una instancia de un objeto [System.TimeZoneInfo](xref:System.TimeZoneInfo) desde el registro del sistema local.

[Cómo: Utilizar zonas horarias en aritmética de fecha y hora](use-time-zones-in-arithmetic.md): describe cómo realizar la aritmética de fecha y hora que refleja las reglas de ajuste de una zona horaria.

[Cómo: Resolver horas ambiguas](resolve-ambiguous-times.md): describe cómo resolver una hora ambigua asignándola a la hora estándar de la zona horaria.

[Cómo: Permitir que los usuarios resuelvan horas ambiguas](let-users-resolve-ambiguous-times.md): describe cómo permitir que los usuarios determinen la asignación entre una hora local ambigua y la hora universal coordinada.

## <a name="reference"></a>Referencia

[System.TimeZoneInfo](xref:System.TimeZoneInfo)

[System.DateTimeOffset](xref:System.DateTimeOffset)

[System.DateTime](xref:System.DateTime)



<!--HONumber=Nov16_HO1-->


