---
title: "Efectuar operaciones aritméticas con fechas y horas"
description: "Efectuar operaciones aritméticas con fechas y horas"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 589ac5ec-8365-4a0d-bc38-72183718110c
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: 64fbb3b25d5959ac1dd781d2076775560d926e1a

---

# <a name="performing-arithmetic-operations-with-dates-and-times"></a>Efectuar operaciones aritméticas con fechas y horas

Aunque tanto la estructura [System.DateTime](xref:System.DateTime) como la estructura [System.DateTimeOffset](xref:System.DateTimeOffset) proporcionan miembros que realizan operaciones aritméticas en sus valores, los resultados de las operaciones aritméticas son muy diferentes. En este artículo se examinan las diferencias, se relacionan con los grados de reconocimiento de la zona horaria en los datos de fecha y hora, y se explica cómo realizar operaciones con reconocimiento completo de la zona horaria mediante datos de fecha y hora.

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>Comparaciones y operaciones aritméticas con valores DateTime

Los valores [System.DateTime](xref:System.DateTime) poseen un grado limitado de reconocimiento de la zona horaria. La propiedad [DateTime.Kind](xref:System.DateTime.Kind) permite asignar un valor [System.DateTimeKind](xref:System.DateTimeKind) a la fecha y hora para indicar si representa la hora local, la hora universal coordinada (UTC) o la hora de una zona horaria no especificada. Pero esta información limitada de zona horaria se omite al realizar comparaciones u operaciones aritméticas con fechas y horas en valores [DateTime](xref:System.DateTime). Esto se muestra en el ejemplo siguiente, que compara la hora local actual con la hora UTC actual.

```csharp
using System;

public enum TimeComparison
{
   EarlierThan = -1,
   TheSameAs = 0,
   LaterThan = 1
}

public class DateManipulation
{
   public static void Main()
   {
      DateTime localTime = DateTime.Now;
      DateTime utcTime = DateTime.UtcNow;

      Console.WriteLine("Difference between {0} and {1} time: {2}:{3} hours", 
                        localTime.Kind.ToString(), 
                        utcTime.Kind.ToString(), 
                        (localTime - utcTime).Hours, 
                        (localTime - utcTime).Minutes);
      Console.WriteLine("The {0} time is {1} the {2} time.", 
                        localTime.Kind.ToString(), 
                        Enum.GetName(typeof(TimeComparison), localTime.CompareTo(utcTime)), 
                        utcTime.Kind.ToString());  
   }
}
// If run in the U.S. Pacific Standard Time zone, the example displays 
// the following output to the console:
//    Difference between Local and Utc time: -7:0 hours
//    The Local time is EarlierThan the Utc time.
```

```vb
Public Enum TimeComparison As Integer
   EarlierThan = -1
   TheSameAs = 0
   LaterThan = 1
End Enum

Module DateManipulation
   Public Sub Main()
      Dim localTime As Date = Date.Now
      Dim utcTime As Date = Date.UtcNow

      Console.WriteLine("Difference between {0} and {1} time: {2}:{3} hours", _
                        localTime.Kind.ToString(), _
                        utcTime.Kind.ToString(), _
                        (localTime - utcTime).Hours, _
                        (localTime - utcTime).Minutes)
      Console.WriteLine("The {0} time is {1} the {2} time.", _
                        localTime.Kind.ToString(), _ 
                        [Enum].GetName(GetType(TimeComparison), localTime.CompareTo(utcTime)), _
                        utcTime.Kind.ToString())  
      ' If run in the U.S. Pacific Standard Time zone, the example displays 
      ' the following output to the console:
      '    Difference between Local and Utc time: -7:0 hours
      '    The Local time is EarlierThan the Utc time.                                                    
   End Sub
End Module
```

El método [DateTime.CompareTo(DateTime, DateTime)](xref:System.DateTime.Compare(System.DateTime,System.DateTime)) informa de que la hora local es anterior a (o menor que) la hora UTC, y la operación de resta indica que la diferencia entre la hora UTC y la hora local de un sistema de la zona de Hora estándar del Pacífico de los Estados Unidos es de siete horas. Pero, dado que estos dos valores proporcionan representaciones diferentes de un único punto en el tiempo, resulta evidente en este caso que este intervalo de tiempo es totalmente atribuible a la diferencia horaria de la zona horaria local respecto de la hora UTC. 

