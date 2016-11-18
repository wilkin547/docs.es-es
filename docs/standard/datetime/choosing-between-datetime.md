---
title: Elegir entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo
description: Elegir entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 08/11/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 2dd84ee8-9f0f-4054-9537-155857a460cd
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: f8a603bab32afd0b8e7d13c9c5755e3f14a9d2bd

---

# <a name="choosing-between-datetime-datetimeoffset-timespan-and-timezoneinfo"></a>Elegir entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo

Las aplicaciones de .NET que usan la información de fecha y hora son muy diversas y pueden usar esa información de varias maneras. Estos son algunos de los usos más comunes de la información de fecha y hora:

* Reflejar solo la fecha (la información de hora no es importante).

* Reflejar solo la hora (la información de fecha no es importante).

* Reflejar una fecha y una hora abstractas que no estén asociadas a una hora ni a un lugar concretos (por ejemplo, la mayoría de tiendas de una cadena internacional abren los días laborables a las 09:00).

* Recuperar la información de fecha y hora desde orígenes situados fuera de la aplicación de .NET, en los que normalmente la información de fecha y hora se almacena en un tipo de datos simple.

* Identificar de forma exclusiva e inequívoca un solo punto en el tiempo. Algunas aplicaciones requieren que la fecha y la hora tan solo sean inequívocas en el sistema host; otras requieren que sean inequívocas en todos los sistemas (es decir, que una fecha serializada en un sistema se pueda deserializar y usar con sentido en otro sistema en cualquier lugar en el mundo). 

* Conservar varias horas relacionadas (como la hora local del solicitante y la hora de recepción del servidor con respecto a una solicitud web).

* Realizar operaciones aritméticas de fecha y hora, posiblemente con un resultado que identifica de forma exclusiva e inequívoca un único punto en el tiempo. 

.NET incluye los tipos [System.DateTime](xref:System.DateTime), [System.DateTimeOffset](xref:System.DateTimeOffset), [System.TimeSpan](xref:System.TimeSpan) y [System.TimeZoneInfo](xref:System.TimeZoneInfo), que se pueden usar para crear aplicaciones que funcionen con fechas y horas. 

> [!NOTE]
> En este tema, no se describe el tipo `TimeZone` antiguo, porque su funcionalidad está incorporada casi por completo en la clase [System.TimeZoneInfo](xref:System.TimeZoneInfo). Siempre que sea posible, los desarrolladores deben usar la clase [System.TimeZoneInfo](xref:System.TimeZoneInfo) en lugar de la clase `TimeZone`.


## <a name="the-datetime-structure"></a>DateTime (estructura)

Un valor [System.DateTime](xref:System.DateTime) define una fecha y hora concretas. Se incluye una propiedad [Kind](xref:System.DateTime.Kind) que proporciona información limitada sobre la zona horaria a la que pertenece la fecha y hora. El valor [DateTimeKind](xref:System.DateTimeKind) devuelto por la propiedad [Kind](xref:System.DateTime.Kind) indica si el valor [DateTime](xref:System.DateTime) representa la hora local [DateTimeKind.Local](xref:System.DateTimeKind.Local)), la hora universal coordinada (UTC) [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) o una hora no especificada [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified).

La estructura [DateTime](xref:System.DateTime) es adecuada para aplicaciones que hacen lo siguiente: 

* Trabajar solo con fechas.

* Trabajar solo con horas.

* Trabajar con fechas y horas abstractas.

* Trabajar con fechas y horas cuya información de zona horaria no esté disponible. 

* Trabajar solo con fechas y horas UTC. 

* Recuperar información de fecha y hora de orígenes situados fuera de .NET Framework, como bases de datos SQL. Normalmente, estos orígenes almacenan la información de fecha y hora en un formato sencillo que es compatible con la estructura [DateTime](xref:System.DateTime).

* Realizar operaciones aritméticas de fecha y hora, pero con interés por los resultados generales. Por ejemplo, en una operación que suma seis meses a una determinada fecha y hora, a menudo no resulta importante si el resultado se ajusta al horario de verano.

