---
title: "Cómo: Comprobar si las cadenas tienen un formato de correo electrónico válido"
description: "Cómo comprobar si las cadenas tienen un formato de correo electrónico válido"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 6d735520-4059-4754-b34c-d117299d36f1
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 077a09152ac23c986a751f42c893e1dcca858291
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-verify-that-strings-are-in-valid-email-format"></a>Cómo: Comprobar si las cadenas tienen un formato de correo electrónico válido

En el ejemplo siguiente se usa una expresión regular para comprobar que una cadena tiene un formato de correo electrónico válido.

## <a name="example"></a>Ejemplo

En el ejemplo se define un método `IsValidEmail`, que devuelve `true` si la cadena contiene una dirección de correo electrónico válida y `false` si no es válida, pero no realiza ninguna otra acción. 

Para comprobar que la dirección de correo electrónico es válida, el método `IsValidEmail` llama al método [Regex.Replace(String, String, MatchEvaluator)](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.Text.RegularExpressions.MatchEvaluator)) con el patrón de expresión regular `(@)(.+)$` para separar el nombre de dominio de la dirección de correo electrónico. El tercer parámetro es un delegado [MatchEvaluator](xref:System.Text.RegularExpressions.MatchEvaluator) que representa el método que procesa y reemplaza el texto coincidente. El patrón de expresión regular se interpreta de esta manera: 

Modelo | Descripción
------- | ----------- 
`(@)` | Buscar el carácter @. Este es el primer grupo de captura.
`(.+)` | Buscar una coincidencia con una o más apariciones de cualquier carácter. Este es el segundo grupo de captura.
`$` | Finalizar la búsqueda al final de la cadena.
 
El nombre de dominio junto con el carácter @ se pasa al método `DomainMapper`, que usa la clase [IdnMapping](xref:System.Globalization.IdnMapping) para convertir a Punycode los caracteres Unicode que están fuera del intervalo de caracteres US-ASCII. El método también establece la marca `invalid` en `true` si el método [IdnMapping.GetAscii](xref:System.Globalization.IdnMapping.GetAscii(System.String)) detecta cualquier carácter no válido en el nombre del dominio. El método devuelve el nombre de dominio Punycode precedido por el símbolo @ al método `IsValidEmail`. 

Después el método `IsValidEmail` llama al método [Regex.IsMatch(String, String)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String)) para comprobar que la dirección se ajusta a un patrón de expresión regular. 

Tenga en cuenta que el método `IsValidEmail` no realiza la autenticación para validar la dirección de correo electrónico. Se limita a determinar si su formato es válido para una dirección de correo electrónico. Asimismo, el método `IsValidEmail` no comprueba que el nombre del dominio de nivel superior sea un nombre válido enumerado en la [base de datos de la zona de la raíz IANA](https://www.iana.org/domains/root/db), lo cual requeriría una operación de búsqueda. En su lugar, la expresión regular comprueba simplemente que el nombre de dominio de nivel superior conste de entre dos y veinticuatro caracteres ASCII alfanuméricos, que los caracteres primero y último sean alfanuméricos y que el resto de caracteres sean alfanuméricos o un guión (-). 

```csharp
using System;
using System.Globalization;
using System.Text.RegularExpressions;

public class RegexUtilities
{
   bool invalid = false;

   public bool IsValidEmail(string strIn)
   {
       invalid = false;
       if (String.IsNullOrEmpty(strIn))
          return false;

       // Use IdnMapping class to convert Unicode domain names.
       try {
          strIn = Regex.Replace(strIn, @"(@)(.+)$", this.DomainMapper,
                                RegexOptions.None, TimeSpan.FromMilliseconds(200));
       }
       catch (RegexMatchTimeoutException) {
         return false;
       }

        if (invalid)
           return false;

       // Return true if strIn is in valid e-mail format.
       try {
          return Regex.IsMatch(strIn,
                @"^(?("")("".+?(?<!\\)""@)|(([0-9a-z]((\.(?!\.))|[-!#\$%&'\*\+/=\?\^`\{\}\|~\w])*)(?<=[0-9a-z])@))" +
                @"(?(\[)(\[(\d{1,3}\.){3}\d{1,3}\])|(([0-9a-z][-\w]*[0-9a-z]*\.)+[a-z0-9][\-a-z0-9]{0,22}[a-z0-9]))$",
                RegexOptions.IgnoreCase, TimeSpan.FromMilliseconds(250));
       }
       catch (RegexMatchTimeoutException) {
          return false;
       }
   }

   private string DomainMapper(Match match)
   {
      // IdnMapping class with default property values.
      IdnMapping idn = new IdnMapping();

      string domainName = match.Groups[2].Value;
      try {
         domainName = idn.GetAscii(domainName);
      }
      catch (ArgumentException) {
         invalid = true;
      }
      return match.Groups[1].Value + domainName;
   }
}
```

```vb
Imports System.Globalization
Imports System.Text.RegularExpressions

