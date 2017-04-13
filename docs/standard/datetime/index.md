---
title: "Fechas, horas y zonas horarias | Microsoft Docs"
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
  - "datos de fecha y hora [.NET Framework]"
  - "hora [.NET Framework], zonas horarias"
  - "objetos de zonas horarias [.NET Framework]"
  - "zonas horarias [.NET Framework]"
  - "horas [.NET Framework], zonas horarias"
ms.assetid: 295c16e0-641b-4771-94b3-39c1ffa98c13
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 22
---
# Fechas, horas y zonas horarias
Además de la estructura de <xref:System.DateTime> básica, [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proporciona las clases siguientes que permiten trabajar con zonas horarias:  
  
-   <xref:System.TimeZone>  
  
     Utilice esta clase para trabajar con la zona horaria local del sistema y la zona horaria universal coordinada \(hora UTC\).  La funcionalidad de la clase <xref:System.TimeZone> ha sido sustituida en buena parte por la clase <xref:System.TimeZoneInfo>.  
  
-   <xref:System.TimeZoneInfo>  
  
     Utilice esta clase para trabajar con cualquier zona horaria que esté predefinida en un sistema, para crear nuevas zonas horarias y para convertir fácilmente las fechas y horas de una zona horaria a otra.  En desarrollos nuevos, utilice la clase <xref:System.TimeZoneInfo> en lugar de la clase <xref:System.TimeZone>.  
  
-   <xref:System.DateTimeOffset>  
  
     Utilice esta estructura para trabajar con las fechas y horas que tienen un desfase \(o diferencia\) conocido respecto a la hora UTC.  La estructura de <xref:System.DateTimeOffset> combina un valor de fecha y hora con ese desfase temporal respecto a la hora UTC.  Debido a su relación con la hora UTC, cada valor de fecha y hora identifica de forma inequívoca un punto único en el tiempo.  Esto hace que un valor <xref:System.DateTimeOffset> sea más fácil de transferir de un equipo a otro que un valor <xref:System.DateTime>.  
  
 En esta sección de la documentación se proporciona la información necesaria para trabajar con zonas horarias y para crear aplicaciones sensibles a la zona horaria que pueden convertir fechas y horas de una zona a otra.  
  
## En esta sección  
 [Información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md)  
 Explica la terminología, los conceptos y los problemas que surgen al crear aplicaciones sensibles a la zona horaria.  
  
 [Elegir entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)  
 Explica cuándo deben utilizarse los tipos <xref:System.DateTime>, <xref:System.DateTimeOffset> y <xref:System.TimeZoneInfo> al trabajar con datos de fecha y hora.  
  
 [Buscar las zonas horarias definidas en un sistema local](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)  
 Describe cómo se enumeran las zonas horarias que se encuentran en un sistema local.  
  
 [Cómo: Enumerar zonas horarias presentes en un equipo](../../../docs/standard/datetime/enumerate-time-zones.md)  
 Proporciona ejemplos en los que se enumeran las zonas horarias definidas en el Registro de un equipo y que permiten a los usuarios seleccionar una zona horaria predefinida en una lista.  
  
 [Cómo: Obtener acceso a los objetos de zona horaria local y UTC predefinidos](../../../docs/standard/datetime/access-utc-and-local.md)  
 Describe cómo se obtiene acceso a la hora universal coordinada y a la zona horaria local.  
  
 [Cómo: Crear instancias de un objeto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md)  
 Describe cómo se crean instancias de un objeto <xref:System.TimeZoneInfo> a partir del Registro del sistema local.  
  
 [Crear instancias de un objeto DateTimeOffset](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md)  
 Discute los mecanismos mediante los que se pueden crear instancias de un objeto <xref:System.DateTimeOffset> y las formas en las que un valor <xref:System.DateTime> se puede convertir en un valor <xref:System.DateTimeOffset>.  
  
 [Cómo: Crear zonas horarias sin reglas de ajuste](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)  
 Describe cómo se crea una zona horaria personalizada que no admite la transición del horario de verano al horario estándar y viceversa.  
  
 [Cómo: Crear zonas horarias con reglas de ajuste](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)  
 Describe cómo se crea una zona horaria personalizada que admita una o varias transiciones del horario de verano al horario estándar y viceversa.  
  
 [Guardar y restaurar zonas horarias](../../../docs/standard/datetime/saving-and-restoring-time-zones.md)  
 Describe la compatibilidad de <xref:System.TimeZoneInfo> para la serialización y deserialización de datos de zona horaria y muestra algunos de los escenarios en los que se pueden usar estas características.  
  
 [Cómo: Guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)  
 Describe cómo se crea una zona horaria personalizada y se guarda su información en un archivo de recursos.  
  
 [Cómo: Restaurar zonas horarias de un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)  
 Describe cómo se crean instancias de zonas horarias personalizadas que se han guardado en un archivo de recursos incrustado.  
  
 [Efectuar operaciones aritméticas con fechas y horas](../../../docs/standard/datetime/performing-arithmetic-operations.md)  
 Explica los problemas que surgen al sumar, restar y comparar valores <xref:System.DateTime> y <xref:System.DateTimeOffset>.  
  
 [Cómo: Utilizar zonas horarias en aritmética de fecha y hora](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)  
 Analiza cómo se realizan operaciones aritméticas de fecha y hora que reflejen las reglas de ajuste de una zona horaria.  
  
 [Convertir entre DateTime y DateTimeOffset](../../../docs/standard/datetime/converting-between-datetime-and-offset.md)  
 Describe cómo se realiza la conversión entre valores <xref:System.DateTime> y <xref:System.DateTimeOffset>.  
  
 [Convertir horas entre zonas horarias](../../../docs/standard/datetime/converting-between-time-zones.md)  
 Describe cómo se convierte una hora de una zona horaria a otra.  
  
 [Cómo: Resolver horas ambiguas](../../../docs/standard/datetime/resolve-ambiguous-times.md)  
 Describe cómo se resuelve una hora ambigua asignándola a la hora estándar de la zona horaria.  
  
 [Cómo: Permitir que los usuarios resuelvan horas ambiguas](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)  
 Describe cómo se le puede permitir a un usuario determinar la correspondencia entre una hora local ambigua y la hora universal coordinada.  
  
## Referencia  
 <xref:System.TimeZoneInfo?displayProperty=fullName>