---
title: "Cómo: Mostrar fechas en calendarios no gregorianos"
description: "Cómo mostrar fechas en calendarios no gregorianos"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 93f06e1d-544b-4ccc-a0b2-95cd674852cb
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 783b51f3145d8b11e79b99cfdc4baefe127306e3

---

# <a name="how-to-display-dates-in-nongregorian-calendars"></a>Cómo: Mostrar fechas en calendarios no gregorianos

Los tipos [DateTime](xref:System.DateTime) y [DateTimeOffset](xref:System.DateTimeOffset) usan el calendario gregoriano como calendario predeterminado. Esto significa que al llamar al método `ToString` de un valor de fecha y hora se muestra la representación de cadena de esa fecha y hora en el calendario gregoriano, aunque se creara con otro calendario. Esto se muestra en el ejemplo siguiente, que usa dos maneras diferentes de crear un valor de fecha y hora con el calendario persa, pero muestra esos valores de fecha y hora en el calendario gregoriano cuando llama al método [ToString](xref:System.DateTime.ToString). En este ejemplo se reflejan dos técnicas usadas habitualmente, aunque incorrectas, para mostrar la fecha en un calendario determinado.

```csharp
PersianCalendar persianCal = new PersianCalendar();

DateTime persianDate = persianCal.ToDateTime(1387, 3, 18, 12, 0, 0, 0);
Console.WriteLine(persianDate.ToString());

persianDate = new DateTime(1387, 3, 18, persianCal);
Console.WriteLine(persianDate.ToString());
// The example displays the following output to the console:
//       6/7/2008 12:00:00 PM
//       6/7/2008 12:00:00 AM
```

```vb
Dim persianCal As New PersianCalendar()

Dim persianDate As Date = persianCal.ToDateTime(1387, 3, 18, _
                                                12, 0, 0, 0)
Console.WriteLine(persianDate.ToString())

persianDate = New DateTime(1387, 3, 18, persianCal)
Console.WriteLine(persianDate.ToString())
' The example displays the following output to the console:
'       6/7/2008 12:00:00 PM
'       6/7/2008 12:00:00 AM
```

Se pueden usar dos técnicas distintas para mostrar la fecha en un calendario determinado. La primera exige que el calendario sea el predeterminado de una referencia cultural determinada. La segunda se puede usar con cualquier calendario.

## <a name="to-display-the-date-for-a-cultures-default-calendar"></a>Para mostrar la fecha del calendario predeterminado de una referencia cultural

1. Cree una instancia de un objeto de calendario derivado de la clase [Calendar](xref:System.Globalization.Calendar) que representa al calendario que se va a usar.

2. Cree una instancia de un objeto [CultureInfo](xref:System.Globalization.CultureInfo) que representa la referencia cultural cuyo formato se va a usar para mostrar la fecha.

3. Llame al método [Array.Exists&lt;T&gt;](xref:System.Array.Exists``1(``0[],System.Predicate{``0})) para determinar si el objeto de calendario es miembro de la matriz devuelta por la propiedad [CultureInfo.OptionalCalendars](xref:System.Globalization.CultureInfo.OptionalCalendars). Esto indica que el calendario puede actuar como calendario predeterminado del objeto [CultureInfo](xref:System.Globalization.CultureInfo). Si no es miembro de la matriz, siga las instrucciones de la sección "Para mostrar la fecha en cualquier calendario".

4. Asigne el objeto de calendario a la propiedad [Calendar](xref:System.Globalization.DateTimeFormatInfo.Calendar) del objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) devuelto por la propiedad [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat).

  > [!NOTE]
  > La clase [CultureInfo](xref:System.Globalization.CultureInfo) también tiene una propiedad [Calendar](xref:System.Globalization.CultureInfo.Calendar). Pero es de solo lectura y constante; no cambia para reflejar el nuevo calendario predeterminado asignado a la propiedad [DateTimeFormatInfo.Calendar](xref:System.Globalization.DateTimeFormatInfo.Calendar).
  