Por lo general, la propiedad [DateTimeKind](xref:System.DateTimeKind) no afecta a los resultados devueltos por los métodos aritméticos y de comparación de [DateTime](xref:System.DateTime) (como indica la comparación de dos puntos idénticos en el tiempo), aunque puede afectar a la interpretación de los resultados. Por ejemplo:

* El resultado de cualquier operación aritmética realizada en dos valores de fecha y hora cuyas propiedades [DateTimeKind](xref:System.DateTimeKind) sean iguales a [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) refleja el intervalo de tiempo real entre los dos valores. Del mismo modo, la comparación de estos dos valores de fecha y hora refleja con exactitud la relación entre los tiempos.

* El resultado de cualquier operación aritmética o de comparación realizada en dos valores de fecha y hora cuyas propiedades [DateTimeKind](xref:System.DateTimeKind) sean iguales a [DateTimeKind.Local](xref:System.DateTimeKind.Local), o en dos valores de fecha y hora con diferentes valores de la propiedad [DateTimeKind](xref:System.DateTimeKind), refleja la diferencia en el tiempo de reloj de los dos valores. 

* Las operaciones aritméticas o de comparación en valores de fecha y hora local no tienen en cuenta si un valor concreto es ambiguo o no válido, ni tienen en cuenta el efecto de las reglas de ajuste que son consecuencia de la transición de la zona horaria local hacia o desde el horario de verano.

* Las operaciones que comparen o calculen la diferencia entre la hora UTC y una hora local incluyen en el resultado un intervalo de tiempo igual a la diferencia horaria de la zona horaria local respecto de la hora UTC. 

* Las operaciones que comparen o calculen la diferencia entre una hora no especificada y la hora UTC o la hora local reflejan la hora de reloj simple. No se consideran las diferencias de zona horaria y el resultado no refleja la aplicación de reglas de ajuste de zona horaria. 

* Las operaciones que comparen o calculen la diferencia entre dos horas no especificadas pueden incluir un intervalo desconocido que refleje la diferencia entre la hora de dos zonas horarias diferentes.

Hay muchos escenarios en los que las diferencias de zona horaria no afectan a los cálculos de fecha y hora, o en los que el contexto de los datos de fecha y hora define el significado de las operaciones aritméticas o de comparación. Para ver una descripción de algunos, consulte [Choosing Between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](choosing-between-datetime.md) (Elegir entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo).

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>Comparaciones y operaciones aritméticas con valores DateTimeOffset

Un valor [System.DateTimeOffset](xref:System.DateTimeOffset) incluye no solo una fecha y hora, sino también una diferencia horaria que define sin ambigüedad esa fecha y hora respecto de la hora UTC. Esto permite definir la igualdad de forma ligeramente diferente que en el caso de los valores [System.DateTime](xref:System.DateTime). Mientras que los valores [DateTime](xref:System.DateTime) son iguales si tienen el mismo valor de fecha y hora, los valores [DateTimeOffset](xref:System.DateTimeOffset) son iguales si hacen referencia al mismo punto en el tiempo. Esto hace que un valor [DateTimeOffset](xref:System.DateTimeOffset) sea más preciso y necesite una menor interpretación cuando se usa en comparaciones y en la mayoría de las operaciones aritméticas que determinan el intervalo entre dos fechas y horas. Esta diferencia de comportamiento se muestra en el ejemplo siguiente, que es el equivalente en [DateTimeOffset](xref:System.DateTimeOffset) al ejemplo anterior en el que se comparaban valores DateTime de hora local y de hora UTC.

```csharp
using System;

public enum TimeComparison
{
   EarlierThan = -1,
   TheSameAs = 0,
   LaterThan = 1
}

public class DateTimeOffsetManipulation
{
   public static void Main()
   {
      DateTimeOffset localTime = DateTimeOffset.Now;
      DateTimeOffset utcTime = DateTimeOffset.UtcNow;

      Console.WriteLine("Difference between local time and UTC: {0}:{1:D2} hours", 
                        (localTime - utcTime).Hours, 
                        (localTime - utcTime).Minutes);
      Console.WriteLine("The local time is {0} UTC.", 
                        Enum.GetName(typeof(TimeComparison), localTime.CompareTo(utcTime)));  
   }
}
// Regardless of the local time zone, the example displays 
// the following output to the console:
//    Difference between local time and UTC: 0:00 hours.
//    The local time is TheSameAs UTC.
```

