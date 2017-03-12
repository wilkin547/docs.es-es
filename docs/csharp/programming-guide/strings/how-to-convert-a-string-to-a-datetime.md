---
title: "C&#243;mo: Convertir una cadena en un valor DateTime (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "cadenas [C#], conversión a DateTime"
ms.assetid: 88abef11-3a06-4b49-8dd2-61ed0e876fc3
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# C&#243;mo: Convertir una cadena en un valor DateTime (Gu&#237;a de programaci&#243;n de C#)
Es habitual que los programas permitan a los usuarios a escribir las fechas como valores de cadena. Para convertir una fecha basada en una cadena en un objeto <xref:System.DateTime?displayProperty=fullName>, puede usar el método <xref:System.Convert.ToDateTime%28System.String%29?displayProperty=fullName> o el método estático <xref:System.DateTime.Parse%28System.String%29?displayProperty=fullName>, tal como se muestra en el ejemplo siguiente.  
  
 **Referencia cultural**.  Las distintas referencias culturales que hay en el mundo escriben las cadenas de fecha de maneras distintas.  Por ejemplo, en Estados Unidos 01\/20\/2008 es el 20 de enero de 2008.  En Francia, esta cadena produciría una InvalidFormatException. Esto es porque en Francia la fecha y la hora se leen con el formato día\/mes\/año y en Estados Unidos con el formato mes\/día\/año.  
  
 Por lo tanto, una cadena como 20\/01\/2008 se analizará como el 20 de enero de 2008 en Francia y generará una InvalidFormatException en Estados Unidos.  
  
 Para determinar la configuración de la referencia cultural actual, puede usar System.Globalization.CultureInfo.CurrentCulture.  
  
 Vea el ejemplo siguiente para obtener un ejemplo de conversión de una cadena a dateTime.  
  
 Para obtener más ejemplos de cadenas de fecha, vea <xref:System.Convert.ToDateTime%28System.String%29?displayProperty=fullName>.  
  
```vb  
string dateTime = "01/08/2008 14:50:50.42"; DateTime dt = Convert.ToDateTime(dateTime); Console.WriteLine("Year: {0}, Month: {1}, Day: {2}, Hour: {3}, Minute: {4}, Second: {5}, Millisecond: {6}", dt.Year, dt.Month, dt.Day, dt.Hour, dt.Minute, dt.Second, dt.Millisecond); // Specify exactly how to interpret the string. IFormatProvider culture = new System.Globalization.CultureInfo("fr-FR", true); // Alternate choice: If the string has been input by an end user, you might // want to format it according to the current culture: // IFormatProvider culture = System.Threading.Thread.CurrentThread.CurrentCulture; DateTime dt2 = DateTime.Parse(dateTime, culture, System.Globalization.DateTimeStyles.AssumeLocal); Console.WriteLine("Year: {0}, Month: {1}, Day: {2}, Hour: {3}, Minute: {4}, Second: {5}, Millisecond: {6}", dt2.Year, dt2.Month, dt2.Day, dt2.Hour, dt2.Minute, dt2.Second, dt2.Millisecond /* Output (assuming first culture is en-US and second is fr-FR): Year: 2008, Month: 1, Day: 8, Hour: 14, Minute: 50, Second: 50, Millisecond: 420 Year: 2008, Month: 8, Day: 1, Hour: 14, Minute: 50, Second: 50, Millisecond: 420 Press any key to continue . . . */  
```  
  
## Ejemplo  
 [!code-cs[csProgGuideStrings#13](../../../csharp/programming-guide/strings/codesnippet/csharp/CSRefStrings/Strings.cs#13)]  
  
## Vea también  
 [Cadenas](../../../csharp/programming-guide/strings/index.md)