5. Llame al método [DateTime.ToString(IFormatProvider)](xref:System.DateTime.ToString(System.IFormatProvider)) o [DateTime.ToString(String,IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) y pásele el objeto [CultureInfo](xref:System.Globalization.CultureInfo) cuyo calendario predeterminado se modificó en el paso anterior.

## <a name="to-display-the-date-in-any-calendar"></a>Para mostrar la fecha en cualquier calendario

1. Cree una instancia de un objeto de calendario derivado de la clase [Calendar](xref:System.Globalization.Calendar) que representa al calendario que se va a usar.

2. Determine qué elementos de fecha y hora deben aparecer en la representación de cadena del valor de fecha y hora.

3. Para cada elemento de fecha y hora que quiera mostrar, llame al método `Get…` del objeto de calendario. Están disponibles los siguientes métodos:

    * [GetYear](xref:System.Globalization.Calendar.GetYear(System.DateTime)), para mostrar el año en el calendario adecuado.
    
    * [GetMonth](xref:System.Globalization.Calendar.GetMonth(System.DateTime)), para mostrar el mes en el calendario adecuado. 
    
    * [GetDayOfMonth](xref:System.Globalization.Calendar.GetDayOfMonth(System.DateTime)), para mostrar el número del día del mes en el calendario adecuado.
    
    * [GetHour](xref:System.Globalization.Calendar.GetHour(System.DateTime)), para mostrar la hora del día en el calendario adecuado.
    
    * [GetMinute](xref:System.Globalization.Calendar.GetMinute(System.DateTime)), para mostrar los minutos de la hora en el calendario adecuado.
    
    * [GetSecond](xref:System.Globalization.Calendar.GetSecond(System.DateTime)), para mostrar los segundos del minuto en el calendario adecuado. 
    
    * [GetMilliseconds](xref:System.Globalization.Calendar.GetMilliseconds(System.DateTime)), para mostrar los milisegundos del segundo en el calendario adecuado.
    
## <a name="example"></a>Ejemplo
    
En el ejemplo se muestra una fecha con dos calendarios diferentes. Se muestra la fecha después de definir el calendario Hijri como calendario predeterminado de la referencia cultural ar-JO y se muestra la fecha con el calendario persa, que no se admite como calendario opcional de la referencia cultural fa-IR.

```csharp
using System;
using System.Globalization;

public class CalendarDates
{
   public static void Main()
   {
      HijriCalendar hijriCal = new HijriCalendar();
      CalendarUtility hijriUtil = new CalendarUtility(hijriCal);
      DateTime dateValue1 = new DateTime(1429, 6, 29, hijriCal);
      DateTimeOffset dateValue2 = new DateTimeOffset(dateValue1, 
                                  TimeZoneInfo.Local.GetUtcOffset(dateValue1));
      CultureInfo jc = CultureInfo.CreateSpecificCulture("ar-JO");

      // Display the date using the Gregorian calendar.
      Console.WriteLine("Using the system default culture: {0}", 
                        dateValue1.ToString("d"));
      // Display the date using the ar-JO culture's original default calendar.
      Console.WriteLine("Using the ar-JO culture's original default calendar: {0}", 
                        dateValue1.ToString("d", jc));
      // Display the date using the Hijri calendar.
      Console.WriteLine("Using the ar-JO culture with Hijri as the default calendar:");
      // Display a Date value.
      Console.WriteLine(hijriUtil.DisplayDate(dateValue1, jc));
      // Display a DateTimeOffset value.
      Console.WriteLine(hijriUtil.DisplayDate(dateValue2, jc));

      Console.WriteLine();

      PersianCalendar persianCal = new PersianCalendar();
      CalendarUtility persianUtil = new CalendarUtility(persianCal);
      CultureInfo ic = CultureInfo.CreateSpecificCulture("fa-IR");

      // Display the date using the ir-FA culture's default calendar.
      Console.WriteLine("Using the ir-FA culture's default calendar: {0}",       
                        dateValue1.ToString("d", ic));
      // Display a Date value.
      Console.WriteLine(persianUtil.DisplayDate(dateValue1, ic));
      // Display a DateTimeOffset value.
      Console.WriteLine(persianUtil.DisplayDate(dateValue2, ic));
   }
}

public class CalendarUtility
{
   private Calendar thisCalendar;
   private CultureInfo targetCulture;

   public CalendarUtility(Calendar cal)
   {
      this.thisCalendar = cal;
   }

   private bool CalendarExists(CultureInfo culture)
   {
      this.targetCulture = culture;
      return Array.Exists(this.targetCulture.OptionalCalendars, 
                          this.HasSameName);
   }

   private bool HasSameName(Calendar cal)
   {
      if (cal.ToString() == thisCalendar.ToString())
         return true;
      else
         return false;
   }

   public string DisplayDate(DateTime dateToDisplay, CultureInfo culture)
   {
      DateTimeOffset displayOffsetDate = dateToDisplay;
      return DisplayDate(displayOffsetDate, culture);
   }

   public string DisplayDate(DateTimeOffset dateToDisplay, 
                             CultureInfo culture)
   {
      string specifier = "yyyy/MM/dd";

      if (this.CalendarExists(culture))
      {
         Console.WriteLine("Displaying date in supported {0} calendar...", 
                           this.thisCalendar.GetType().Name);
         culture.DateTimeFormat.Calendar = this.thisCalendar;
         return dateToDisplay.ToString(specifier, culture);
      }
      else
      {
         Console.WriteLine("Displaying date in unsupported {0} calendar...", 
                           thisCalendar.GetType().Name);

         string separator = targetCulture.DateTimeFormat.DateSeparator;

         return thisCalendar.GetYear(dateToDisplay.DateTime).ToString("0000") +
                separator +
                thisCalendar.GetMonth(dateToDisplay.DateTime).ToString("00") + 
                separator +
                thisCalendar.GetDayOfMonth(dateToDisplay.DateTime).ToString("00"); 
      }
   } 
}
// The example displays the following output to the console:
//       Using the system default culture: 7/3/2008
//       Using the ar-JO culture's original default calendar: 03/07/2008
//       Using the ar-JO culture with Hijri as the default calendar:
//       Displaying date in supported HijriCalendar calendar...
//       1429/06/29
//       Displaying date in supported HijriCalendar calendar...
//       1429/06/29
//       
//       Using the ir-FA culture's default calendar: 7/3/2008
//       Displaying date in unsupported PersianCalendar calendar...
//       1387/04/13
//       Displaying date in unsupported PersianCalendar calendar...
//       1387/04/13
```

```vb
Imports System.Globalization

Public Class CalendarDates
   Public Shared Sub Main()
      Dim hijriCal As New HijriCalendar()
      Dim hijriUtil As New CalendarUtility(hijriCal)
      Dim dateValue1 As Date = New Date(1429, 6, 29, hijriCal)
      Dim dateValue2 As DateTimeOffset = New DateTimeOffset(dateValue1, _
                                         TimeZoneInfo.Local.GetUtcOffset(dateValue1))
      Dim jc As CultureInfo = CultureInfo.CreateSpecificCulture("ar-JO")

      ' Display the date using the Gregorian calendar.
      Console.WriteLine("Using the system default culture: {0}", _
                        dateValue1.ToString("d"))
      ' Display the date using the ar-JO culture's original default calendar.
      Console.WriteLine("Using the ar-JO culture's original default calendar: {0}", _
                        dateValue1.ToString("d", jc))
      ' Display the date using the Hijri calendar.
      Console.WriteLine("Using the ar-JO culture with Hijri as the default calendar:")
      ' Display a Date value.
      Console.WriteLine(hijriUtil.DisplayDate(dateValue1, jc))
      ' Display a DateTimeOffset value.
      Console.WriteLine(hijriUtil.DisplayDate(dateValue2, jc))

      Console.WriteLine()

      Dim persianCal As New PersianCalendar()
      Dim persianUtil As New CalendarUtility(persianCal)
      Dim ic As CultureInfo = CultureInfo.CreateSpecificCulture("fa-IR")

      ' Display the date using the ir-FA culture's default calendar.
      Console.WriteLine("Using the ir-FA culture's default calendar: {0}", _      
                        dateValue1.ToString("d", ic))
      ' Display a Date value.
      Console.WriteLine(persianUtil.DisplayDate(dateValue1, ic))
      ' Display a DateTimeOffset value.
      Console.WriteLine(persianUtil.DisplayDate(dateValue2, ic))
   End Sub
End Class

Public Class CalendarUtility
   Private thisCalendar As Calendar
   Private targetCulture As CultureInfo

   Public Sub New(cal As Calendar)
      Me.thisCalendar = cal
   End Sub

   Private Function CalendarExists(culture As CultureInfo) As Boolean
      Me.targetCulture = culture
      Return Array.Exists(Me.targetCulture.OptionalCalendars, _
                          AddressOf Me.HasSameName)
   End Function 

   Private Function HasSameName(cal As Calendar) As Boolean
      If cal.ToString() = thisCalendar.ToString() Then
         Return True
      Else
         Return False
      End If
   End Function

   Public Function DisplayDate(dateToDisplay As Date, _
                               culture As CultureInfo) As String
      Dim displayOffsetDate As DateTimeOffset = dateToDisplay
      Return DisplayDate(displayOffsetDate, culture)
   End Function

   Public Function DisplayDate(dateToDisplay As DateTimeOffset, _
                               culture As CultureInfo) As String
      Dim specifier As String = "yyyy/MM/dd"

      If Me.CalendarExists(culture) Then
         Console.WriteLine("Displaying date in supported {0} calendar...", _
                           thisCalendar.GetType().Name)
         culture.DateTimeFormat.Calendar = Me.thisCalendar
         Return dateToDisplay.ToString(specifier, culture)
      Else
         Console.WriteLine("Displaying date in unsupported {0} calendar...", _
                           thisCalendar.GetType().Name)

         Dim separator As String = targetCulture.DateTimeFormat.DateSeparator

         Return thisCalendar.GetYear(dateToDisplay.DateTime).ToString("0000") & separator & _
                thisCalendar.GetMonth(dateToDisplay.DateTime).ToString("00") & separator & _
                thisCalendar.GetDayOfMonth(dateToDisplay.DateTime).ToString("00") 
      End If             
   End Function
End Class
' The example displays the following output to the console:
'       Using the system default culture: 7/3/2008
'       Using the ar-JO culture's original default calendar: 03/07/2008
'       Using the ar-JO culture with Hijri as the default calendar:
'       Displaying date in supported HijriCalendar calendar...
'       1429/06/29
'       Displaying date in supported HijriCalendar calendar...
'       1429/06/29
'       
'       Using the ir-FA culture's default calendar: 7/3/2008
'       Displaying date in unsupported PersianCalendar calendar...
'       1387/04/13
'       Displaying date in unsupported PersianCalendar calendar...
'       1387/04/13
```

Cada objeto [CultureInfo](xref:System.Globalization.CultureInfo) puede admitir uno o varios calendarios, que se indican mediante la propiedad [OptionalCalendars](xref:System.Globalization.CultureInfo.OptionalCalendars). Uno de ellos se designa como calendario predeterminado de la referencia cultural y es devuelto por la propiedad de solo lectura [CultureInfo.Calendar](xref:System.Globalization.CultureInfo.Calendar). Otro de los calendarios opcionales se puede designar como valor predeterminado si se asigna un objeto [Calendar](xref:System.Globalization.Calendar) que represente ese calendario a la propiedad [DateTimeFormatInfo.Calendar](xref:System.Globalization.DateTimeFormatInfo.Calendar) devuelta por la propiedad [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat). Pero algunos calendarios, como el persa representado por la clase [PersianCalendar](xref:System.Globalization.PersianCalendar), no actúan como calendarios opcionales de ninguna referencia cultural.   

En el ejemplo se define una clase de utilidad de calendario reutilizable, `CalendarUtility`, para controlar muchos de los detalles de generación de la representación de cadena de una fecha mediante un calendario determinado. La clase `CalendarUtility` tiene los siguientes miembros: 

* Un constructor parametrizado cuyo único parámetro es un objeto [Calendar](xref:System.Globalization.Calendar) en el que se va a representar una fecha. Se asigna a un campo privado de la clase.

* `CalendarExists`, un método privado que devuelve un valor booleano que indica si el calendario representado por el objeto `CalendarUtility` es compatible con el objeto [CultureInfo](xref:System.Globalization.CultureInfo) pasado al método como parámetro. El método ajusta una llamada al método [Array.Exists&lt;T&gt;](xref:System.Array.Exists``1(``0[],System.Predicate{``0})), al que le pasa la matriz [CultureInfo.OptionalCalendars](xref:System.Globalization.CultureInfo.OptionalCalendars).

* `HasSameName`, un método privado asignado al delegado [Predicate&lt;T&gt;](xref:System.Predicate%601) que se pasa como parámetro al método [Array.Exists&lt;T&gt;](xref:System.Array.Exists``1(``0[],System.Predicate{``0})). Cada miembro de la matriz se pasa al método hasta que este devuelve `true`. El método determina si el nombre de un calendario opcional es igual que el calendario representado por el objeto `CalendarUtility`.

* `DisplayDate`, un método público sobrecargado al que se pasan dos parámetros: un valor [DateTime](xref:System.DateTime) o [DateTimeOffset](xref:System.DateTimeOffset) para expresar en el calendario representado por el objeto `CalendarUtility`; y la referencia cultural cuyas reglas de formato se van a usar. Su comportamiento a la hora de devolver la representación de cadena de una fecha depende de si la referencia cultural cuyas reglas de formato se van a usar admite el calendario de destino.

Independientemente del calendario usado para crear un valor [DateTime](xref:System.DateTime) o [DateTimeOffset](xref:System.DateTimeOffset) en este ejemplo, ese valor normalmente se expresa como una fecha gregoriana. Esto se debe a que los tipos [DateTime](xref:System.DateTime) y [DateTimeOffset](xref:System.DateTimeOffset) no conservan ninguna información del calendario. Internamente, se representan como el número de tics transcurridos desde la medianoche del 1 de enero de 0001. La interpretación de ese número depende del calendario. En la mayoría de las referencias culturales, el calendario predeterminado es el gregoriano. 

## <a name="see-also"></a>Vea también

[Efectuar operaciones de formato](performing-formatting-operations.md)



<!--HONumber=Nov16_HO1-->