A menos que un determinado valor [DateTime](xref:System.DateTime) represente la hora UTC, ese valor de fecha y hora suele ser ambiguo o limitado en su portabilidad. Por ejemplo, si un valor [DateTime](xref:System.DateTime) representa la hora local, entonces se puede mover en la zona horaria local (es decir, si el valor se deserializa en otro sistema de la misma zona horaria, dicho valor sigue identificando inequívocamente un único momento específico). Fuera de la zona horaria local, ese valor [DateTime](xref:System.DateTime) puede tener varias interpretaciones. Si la propiedad [Kind](xref:System.DateTime.Kind) del valor es [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), es aún menos móvil: ahora es ambiguo dentro de la misma zona horaria y posiblemente incluso en el mismo sistema en el que se ha serializado por primera vez. Solo si un valor [DateTime](xref:System.DateTime) representa la hora UTC, ese valor identificará inequívocamente un único momento específico con independencia del sistema o la zona horaria en los que se usa el valor.

> [!IMPORTANT]
> Al guardar o compartir datos de [DateTime](xref:System.DateTime), debe usarse la hora UTC, y la propiedad [Kind](xref:System.DateTime.Kind) del valor [DateTime](xref:System.DateTime) debe establecerse en [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).

## <a name="the-datetimeoffset-structure"></a>DateTimeOffset (estructura)

La estructura [System.DateTimeOffset](xref:System.DateTimeOffset) representa un valor de fecha y hora, junto con un desplazamiento que indica la diferencia de ese valor con respecto a la hora UTC. Por lo tanto, el valor identifica siempre de forma inequívoca un único punto en el tiempo. 

El tipo [DateTimeOffset](xref:System.DateTimeOffset) incluye toda la funcionalidad del tipo [DateTime](xref:System.DateTime) junto con la zona horaria. Esto lo hace adecuado para aplicaciones que hacen lo siguiente: 

* Identificar de forma exclusiva e inequívoca un solo punto en el tiempo. El tipo [DateTimeOffset](xref:System.DateTimeOffset) puede usarse para definir inequívocamente el significado de "ahora", para registrar los tiempos de transacción, para registrar la hora de eventos del sistema o de aplicaciones y para registrar los tiempos de creación y modificación de archivos. 

* Realizar operaciones aritméticas generales de fecha y hora.

* Conservar varias horas relacionadas, siempre que esas horas se almacenen como dos valores independientes o como dos miembros de una estructura.

> [!NOTE]
> Estos usos de valores [DateTimeOffset](xref:System.DateTimeOffset) son mucho más comunes que los de valores [DateTime](xref:System.DateTime). Como resultado, [DateTimeOffset](xref:System.DateTimeOffset) debe considerarse como el tipo de fecha y hora predeterminado para el desarrollo de aplicaciones.

Un valor [DateTimeOffset](xref:System.DateTimeOffset) no está asociado a una zona horaria determinada, pero puede originarse en distintas zonas horarias. Para ilustrar esto, en el ejemplo siguiente, se enumeran las zonas horarias a las que pueden pertenecer varios valores [DateTimeOffset](xref:System.DateTimeOffset) (incluida una hora estándar local del Pacífico).

```csharp
using System;
using System.Collections.ObjectModel;

public class TimeOffsets
{
   public static void Main()
   {
      DateTime thisDate = new DateTime(2007, 3, 10, 0, 0, 0);
      DateTime dstDate = new DateTime(2007, 6, 10, 0, 0, 0);
      DateTimeOffset thisTime;

      thisTime = new DateTimeOffset(dstDate, new TimeSpan(-7, 0, 0));
      ShowPossibleTimeZones(thisTime);

      thisTime = new DateTimeOffset(thisDate, new TimeSpan(-6, 0, 0));  
      ShowPossibleTimeZones(thisTime);

      thisTime = new DateTimeOffset(thisDate, new TimeSpan(+1, 0, 0));
      ShowPossibleTimeZones(thisTime);
   }

   private static void ShowPossibleTimeZones(DateTimeOffset offsetTime)
   {
      TimeSpan offset = offsetTime.Offset;
      ReadOnlyCollection<TimeZoneInfo> timeZones;

      Console.WriteLine("{0} could belong to the following time zones:", 
                        offsetTime.ToString());
      // Get all time zones defined on local system
      timeZones = TimeZoneInfo.GetSystemTimeZones();     
      // Iterate time zones 
      foreach (TimeZoneInfo timeZone in timeZones)
      {
         // Compare offset with offset for that date in that time zone
         if (timeZone.GetUtcOffset(offsetTime.DateTime).Equals(offset))
            Console.WriteLine("   {0}", timeZone.DisplayName);
      }
      Console.WriteLine();
   } 
}
// This example displays the following output to the console:
//       6/10/2007 12:00:00 AM -07:00 could belong to the following time zones:
//          (GMT-07:00) Arizona
//          (GMT-08:00) Pacific Time (US & Canada)
//          (GMT-08:00) Tijuana, Baja California
//       
//       3/10/2007 12:00:00 AM -06:00 could belong to the following time zones:
//          (GMT-06:00) Central America
//          (GMT-06:00) Central Time (US & Canada)
//          (GMT-06:00) Guadalajara, Mexico City, Monterrey - New
//          (GMT-06:00) Guadalajara, Mexico City, Monterrey - Old
//          (GMT-06:00) Saskatchewan
//       
//       3/10/2007 12:00:00 AM +01:00 could belong to the following time zones:
//          (GMT+01:00) Amsterdam, Berlin, Bern, Rome, Stockholm, Vienna
//          (GMT+01:00) Belgrade, Bratislava, Budapest, Ljubljana, Prague
//          (GMT+01:00) Brussels, Copenhagen, Madrid, Paris
//          (GMT+01:00) Sarajevo, Skopje, Warsaw, Zagreb
//          (GMT+01:00) West Central Africa
```

