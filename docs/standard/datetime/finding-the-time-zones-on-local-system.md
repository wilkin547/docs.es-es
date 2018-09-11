---
title: Buscar las zonas horarias definidas en un sistema local
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zones [.NET Framework], local
- time zones [.NET Framework], finding local system time zones
- time zone identifiers [.NET Framework]
- local time zone access
- time zones [.NET Framework], retrieving
- UTC times, finding local system time zones
- time zones [.NET Framework], UTC
ms.assetid: 3f63b1bc-9a4b-4bde-84ea-ab028a80d3e1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a65798c46b01bb7a702559d685590ecf7a6f2793
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44262222"
---
# <a name="finding-the-time-zones-defined-on-a-local-system"></a>Buscar las zonas horarias definidas en un sistema local

La clase <xref:System.TimeZoneInfo> no expone un constructor público. Como resultado, la palabra clave `new` no se puede utilizar para crear un nuevo objeto <xref:System.TimeZoneInfo>. En su lugar, se crean instancias de los objetos <xref:System.TimeZoneInfo> recuperando información sobre zonas horarias predefinidas del registro o creando una zona horaria personalizada. En este tema, se explica cómo crear instancias de una zona horaria a partir de los datos almacenados en el registro. Además, las propiedades `static` (`shared` en Visual Basic) de la clase <xref:System.TimeZoneInfo> proporcionan acceso a la hora universal coordinada (UTC) y a la zona horaria local.

> [!NOTE]
> Para las zonas horarias que no están definidas en el registro, puede crear zonas horarias personalizadas mediante llamadas a las sobrecargas del método <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>. Creación de una zona horaria personalizada se describe en el [Cómo: crear zonas horarias sin reglas de ajuste](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) y [Cómo: crear zonas horarias con reglas de ajuste](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) temas. Además, puede crear instancias de un objeto <xref:System.TimeZoneInfo> restaurándolo a partir de una cadena serializada con el método <xref:System.TimeZoneInfo.FromSerializedString%2A>. Serializar y deserializar un <xref:System.TimeZoneInfo> objeto se describe en el [Cómo: guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) y [Cómo: restaurar zonas horarias de un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) temas.

## <a name="accessing-individual-time-zones"></a>Acceso a zonas horarias individuales

La clase <xref:System.TimeZoneInfo> proporciona dos objetos de zona horaria predefinidos que representan la hora UTC y la zona horaria local. Están disponibles desde las propiedades <xref:System.TimeZoneInfo.Utc%2A> y <xref:System.TimeZoneInfo.Local%2A>, respectivamente. Para obtener instrucciones sobre cómo acceder a las zonas de hora local o UTC, consulte [Cómo: obtener acceso a los objetos de zona horaria local y UTC predefinidos](../../../docs/standard/datetime/access-utc-and-local.md).

También puede crear instancias de un objeto <xref:System.TimeZoneInfo> que representa cualquier zona horaria definida en el registro. Para obtener instrucciones sobre cómo crear instancias de un objeto de zona horaria concreto, vea [Cómo: crear una instancia de un objeto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md).

## <a name="time-zone-identifiers"></a>Identificadores de zona horaria

El identificador de zona horaria es un campo clave que identifica de forma única la zona horaria. Aunque la mayoría de las claves son relativamente cortas, el identificador de zona horaria es comparativamente largo. En la mayoría de los casos, su valor corresponde a la propiedad <xref:System.TimeZoneInfo.StandardName%2A?displayProperty=nameWithType>, que se utiliza para proporcionar el nombre de la hora estándar de la zona horaria. Sin embargo, hay excepciones. La mejor manera de asegurarse de que se proporciona un identificador válido es enumerar las zonas horarias disponibles en el sistema y anotar los identificadores de las zonas horarias presentes.

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
- [Acceso a los objetos de zona horaria local y UTC predefinidos](../../../docs/standard/datetime/access-utc-and-local.md)
- [Crear instancias de un objeto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md)
- [Conversión de horas entre zonas horarias](../../../docs/standard/datetime/converting-between-time-zones.md)