Public Class RegexUtilities
   Dim invalid As Boolean = False

   public Function IsValidEmail(strIn As String) As Boolean
       invalid = False
       If String.IsNullOrEmpty(strIn) Then Return False

       ' Use IdnMapping class to convert Unicode domain names.
       Try
          strIn = Regex.Replace(strIn, "(@)(.+)$", AddressOf Me.DomainMapper, 
                                RegexOptions.None, TimeSpan.FromMilliseconds(200))
       Catch e As RegexMatchTimeoutException
          Return False
       End Try

       If invalid Then Return False

       ' Return true if strIn is in valid e-mail format.
       Try
          Return Regex.IsMatch(strIn,
                 "^(?("")("".+?(?<!\\)""@)|(([0-9a-z]((\.(?!\.))|[-!#\$%&'\*\+/=\?\^`\{\}\|~\w])*)(?<=[0-9a-z])@))" +
                 "(?(\[)(\[(\d{1,3}\.){3}\d{1,3}\])|(([0-9a-z][-\w]*[0-9a-z]*\.)+[a-z0-9][\-a-z0-9]{0,22}[a-z0-9]))$",
                 RegexOptions.IgnoreCase, TimeSpan.FromMilliseconds(250))
       Catch e As RegexMatchTimeoutException
          Return False
       End Try  
   End Function

   Private Function DomainMapper(match As Match) As String
      ' IdnMapping class with default property values.
      Dim idn As New IdnMapping()

      Dim domainName As String = match.Groups(2).Value
      Try
         domainName = idn.GetAscii(domainName)
      Catch e As ArgumentException
         invalid = True      
      End Try      
      Return match.Groups(1).Value + domainName
   End Function
