---
title: "Cómo: Aplicar acciones de ida y vuelta a valores de fecha y hora"
description: "Cómo aplicar acciones de ida y vuelta a valores de fecha y hora"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 15690f18-1bb9-4bb8-bc11-0b737e2f0859
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 79c4da0cc6b4436fcbd5b345e23b387f2ad933d1
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-round-trip-date-and-time-values"></a>Cómo: Aplicar acciones de ida y vuelta a valores de fecha y hora

En muchas aplicaciones, un valor de fecha y hora sirve para identificar inequívocamente un único punto en el tiempo. Este tema muestra cómo guardar y restaurar un valor [DateTime](xref:System.DateTime) y un valor [DateTimeOffset](xref:System.DateTimeOffset) de manera que el valor restaurado identifique la misma hora que el valor guardado.

## <a name="to-round-trip-a-datetime-value"></a>Para un valor DateTime de ida y vuelta

1. Convierta el valor [DateTime](xref:System.DateTime) en su representación de cadena mediante una llamada al método [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)) con el especificador de formato "o".

2. Guarde la representación de cadena del valor [DateTime](xref:System.DateTime) en un archivo o pásela a través de un límite de proceso, dominio de aplicación o máquina.

3. Recupere la cadena que representa el valor [DateTime](xref:System.DateTime).

4. Llame al método [DateTime.Parse(String, IFormatProvider, DateTimeStyles)](xref:System.DateTime.Parse(System.String,System.IFormatProvider,System.Globalization.DateTimeStyles)) y pase [DateTimeStyles.RoundtripKind](xref:System.Globalization.DateTimeStyles.RoundtripKind) como el valor del parámetro *DateTimeStyles*.

En el ejemplo siguiente se muestra cómo usar un valor [DateTime](xref:System.DateTime) de ida y vuelta.

```csharp
const string fileName = @".\DateFile.txt";

StreamWriter outFile = new StreamWriter(fileName);

// Save DateTime value.
DateTime dateToSave = DateTime.SpecifyKind(new DateTime(2008, 6, 12, 18, 45, 15), 
                                           DateTimeKind.Local);
string dateString = dateToSave.ToString("o");      
Console.WriteLine("Converted {0} ({1}) to {2}.", 
                  dateToSave.ToString(), 
                  dateToSave.Kind.ToString(), 
                  dateString);      
outFile.WriteLine(dateString);
Console.WriteLine("Wrote {0} to {1}.", dateString, fileName);
outFile.Close();

// Restore DateTime value.
DateTime restoredDate;

StreamReader inFile = new StreamReader(fileName);
dateString = inFile.ReadLine();
inFile.Close();
restoredDate = DateTime.Parse(dateString, null, DateTimeStyles.RoundtripKind);
Console.WriteLine("Read {0} ({2}) from {1}.", restoredDate.ToString(), 
                                              fileName, 
                                              restoredDate.Kind.ToString());
// The example displays the following output:
//    Converted 6/12/2008 6:45:15 PM (Local) to 2008-06-12T18:45:15.0000000-05:00.
//    Wrote 2008-06-12T18:45:15.0000000-05:00 to .\DateFile.txt.
//    Read 6/12/2008 6:45:15 PM (Local) from .\DateFile.txt.
```

```vb
Const fileName As String = ".\DateFile.txt"

Dim outFile As New StreamWriter(fileName)

' Save DateTime value.
Dim dateToSave As Date = DateTime.SpecifyKind(#06/12/2008 6:45:15 PM#, _
                                              DateTimeKind.Local)
Dim dateString As String = dateToSave.ToString("o")      
Console.WriteLine("Converted {0} ({1}) to {2}.", dateToSave.ToString(), _
                  dateToSave.Kind.ToString(), dateString)      
outFile.WriteLine(dateString)
Console.WriteLine("Wrote {0} to {1}.", dateString, fileName)
outFile.Close()   

' Restore DateTime value.
Dim restoredDate As Date

Dim inFile As New StreamReader(fileName)
dateString = inFile.ReadLine()
inFile.Close()
restoredDate = DateTime.Parse(dateString, Nothing, DateTimeStyles.RoundTripKind)
Console.WriteLine("Read {0} ({2}) from {1}.", restoredDate.ToString(), _
                  fileName, restoredDAte.Kind.ToString())
' The example displays the following output:
'    Converted 6/12/2008 6:45:15 PM (Local) to 2008-06-12T18:45:15.0000000-05:00.
'    Wrote 2008-06-12T18:45:15.0000000-05:00 to .\DateFile.txt.
'    Read 6/12/2008 6:45:15 PM (Local) from .\DateFile.txt.
```

Cuando se usa un valor [DateTime](xref:System.DateTime) de ida y vuelta, esta técnica mantiene correctamente la hora para todas las horas locales y universales. Por ejemplo, si un valor local [DateTime](xref:System.DateTime) se guarda en un sistema de la zona horaria estándar del Pacífico de Estados Unidos y se restaura en un sistema de la zona horaria estándar central de Estados Unidos, la fecha y hora restauradas serán dos horas posteriores a la hora original, lo que refleja la diferencia horaria entre las dos zonas. Pero esta técnica no es necesariamente precisa para horas no especificadas. Todos los valores [DateTime](xref:System.DateTime) cuya propiedad [Kind](xref:System.DateTime.Kind) es [Unspecified](xref:System.DateTimeKind.Unspecified) se tratan como si fueran horas locales. Si no es el caso, [DateTime](xref:System.DateTime) no identificará correctamente el punto en el tiempo. La solución alternativa para esta limitación es acoplar estrechamente un valor de fecha y hora con su zona horaria para la operación de guardado y restauración.

