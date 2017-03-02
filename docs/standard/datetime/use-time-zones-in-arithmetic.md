---
title: "Cómo usar zonas horarias en operaciones aritméticas de fecha y hora"
description: "Cómo usar zonas horarias en operaciones aritméticas de fecha y hora"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 26870cdc-1709-4978-831b-ff2a2f24856f
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: a86471972d42adcbc412cc8eeb300410ca8a9c42
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a>Cómo usar zonas horarias en operaciones aritméticas de fecha y hora

Normalmente, cuando se realizan operaciones aritméticas de fecha y hora mediante valores [System.DateTimeOffset](xref:System.DateTimeOffset), el resultado no refleja ninguna regla de ajuste de zona horaria. Esto ocurre incluso cuando la zona horaria del valor de fecha y hora es claramente identificable. Este artículo muestra cómo realizar operaciones aritméticas en valores de fecha y hora que pertenecen a una zona horaria determinada. Los resultados de las operaciones aritméticas reflejarán las reglas de ajuste de la zona horaria.

## <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a>Para aplicar las reglas de ajuste a la fecha y hora aritmético

1. Implemente algún método para acoplar estrechamente un valor de fecha y hora con la zona horaria a la que pertenece. Por ejemplo, declare una estructura que incluya tanto el valor de fecha y hora como su zona horaria. En el ejemplo siguiente se usa este enfoque para vincular un valor [DateTimeOffset](xref:System.DateTimeOffset) con su zona horaria.

    ```csharp
    // Define a structure for DateTime values for internal use only
    internal struct TimeWithTimeZone
    {
    TimeZoneInfo TimeZone;
    DateTimeOffset Time;
    }
    ```

    ```vb
    ' Define a structure for DateTime values for internal use only
    Friend Structure TimeWithTimeZone
       Dim TimeZone As TimeZoneInfo
       Dim Time As Date
    End Structure
    ```
    
2. Convierta una hora en hora universal coordinada (UTC) llamando al método [TimeZoneInfo.ConvertTime (DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)).

3. Realice la operación aritmética en la hora UTC.

4. Convierta la hora de la hora UTC a la zona horaria asociada a la hora original llamando al método [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)). 

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se agregan dos horas y treinta minutos al 9 de marzo de 2008, a la 1:30 A.M. zona horaria estándar central. La transición de esa zona horaria al horario de verano se produce treinta minutos más tarde, a las 2:00 A.M. del 9 de marzo de 2008. Puesto que el ejemplo sigue los cuatro pasos indicados en la sección anterior, se notifica correctamente la hora resultante como las 5:00 A.M. del 9 de marzo de 2008. 

```csharp
using System;

public struct TimeZoneTime
{
   public TimeZoneInfo TimeZone;
   public DateTimeOffset Time;

   public TimeZoneTime(TimeZoneInfo tz, DateTimeOffset time)
   {
      if (tz == null) 
         throw new ArgumentNullException("The time zone cannot be a null reference.");

      this.TimeZone = tz;
      this.Time = time;   
   }

   public TimeZoneTime AddTime(TimeSpan interval)
   {
      // Convert time to UTC
      DateTimeOffset utcTime = TimeZoneInfo.ConvertTime(this.Time, TimeZoneInfo.Utc);      
      // Add time interval to time
      utcTime = utcTime.Add(interval);
      // Convert time back to time in time zone
      return new TimeZoneTime(this.TimeZone, TimeZoneInfo.ConvertTime(utcTime, this.TimeZone));
   }
}

public class TimeArithmetic
{
   public const string tzName = "Central Standard Time";

   public static void Main()
   {
      try
      {
         TimeZoneTime cstTime1, cstTime2;

         TimeZoneInfo cst = TimeZoneInfo.FindSystemTimeZoneById(tzName);
         DateTime time1 = new DateTime(2008, 3, 9, 1, 30, 0);          
         TimeSpan twoAndAHalfHours = new TimeSpan(2, 30, 0);

         cstTime1 = new TimeZoneTime(cst, 
                        new DateTimeOffset(time1, cst.GetUtcOffset(time1)));
         cstTime2 = cstTime1.AddTime(twoAndAHalfHours);
         Console.WriteLine("{0} + {1} hours = {2}", cstTime1.Time, 
                                                    twoAndAHalfHours.ToString(),  
                                                    cstTime2.Time);
      }
      catch
      {
         Console.WriteLine("Unable to find {0}.", tzName);
      }
   }
}
```

