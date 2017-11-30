---
title: "Cómo: Convertir una cadena en un valor DateTime (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: strings [C#], converting to DateTIme
ms.assetid: 88abef11-3a06-4b49-8dd2-61ed0e876fc3
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b459f245f0090fff16918bceb12a0082f6944331
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-convert-a-string-to-a-datetime-c-programming-guide"></a>Cómo: Convertir una cadena en un valor DateTime (Guía de programación de C#)
Es habitual que los programas permitan a los usuarios a escribir las fechas como valores de cadena. Para convertir una fecha basada en una cadena en un objeto <xref:System.DateTime?displayProperty=nameWithType> , puede usar el método <xref:System.Convert.ToDateTime%28System.String%29?displayProperty=nameWithType> o el método estático <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> , tal como se muestra en el ejemplo siguiente.  
  
 **Referencia cultural**.  Las distintas referencias culturales que hay en el mundo escriben las cadenas de fecha de maneras distintas.  Por ejemplo, en Estados Unidos 01/20/2008 es el 20 de enero de 2008.  En Francia, esta cadena produciría una InvalidFormatException. Esto es porque en Francia la fecha y la hora se leen con el formato día/mes/año y en Estados Unidos con el formato mes/día/año.  
  
 Por lo tanto, una cadena como 20/01/2008 se analizará como el 20 de enero de 2008 en Francia y generará una InvalidFormatException en Estados Unidos.  
  
 Para determinar la configuración de la referencia cultural actual, puede usar System.Globalization.CultureInfo.CurrentCulture.  
  
 Vea el ejemplo siguiente para obtener un ejemplo de conversión de una cadena a dateTime.  
  
 Para obtener más ejemplos de cadenas de fecha, vea <xref:System.Convert.ToDateTime%28System.String%29?displayProperty=nameWithType>.  
  
```csharp  
string dateTime = "01/08/2008 14:50:50.42";  
            DateTime dt = Convert.ToDateTime(dateTime);  
            Console.WriteLine("Year: {0}, Month: {1}, Day: {2}, Hour: {3}, Minute: {4}, Second: {5}, Millisecond: {6}",  
                              dt.Year, dt.Month, dt.Day, dt.Hour, dt.Minute, dt.Second, dt.Millisecond);  
            // Specify exactly how to interpret the string.  
            IFormatProvider culture = new System.Globalization.CultureInfo("fr-FR", true);  
  
            // Alternate choice: If the string has been input by an end user, you might    
            // want to format it according to the current culture:   
            // IFormatProvider culture = System.Threading.Thread.CurrentThread.CurrentCulture;  
            DateTime dt2 = DateTime.Parse(dateTime, culture, System.Globalization.DateTimeStyles.AssumeLocal);  
            Console.WriteLine("Year: {0}, Month: {1}, Day: {2}, Hour: {3}, Minute: {4}, Second: {5}, Millisecond: {6}",  
                              dt2.Year, dt2.Month, dt2.Day, dt2.Hour, dt2.Minute, dt2.Second, dt2.Millisecond  
/* Output (assuming first culture is en-US and second is fr-FR):  
    Year: 2008, Month: 1, Day: 8, Hour: 14, Minute: 50, Second: 50, Millisecond: 420  
Year: 2008, Month: 8, Day: 1, Hour: 14, Minute: 50, Second: 50, Millisecond: 420  
Press any key to continue . . .  
 */  
```  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideStrings#13](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-a-string-to-a-datetime_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Cadenas](../../../csharp/programming-guide/strings/index.md)