```vb
Public Enum TimeComparison As Integer
   EarlierThan = -1
   TheSameAs = 0
   LaterThan = 1
End Enum

Module DateTimeOffsetManipulation
   Public Sub Main()
      Dim localTime As DateTimeOffset = DateTimeOffset.Now
      Dim utcTime As DateTimeOffset = DateTimeOffset.UtcNow

      Console.WriteLine("Difference between local time and UTC: {0}:{1:D2} hours.", _
                        (localTime - utcTime).Hours, _
                        (localTime - utcTime).Minutes)
      Console.WriteLine("The local time is {0} UTC.", _
                        [Enum].GetName(GetType(TimeComparison), localTime.CompareTo(utcTime)))  
   End Sub
End Module
' Regardless of the local time zone, the example displays 
' the following output to the console:
'    Difference between local time and UTC: 0:00 hours.
'    The local time is TheSameAs UTC.
'          Console.WriteLine(e.GetType().Name)
```

En este ejemplo, el método [DateTimeOffset.CompareTo](xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)) indica que la hora local actual y la hora UTC actual son iguales, y la resta de los valores [DateTimeOffset](xref:System.DateTimeOffset) indica que la diferencia entre las dos horas es [TimeSpan.Zero](xref:System.TimeSpan.Zero). 

La principal limitación de usar valores [DateTimeOffset](xref:System.DateTimeOffset) en una operación aritmética de fecha y hora es que, aunque los valores [DateTimeOffset](xref:System.DateTimeOffset) tienen cierto reconocimiento de la zona horaria, no tienen un reconocimiento completo de la zona horaria. Aunque la diferencia horaria del valor [DateTimeOffset](xref:System.DateTimeOffset) refleja la diferencia horaria de una zona horaria respecto de la hora UTC cuando se asigna por primera vez un valor a una variable [DateTimeOffset](xref:System.DateTimeOffset), se desasocia de la zona horaria a partir de entonces. Dado que ya no está directamente asociada con una hora identificable, la suma y resta de intervalos de fecha y hora no tiene en cuenta las reglas de ajuste de una zona horaria. 

Por ejemplo, la transición al horario de verano en la zona de la hora estándar central de los Estados Unidos se produce a las 2:00 a. m. del 9 de marzo de 2008. Esto significa que la suma de un intervalo de dos horas y media a la hora estándar central 1:30 a. m. del día 9 de marzo de 2008 debería generar la siguiente fecha y hora: 5:00 a. m. del 9 de marzo de 2008. Pero como se muestra en el ejemplo siguiente, el resultado de la suma es 4:00 a. m. del 9 de marzo de 2008. Observe que el resultado de esta operación representa el punto correcto en el tiempo, aunque no es la hora de la zona horaria que nos interesa (es decir, no tiene la diferencia horaria de la zona horaria esperada).

```csharp
using System;

public class IntervalArithmetic
{
   public static void Main()
   {
      DateTime generalTime = new DateTime(2008, 3, 9, 1, 30, 0);
      const string tzName = "Central Standard Time";
      TimeSpan twoAndAHalfHours = new TimeSpan(2, 30, 0);

      // Instantiate DateTimeOffset value to have correct CST offset
      try
      {
         DateTimeOffset centralTime1 = new DateTimeOffset(generalTime, 
                    TimeZoneInfo.FindSystemTimeZoneById(tzName).GetUtcOffset(generalTime));

         // Add two and a half hours      
         DateTimeOffset centralTime2 = centralTime1.Add(twoAndAHalfHours);
         // Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, 
                                                    twoAndAHalfHours.ToString(), 
                                                    centralTime2);  
      }
      catch (TimeZoneNotFoundException)
      {
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.");
      }
   }
}
// The example displays the following output to the console:
//    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 4:00:00 AM -06:00
```

