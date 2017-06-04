---
title: "Informaci&#243;n general sobre zonas horarias | Microsoft Docs"
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
  - "regla de ajuste [.NET Framework]"
  - "hora ambigua [.NET Framework]"
  - "horario de verano [.NET Framework]"
  - "regla fija [.NET Framework]"
  - "regla flotante [.NET Framework]"
  - "hora no válida [.NET Framework]"
  - "zonas horarias [.NET Framework], acerca de las zonas horarias"
  - "zonas horarias [.NET Framework], crear"
  - "zonas horarias [.NET Framework], terminología"
  - "TimeZoneInfo (clase), acerca de la clase TimeZoneInfo"
  - "hora de transición [.NET Framework]"
ms.assetid: c4b7ed01-5e38-4959-a3b6-ef9765d6ccf1
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Informaci&#243;n general sobre zonas horarias
La clase <xref:System.TimeZoneInfo> simplifica la creación de aplicaciones que tienen en cuenta la zona horaria.  La clase <xref:System.TimeZone> admite el trabajo con la zona horaria local y la hora universal coordinada \(UTC\).  La clase <xref:System.TimeZoneInfo> admite ambas zonas así como cualquier zona horaria sobre la que haya información predefinida en el Registro.  También puede utilizar <xref:System.TimeZoneInfo> para definir las zonas horarias personalizadas sobre las que el sistema no tiene ninguna información.  
  
## Aspectos básicos de las zonas horarias  
 Una zona horaria es una región geográfica donde se utiliza la misma hora.  Normalmente, aunque no siempre, las zonas horarias adyacentes tienen una hora de diferencia.  La hora en cualquiera de las zonas horarias del mundo se puede expresar como una diferencia respecto a la hora universal coordinada \(UTC\).  
  
 Muchas de las zonas horarias del mundo admiten el horario de verano.  El horario de verano intenta maximizar las horas de luz diurna adelantando el reloj una hora en primavera o a principios de verano, y volviendo al horario normal \(o estándar\) a finales de verano o en otoño.  Estos cambios del horario estándar se conocen como reglas de ajuste.  
  
 El cambio de horario de verano en una zona horaria determinada se puede definir mediante una regla de ajuste fija o flotante.  Una regla de ajuste fija establece una fecha determinada en que se produce el cambio de horario de verano cada año.  Por ejemplo, el cambio de horario de verano a horario estándar que se produce cada año el 25 de octubre, sigue una regla de ajuste fija.  Las reglas de ajuste flotantes son mucho más habituales, y establecen un día de una semana de un mes determinados para el cambio del horario de verano.  Por ejemplo, el cambio de horario estándar a horario de verano que se produce el tercer domingo de marzo sigue una regla de ajuste flotante.  
  
 Para las zonas horarias que admiten reglas de ajuste, el cambio de horario de verano crea dos tipos de horas anómalas: horas no válidas y horas ambiguas.  Una hora no válida es una hora no existente creada por el cambio del horario estándar al horario de verano.  Por ejemplo, si esta transición se produce en un día determinado a las 2:00 a.m. y hace que la hora cambie a 3:00 a.m., el intervalo entre las 2:00 a.m. y 2:59: 99 A.m. no es válido.  Una hora ambigua es aquella que se puede asignar a dos horas diferentes en una sola zona horaria.  Es creada por el cambio de horario de verano a horario estándar.  Por ejemplo, si esta transición se produce en un día determinado a las 2:00 a.m. y hace que la hora cambie a 1:00 a.m., el intervalo entre las 1:00 a.m. y 1:59: 99 A.m. puede interpretarse como una hora estándar o al horario de verano.  
  
## Terminología de las zonas horarias  
 La tabla siguiente define los términos que normalmente se utilizan cuando se trabaja con zonas horarias y se desarrollan aplicaciones que tienen en cuenta la zona horaria.  
  
|Término|Definición|  
|-------------|----------------|  
|Regla de ajuste|Regla que define cuándo se produce el cambio de horario estándar a horario de verano y de horario de verano a horario estándar.  Cada regla de ajuste tiene una fecha de inicio y finalización que define cuándo se aplica la regla \(por ejemplo, la regla de ajuste se aplica desde el 1 de enero de 1986 al 31 de diciembre de 2006\), un incremento \(la cantidad de tiempo que cambia el horario estándar como resultado de aplicar la regla de ajuste\) e información acerca de la fecha y la hora concretas en que se produce el cambio durante el período de ajuste.  Los cambios pueden seguir una regla fija o una regla flotante.|  
|Hora ambigua|Hora que se puede asignar a dos horas diferentes en una sola zona horaria.  Se produce al retrasar los relojes, como en el cambio de horario de verano a horario estándar.  Por ejemplo, si esta transición se produce en un día determinado a las 2:00 a.m. y hace que la hora cambie a 1:00 a.m., el intervalo entre las 1:00 a.m. y 1:59: 99 A.m. puede interpretarse como una hora estándar o al horario de verano.|  
|Regla fija|Regla de ajuste que establece una fecha determinada para el cambio de horario de verano.  Por ejemplo, el cambio de horario de verano a horario estándar que se produce cada año el 25 de octubre, sigue una regla de ajuste fija.|  
|Regla flotante|Regla de ajuste que establece un día de una semana de un mes determinados para el cambio de horario de verano.  Por ejemplo, el cambio de horario estándar a horario de verano que se produce el tercer domingo de marzo sigue una regla de ajuste flotante.|  
|Hora no válida|Hora no existente que se produce por el cambio del horario estándar al horario de verano.  Se produce al adelantar los relojes, como en el cambio de horario estándar de una zona horaria a horario de verano.  Por ejemplo, si esta transición se produce en un día determinado a las 2:00 a.m. y hace que la hora cambie a 3:00 a.m., el intervalo entre las 2:00 a.m. y 2:59: 99 A.m. no es válido.|  
|Hora del cambio|Información sobre un cambio horario concreto, como el cambio de horario de verano a horario estándar o viceversa, en una zona horaria determinada.|  
  
