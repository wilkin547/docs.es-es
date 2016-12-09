---
title: Buscar las zonas horarias definidas en un sistema local
description: Buscar las zonas horarias definidas en un sistema local
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 3a6ee323-f3cf-486d-aa0c-103931f1eba9
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: e7f07a1f86ca31a24e25d98de2f8918ff098db24

---

# <a name="finding-the-time-zones-defined-on-a-local-system"></a>Buscar las zonas horarias definidas en un sistema local

La clase [System.TimeZoneInfo](xref:System.TimeZoneInfo) no expone un constructor público. Como resultado, la palabra clave `new` no se puede usar para crear un nuevo objeto [TimeZoneInfo](xref:System.TimeZoneInfo). En su lugar, se crean instancias de los objetos [TimeZoneInfo](xref:System.TimeZoneInfo) recuperando información sobre zonas horarias predefinidas del sistema operativo. En este tema, se explica cómo crear instancias de una zona horaria a partir de los datos del sistema operativo. Además, las propiedades `static` (`Shared` en Visual Basic) de la clase [TimeZoneInfo](xref:System.TimeZoneInfo) proporcionan acceso a la hora universal coordinada (UTC) y a la zona horaria local.

## <a name="accessing-individual-time-zones"></a>Acceso a zonas horarias individuales

La clase [TimeZoneInfo](xref:System.TimeZoneInfo) proporciona dos objetos de zona horaria predefinidos que representan la hora UTC y la zona horaria local. Están disponibles en las propiedades [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) y [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local), respectivamente. Para obtener instrucciones sobre cómo acceder a las zonas de hora local o UTC, consulte [Cómo: obtener acceso a los objetos de zona horaria local y UTC predefinidos](access-utc-and-local.md). 

También puede crear instancias de un objeto [TimeZoneInfo](xref:System.TimeZoneInfo) que representa cualquier zona horaria definida en el sistema operativo. Para obtener instrucciones acerca de cómo crear instancias de un objeto de zona horaria concreto, consulte [Cómo: crear instancias de un objeto TimeZoneInfo](instantiate-time-zone-info.md).

## <a name="time-zone-identifiers"></a>Identificadores de zona horaria

El identificador de zona horaria es un campo clave que identifica de forma única la zona horaria. Aunque la mayoría de las claves son relativamente cortas, el identificador de zona horaria es comparativamente largo. En la mayoría de los casos, su valor corresponde a la propiedad [TimeZoneInfo.StandardName](xref:System.TimeZoneInfo.StandardName), que se usa para proporcionar el nombre de la hora estándar de la zona horaria. Sin embargo, hay excepciones. La mejor manera de asegurarse de que se proporciona un identificador válido es enumerar las zonas horarias disponibles en el sistema y anotar los identificadores de las zonas horarias presentes. Para obtener instrucciones sobre cómo enumerar zonas horarias, consulte [Cómo: enumerar zonas horarias presentes en un equipo](enumerate-time-zones.md).

## <a name="see-also"></a>Vea también

[Fechas, horas y zonas horarias](index.md)

[Cómo: Acceder a los objetos de zona horaria local y UTC predefinidos](access-utc-and-local.md)

[Cómo: Crear instancias de un objeto TimeZoneInfo](instantiate-time-zone-info.md)

[Cómo: enumerar zonas horarias presentes en un equipo](enumerate-time-zones.md)

[Conversión de horas entre zonas horarias](converting-between-time-zones.md)


<!--HONumber=Nov16_HO3-->


