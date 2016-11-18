---
title: 'Ejemplo de expresiones regulares: cambiar formatos de fecha'
description: 'Ejemplo de expresiones regulares: cambiar formatos de fecha'
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 3e196697-981c-4c1d-93dd-c3b236ef36dd
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 65cdec2c8bc8caf44329ee44bd574e612723be11

---

# <a name="regular-expression-example-changing-date-formats"></a>Ejemplo de expresiones regulares: cambiar formatos de fecha

En el siguiente ejemplo de código, se usa el método [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) para reemplazar las fechas con el formato *mm/dd/aa* con fechas que tienen el formato *dd-mm-aa*.

## <a name="example"></a>Ejemplo

```csharp
static string MDYToDMY(string input) 
{
   try {
      return Regex.Replace(input, 
            "\\b(?<month>\\d{1,2})/(?<day>\\d{1,2})/(?<year>\\d{2,4})\\b",
            "${day}-${month}-${year}", RegexOptions.None,
            TimeSpan.FromMilliseconds(150));
   }         
   catch (RegexMatchTimeoutException) {
      return input;
   }
}
```

```vb
Function MDYToDMY(input As String) As String
   Try
      Return Regex.Replace(input, _
             "\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b", _
             "${day}-${month}-${year}", RegexOptions.None,
             TimeSpan.FromMilliseconds(150))
    Catch e As RegexMatchTimeoutException
       Return input
    End Try         
End Function
```

El código siguiente muestra cómo se puede llamar al método `MDYToDMY` en una aplicación. 

```csharp
using System;
using System.Globalization;
using System.Text.RegularExpressions;

public class Class1
{
   public static void Main()
   {
      string dateString = DateTime.Today.ToString("d", 
                                        DateTimeFormatInfo.InvariantInfo);
      string resultString = MDYToDMY(dateString);
      Console.WriteLine("Converted {0} to {1}.", dateString, resultString);
   }

   static string MDYToDMY(string input) 
   {
      try {
         return Regex.Replace(input, 
               "\\b(?<month>\\d{1,2})/(?<day>\\d{1,2})/(?<year>\\d{2,4})\\b",
               "${day}-${month}-${year}", RegexOptions.None,
               TimeSpan.FromMilliseconds(150));
      }         
      catch (RegexMatchTimeoutException) {
         return input;
      }
   }

}
// The example displays the following output to the console if run on 8/21/2007:
//      Converted 08/21/2007 to 21-08-2007.
```

```vb
Imports System.Globalization
Imports System.Text.RegularExpressions

Module DateFormatReplacement
   Public Sub Main()
      Dim dateString As String = Date.Today.ToString("d", _
                                           DateTimeFormatInfo.InvariantInfo)
      Dim resultString As String = MDYToDMY(dateString)
      Console.WriteLine("Converted {0} to {1}.", dateString, resultString)
   End Sub

    Function MDYToDMY(input As String) As String
       Try
          Return Regex.Replace(input, _
                 "\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b", _
                 "${day}-${month}-${year}", RegexOptions.None,
                 TimeSpan.FromMilliseconds(150))
        Catch e As RegexMatchTimeoutException
           Return input
        End Try         
    End Function
End Module
' The example displays the following output to the console if run on 8/21/2007:
'      Converted 08/21/2007 to 21-08-2007.
```

## <a name="comments"></a>Comentarios

El patrón de la expresión regular `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` se interpreta como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`\b` | Iniciar la búsqueda de coincidencias en un límite de palabras.
`(?<month>\d{1,2})` | Buscar coincidencias con uno o dos dígitos decimales. Es el grupo `month` capturado.
`/` | Buscar coincidencias con la barra diagonal.
`(?<day>\d{1,2})` | Buscar coincidencias con uno o dos dígitos decimales. Es el grupo `day` capturado.
`/` | Buscar coincidencias con la barra diagonal.
`(?<year>\d{2,4})` | Buscar coincidencias de dos a cuatro dígitos decimales. Es el grupo `year` capturado.
`\b` | Finalizar la búsqueda de coincidencias en un límite de palabras.
 
El patrón `${day}-${month}-${year}` define la cadena de reemplazo como se muestra en la siguiente tabla.

Modelo | Descripción
------- | ----------- 
`$(day)` | Agregar la cadena capturada por el grupo de captura `day`.
`-` | Agregar un guión.
`$(month)` | Agregar la cadena capturada por el grupo de captura `month`.
`-` | Agregar un guión.
`$(year)` | Agregar la cadena capturada por el grupo de captura `year`.
 
## <a name="see-also"></a>Vea también

[Expresiones regulares de .NET](regular-expressions.md)

[Ejemplos de expresiones regulares](regex-examples.md)



<!--HONumber=Nov16_HO3-->