```vb
Imports System.Collections.ObjectModel

Module TimeOffsets
   Public Sub Main()
      Dim thisTime As DateTimeOffset 

      thisTime = New DateTimeOffset(#06/10/2007#, New TimeSpan(-7, 0, 0))
      ShowPossibleTimeZones(thisTime) 

      thisTime = New DateTimeOffset(#03/10/2007#, New TimeSpan(-6, 0, 0))  
      ShowPossibleTimeZones(thisTime)

      thisTime = New DateTimeOffset(#03/10/2007#, New TimeSpan(+1, 0, 0))
      ShowPossibleTimeZones(thisTime)
   End Sub

   Private Sub ShowPossibleTimeZones(offsetTime As DateTimeOffset)
      Dim offset As TimeSpan = offsetTime.Offset
      Dim timeZones As ReadOnlyCollection(Of TimeZoneInfo)

      Console.WriteLine("{0} could belong to the following time zones:", _
                        offsetTime.ToString())
      ' Get all time zones defined on local system
      timeZones = TimeZoneInfo.GetSystemTimeZones()     
      ' Iterate time zones
      For Each timeZone As TimeZoneInfo In timeZones
         ' Compare offset with offset for that date in that time zone
         If timeZone.GetUtcOffset(offsetTime.DateTime).Equals(offset) Then
            Console.WriteLine("   {0}", timeZone.DisplayName)
         End If   
      Next
      Console.WriteLine()
   End Sub
End Module
' This example displays the following output to the console:
'       6/10/2007 12:00:00 AM -07:00 could belong to the following time zones:
'          (GMT-07:00) Arizona
'          (GMT-08:00) Pacific Time (US & Canada)
'          (GMT-08:00) Tijuana, Baja California
'       
'       3/10/2007 12:00:00 AM -06:00 could belong to the following time zones:
'          (GMT-06:00) Central America
'          (GMT-06:00) Central Time (US & Canada)
'          (GMT-06:00) Guadalajara, Mexico City, Monterrey - New
'          (GMT-06:00) Guadalajara, Mexico City, Monterrey - Old
'          (GMT-06:00) Saskatchewan
'       
'       3/10/2007 12:00:00 AM +01:00 could belong to the following time zones:
'          (GMT+01:00) Amsterdam, Berlin, Bern, Rome, Stockholm, Vienna
'          (GMT+01:00) Belgrade, Bratislava, Budapest, Ljubljana, Prague
'          (GMT+01:00) Brussels, Copenhagen, Madrid, Paris
'          (GMT+01:00) Sarajevo, Skopje, Warsaw, Zagreb
'          (GMT+01:00) West Central Africa
```

