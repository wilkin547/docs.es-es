---
title: "Buscar las zonas horarias definidas en un sistema local | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "acceso a zona horaria local"
  - "identificadores de zona horaria [.NET Framework]"
  - "zonas horarias [.NET Framework], buscar zonas horarias del sistema local"
  - "zonas horarias [.NET Framework], locales"
  - "zonas horarias [.NET Framework], recuperar"
  - "zonas horarias [.NET Framework], UTC"
  - "horas UTC, buscar zonas horarias del sistema local"
ms.assetid: 3f63b1bc-9a4b-4bde-84ea-ab028a80d3e1
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Buscar las zonas horarias definidas en un sistema local
La clase <xref:System.TimeZoneInfo> no expone un constructor público.  Como resultado, la palabra clave `new` no se puede utilizar para crear un nuevo objeto <xref:System.TimeZoneInfo>.  En su lugar, se crean instancias de los objetos <xref:System.TimeZoneInfo> recuperando información sobre zonas horarias predefinidas del registro o creando una zona horaria personalizada.  En este tema, se explica cómo crear instancias de una zona horaria a partir de los datos almacenados en el registro.  Además, las propiedades `static` \(`shared` en Visual Basic\) de la clase <xref:System.TimeZoneInfo> proporcionan acceso a la hora universal coordinada \(UTC\) y a la zona horaria local.  
  
> [!NOTE]
>  Para las zonas horarias que no están definidas en el registro, puede crear zonas horarias personalizadas mediante llamadas a las sobrecargas del método <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>.  En los temas [Cómo: Crear zonas horarias sin reglas de ajuste](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) y [Cómo: Crear zonas horarias con reglas de ajuste](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) se explica cómo crear una zona horaria personalizada.  Además, puede crear instancias de un objeto <xref:System.TimeZoneInfo> restaurándolo a partir de una cadena serializada con el método <xref:System.TimeZoneInfo.FromSerializedString%2A>.  En los temas [Cómo: Guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) y [Cómo: Restaurar zonas horarias de un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) se explica cómo serializar y deserializar un objeto <xref:System.TimeZoneInfo>.  
  
## Acceso a zonas horarias individuales  
 La clase <xref:System.TimeZoneInfo> proporciona dos objetos de zona horaria predefinidos que representan la hora UTC y la zona horaria local.  Están disponibles desde las propiedades <xref:System.TimeZoneInfo.Utc%2A> y <xref:System.TimeZoneInfo.Local%2A>, respectivamente.  Para obtener instrucciones sobre cómo acceder a las zonas de hora local o UTC, consulte [Cómo: Obtener acceso a los objetos de zona horaria local y UTC predefinidos](../../../docs/standard/datetime/access-utc-and-local.md).  
  
 También puede crear instancias de un objeto <xref:System.TimeZoneInfo> que representa cualquier zona horaria definida en el registro.  Para obtener instrucciones acerca de cómo crear instancias de un objeto de zona horaria concreto, consulte [Cómo: Crear instancias de un objeto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md).  
  
## Identificadores de zona horaria  
 El identificador de zona horaria es un campo clave que identifica de forma única la zona horaria.  Aunque la mayoría de las claves son relativamente cortas, el identificador de zona horaria es comparativamente largo.  En la mayoría de los casos, su valor corresponde a la propiedad <xref:System.TimeZoneInfo.StandardName%2A?displayProperty=fullName>, que se utiliza para proporcionar el nombre de la hora estándar de la zona horaria.  Sin embargo, hay excepciones.  La mejor manera de asegurarse de que se proporciona un identificador válido es enumerar las zonas horarias disponibles en el sistema y anotar los identificadores de las zonas horarias presentes.  
  
## Vea también  
 [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)   
 [Cómo: Obtener acceso a los objetos de zona horaria local y UTC predefinidos](../../../docs/standard/datetime/access-utc-and-local.md)   
 [Cómo: Crear instancias de un objeto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md)   
 [Convertir horas entre zonas horarias](../../../docs/standard/datetime/converting-between-time-zones.md)