## Zonas horarias y la clase TimeZoneInfo  
 En .NET Framework, un objeto <xref:System.TimeZoneInfo> representa una zona horaria.  La clase <xref:System.TimeZoneInfo> incluye un método <xref:System.TimeZoneInfo.GetAdjustmentRules%2A> que devuelve una matriz de objetos <xref:System.TimeZoneInfo.AdjustmentRule>.  Cada elemento de esta matriz proporciona información acerca del cambio del horario verano para un período de tiempo determinado. \(Para las zonas horarias que no admiten el horario de verano, el método devuelve una matriz vacía\). Cada objeto <xref:System.TimeZoneInfo.AdjustmentRule> tiene una propiedad <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionStart%2A> y <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionEnd%2A> que define la fecha y la hora concretas del cambio del horario de verano.  La propiedad <xref:System.TimeZoneInfo.TransitionTime.IsFixedDateRule%2A> indica si ese cambio es fijo o flotante.  
  
 .NET Framework utiliza la información sobre la zona horaria proporcionada por el sistema operativo Windows y almacenada en el Registro.  Debido al número de zonas horarias que existen, no todas las zonas horarias existentes están representadas en el Registro.  Además, debido a que el Registro es una estructura dinámica, se pueden agregar a él, o quitar de él, zonas horarias predefinidas.  Por último, el Registro no contiene necesariamente datos históricos de zonas horarias.  Por ejemplo, en Windows XP, el Registro contiene únicamente datos sobre un conjunto de ajustes de la zona horaria.  Windows Vista admite datos dinámicos de zonas horarias, lo que significa que una sola zona horaria puede tener varias reglas de ajuste que se aplican a intervalos concretos de años.  Sin embargo, la mayoría de las zonas horarias definidas en el Registro de Windows Vista y que admiten el horario de verano, sólo tienen una o dos reglas de ajuste predefinidas.  
  
 La dependencia de la clase <xref:System.TimeZoneInfo> en el Registro significa que una aplicación que tiene en cuenta la zona horaria puede no estar segura de que una zona horaria determinada esté definida en el Registro.  Como resultado, al intentar crear instancias de una zona horaria concreta \(excepto la zona horaria local o la zona horaria que representa UTC\) se debe utilizar el control de excepciones.  También se debe proporcionar algún método para permitir a la aplicación continuar si no se puede crear una instancia de un objeto <xref:System.TimeZoneInfo> necesario desde el Registro.  
  
 Para tratar la ausencia de una zona horaria necesaria, la clase <xref:System.TimeZoneInfo> incluye un método <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> que se puede utilizar para crear zonas horarias personalizadas no encontradas en el Registro.  Para obtener detalles sobre cómo crear una zona horaria personalizada, vea [Cómo: Crear zonas horarias sin reglas de ajuste](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) y [Cómo: Crear zonas horarias con reglas de ajuste](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).  Además, puede utilizar el método <xref:System.TimeZoneInfo.ToSerializedString%2A> para convertir una zona horaria recientemente creada en una cadena y guardarla en un almacén de datos \(una base de datos, un archivo de texto, el Registro o un recurso de aplicación\).  Después, puede utilizar el método <xref:System.TimeZoneInfo.FromSerializedString%2A> para volver a convertir esta cadena en un objeto <xref:System.TimeZoneInfo>.  Para obtener información detallada, vea [Cómo: Guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) y [Cómo: Restaurar zonas horarias de un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).  
  
 Debido a que cada zona horaria se caracteriza por una diferencia base respecto a la hora UTC, así como por una diferencia respecto a la hora UTC que refleja las reglas de ajuste existentes, una hora de una zona horaria se puede convertir fácilmente en la hora de otra zona horaria.  Con esta finalidad, el objeto <xref:System.TimeZoneInfo> incluye varios métodos de conversión, entre los que se incluyen:  
  
-   <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>, que convierte la hora UTC en la hora de una zona horaria designada.  
  
-   <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>, que convierte la hora de una zona horaria designada en la hora UTC.  
  
-   <xref:System.TimeZoneInfo.ConvertTime%2A>, que convierte la hora de una zona horaria designada en la hora de otra zona horaria designada.  
  
-   <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>, que utiliza identificadores de zona horaria \(en lugar de objetos <xref:System.TimeZoneInfo>\) como parámetros para convertir la hora de una zona horaria designada en la hora de otra zona horaria designada.  
  
 Para obtener información más detallada sobre cómo convertir horas entre zonas horarias, vea [Convertir horas entre zonas horarias](../../../docs/standard/datetime/converting-between-time-zones.md).  
  
## Vea también  
 [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)