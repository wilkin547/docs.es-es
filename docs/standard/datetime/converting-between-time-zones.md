---
title: Convertir horas entre zonas horarias
description: Convertir horas entre zonas horarias
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: bf8f74e6-e7f2-4c2a-a04c-57db0e28dd36
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 051a4891336470e79bda9d7b9bb1be4e2c9187b8

---

# <a name="converting-times-between-time-zones"></a>Convertir horas entre zonas horarias

Para cualquier aplicación que trabaje con fechas y horas se está volviendo cada vez más importante controlar las diferencias entre zonas horarias. Una aplicación ya no puede suponer que todas las horas se pueden expresar en la hora local, que es la disponible en la estructura [System.DateTime](xref:System.DateTime). Por ejemplo, una página web que muestre la hora actual en la zona oriental de los Estados Unidos no tendrá credibilidad para un cliente de Asia oriental. En este tema se explica cómo convertir las horas de una zona horaria a otra, así como cómo convertir valores [System.DateTimeOffset](xref:System.DateTimeOffset) con un reconocimiento limitado de la zona horaria.

## <a name="converting-to-coordinated-universal-time"></a>Conversión a la hora universal coordinada

La hora universal coordinada (UTC) es un estándar de hora atómica de alta precisión. Las zonas horarias del mundo se expresan como diferencias positivas o negativas con respecto a la hora UTC. Por lo tanto, UTC proporciona un tipo de hora libre o neutra de zona horaria. Se recomienda el uso de la hora UTC cuando importa la portabilidad de la fecha y la hora entre equipos. La conversión de zonas horarias individuales a UTC facilita las comparaciones de hora.

> [!NOTE]
> También puede serializar una estructura [DateTimeOffset](xref:System.DateTimeOffset) para representar de forma inequívoca un único punto en el tiempo. Dado que los objetos [DateTimeOffset](xref:System.DateTimeOffset) almacenan un valor de fecha y hora junto con su diferencia horaria con respecto a UTC, siempre representan un punto concreto en el tiempo en relación a la hora UTC.

La manera más fácil de convertir una hora a UTC es llamar al método `static` (`Shared` en Visual Basic) [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx). 

> [!IMPORTANT]
> El método `TimeZoneInfo.ConvertTimeToUtc(DateTime)` no está disponible actualmente en .NET Core. 

La conversión exacta realizada por el método depende del valor de la propiedad [Kind](xref:System.DateTime.Kind) del parámetro `DateTime`, como se muestra en la tabla siguiente.

Propiedad [DateTime.Kind](xref:System.DateTimeKind) | Conversión
---------------------------------------------------------------------------------------------- | ----------
[DateTimeKind.Local](xref:System.DateTimeKind.Local) | Convierte la hora local a UTC.
[DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) | Supone que el parámetro `DateTime` es la hora local y la convierte a UTC.
[DateTimeKind.Utc](xref:System.DateTimeKind.Utc) | Devuelve el parámetro `DateTime` sin modificar.

El código siguiente convierte la hora local actual a UTC y muestra el resultado en la consola.

```csharp
DateTime dateNow = DateTime.Now;
Console.WriteLine("The date and time are {0} UTC.", 
                   TimeZoneInfo.ConvertTimeToUtc(dateNow));
```

```vb
Dim dateNow As Date = Date.Now      
Console.WriteLine("The date and time are {0} UTC.", _
                  TimeZoneInfo.ConvertTimeToUtc(dateNow))
```