## <a name="to-round-trip-a-datetimeoffset-value"></a>Para un valor DateTimeOffset de ida y vuelta

Convierta el valor [DateTimeOffset](xref:System.DateTimeOffset) en su representación de cadena mediante una llamada al método [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) con el especificador de formato "o".

2. Guarde la representación de cadena del valor [DateTimeOffset](xref:System.DateTimeOffset) en un archivo o pásela a través de un límite de proceso, dominio de aplicación o máquina.

3. Recupere la cadena que representa el valor [DateTimeOffset](xref:System.DateTimeOffset).

4. Llame al método [DateTimeOffset.Parse(String, IFormatProvider, DateTimeStyles)](xref:System.DateTimeOffset.Parse(System.String,System.IFormatProvider,System.Globalization.DateTimeStyles)) y pase [DateTimeStyles.RoundtripKind](xref:System.Globalization.DateTimeStyles.RoundtripKind) como el valor del parámetro *styles*.

En el ejemplo siguiente se muestra cómo usar un valor [DateTimeOffset](xref:System.DateTimeOffset) de ida y vuelta.

```csharp
const string fileName = @".\DateOff.txt";

StreamWriter outFile = new StreamWriter(fileName);

// Save DateTime value.
DateTimeOffset dateToSave = new DateTimeOffset(2008, 6, 12, 18, 45, 15, 
                                               new TimeSpan(7, 0, 0));
string dateString = dateToSave.ToString("o");      
Console.WriteLine("Converted {0} to {1}.", dateToSave.ToString(), 
                  dateString);      
outFile.WriteLine(dateString);
Console.WriteLine("Wrote {0} to {1}.", dateString, fileName);
outFile.Close();

// Restore DateTime value.
DateTimeOffset restoredDateOff;

StreamReader inFile = new StreamReader(fileName);
dateString = inFile.ReadLine();
inFile.Close();
restoredDateOff = DateTimeOffset.Parse(dateString, null, 
                                       DateTimeStyles.RoundtripKind);
Console.WriteLine("Read {0} from {1}.", restoredDateOff.ToString(), 
                  fileName);
// The example displays the following output:
//    Converted 6/12/2008 6:45:15 PM +07:00 to 2008-06-12T18:45:15.0000000+07:00.
//    Wrote 2008-06-12T18:45:15.0000000+07:00 to .\DateOff.txt.
//    Read 6/12/2008 6:45:15 PM +07:00 from .\DateOff.txt.
```

```vb
Const fileName As String = ".\DateOff.txt"

Dim outFile As New StreamWriter(fileName)

' Save DateTime value.
Dim dateToSave As New DateTimeOffset(2008, 6, 12, 18, 45, 15, _
                                     New TimeSpan(7, 0, 0))
Dim dateString As String = dateToSave.ToString("o")      
Console.WriteLine("Converted {0} to {1}.", dateToSave.ToString(), dateString)      
outFile.WriteLine(dateString)
Console.WriteLine("Wrote {0} to {1}.", dateString, fileName)
outFile.Close()   

' Restore DateTime value.
Dim restoredDateOff As DateTimeOffset

Dim inFile As New StreamReader(fileName)
dateString = inFile.ReadLine()
inFile.Close()
restoredDateOff = DateTimeOffset.Parse(dateString, Nothing, DateTimeStyles.RoundTripKind)
Console.WriteLine("Read {0} from {1}.", restoredDateOff.ToString(), fileName)
' The example displays the following output:
'    Converted 6/12/2008 6:45:15 PM +07:00 to 2008-06-12T18:45:15.0000000+07:00.
'    Wrote 2008-06-12T18:45:15.0000000+07:00 to .\DateOff.txt.
'    Read 6/12/2008 6:45:15 PM +07:00 from .\DateOff.txt.
```

Esta técnica identifica siempre de forma inequívoca un valor [DateTimeOffset](xref:System.DateTimeOffset) como un único punto en el tiempo. Después, el valor se puede convertir en hora universal coordinada (UTC) llamando al método [DateTimeOffset.ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime), o bien se puede convertir a la hora de una zona horaria determinada llamando al método [DateTimeOffset.ToOffset](xref:System.DateTimeOffset.ToOffset(System.TimeSpan)) o [TimeZoneInfo.ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo). La limitación principal de esta técnica está en que las operaciones aritméticas de fecha y hora, cuando se realizan en un valor [DateTimeOffset](xref:System.DateTimeOffset) que representa la hora en una zona horaria determinada, podrían no generar resultados precisos para esa zona horaria. Esto se debe a que, cuando se crea una instancia de un valor [DateTimeOffset](xref:System.DateTimeOffset), se desasocia de su zona horaria. Por lo tanto, ya no se pueden aplicar las reglas de ajuste de esa zona de horaria al realizar cálculos de fecha y hora. Para evitar este problema, puede definir un tipo personalizado que incluya tanto el valor de fecha y hora como la zona horaria correspondiente.

## <a name="see-also"></a>Vea también

[Efectuar operaciones de formato](performing-formatting-operations.md)

[Cadenas con formato de fecha y hora estándar](standard-datetime.md)


