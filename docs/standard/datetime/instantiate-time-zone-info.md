---
title: "Cómo: Crear instancias de un objeto TimeZoneInfo"
description: "Cómo crear instancias de un objeto TimeZoneInfo"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: bff137e5-d550-44c3-b460-b3f2dabd4035
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f2584d446c92d2df2f6d74533ef07fe96888d36a
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-instantiate-a-timezoneinfo-object"></a>Cómo: Crear instancias de un objeto TimeZoneInfo

La manera más común para crear una instancia de un objeto [TimeZoneInfo](xref:System.TimeZoneInfo) es recuperar información sobre él del sistema operativo. En este tema se describe cómo crear una instancia de un objeto [TimeZoneInfo](xref:System.TimeZoneInfo) desde el sistema local.

## <a name="to-instantiate-a-timezoneinfo-object"></a>Cómo crear una instancia de un objeto TimeZoneInfo

1. Declarar un objeto [TimeZoneInfo](xref:System.TimeZoneInfo).

2. Llamar al método `static` (`Shared` en Visual Basic) [TimeZoneInfo.FindSystemTimeZoneById](xref:System.TimeZoneInfo.FindSystemTimeZoneById(System.String)).

3. Controlar las excepciones iniciadas por el método.

## <a name="example"></a>Ejemplo

El siguiente código recupera un objeto [TimeZoneInfo](xref:System.TimeZoneInfo) que representa la zona horaria estándar del Este y muestra la hora estándar del Este que corresponde a la hora local.

```csharp
DateTime timeNow = DateTime.Now;
try
{
   TimeZoneInfo easternZone = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time");
   DateTime easternTimeNow = TimeZoneInfo.ConvertTime(timeNow, TimeZoneInfo.Local, 
                                                   easternZone);
   Console.WriteLine("{0} {1} corresponds to {2} {3}.",
                     timeNow, 
                     TimeZoneInfo.Local.IsDaylightSavingTime(timeNow) ?
                               TimeZoneInfo.Local.DaylightName : 
                               TimeZoneInfo.Local.StandardName,
                     easternTimeNow, 
                     easternZone.IsDaylightSavingTime(easternTimeNow) ?
                                 easternZone.DaylightName : 
                                 easternZone.StandardName);
}
// Handle exception
//
// As an alternative to simply displaying an error message, an alternate Eastern
// Standard Time TimeZoneInfo object could be instantiated here either by restoring
// it from a serialized string or by providing the necessary data to the
// CreateCustomTimeZone method.
catch (InvalidTimeZoneException)
{
   Console.WriteLine("The Eastern Standard Time Zone contains invalid or missing data.");
}
catch (SecurityException)
{
   Console.WriteLine("The application lacks permission to read time zone information from the registry.");
}
catch (OutOfMemoryException)
{
   Console.WriteLine("Not enough memory is available to load information on the Eastern Standard Time zone.");
}
// If we weren't passing FindSystemTimeZoneById a literal string, we also 
// would handle an ArgumentNullException.
```

```vb
Dim timeNow As Date = Date.Now
Try
   Dim easternZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time")
   Dim easternTimeNow As Date = TimeZoneInfo.ConvertTime(timeNow, TimeZoneInfo.Local, easternZone)
   Console.WriteLine("{0} {1} corresponds to {2} {3}.", _
                     timeNow, _
                     IIf(TimeZoneInfo.Local.IsDaylightSavingTime(timeNow), _
                         TimeZoneInfo.Local.DaylightName, TimeZoneInfo.Local.StandardName), _
                     easternTimeNow, _
                     IIf(easternZone.IsDaylightSavingTime(easternTimeNow), _
                         easternZone.DaylightName, easternZone.StandardName))
' Handle exception
'
' As an alternative to simply displaying an error message, an alternate Eastern
' Standard Time TimeZoneInfo object could be instantiated here either by restoring
' it from a serialized string or by providing the necessary data to the
' CreateCustomTimeZone method.
Catch e As InvalidTimeZoneException
   Console.WriteLine("The Eastern Standard Time Zone contains invalid or missing data.")   
Catch e As SecurityException
   Console.WriteLine("The application lacks permission to read time zone information from the registry.")
Catch e As OutOfMemoryException
   Console.WriteLine("Not enough memory is available to load information on the Eastern Standard Time zone.")
' If we weren't passing FindSystemTimeZoneById a literal string, we also 
' would handle an ArgumentNullException.
End
``` 

El único parámetro simple del método [TimeZoneInfo.FindSystemTimeZoneById](xref:System.TimeZoneInfo.FindSystemTimeZoneById(System.String)) es el identificador de la zona horaria que quiere recuperar, que se corresponde con la propiedad [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id) del objeto. El identificador de zona horaria es un campo clave que identifica de forma única la zona horaria. Aunque la mayoría de las claves son relativamente cortas, el identificador de zona horaria es comparativamente largo. En la mayoría de los casos, su valor corresponde a la propiedad [StandardName](xref:System.TimeZoneInfo.StandardName) de un objeto [TimeZoneInfo](xref:System.TimeZoneInfo), que se usa para proporcionar el nombre de la hora estándar de la zona horaria. Sin embargo, hay excepciones. La mejor manera de asegurarse de que se proporciona un identificador válido es enumerar las zonas horarias disponibles en el sistema y anotar los identificadores de las zonas horarias que figuran en ellas. Para ver una ilustración, consulte [Cómo: Enumerar zonas horarias presentes en un equipo](enumerate-time-zones.md). El tema [Buscar las zonas horarias definidas en un sistema local](finding-the-time-zones-on-local-system.md) también contiene una lista de los identificadores de zona horaria seleccionada.

Si se encuentra la zona horaria, el método devuelve su objeto [TimeZoneInfo](xref:System.TimeZoneInfo). Si se encuentra la zona horaria, pero sus datos están dañados o incompletos, el método produce [InvalidTimeZoneException](xref:System.InvalidTimeZoneException). 

## <a name="see-also"></a>Vea también

[Fechas, horas y zonas horarias](index.md)

[Buscar las zonas horarias definidas en un sistema local](finding-the-time-zones-on-local-system.md)