> [!NOTE]
>El método [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) no produce necesariamente resultados idénticos a los métodos [TimeZone.ToUniversalTime](https://msdn.microsoft.com/en-us/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) y [DateTime.ToUniversalTime](xref:System.DateTime.ToUniversalTime). Si la zona horaria local del sistema host incluye varias reglas de ajuste, [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/System.TimeZone.ConvertTimeToUtc(v=vs.110).aspx) aplica la regla adecuada para una determinada fecha y hora. Los otros dos métodos siempre aplican la última regla de ajuste.

Si el valor de fecha y hora no representa la hora local ni UTC, el método [ToUniversalTime](https://msdn.microsoft.com/en-us/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) probablemente devolverá un resultado erróneo. Pero puede usar el método [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) para convertir la fecha y hora desde una zona horaria especificada. (Para conocer detalles sobre cómo recuperar un objeto TimeZoneInfo que representa la zona horaria de destino, consulte [Buscar las zonas horarias definidas en un sistema local](finding-the-time-zones-on-local-system.md)). El siguiente código usa el método [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) para convertir la hora estándar del Este a UTC.

```csharp
DateTime easternTime = new DateTime(2007, 01, 02, 12, 16, 00);
string easternZoneId = "Eastern Standard Time";
try
{
   TimeZoneInfo easternZone = TimeZoneInfo.FindSystemTimeZoneById(easternZoneId);
   Console.WriteLine("The date and time are {0} UTC.", 
                     TimeZoneInfo.ConvertTimeToUtc(easternTime, easternZone));
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("Unable to find the {0} zone in the registry.", 
                     easternZoneId);
}                           
catch (InvalidTimeZoneException)
{
   Console.WriteLine("Registry data on the {0} zone has been corrupted.", 
                     easternZoneId);
}
```

```vb
Dim easternTime As New Date(2007, 01, 02, 12, 16, 00)
Dim easternZoneId As String = "Eastern Standard Time"
Try
   Dim easternZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(easternZoneId)
   Console.WriteLine("The date and time are {0} UTC.", _ 
                     TimeZoneInfo.ConvertTimeToUtc(easternTime, easternZone))
Catch e As TimeZoneNotFoundException
   Console.WriteLine("Unable to find the {0} zone in the registry.", _
                     easternZoneId)
Catch e As InvalidTimeZoneException
   Console.WriteLine("Registry data on the {0} zone has been corrupted.", _ 
                     easternZoneId)
End Try    
```

Tenga en cuenta que este método inicia una [ArgumentException](xref:System.ArgumentException) si la propiedad [Kind](xref:System.DateTimeKind) del objeto [DateTime](xref:System.DateTime) y la zona horaria no coinciden. No hay coincidencia si la propiedad Kind es [DateTimeKind.Local](xref:System.DateTimeKind.Local) pero el objeto [TimeZoneInfo](xref:System.TimeZoneInfo) no representa la zona horaria local o si la propiedad Kind es [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) pero el objeto [TimeZoneInfo](xref:System.TimeZoneInfo) no es igual a [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).

Todos estos métodos toman los valores [DateTime](xref:System.DateTime) como parámetros y devuelven un valor [DateTime](xref:System.DateTime). En el caso de los valores [DateTimeOffset](xref:System.DateTimeOffset), la estructura [DateTimeOffset](xref:System.DateTimeOffset) tiene un método de instancia [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) que convierte la fecha y hora de la instancia actual en hora UTC. El ejemplo siguiente llama al método [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) para convertir una hora local y varias horas más a la hora universal coordinada (UTC).

```csharp
DateTimeOffset localTime, otherTime, universalTime;

// Define local time in local time zone
localTime = new DateTimeOffset(new DateTime(2007, 6, 15, 12, 0, 0));
Console.WriteLine("Local time: {0}", localTime);
Console.WriteLine();

// Convert local time to offset 0 and assign to otherTime
otherTime = localTime.ToOffset(TimeSpan.Zero);
Console.WriteLine("Other time: {0}", otherTime);
Console.WriteLine("{0} = {1}: {2}", 
                  localTime, otherTime, 
                  localTime.Equals(otherTime));
Console.WriteLine("{0} exactly equals {1}: {2}", 
                  localTime, otherTime, 
                  localTime.EqualsExact(otherTime));
Console.WriteLine();

// Convert other time to UTC
universalTime = localTime.ToUniversalTime(); 
Console.WriteLine("Universal time: {0}", universalTime);
Console.WriteLine("{0} = {1}: {2}", 
                  otherTime, universalTime, 
                  universalTime.Equals(otherTime));
Console.WriteLine("{0} exactly equals {1}: {2}", 
                  otherTime, universalTime, 
                  universalTime.EqualsExact(otherTime));
Console.WriteLine();
// The example produces the following output to the console:
//    Local time: 6/15/2007 12:00:00 PM -07:00
//    
//    Other time: 6/15/2007 7:00:00 PM +00:00
//    6/15/2007 12:00:00 PM -07:00 = 6/15/2007 7:00:00 PM +00:00: True
//    6/15/2007 12:00:00 PM -07:00 exactly equals 6/15/2007 7:00:00 PM +00:00: False
//    
//    Universal time: 6/15/2007 7:00:00 PM +00:00
//    6/15/2007 7:00:00 PM +00:00 = 6/15/2007 7:00:00 PM +00:00: True
//    6/15/2007 7:00:00 PM +00:00 exactly equals 6/15/2007 7:00:00 PM +00:00: True 
```

```vb
Dim localTime, otherTime, universalTime As DateTimeOffset

' Define local time in local time zone
localTime = New DateTimeOffset(#6/15/2007 12:00:00PM#)
Console.WriteLine("Local time: {0}", localTime)
Console.WriteLine()

' Convert local time to offset 0 and assign to otherTime
otherTime = localTime.ToOffset(TimeSpan.Zero)
Console.WriteLine("Other time: {0}", otherTime)
Console.WriteLine("{0} = {1}: {2}", _
                  localTime, otherTime, _
                  localTime.Equals(otherTime))
Console.WriteLine("{0} exactly equals {1}: {2}", _ 
                  localTime, otherTime, _
                  localTime.EqualsExact(otherTime))
Console.WriteLine()

' Convert other time to UTC
universalTime = localTime.ToUniversalTime() 
Console.WriteLine("Universal time: {0}", universalTime)
Console.WriteLine("{0} = {1}: {2}", _
                  otherTime, universalTime, _ 
                  universalTime.Equals(otherTime))
Console.WriteLine("{0} exactly equals {1}: {2}", _ 
                  otherTime, universalTime, _
                  universalTime.EqualsExact(otherTime))
Console.WriteLine()
' The example produces the following output to the console:
'    Local time: 6/15/2007 12:00:00 PM -07:00
'    
'    Other time: 6/15/2007 7:00:00 PM +00:00
'    6/15/2007 12:00:00 PM -07:00 = 6/15/2007 7:00:00 PM +00:00: True
'    6/15/2007 12:00:00 PM -07:00 exactly equals 6/15/2007 7:00:00 PM +00:00: False
'    
'    Universal time: 6/15/2007 7:00:00 PM +00:00
'    6/15/2007 7:00:00 PM +00:00 = 6/15/2007 7:00:00 PM +00:00: True
'    6/15/2007 7:00:00 PM +00:00 exactly equals 6/15/2007 7:00:00 PM +00:00: True 
```

## <a name="converting-utc-to-a-designated-time-zone"></a>Conversión de una hora UTC a una zona horaria designada

Para convertir la hora UTC a la hora local, consulte la sección [Conversión de una hora UTC a la hora local](#converting-utc-to-local-time) que aparece a continuación. 

Para convertir la hora UTC a la hora de cualquier zona horaria que designe, llame al método [ConvertTimeFromUtc](https://msdn.microsoft.com/en-us/library/System.TimeZoneInfo.converttimefromutc(v=vs.110).aspx). 

> [!IMPORTANT]
> El método `TimeZoneInfo.ConvertTimeFromUtc' no está disponible en este momento en .NET Core. 

El método toma dos parámetros:

* La hora UTC que se va a convertir. Debe ser un valor [DateTime](xref:System.DateTime) cuya propiedad [Kind](xref:System.DateTime.Kind) esté establecida en [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) o [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified). 

* La zona horaria a la que se va a convertir la hora UTC. 

El código siguiente convierte la hora UTC a la hora estándar central.

```csharp
DateTime timeUtc = DateTime.UtcNow;
try
{
   TimeZoneInfo cstZone = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time");
   DateTime cstTime = TimeZoneInfo.ConvertTimeFromUtc(timeUtc, cstZone);
   Console.WriteLine("The date and time are {0} {1}.", 
                     cstTime, 
                     cstZone.IsDaylightSavingTime(cstTime) ?
                             cstZone.DaylightName : cstZone.StandardName);
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("The registry does not define the Central Standard Time zone.");
}                           
catch (InvalidTimeZoneException)
{
   Console.WriteLine("Registry data on the Central Standard Time zone has been corrupted.");
}
```

```vb
Dim timeUtc As Date = Date.UtcNow
Try
   Dim cstZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time")
   Dim cstTime As Date = TimeZoneInfo.ConvertTimeFromUtc(timeUtc, cstZone)
   Console.WriteLine("The date and time are {0} {1}.", _
                     cstTime, _
                     IIf(cstZone.IsDaylightSavingTime(cstTime), _
                         cstZone.DaylightName, cstZone.StandardName))
Catch e As TimeZoneNotFoundException
   Console.WriteLine("The registry does not define the Central Standard Time zone.")
Catch e As InvalidTimeZoneException
   Console.WriteLine("Registry data on the Central Standard Time zone has been corrupted.")
End Try
``` 

## <a name="converting-utc-to-local-time"></a>Conversión de una hora UTC a la hora local

Para convertir la hora UTC a la hora local, llame al método [DateTime.ToLocalTime](xref:System.DateTime) del objeto [DateTime](xref:System.DateTime) cuya hora quiere convertir. El comportamiento exacto del método depende del valor de la propiedad [Kind](xref:System.DateTime.Kind) del objeto, como se muestra en la tabla siguiente.

Propiedad [DateTime.Kind](xref:System.DateTimeKind) | Conversión
---------------------------------------------------------------------------------------------- | ----------
[DateTimeKind.Local](xref:System.DateTimeKind.Local) | Devuelve el valor [DateTime](xref:System.DateTime) sin modificar.
[DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) | Supone que el valor [DateTime](xref:System.DateTime) es la hora UTC y la convierte en hora local.
[DateTimeKind.Utc](xref:System.DateTimeKind.Utc) | Convierte el valor [DateTime](xref:System.DateTime) a la hora local.

## <a name="converting-between-any-two-time-zones"></a>Conversión entre dos zonas horarias cualquiera

Puede convertir entre dos zonas horarias cualquiera con el método estático [TimeZoneInfo.ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)). Los parámetros de este método son el valor [DateTime](xref:System.DateTime) que se va a convertir, un objeto [TimeZoneInfo](xref:System.TimeZoneInfo) que representa la zona horaria del valor de fecha y hora y un objeto [TimeZoneInfo](xref:System.TimeZoneInfo) que representa la zona horaria a la que se va a convertir el valor de fecha y hora.

El método exige que la propiedad [Kind](xref:System.DateTime.Kind) del valor de fecha y hora que se va a convertir y el objeto [TimeZoneInfo](xref:System.TimeZoneInfo) o el identificador de la zona horaria que representa su zona horaria coincidan. De lo contrario, se inicia una [ArgumentException](xref:System.ArgumentException). Por ejemplo, si la propiedad [Kind](xref:System.DateTime.Kind) del valor de fecha y hora es [DateTimeKind.Local](xref:System.DateTimeKind.Local), se inicia una excepción si el objeto [TimeZoneInfo](xref:System.TimeZoneInfo) pasado como un parámetro al método no es igual a [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local). También se inicia una excepción si el identificador pasado como un parámetro al método no es igual a [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id).

En el ejemplo siguiente se usa el método [ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) para convertir la hora estándar de Hawai en hora local.

```csharp
DateTime hwTime = new DateTime(2007, 02, 01, 08, 00, 00);
try
{
   TimeZoneInfo hwZone = TimeZoneInfo.FindSystemTimeZoneById("Hawaiian Standard Time");
   Console.WriteLine("{0} {1} is {2} local time.", 
           hwTime, 
           hwZone.IsDaylightSavingTime(hwTime) ? hwZone.DaylightName : hwZone.StandardName, 
           TimeZoneInfo.ConvertTime(hwTime, hwZone, TimeZoneInfo.Local));
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("The registry does not define the Hawaiian Standard Time zone.");
}                           
catch (InvalidTimeZoneException)
{
   Console.WriteLine("Registry data on the Hawaiian STandard Time zone has been corrupted.");
}
```

```vb
Dim hwTime As Date = #2/01/2007 8:00:00 AM#
Try
   Dim hwZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById("Hawaiian Standard Time")
   Console.WriteLine("{0} {1} is {2} local time.", _
                     hwTime, _
                     IIf(hwZone.IsDaylightSavingTime(hwTime), hwZone.DaylightName, hwZone.StandardName), _
                     TimeZoneInfo.ConvertTime(hwTime, hwZone, TimeZoneInfo.Local))
Catch e As TimeZoneNotFoundException
   Console.WriteLine("The registry does not define the Hawaiian Standard Time zone.")
Catch e As InvalidTimeZoneException
   Console.WriteLine("Registry data on the Hawaiian Standard Time zone has been corrupted.")
End Try
```

## <a name="converting-datetimeoffset-values"></a>Conversión de valores DateTimeOffset

Los valores de fecha y hora representados por objetos [System.DateTimeOffset](xref:System.DateTimeOffset) no reconocen totalmente la zona horaria porque el objeto está desasociado de su zona horaria en el momento en que se crea su instancia. Pero en muchos casos una aplicación simplemente necesita convertir una fecha y hora basada en dos diferencias horarias diferentes con respecto a la hora UTC en lugar de en la hora en zonas horarias determinadas. Para llevar a cabo esta conversión, puede llamar al método [ToOffset](xref:System.DateTimeOffset.ToOffset(System.TimeSpan)) de la instancia actual. El parámetro único del método es [TimeSpan](xref:System.TimeSpan), que representa la diferencia horaria del nuevo valor de fecha y hora que el método va a devolver.  

Por ejemplo, si la fecha y hora de una solicitud de usuario de una página web se conoce y se serializa como una cadena con el formato MM/dd/aaaa hh: mm:ss zzzz, el siguiente método `ReturnTimeOnServer` convierte este valor de fecha y hora en la fecha y hora del servidor web.

```csharp
public DateTimeOffset ReturnTimeOnServer(string clientString)
{
   string format = @"M/d/yyyy H:m:s zzz";
   TimeSpan serverOffset = TimeZoneInfo.Local.GetUtcOffset(DateTimeOffset.Now);

   try
   {      
      DateTimeOffset clientTime = DateTimeOffset.ParseExact(clientString, format, CultureInfo.InvariantCulture);
      DateTimeOffset serverTime = clientTime.ToOffset(serverOffset);
      return serverTime;
   }
   catch (FormatException)
   {
      return DateTimeOffset.MinValue;
   }
}
```

```vb
Public Function ReturnTimeOnServer(clientString As String) As DateTimeOffset
   Dim format As String = "M/d/yyyy H:m:s zzz"
   Dim serverOffset As TimeSpan = TimeZoneInfo.Local.GetUtcOffset(DateTimeOffset.Now)

   Try      
      Dim clientTime As DateTimeOffset = DateTimeOffset.ParseExact(clientString, format, CultureInfo.InvariantCulture)
      Dim serverTime As DateTimeOffset = clientTime.ToOffset(serverOffset)
      Return serverTime
   Catch e As FormatException
      Return DateTimeOffset.MinValue
   End Try    
End Function
```

Si se pasa al método la cadena "9/1/2007 5:32:07 -05:00", que representa la fecha y hora de una zona horaria cinco horas anterior a UTC, devuelve 9/1/2007 3:32:07 AM -07:00 para un servidor ubicado en los Estados Unidos. Zona horaria estándar del Pacífico.

La clase [TimeZoneInfo](xref:System.TimeZoneInfo) también incluye un método [TimeZoneInfo.ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)) sobrecargado que realiza conversiones de zona horaria con valores [System.DateTimeOffset](xref:System.DateTimeOffset). Los parámetros del método son un valor [System.DateTimeOffset](xref:System.DateTimeOffset) y una referencia a la zona horaria a la que se va a convertir la hora. La llamada al método devuelve un valor [System.DateTimeOffset](xref:System.DateTimeOffset). Por ejemplo, el método `ReturnTimeOnServer` del ejemplo anterior podría volver a escribirse como sigue para llamar al método [ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)).

```csharp
public DateTimeOffset ReturnTimeOnServer(string clientString)
{
   string format = @"M/d/yyyy H:m:s zzz";

   try
   {      
      DateTimeOffset clientTime = DateTimeOffset.ParseExact(clientString, format, 
                                  CultureInfo.InvariantCulture);
      DateTimeOffset serverTime = TimeZoneInfo.ConvertTime(clientTime, 
                                  TimeZoneInfo.Local);
      return serverTime;
   }
   catch (FormatException)
   {
      return DateTimeOffset.MinValue;
   }
}
```

```vb
Public Function ReturnTimeOnServer(clientString As String) As DateTimeOffset
   Dim format As String = "M/d/yyyy H:m:s zzz"

   Try      
      Dim clientTime As DateTimeOffset = DateTimeOffset.ParseExact(clientString, format, CultureInfo.InvariantCulture)
      Dim serverTime As DateTimeOffset = TimeZoneInfo.ConvertTime(clientTime, TimeZoneInfo.Local)
      Return serverTime
   Catch e As FormatException
      Return DateTimeOffset.MinValue
   End Try    
End Function
```

## <a name="see-also"></a>Vea también

[TimeZoneInfo](xref:System.TimeZoneInfo)

[Fechas, horas y zonas horarias](index.md)

[Buscar las zonas horarias definidas en un sistema local](finding-the-time-zones-on-local-system.md)





<!--HONumber=Nov16_HO1-->


