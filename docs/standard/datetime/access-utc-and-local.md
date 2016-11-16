---
title: "Cómo: Obtener acceso a los objetos de zona horaria local y UTC predefinidos"
description: "Cómo obtener acceso a los objetos de zona horaria local y UTC predefinidos"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 08/11/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 13454d47-d957-421b-9ecd-940058b8835e
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: 865e41ca544e8931d0a7037310387e077d8a5547

---

# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a>Cómo: Obtener acceso a los objetos de zona horaria local y UTC predefinidos

La clase [System.TimeZoneInfo](xref:System.TimeZoneInfo) proporciona dos propiedades, `Utc` y `Local`, que dan al código acceso a los objetos de zona horaria predefinidos. En este tema, se describe cómo obtener acceso a los objetos `TimeZoneInfo` que devuelven esas propiedades.

## <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a>Para obtener acceso al objeto TimeZoneInfo de la hora universal coordinada (UTC)

1. Use la propiedad **static** (**Shared** en Visual Basic) [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) para obtener acceso a la hora universal coordinada.

2. En lugar de asignar el objeto [TimeZoneInfo](xref:System.TimeZoneInfo) que ha devuelto la propiedad a una variable de objeto, siga accediendo a la hora universal coordinada a través de la propiedad [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc).


## <a name="to-access-the-local-time-zone"></a>Para obtener acceso a la zona horaria local

1. Use la propiedad **static** (**Shared** en Visual Basic) [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) para obtener acceso a la zona horaria local del sistema.

2. En lugar de asignar el objeto [TimeZoneInfo](xref:System.TimeZoneInfo) que ha devuelto la propiedad a una variable de objeto, siga accediendo a la zona horaria local a través de la propiedad [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local).

## <a name="example"></a>Ejemplo

En el siguiente código, se usan las propiedades [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) y [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) para convertir una hora de la zona horaria estándar del Este de Estados Unidos y Canadá, así como para mostrar el nombre de la zona horaria en la consola.

```csharp
// Create Eastern Standard Time value and TimeZoneInfo object      
DateTime estTime = new DateTime(2007, 1, 1, 00, 00, 00);
string timeZoneName = "Eastern Standard Time";
try
{
   TimeZoneInfo est = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName);

   // Convert EST to local time
   DateTime localTime = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Local);
   Console.WriteLine("At {0} {1}, the local time is {2} {3}.", 
           estTime, 
           est, 
           localTime, 
           TimeZoneInfo.Local.IsDaylightSavingTime(localTime) ?
                     TimeZoneInfo.Local.DaylightName : 
                     TimeZoneInfo.Local.StandardName);

   // Convert EST to UTC
   DateTime utcTime = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Utc);
   Console.WriteLine("At {0} {1}, the time is {2} {3}.", 
           estTime, 
           est, 
           utcTime, 
           TimeZoneInfo.Utc.StandardName);
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("The {0} zone cannot be found in the registry.", 
                     timeZoneName);
}
catch (InvalidTimeZoneException)
{
   Console.WriteLine("The registry contains invalid data for the {0} zone.", 
                     timeZoneName);
}
```

```vb
' Create Eastern Standard Time value and TimeZoneInfo object      
Dim estTime As Date = #01/01/2007 00:00:00#
Dim timeZoneName As String = "Eastern Standard Time"
Try
   Dim est As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName)

   ' Convert EST to local time
   Dim localTime As Date = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Local)
   Console.WriteLine("At {0} {1}, the local time is {2} {3}.", _
           estTime, _
           est, _
           localTime, _
           IIf(TimeZoneInfo.Local.IsDaylightSavingTime(localTime), _
               TimeZoneInfo.Local.DaylightName, _
               TimeZoneInfo.Local.StandardName))

   ' Convert EST to UTC
   Dim utcTime As Date = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Utc)
   Console.WriteLine("At {0} {1}, the time is {2} {3}.", _
           estTime, _
           est, _
           utcTime, _
           TimeZoneInfo.Utc.StandardName)
Catch e As TimeZoneNotFoundException
   Console.WriteLine("The {0} zone cannot be found in the registry.", _
                     timeZoneName)
Catch e As InvalidTimeZoneException
   Console.WriteLine("The registry contains invalid data for the {0} zone.", _
                     timeZoneName)
End Try
```

Siempre debe obtener acceso a la zona horaria local a través de la propiedad [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) en lugar de asignar la zona horaria local a una variable de objeto [TimeZoneInfo](xref:System.TimeZoneInfo). Asimismo, siempre debe obtener acceso a la hora universal coordinada a través de la propiedad [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) en lugar de asignar la zona UTC a una variable de objeto [TimeZoneInfo](xref:System.TimeZoneInfo). Esto evita que un método externo invalide la variable de objeto [TimeZoneInfo](xref:System.TimeZoneInfo).


## <a name="see-also"></a>Vea también

[Fechas, horas y zonas horarias](index.md)

[Buscar las zonas horarias definidas en un sistema local](finding-the-time-zones-on-local-system.md)



<!--HONumber=Nov16_HO1-->