End Class
```

En este ejemplo, el patrón de expresión regular `^(?(")(".+?(?<!\\)"@)|(([0-9a-z]((\.(?!\.))|[-!#\$%&'\*\+/=\?\^` \{ \} \|~ \w])*)(?<=[0-9a-z])@))(?(\[)(\[(\d{1,3}\.){3}\d{1,3}\])|( ([0-9a-z] [-\w]*[0-9a-z] *\.) + [a-z0-9] [\-a-z0-9]{0,22}[a-z0-9]))$` se interpreta como se muestra en la tabla siguiente. Tenga en cuenta que la expresión regular se compila usando la marca [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase).

Modelo | Descripción
------- | ----------- 
`^` | Comenzar la búsqueda de coincidencia al principio de la cadena.
`(?(")` | Determinar si el primer carácter es una comilla. `(?(")` es el principio de una construcción de alternancia.
`(?("")("".+?(?<!\\)""@)` | Si el primer carácter es un signo de comillas, buscar unas comillas iniciales seguidas de al menos un carácter cualquiera, seguido a su vez de unas comillas finales. Las comillas finales no deben ir precedidas por un carácter de barra diagonal inversa `(\). (?<!` es el principio de una aserción de búsqueda tardía negativa de ancho cero. La cadena debe concluir con una arroba (@).
`&#124;(([0-9a-z] | Si el primer carácter no es un signo de comillas, buscar cualquier carácter alfabético de la a a la z o de la A a la Z (la comparación distingue entre mayúsculas y minúsculas) o cualquier carácter numérico del 0 al 9.
`(\.(?!\.))` | Si el carácter siguiente es un punto, determinar que coincide. Si no lo es, buscar más adelante en el siguiente carácter y probar si coincide. `(?!\.)` es una aserción de búsqueda anticipada negativa de ancho igual a cero que evita que aparezcan dos puntos consecutivos en la parte local de una dirección de correo electrónico.
`&#124;[-!#\$%&'\*\+/=\?\^`\{\}\&#124;~\w] | Si el carácter siguiente no es un punto, buscar cualquier carácter de palabra coincidente o uno de los siguientes caracteres: -!#$%'*+=?^`{}&#124;~. 
`((\.(?!\.))&#124;[-!#\$%'\*\+/=\?\^`\{\}\&#124;~\w])* | Buscar el modelo de alternancia (un punto seguido de algo que no sea un punto, o uno de varios caracteres) cero o más veces.
`@` | Buscar el carácter @.
`(?<=[0-9a-z])` | Continuar buscando si el carácter que precede al carácter @ es uno de la A a la Z, de la a a la z o del 0 al 9. La construcción `(?<=[0-9a-z])` define una aserción de búsqueda tardía positiva de ancho igual a cero.
`(?(\[)` | Comprobar si el carácter que va detrás de @ es un corchete de apertura.
`(\[(\d{1,3}\.){3}\d{1,3}\])` | Si lo es, buscar el corchete de apertura, seguido por una dirección IP (cuatro grupos de uno a tres dígitos, separados por puntos) y por un corchete de cierre.
`&#124;(([0-9a-z][-\w]*[0-9a-z]*\.)+` | Si el carácter que va detrás de @ no es un corchete de apertura, buscar un carácter alfanumérico con un valor de la A a la Z, de la a a la z o del 0 al 9, seguido de cero o más apariciones de un carácter alfabético o un guion, seguido de cero o de un carácter alfanumérico con un valor de la A a la Z, de la a a la z o del 0 al 9, seguido de un punto. Este patrón se puede repetir una o más veces y debe ir seguido del nombre de dominio de nivel superior. 
`[a-z0-9][\-a-z0-9]{0,22}[a-z0-9]))` | El nombre de dominio de nivel superior debe empezar y finalizar por un carácter alfanumérico (a-z, A-Z y 0-9). También puede incluir de cero a 22 caracteres ASCII que sean alfanuméricos o guiones. 
`$` | Finalizar la búsqueda al final de la cadena.
 
Puede llamar a los métodos `IsValidEmail` y `DomainMapper` con un código como el siguiente:

```csharp
public class Application
{
   public static void Main()
   {
      RegexUtilities util = new RegexUtilities();
      string[] emailAddresses = { "david.jones@proseware.com", "d.j@server1.proseware.com",
                                  "jones@ms1.proseware.com", "j.@server1.proseware.com",
                                  "j@proseware.com9", "js#internal@proseware.com",
                                  "j_9@[129.126.118.1]", "j..s@proseware.com",
                                  "js*@proseware.com", "js@proseware..com",
                                  "js@proseware.com9", "j.s@server1.proseware.com",
                                   "\"j\\\"s\\\"\"@proseware.com", "js@contoso.中国" };

      foreach (var emailAddress in emailAddresses) {
         if (util.IsValidEmail(emailAddress))
            Console.WriteLine("Valid: {0}", emailAddress);
         else
            Console.WriteLine("Invalid: {0}", emailAddress);
      }                                            
   }
}
// The example displays the following output:
//       Valid: david.jones@proseware.com
//       Valid: d.j@server1.proseware.com
//       Valid: jones@ms1.proseware.com
//       Invalid: j.@server1.proseware.com
//       Valid: j@proseware.com9
//       Valid: js#internal@proseware.com
//       Valid: j_9@[129.126.118.1]
//       Invalid: j..s@proseware.com
//       Invalid: js*@proseware.com
//       Invalid: js@proseware..com
//       Valid: js@proseware.com9
//       Valid: j.s@server1.proseware.com
//       Valid: "j\"s\""@proseware.com
//       Valid: js@contoso.ä¸­å›½
```

```vb
Public Class Application
   Public Shared Sub Main()
      Dim util As New RegexUtilities()
      Dim emailAddresses() As String = { "david.jones@proseware.com", "d.j@server1.proseware.com", _
                                         "jones@ms1.proseware.com", "j.@server1.proseware.com", _
                                         "j@proseware.com9", "js#internal@proseware.com", _
                                         "j_9@[129.126.118.1]", "j..s@proseware.com", _
                                         "js*@proseware.com", "js@proseware..com", _
                                         "js@proseware.com9", "j.s@server1.proseware.com",
                                         """j\""s\""""@proseware.com", "js@contoso.中国" }

      For Each emailAddress As String In emailAddresses
         If util.IsValidEmail(emailAddress) Then
            Console.WriteLine("Valid: {0}", emailAddress)
         Else
            Console.WriteLine("Invalid: {0}", emailAddress)
         End If      
      Next                                            
   End Sub
End Class
' The example displays the following output:
'       Valid: david.jones@proseware.com
'       Valid: d.j@server1.proseware.com
'       Valid: jones@ms1.proseware.com
'       Invalid: j.@server1.proseware.com
'       Valid: j@proseware.com9
'       Valid: js#internal@proseware.com
'       Valid: j_9@[129.126.118.1]
'       Invalid: j..s@proseware.com
'       Invalid: js*@proseware.com
'       Invalid: js@proseware..com
'       Valid: js@proseware.com9
'       Valid: j.s@server1.proseware.com
'       Valid: "j\"s\""@proseware.com
'       Valid: js@contoso.ä¸­å›½
```

## <a name="see-also"></a>Vea también

[Expresiones regulares de .NET](regular-expressions.md)

[Ejemplos de expresiones regulares](regex-examples.md)

