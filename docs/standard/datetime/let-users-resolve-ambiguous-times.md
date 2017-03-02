---
title: "Cómo permitir que los usuarios resuelvan horas ambiguas"
description: "Cómo permitir que los usuarios resuelvan horas ambiguas"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: d6858a5c-02ab-4367-9e08-fa22c051c38d
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: ede8d021a4f524cf37f7ad00b6aed89d1b1729f8
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-let-users-resolve-ambiguous-times"></a>Cómo permitir que los usuarios resuelvan horas ambiguas

Una hora ambigua es aquella que se asigna a más de una hora universal coordinada (UTC). Esto sucede cuando la hora del reloj se atrasa, como durante la transición del horario de verano de una zona horaria al horario estándar. Cuando se enfrente a una hora ambigua, puede realizar una de las siguientes acciones:

* Si la hora ambigua es un dato introducido por el usuario, puede dejar que el usuario resuelva la ambigüedad.

* Piense cómo se corresponde esa hora con la hora UTC. Por ejemplo, puede dar por supuesto que una hora ambigua siempre se expresa en la hora estándar de la zona horaria.

En este artículo se muestra cómo permitir que un usuario resuelva una hora ambigua.

## <a name="to-let-a-user-resolve-an-ambiguous-time"></a>Para permitir que un usuario resuelva una hora ambigua

1. Obtenga la entrada de fecha y hora del usuario.

2. Llame al método [IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) o [IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) para determinar si la hora es ambigua.

3. Permita que el usuario seleccione la diferencia horaria que quiera.

4. Para obtener la fecha y hora UTC, reste de la hora local la diferencia horaria que ha seleccionado el usuario.

5. Llame al método [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) `static` (`Shared` en Visual Basic) para establecer la propiedad [Kind](xref:System.DateTime.Kind) del valor de fecha y hora UTC en [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se le pide al usuario que escriba un valor de fecha y hora y, si es ambiguo, se permite que el usuario seleccione la hora UTC con la que se corresponde dicha hora ambigua. En el ejemplo se usa un objeto [DateTime](xref:System.DateTime) pero, si quiere, puede sustituirlo por un objeto [DateTimeOffset](xref:System.DateTimeOffset).

```csharp
private void GetUserDateInput()
{
   // Get date and time from user
   DateTime inputDate = GetUserDateTime();
   DateTime utcDate;

   // Exit if date has no significant value
   if (inputDate == DateTime.MinValue) return;

   if (TimeZoneInfo.Local.IsAmbiguousTime(inputDate))
   {
      Console.WriteLine("The date you've entered is ambiguous.");
      Console.WriteLine("Please select the correct offset from Universal Coordinated Time:");
      TimeSpan[] offsets = TimeZoneInfo.Local.GetAmbiguousTimeOffsets(inputDate);
      for (int ctr = 0; ctr < offsets.Length; ctr++)
      {
         Console.WriteLine("{0}.) {1} hours, {2} minutes", ctr, offsets[ctr].Hours, offsets[ctr].Minutes);
      }
      Console.Write("> ");
      int selection = Convert.ToInt32(Console.ReadLine());

      // Convert local time to UTC, and set Kind property to DateTimeKind.Utc
      utcDate = DateTime.SpecifyKind(inputDate - offsets[selection], DateTimeKind.Utc);

      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString());
   }
   else
   {
      utcDate = inputDate.ToUniversalTime();
      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString());    
   }
}

private DateTime GetUserDateTime() 
{
   bool exitFlag = false;             // flag to exit loop if date is valid
   string dateString;  
   DateTime inputDate = DateTime.MinValue;

   Console.Write("Enter a local date and time: ");
   while (! exitFlag)
   {
      dateString = Console.ReadLine();
      if (dateString.ToUpper() == "E")
         exitFlag = true;

      if (DateTime.TryParse(dateString, out inputDate))
         exitFlag = true;
      else
         Console.Write("Enter a valid date and time, or enter 'e' to exit: ");
   }

   return inputDate;        
}
```

```vb
Private Sub GetUserDateInput()
   ' Get date and time from user
   Dim inputDate As Date = GetUserDateTime()
   Dim utcDate As Date

   ' Exit if date has no significant value
   If inputDate = Date.MinValue Then Exit Sub

   If TimeZoneInfo.Local.IsAmbiguousTime(inputDate) Then
      Console.WriteLine("The date you've entered is ambiguous.")
      Console.WriteLine("Please select the correct offset from Universal Coordinated Time:")
      Dim offsets() As TimeSpan = TimeZoneInfo.Local.GetAmbiguousTimeOffsets(inputDate)
      For ctr As Integer = 0 to offsets.Length - 1
         Dim zoneDescription As String
         If offsets(ctr).Equals(TimeZoneInfo.Local.BaseUtcOffset) Then 
            zoneDescription = TimeZoneInfo.Local.StandardName
         Else
            zoneDescription = TimeZoneInfo.Local.DaylightName
         End If
         Console.WriteLine("{0}.) {1} hours, {2} minutes ({3})", _
                           ctr, offsets(ctr).Hours, offsets(ctr).Minutes, zoneDescription)
      Next         
      Console.Write("> ")
      Dim selection As Integer = CInt(Console.ReadLine())

      ' Convert local time to UTC, and set Kind property to DateTimeKind.Utc
      utcDate = Date.SpecifyKind(inputDate - offsets(selection), DateTimeKind.Utc)

      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString())
   Else
      utcDate = inputDate.ToUniversalTime()
      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString())    
   End If
End Sub

Private Function GetUserDateTime() As Date
   Dim exitFlag As Boolean = False            ' flag to exit loop if date is valid
   Dim dateString As String 
   Dim inputDate As Date = Date.MinValue

   Console.Write("Enter a local date and time: ")
   Do While Not exitFlag
      dateString = Console.ReadLine()
      If dateString.ToUpper = "E" Then exitFlag = True
      If Date.TryParse(dateString, inputDate) Then
         exitFlag = true
      Else   
         Console.Write("Enter a valid date and time, or enter 'e' to exit: ")
      End If
   Loop

   Return inputDate        
End Function
```

En la parte central del código de ejemplo se usa una matriz de objetos [TimeSpan](xref:System.TimeSpan) para indicar las posibles diferencias horarias de la hora ambigua con respecto a la hora UTC. Pero es probable que estas diferencias horarias sean poco significativas para el usuario. Para aclarar el significado de las diferencias horarias, el código también indica si una diferencia horaria representa la hora estándar o el horario de verano de la zona horaria local. Para determinar cuál es la hora estándar y cuál es el horario de verano, el código compara la diferencia horaria con el valor de la propiedad [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset). Esta propiedad indica la diferencia entre la hora UTC y la hora estándar de la zona horaria.

En este ejemplo, todas las referencias a la zona horaria local se realizan a través de la propiedad [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local). La zona horaria local nunca se asigna a una variable de objeto. Esto es una práctica recomendada, ya que otra llamada podría borrar los datos en caché e invalidar los objetos a los que está asignada la zona horaria local.

## <a name="see-also"></a>Vea también

[Fechas, horas y zonas horarias](index.md)

[Cómo: Resolver horas ambiguas](resolve-ambiguous-times.md)


