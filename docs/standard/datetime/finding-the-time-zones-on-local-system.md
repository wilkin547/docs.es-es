---
title: Buscar las zonas horarias definidas en un sistema local
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- time zones [.NET Framework], local
- time zones [.NET Framework], finding local system time zones
- time zone identifiers [.NET Framework]
- local time zone access
- time zones [.NET Framework], retrieving
- UTC times, finding local system time zones
- time zones [.NET Framework], UTC
ms.assetid: 3f63b1bc-9a4b-4bde-84ea-ab028a80d3e1
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c86932455301d15621c03d4440a8a16e44575bac
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="finding-the-time-zones-defined-on-a-local-system"></a>Buscar las zonas horarias definidas en un sistema local

La clase <xref:System.TimeZoneInfo> no expone un constructor público. Como resultado, la palabra clave `new` no se puede utilizar para crear un nuevo objeto <xref:System.TimeZoneInfo>. En su lugar, se crean instancias de los objetos <xref:System.TimeZoneInfo> recuperando información sobre zonas horarias predefinidas del registro o creando una zona horaria personalizada. En este tema, se explica cómo crear instancias de una zona horaria a partir de los datos almacenados en el registro. Además, las propiedades `static` (`shared` en Visual Basic) de la clase <xref:System.TimeZoneInfo> proporcionan acceso a la hora universal coordinada (UTC) y a la zona horaria local.

> [!NOTE]
> Para las zonas horarias que no están definidas en el registro, puede crear zonas horarias personalizadas mediante llamadas a las sobrecargas del método <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>. Crear una zona horaria personalizada se explica en la [Cómo: crear zonas horarias sin reglas de ajuste](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) y [Cómo: crear zonas horarias con reglas de ajuste](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) temas. Además, puede crear instancias de un objeto <xref:System.TimeZoneInfo> restaurándolo a partir de una cadena serializada con el método <xref:System.TimeZoneInfo.FromSerializedString%2A>. Serializar y deserializar un <xref:System.TimeZoneInfo> objeto se describe en el [Cómo: guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) y [Cómo: restaurar zonas horarias de un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) temas.

## <a name="accessing-individual-time-zones"></a>Obtener acceso a zonas horarias individuales

La clase <xref:System.TimeZoneInfo> proporciona dos objetos de zona horaria predefinidos que representan la hora UTC y la zona horaria local. Están disponibles desde las propiedades <xref:System.TimeZoneInfo.Utc%2A> y <xref:System.TimeZoneInfo.Local%2A>, respectivamente. Para obtener instrucciones sobre cómo acceder a las zonas de hora local o UTC, consulte [Cómo: obtener acceso a los objetos de zona hora local y UTC predefinidos](../../../docs/standard/datetime/access-utc-and-local.md).

También puede crear instancias de un objeto <xref:System.TimeZoneInfo> que representa cualquier zona horaria definida en el registro. Para obtener instrucciones sobre instancias de un objeto de zona horaria específica, consulte [Cómo: crear una instancia de un objeto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md).

## <a name="time-zone-identifiers"></a>Identificadores de zona horaria

El identificador de zona horaria es un campo clave que identifica de forma única la zona horaria. Aunque la mayoría de las claves son relativamente cortas, el identificador de zona horaria es comparativamente largo. En la mayoría de los casos, su valor corresponde a la propiedad <xref:System.TimeZoneInfo.StandardName%2A?displayProperty=nameWithType>, que se utiliza para proporcionar el nombre de la hora estándar de la zona horaria. Sin embargo, hay excepciones. La mejor manera de asegurarse de que se proporciona un identificador válido es enumerar las zonas horarias disponibles en el sistema y anotar los identificadores de las zonas horarias presentes.

## <a name="see-also"></a>Vea también

[Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
[Cómo: obtener acceso a los objetos de zona hora local y UTC predefinidos](../../../docs/standard/datetime/access-utc-and-local.md)
[Cómo: crear una instancia de un objeto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md) 
 [Convertir horas entre zonas horarias](../../../docs/standard/datetime/converting-between-time-zones.md)