```vb
Public Structure TimeZoneTime
   Public TimeZone As TimeZoneInfo
   Public Time As Date

   Public Sub New(tz As TimeZoneInfo, time As Date)
      If tz Is Nothing Then _
         Throw New ArgumentNullException("The time zone cannot be a null reference.")

      Me.TimeZone = tz
      Me.Time = time
   End Sub

   Public Function AddTime(interval As TimeSpan) As TimeZoneTime
      ' Convert time to UTC
      Dim utcTime As DateTime = TimeZoneInfo.ConvertTimeToUtc(Me.Time, _
                                                              Me.TimeZone)      
      ' Add time interval to time
      utcTime = utcTime.Add(interval)
      ' Convert time back to time in time zone
      Return New TimeZoneTime(Me.TimeZone, TimeZoneInfo.ConvertTime(utcTime, _
                              TimeZoneInfo.Utc, Me.TimeZone))
   End Function
End Structure

Module TimeArithmetic
   Public Const tzName As String = "Central Standard Time"

   Public Sub Main()
      Try
         Dim cstTime1, cstTime2 As TimeZoneTime

         Dim cst As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(tzName)
         Dim time1 As Date = #03/09/2008 1:30AM#
         Dim twoAndAHalfHours As New TimeSpan(2, 30, 0)

         cstTime1 = New TimeZoneTime(cst, time1)
         cstTime2 = cstTime1.AddTime(twoAndAHalfHours)

         Console.WriteLine("{0} + {1} hours = {2}", cstTime1.Time, _
                                                    twoAndAHalfHours.ToString(), _ 
                                                    cstTime2.Time)  
      Catch
         Console.WriteLine("Unable to find {0}.", tzName)
      End Try   
   End Sub   
End Module
```

Tenga en cuenta que, si esta suma se realiza simplemente en el valor [DateTimeOffset](xref:System.DateTimeOffset) sin convertirlo antes a UTC, el resultado reflejará el punto en el tiempo correcto, pero su desplazamiento no reflejará el de la zona horaria designada para esa hora. 

Los valores [DateTimeOffset](xref:System.DateTimeOffset) están desasociados de cualquier zona horaria a la que puedan pertenecer. Para realizar operaciones aritméticas de fecha y hora de tal manera que apliquen automáticamente las reglas de ajuste de una zona horaria, la zona horaria a la que pertenezca cualquier valor de fecha y hora debe ser identificable de forma inmediata. Esto significa que un valor de fecha y hora y su zona horaria asociada deben estar estrechamente acoplados. Hay varias maneras de hacer esto, que incluyen las siguientes:

* Suponer que todas las horas usadas en una aplicación pertenecen a una zona horaria determinada. Aunque es adecuado en algunos casos, este enfoque tiene una flexibilidad limitada y posiblemente, una portabilidad limitada.

* Definir un tipo que acople estrechamente una fecha y hora con su zona horaria asociada, incluyendo ambas como campos del tipo. Este enfoque es el que se usa en el ejemplo de código, que define una estructura para almacenar la fecha y hora y la zona horaria en dos campos de miembro.

## <a name="see-also"></a>Vea también

[Fechas, horas y zonas horarias](index.md)

[Efectuar operaciones aritméticas con fechas y horas](performing-arithmetic-operations.md)