```vb
Module IntervalArithmetic
   Public Sub Main()
      Dim generalTime As Date = #03/09/2008 1:30AM#
      Const tzName As String = "Central Standard Time"
      Dim twoAndAHalfHours As New TimeSpan(2, 30, 0)

      ' Instantiate DateTimeOffset value to have correct CST offset
      Try
         Dim centralTime1 As New DateTimeOffset(generalTime, _
                    TimeZoneInfo.FindSystemTimeZoneById(tzName).GetUtcOffset(generalTime))

         ' Add two and a half hours      
         Dim centralTime2 As DateTimeOffset = centralTime1.Add(twoAndAHalfHours)
         ' Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, _
                                                    twoAndAHalfHours.ToString(), _
                                                    centralTime2)   
      Catch e As TimeZoneNotFoundException
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.")
      End Try
   End Sub
End Module
' The example displays the following output to the console:
'    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 4:00:00 AM -06:00
```

## <a name="arithmetic-operations-with-times-in-time-zones"></a>Operaciones aritméticas con horas de zonas horarias

La clase [System.TimeZoneInfo](xref:System.TimeZoneInfo) no proporciona métodos que apliquen automáticamente reglas de ajuste al realizar operaciones aritméticas de fecha y hora. Para hacerlo, puede convertir la hora de una zona horaria a la hora UTC, realizar la operación aritmética y, después, convertir la hora UTC de nuevo a la hora de la zona horaria. Para obtener más información, consulte [How to: Use Time Zones in Date and Time Arithmetic](use-time-zones-in-arithmetic.md) (Cómo usar zonas horarias en operaciones aritméticas de fecha y hora).

Por ejemplo, el código siguiente se parece al código anterior que sumaba dos horas y media a la fecha y hora 2:00 a. m. del 9 de marzo de 2008. Pero, dado que convierte una hora estándar central a la hora UTC antes de realizar la operación aritmética de fecha y hora y, después, convierte el resultado en hora UTC de nuevo a la hora estándar central, la hora resultante refleja la transición de la zona de la hora estándar central al horario de verano.

```csharp
using System;

public class TimeZoneAwareArithmetic
{
   public static void Main()
   {
      const string tzName = "Central Standard Time";

      DateTime generalTime = new DateTime(2008, 3, 9, 1, 30, 0);
      TimeZoneInfo cst = TimeZoneInfo.FindSystemTimeZoneById(tzName);
      TimeSpan twoAndAHalfHours = new TimeSpan(2, 30, 0);

      // Instantiate DateTimeOffset value to have correct CST offset
      try
      {
         DateTimeOffset centralTime1 = new DateTimeOffset(generalTime, 
                                       cst.GetUtcOffset(generalTime));

         // Add two and a half hours
         DateTimeOffset utcTime = centralTime1.ToUniversalTime();
         utcTime += twoAndAHalfHours;

         DateTimeOffset centralTime2 = TimeZoneInfo.ConvertTime(utcTime, cst);
         // Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, 
                                                    twoAndAHalfHours.ToString(), 
                                                    centralTime2);  
      }
      catch (TimeZoneNotFoundException)
      {
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.");
      }
   }
}
// The example displays the following output to the console:
//    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 5:00:00 AM -05:00
```

```vb
Module TimeZoneAwareArithmetic
   Public Sub Main()
      Const tzName As String = "Central Standard Time"

      Dim generalTime As Date = #03/09/2008 1:30AM#
      Dim cst As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(tzName) 
      Dim twoAndAHalfHours As New TimeSpan(2, 30, 0)

      ' Instantiate DateTimeOffset value to have correct CST offset
      Try
         Dim centralTime1 As New DateTimeOffset(generalTime, _
                    cst.GetUtcOffset(generalTime))

         ' Add two and a half hours 
         Dim utcTime As DateTimeOffset = centralTime1.ToUniversalTime()
         utcTime += twoAndAHalfHours

         Dim centralTime2 As DateTimeOffset = TimeZoneInfo.ConvertTime(utcTime, cst)
         ' Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, _
                                                    twoAndAHalfHours.ToString(), _
                                                    centralTime2)   
      Catch e As TimeZoneNotFoundException
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.")
      End Try
   End Sub
End Module
' The example displays the following output to the console:
'    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 5:00:00 AM -05:00
```

## <a name="see-also"></a>Vea también

[Fechas, horas y zonas horarias](index.md)

[Cómo: Usar zonas horarias en operaciones aritméticas de fecha y hora](use-time-zones-in-arithmetic.md)





<!--HONumber=Nov16_HO1-->