La salida muestra que cada valor de fecha y hora de este ejemplo puede pertenecer al menos a tres zonas horarias diferentes. El valor [DateTimeOffset](xref:System.DateTimeOffset) de 6/10/2007 muestra que, si un valor de fecha y hora representa un horario de verano, su desplazamiento de la hora UTC no tiene que corresponderse necesariamente con el desplazamiento de UTC base de la zona horaria de origen o con el desplazamiento de UTC de su nombre para mostrar. Esto significa que, dado que un solo valor [DateTimeOffset](xref:System.DateTimeOffset) no está asociado estrechamente con su zona horaria, no puede reflejar un cambio de zona horaria con respecto al horario de verano. Esto puede ser particularmente problemático cuando se usan operaciones aritméticas de fecha y hora para manipular un valor [DateTimeOffset](xref:System.DateTimeOffset). Para obtener información sobre cómo realizar operaciones aritméticas de fecha y hora teniendo en cuenta las reglas de ajuste de una zona horaria, consulte [Efectuar operaciones aritméticas con fechas y horas](performing-arithmetic-operations.md).

## <a name="the-timespan-structure"></a>TimeSpan (estructura)

La estructura [System.TimeSpan](xref:System.TimeSpan) representa un intervalo de tiempo. Sus dos usos típicos son: 

* Reflejar el intervalo de tiempo entre dos valores de fecha y hora. Por ejemplo, restar un valor [DateTime](xref:System.DateTime) de otro devuelve un valor [TimeSpan](xref:System.TimeSpan). 

* Medir el tiempo transcurrido. Por ejemplo, la propiedad [Stopwatch.Elapsed](xref:System.Diagnostics.Stopwatch.Elapsed) devuelve un valor [TimeSpan](xref:System.TimeSpan) que refleja el intervalo de tiempo transcurrido desde la llamada a uno de los métodos [System.Diagnostics.Stopwatch](xref:System.Diagnostics.Stopwatch) que empieza a medir el tiempo transcurrido.

Un valor [TimeSpan](xref:System.TimeSpan) también puede usarse como sustituto de un valor [DateTime](xref:System.DateTime) cuando ese valor refleja una hora sin referencia a una hora determinada del día. Este uso es similar a las propiedades [DateTime.TimeOfDay](xref:System.DateTime.TimeOfDay) y [DateTimeOffset.TimeOfDay](xref:System.DateTimeOffset.TimeOfDay), que devuelven un valor [TimeSpan](xref:System.TimeSpan) que representa el tiempo sin referencia a una fecha. Por ejemplo, la estructura [TimeSpan](xref:System.TimeSpan) puede usarse para reflejar la hora diaria de apertura o cierre de una tienda, o puede usarse para representar la hora en que se produce cualquier evento habitual.

En el ejemplo siguiente, se define una estructura `StoreInfo` que incluye objetos [TimeSpan](xref:System.TimeSpan) para las horas de apertura y cierre de la tienda, así como un objeto [TimeZoneInfo](xref:System.TimeZoneInfo) que representa la zona horaria de la tienda. La estructura también incluye dos métodos, `IsOpenNow` e `IsOpenAt`, que indican si la tienda está abierta en el momento especificado por el usuario, quien se supone que está en la zona horaria local.  

```csharp
using System;

public struct StoreInfo
{
   public String store;
   public TimeZoneInfo tz;
   public TimeSpan open;
   public TimeSpan close;

   public bool IsOpenNow()
   {
      return IsOpenAt(DateTime.TimeOfDay);
   }

   public bool IsOpenAt(TimeSpan time)
   {
      TimeZoneInfo local = TimeZoneInfo.Local;
      TimeSpan offset = TimeZoneInfo.BaseUtcOffset;

      // Is the store in the same time zone?
      if (tz.Equals(local)) {
         return time >= open & time <= close;
      }
   }
}
```

```vb
Public Structure StoreInfo
   Dim store As String
   Dim tz As TimeZoneInfo
   Dim open As TimeSpan
   Dim close As TimeSpan

   Public Function IsOpenNow() As Boolean
      Return IsOpenAt(Date.Now.TimeOfDay)
   End Function

   Public Function IsOpenAt(time As TimeSpan) As Boolean
      Dim local As TimeZoneInfo = TimeZoneInfo.Local
      Dim offset As TimeSpan = TimeZoneInfo.Local.BaseUtcOffset

      ' Is the store in the same time zone?
      If tz.Equals(local) Then
         Return time >= open And time <= close
      Else
         Dim delta As TimeSpan = TimeSpan.Zero
         Dim storeDelta As TimeSpan = TimeSpan.Zero

         ' Is it daylight saving time in either time zone?
         If local.IsDaylightSavingTime(Date.Now.Date + time) Then
            delta = local.GetAdjustmentRules(local.GetAdjustmentRules().Length - 1).DaylightDelta
         End If
         If tz.IsDaylightSavingTime(TimeZoneInfo.ConvertTime(Date.Now.Date + time, local, tz))
            storeDelta = tz.GetAdjustmentRules(local.GetAdjustmentRules().Length - 1).DaylightDelta
         End If
         Dim comparisonTime As TimeSpan = time + (offset - tz.BaseUtcOffset).Negate() + (delta - storeDelta).Negate
         Return (comparisonTime >= open And comparisonTime <= close)
      End If
   End Function
End Structure
```

