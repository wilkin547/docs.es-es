---
description: Más información acerca de cómo buscar las zonas horarias definidas en un sistema local
title: Buscar las zonas horarias definidas en un sistema local
ms.date: 04/10/2017
helpviewer_keywords:
- time zones [.NET], local
- time zones [.NET], finding local system time zones
- time zone identifiers [.NET]
- local time zone access
- time zones [.NET], retrieving
- UTC times, finding local system time zones
- time zones [.NET], UTC
ms.assetid: 3f63b1bc-9a4b-4bde-84ea-ab028a80d3e1
ms.openlocfilehash: 1b7a4d1962adac42b47cda42d4d1223c4b79852a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99702644"
---
# <a name="finding-the-time-zones-defined-on-a-local-system"></a>Buscar las zonas horarias definidas en un sistema local

La clase <xref:System.TimeZoneInfo> no expone un constructor público. Como resultado, la palabra clave `new` no se puede utilizar para crear un nuevo objeto <xref:System.TimeZoneInfo>. En su lugar, se crean instancias de los objetos <xref:System.TimeZoneInfo> recuperando información sobre zonas horarias predefinidas del registro o creando una zona horaria personalizada. En este tema, se explica cómo crear instancias de una zona horaria a partir de los datos almacenados en el registro. Además, las propiedades `static` (`shared` en Visual Basic) de la clase <xref:System.TimeZoneInfo> proporcionan acceso a la hora universal coordinada (UTC) y a la zona horaria local.

> [!NOTE]
> Para las zonas horarias que no están definidas en el registro, puede crear zonas horarias personalizadas mediante llamadas a las sobrecargas del método <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>. La creación de una zona horaria personalizada se describe en los temas [Cómo: crear zonas horarias sin reglas de ajuste](create-time-zones-without-adjustment-rules.md) y [Cómo: crear zonas horarias con reglas de ajuste](create-time-zones-with-adjustment-rules.md) . Además, puede crear instancias de un objeto <xref:System.TimeZoneInfo> restaurándolo a partir de una cadena serializada con el método <xref:System.TimeZoneInfo.FromSerializedString%2A>. La serialización y deserialización de un <xref:System.TimeZoneInfo> objeto se describe en los temas [Cómo: guardar zonas horarias en un recurso incrustado](save-time-zones-to-an-embedded-resource.md) y [Cómo: restaurar zonas horarias de un recurso incrustado](restore-time-zones-from-an-embedded-resource.md) .

## <a name="accessing-individual-time-zones"></a>Acceso a zonas horarias individuales

La clase <xref:System.TimeZoneInfo> proporciona dos objetos de zona horaria predefinidos que representan la hora UTC y la zona horaria local. Están disponibles desde las propiedades <xref:System.TimeZoneInfo.Utc%2A> y <xref:System.TimeZoneInfo.Local%2A>, respectivamente. Para obtener instrucciones sobre cómo obtener acceso a la hora UTC o a las zonas horarias locales, consulte [Cómo: obtener acceso a los objetos de zona horaria local y UTC predefinidos](access-utc-and-local.md).

También puede crear instancias de un objeto <xref:System.TimeZoneInfo> que representa cualquier zona horaria definida en el registro. Para obtener instrucciones sobre cómo crear instancias de un objeto de zona horaria concreto, consulte [Cómo: crear instancias de un objeto TimeZoneInfo](instantiate-time-zone-info.md).

## <a name="time-zone-identifiers"></a>Identificadores de zona horaria

El identificador de zona horaria es un campo clave que identifica de forma única la zona horaria. Aunque la mayoría de las claves son relativamente cortas, el identificador de zona horaria es comparativamente largo. En la mayoría de los casos, su valor corresponde a la propiedad <xref:System.TimeZoneInfo.StandardName%2A?displayProperty=nameWithType>, que se utiliza para proporcionar el nombre de la hora estándar de la zona horaria. Sin embargo, hay excepciones. La mejor manera de asegurarse de que se proporciona un identificador válido es enumerar las zonas horarias disponibles en el sistema y anotar los identificadores de las zonas horarias presentes.

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](index.md)
- [Cómo: obtener acceso a los objetos de zona horaria local y UTC predefinidos](access-utc-and-local.md)
- [Cómo: crear instancias de un objeto TimeZoneInfo](instantiate-time-zone-info.md)
- [Convertir horas entre zonas horarias](converting-between-time-zones.md)