La estructura `StoreInfo` puede usarla un código de cliente como este. 

```csharp
public class Example
{
   public static void Main()
   {
      // Instantiate a StoreInfo object.
      var store103 = new StoreInfo();
      store103.store = "Store #103";
      store103.tz = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time");
      // Store opens at 8:00.
      store103.open = new TimeSpan(8, 0, 0);
      // Store closes at 9:30.
      store103.close = new TimeSpan(21, 30, 0);

      Console.WriteLine("Store is open now at {0}: {1}",
                        DateTime.TimeOfDay, store103.IsOpenNow());
      TimeSpan[] times = { new TimeSpan(8, 0, 0), new TimeSpan(21, 0, 0),
                           new TimeSpan(4, 59, 0), new TimeSpan(18, 31, 0) };
      foreach (var time in times)
         Console.WriteLine("Store is open at {0}: {1}",
                           time, store103.IsOpenAt(time));
   }
}
// The example displays the following output:
//       Store is open now at 15:29:01.6129911: True
//       Store is open at 08:00:00: True
//       Store is open at 21:00:00: False
//       Store is open at 04:59:00: False
//       Store is open at 18:31:00: False
```

```vb
Module Example
   Public Sub Main()
      ' Instantiate a StoreInfo object.
      Dim store103 As New StoreInfo()
      store103.store = "Store #103"
      store103.tz = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time")
      ' Store opens at 8:00.
      store103.open = new TimeSpan(8, 0, 0)
      ' Store closes at 9:30.
      store103.close = new TimeSpan(21, 30, 0)

      Console.WriteLine("Store is open now at {0}: {1}",
                        Date.Now.TimeOfDay, store103.IsOpenNow())
      Dim times() As TimeSpan = { New TimeSpan(8, 0, 0),
                                  New TimeSpan(21, 0, 0),
                                  New TimeSpan(4, 59, 0),
                                  New TimeSpan(18, 31, 0) }
      For Each time In times
         Console.WriteLine("Store is open at {0}: {1}",
                           time, store103.IsOpenAt(time))
      Next
   End Sub
End Module
' The example displays the following output:
'       Store is open now at 15:29:01.6129911: True
'       Store is open at 08:00:00: True
'       Store is open at 21:00:00: False
'       Store is open at 04:59:00: False
'       Store is open at 18:31:00: False
```

## <a name="the-timezoneinfo-class"></a>TimeZoneInfo (clase)

La clase [System.TimeZoneInfo](xref:System.TimeZoneInfo) representa cualquiera de las zonas horarias del mundo y permite la conversión de cualquier fecha y hora de una zona horaria a su equivalente de otra zona horaria. La clase [TimeZoneInfo](xref:System.TimeZoneInfo) permite trabajar con valores de fecha y hora de forma que cada uno de esos valores identifique de forma inequívoca un único momento específico.

En algunos casos, si quiere aprovechar al máximo la clase [TimeZoneInfo](xref:System.TimeZoneInfo) puede que tenga que desarrollar aún más. Los valores de fecha y hora no están vinculados estrechamente con las zonas horarias a las que pertenecen. Como resultado, a menos que la aplicación proporcione algún mecanismo para vincular una fecha y hora con su zona horaria asociada, es fácil que un determinado valor de fecha y hora se desasocie de su zona horaria. Un método para vincular esta información es definir una clase o estructura que contenga el valor de fecha y hora, y su objeto de zona horaria asociada.

Aprovechar la compatibilidad de zona horaria en .NET solo es posible si se conoce la zona horaria a la que pertenece un valor de fecha y hora cuando se crea una instancia de ese objeto de fecha y hora. A menudo este no es el caso, especialmente en aplicaciones web o de red.

## <a name="see-also"></a>Vea también

[Fechas, horas y zonas horarias](index.md)


<!--HONumber=Nov16_HO3-->


