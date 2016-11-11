---
title: Procedimientos recomendados para el uso de cadenas
description: Procedimientos recomendados para el uso de cadenas
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: b3cefaa4-0a3f-4a96-aba9-1de30fb07c29
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 3efd30bade564fe1b7dbf93237a9ff40c58c5f1e

---

# <a name="best-practices-for-using-strings"></a>Procedimientos recomendados para el uso de cadenas

.NET proporciona una gran compatibilidad para desarrollar aplicaciones localizadas y globalizadas, y simplifica la aplicación de las convenciones de la referencia cultural actual o de una referencia cultural concreta al realizar operaciones comunes como ordenar y mostrar cadenas. Pero ordenar o comparar cadenas no es siempre una operación dependiente de la referencia cultural. Por ejemplo, las cadenas usadas internamente por una aplicación normalmente se deben administrar de forma idéntica en todas las referencias culturales. Cuando los datos de cadenas independientes de la referencia cultural (como etiquetas XML, etiquetas HTML, nombres de usuario, rutas de acceso de archivos y nombres de objetos del sistema) se interpretan como si fueran dependientes de la referencia cultural, el código de aplicación puede estar sujeto a errores imperceptibles, un rendimiento inadecuado y, en algunos casos, a problemas de seguridad.

En este artículo, se examinan los métodos de ordenación, comparación y uso de mayúsculas y minúsculas de cadenas de .NET, se presentan recomendaciones para seleccionar un método adecuado de control de cadenas y se proporciona información adicional sobre los métodos de control de cadenas. También se examina cómo se usan para la presentación y el almacenamiento los datos con formato, como los datos numéricos y los datos de fecha y hora. 

Este artículo contiene las siguientes secciones:

* [Recomendaciones sobre el uso de cadenas](#recommendations-for-string-usage)

* [Especificar comparaciones de cadenas explícitamente](#specifying-string-comparisons-explicitly)

* [Detalles de la comparación de cadenas](#the-details-of-string-comparison)

* [Elegir un miembro StringComparison para la llamada al método](#choosing-a-stringcomparison-member-for-your-method-call)

* [Métodos comunes de comparación de cadenas](#common-string-comparison-methods)

* [Métodos que realizan la comparación de cadenas indirectamente](#methods-that-perform-string-comparison-indirectly)

* [Mostrar y conservar datos con formato](#displaying-and-persisting-formatted-data)

## <a name="recommendations-for-string-usage"></a>Recomendaciones sobre el uso de cadenas

Cuando desarrolle con .NET, siga estas recomendaciones sencillas a la hora de usar cadenas: 

* Use sobrecargas que especifiquen explícitamente las reglas de comparación de cadenas para las operaciones de cadenas. Normalmente, esto implica llamar a una sobrecarga de método que tiene un parámetro de tipo [StringComparison](xref:System.StringComparison).

* Use [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) o [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) para las comparaciones como su valor predeterminado seguro para la coincidencia de cadenas válidas para la referencia cultural.

* Use comparaciones con [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) o [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) para mejorar el rendimiento.

* Use operaciones de cadena basadas en [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) al mostrar la salida al usuario.

* Use los valores [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) o [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) no lingüísticos en lugar de operaciones de cadena basadas en [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) cuando la comparación sea lingüísticamente pertinente (por ejemplo, nombre simbólico).

* Use el método [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) en lugar del método [String.ToLowerInvariant](xref:System.String.ToLowerInvariant) al normalizar cadenas para la comparación.

* Use una sobrecarga del método [String](xref:System.String) `Equals` para probar si dos cadenas son iguales.

* Use una sobrecarga de los métodos [String](xref:System.String) `Compare` y [String.CompareTo](xref:System.String.CompareTo(System.String)) para ordenar cadenas, no para comprobar la igualdad.

* Use el formato dependiente de la referencia cultural para mostrar datos que no son de cadena, como números y fechas, en una interfaz de usuario. Use el formato con la referencia cultural de todos los idiomas para conservar datos que no son de cadena en forma de cadena.

Evite lo siguiente cuando use cadenas:

* No emplee sobrecargas que no especifiquen explícita o implícitamente las reglas de comparación de cadenas para las operaciones de cadena. 

* No use ninguna sobrecarga del método [String](xref:System.String) `Compare` o [String.CompareTo](xref:System.String.CompareTo(System.String)) y pruebe si se devuelve un valor cero para determinar si dos cadenas son iguales.

* No use el formato dependiente de la referencia cultural para conservar datos numéricos o datos de fecha y hora en formato de cadena.

## <a name="specifying-string-comparisons-explicitly"></a>Especificar comparaciones de cadenas explícitamente

La mayoría de los métodos de manipulación de cadenas de .NET están sobrecargados. Normalmente, una o más sobrecargas aceptan la configuración predeterminada, mientras que otras no aceptan ningún valor predeterminado y en su lugar definen la manera precisa en la que se van a comparar o manipular las cadenas. La mayoría de los métodos que no confían en los valores predeterminados incluye un parámetro de tipo [StringComparison](xref:System.StringComparison), que es una enumeración que especifica explícitamente reglas para la comparación de cadenas por referencia cultural y uso de mayúsculas y minúsculas. En la tabla siguiente, se describen los miembros de la enumeración [StringComparison](xref:System.StringComparison). 

Miembro de StringComparison | Descripción
----------------------- | -----------
[StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) | Realiza una comparación con distinción entre mayúsculas y minúsculas usando la referencia cultural actual.
[CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase) | Realiza una comparación sin distinción entre mayúsculas y minúsculas usando la referencia cultural actual.
[StringComparison.Ordinal](xref:System.StringComparison.Ordinal) | Realiza una comparación ordinal.
[StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) | Realiza una comparación ordinal sin distinción entre mayúsculas y minúsculas.

Por ejemplo, el método [String](xref:System.String) `IndexOf`, que devuelve el índice de una subcadena en un objeto [String](xref:System.String) que coincide con un carácter o una cadena, tiene nueve sobrecargas:

* [IndexOf(Char)](xref:System.String.IndexOf(System.Char)), [IndexOf(Char, Int32)](xref:System.String.IndexOf(System.Char,System.Int32)) e [IndexOf(Char, Int32, Int32)](xref:System.String.IndexOf(System.Char,System.Int32,System.Int32)) que, de manera predeterminada, realizan una búsqueda ordinal (con distinción entre mayúsculas y minúsculas e independiente de la referencia cultural) de un carácter de la cadena.

* [IndexOf(String)](xref:System.String.IndexOf(System.String)), [IndexOf(String, Int32)](xref:System.String.IndexOf(System.String,System.Int32)) e [IndexOf(String, Int32, Int32)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32)) que, de manera predeterminada, realizan una búsqueda con distinción entre mayúsculas y minúsculas, y dependiente de la referencia cultural de una subcadena de la cadena.

* [IndexOf(String, StringComparison)](xref:System.String.IndexOf(System.String,System.StringComparison)), [IndexOf(String, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.StringComparison)) e [IndexOf(String, Int32, Int32, StringComparison)](xref:System.String.IndexOf(System.String,System.Int32,System.Int32,System.StringComparison)) que incluyen un parámetro de tipo StringComparison que permite especificar el formato de la comparación.

Se recomienda seleccionar una sobrecarga que no use valores predeterminados, por las razones siguientes:

* Algunas sobrecargas con parámetros predeterminados (las que buscan un valor [Char](xref:System.Char) en la instancia de la cadena) realizan una comparación ordinal, mientras que otras (las que buscan una cadena en la instancia de la cadena) son dependientes de la referencia cultural. Es difícil recordar qué método usa cada valor predeterminado y resulta fácil confundir las sobrecargas.

* La intención del código que usa valores predeterminados para las llamadas al método no está clara. En el ejemplo siguiente, donde se usan valores predeterminados, es difícil saber si el desarrollador pretendía realmente realizar una comparación ordinal o lingüística de dos cadenas, o si una diferencia en el uso de mayúsculas y minúsculas entre `protocol` y "http" podría hacer que la prueba de igualdad devolviera `false`.

  ```csharp
  string protocol = GetProtocol(url);       
  if (String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase)) {
     // ...Code to handle HTTP protocol.
  }
  else {
     throw new InvalidOperationException();
  }
  ```

  ```vb
  Dim protocol As String = GetProtocol(url)       
  If String.Equals(protocol, "http") Then
    ' ...Code to handle HTTP protocol.
  Else
     Throw New InvalidOperationException()
  End If
  ```

En general, se recomienda llamar a un método que no use los valores predeterminados, ya que hace que la intención del código no sea ambigua. Esto, a su vez, hace el código más legible y más fácil de depurar y mantener. En el ejemplo siguiente se abordan las cuestiones que se derivan del ejemplo anterior. Indica claramente que se usa la comparación ordinal y que se omiten las diferencias en cuanto al uso de mayúsculas y minúsculas. 

```csharp
string protocol = GetProtocol(url);       
if (String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase)) {
   // ...Code to handle HTTP protocol.
}
else {
   throw new InvalidOperationException();
}
```

```vb
Dim protocol As String = GetProtocol(url)       
If String.Equals(protocol, "http", StringComparison.OrdinalIgnoreCase) Then
   ' ...Code to handle HTTP protocol.
Else
   Throw New InvalidOperationException()
End If
```

## <a name="the-details-of-string-comparison"></a>Detalles de la comparación de cadenas

La comparación de cadenas es el corazón de muchas operaciones relacionadas con cadenas, especialmente la ordenación y la comprobación de igualdad. Las cadenas se ordenan en un orden determinado: si "mi" aparece antes que "cadena" en una lista ordenada de cadenas, "mi" debe compararse como menor o igual que "cadena". Además, la comparación define la igualdad implícitamente. La operación de comparación devuelve cero para las cadenas que considera iguales. Una buena interpretación es que ninguna cadena es menor que otra. La mayoría de las operaciones significativas que implican cadenas incluyen uno o ambos de estos procedimientos: comparar con otra cadena y ejecutar una operación de ordenación bien definida.

Sin embargo, la evaluación de dos cadenas para comprobar su igualdad o su criterio de ordenación no produce ningún resultado correcto único; el resultado depende de los criterios empleados para comparar las cadenas. En especial, las comparaciones de cadenas que son ordinales o que se basan en las convenciones de ordenación y uso de mayúsculas y minúsculas de la referencia cultural actual o de la referencia cultural de todos los idiomas (una referencia cultural válida para la configuración regional basada en el idioma inglés) pueden producir resultados diferentes.

### <a name="string-comparisons-that-use-the-current-culture"></a>Comparaciones de cadenas que usan la referencia cultural actual

Un criterio implica usar las convenciones de la referencia cultural actual a la hora de comparar cadenas. Las comparaciones que se basan en la referencia cultural actual usan la referencia cultural o la configuración regional actual del subproceso. Siempre debe usar comparaciones basadas en la referencia cultural actual cuando los datos sean lingüísticamente pertinentes y cuando refleje una interacción con el usuario dependiente de la referencia cultural. 

En cambio, el comportamiento de comparación y uso de mayúsculas y minúsculas de .NET cambia cuando la referencia cultural cambia. Esto ocurre cuando una aplicación se ejecuta en un equipo que tiene una referencia cultural diferente que el equipo en el que se desarrolló la aplicación o cuando el subproceso en ejecución cambia su referencia cultural. Este comportamiento es deliberado, pero sigue resultando no obvio para muchos desarrolladores. En el ejemplo siguiente, se muestran las diferencias en el criterio de ordenación entre las referencias culturales de inglés de EE. UU. ("en-US") y sueco ("sv-SE"). Tenga en cuenta que las palabras "ångström", "Windows" y "Visual Studio" aparecen en distintas posiciones en las matrices de cadenas ordenadas.

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] values= { "able", "ångström", "apple", "Æble", 
                         "Windows", "Visual Studio" };
      Array.Sort(values);
      DisplayArray(values);

      // Change culture to Swedish (Sweden).
      string originalCulture = CultureInfo.CurrentCulture.Name;
      Thread.CurrentThread.CurrentCulture = new CultureInfo("sv-SE");
      Array.Sort(values);
      DisplayArray(values);

      // Restore the original culture.
      Thread.CurrentThread.CurrentCulture = new CultureInfo(originalCulture);
    }

    private static void DisplayArray(string[] values)
    {
      Console.WriteLine("Sorting using the {0} culture:",  
                        CultureInfo.CurrentCulture.Name);
      foreach (string value in values)
         Console.WriteLine("   {0}", value);

      Console.WriteLine();
    }
}
// The example displays the following output:
//       Sorting using the en-US culture:
//          able
//          Æble
//          ångström
//          apple
//          Visual Studio
//          Windows
//       
//       Sorting using the sv-SE culture:
//          able
//          Æble
//          apple
//          Windows
//          Visual Studio
//          ångström
```

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim values() As String = { "able", "ångström", "apple", _
                                 "Æble", "Windows", "Visual Studio" }
      Array.Sort(values)
      DisplayArray(values)

      ' Change culture to Swedish (Sweden).
      Dim originalCulture As String = CultureInfo.CurrentCulture.Name
      Thread.CurrentThread.CurrentCulture = New CultureInfo("sv-SE")
      Array.Sort(values)
      DisplayArray(values)

      ' Restore the original culture.
      Thread.CurrentThread.CurrentCulture = New CultureInfo(originalCulture)
    End Sub

    Private Sub DisplayArray(values() As String)
      Console.WRiteLine("Sorting using the {0} culture:", _ 
                        CultureInfo.CurrentCulture.Name)
      For Each value As String In values
         Console.WriteLine("   {0}", value)
      Next
      Console.WriteLine()   
    End Sub
End Module
' The example displays the following output:
'       Sorting using the en-US culture:
'          able
'          Æble
'          ångström
'          apple
'          Visual Studio
'          Windows
'       
'       Sorting using the sv-SE culture:
'          able
'          Æble
'          apple
'          Windows
'          Visual Studio
'          ångström
```

Las comparaciones sin distinción entre mayúsculas y minúsculas que usan la referencia cultural actual son iguales que las comparaciones dependientes de la referencia cultural, excepto que omiten el uso de mayúsculas y minúsculas según indica la referencia cultural actual del subproceso. Este comportamiento también se puede manifestar en los criterios de ordenación. 

Las comparaciones que usan semántica de la referencia cultural actual son el valor predeterminado para los métodos siguientes:

* Sobrecargas de [String](xref:System.String) `Compare` que no incluyen un parámetro [StringComparison](xref:System.StringComparison).

* Sobrecargas de [String.CompareTo](xref:System.String.CompareTo(System.String)).

* El método [String.StartsWith(String)](xref:System.String.StartsWith(System.String)) predeterminado. 

* El método [String.EndsWith(String)](xref:System.String.EndsWith(System.String)) predeterminado.

* Sobrecargas de [String](xref:System.String) `IndexOf` que aceptan [String](xref:System.String) como un parámetro de búsqueda y que no tienen un parámetro [StringComparison](xref:System.StringComparison).

* Sobrecargas de [String](xref:System.String) `LastIndexOf` que aceptan [String](xref:System.String) como un parámetro de búsqueda y que no tienen un parámetro [StringComparison](xref:System.StringComparison).

En cualquier caso, se recomienda llamar a una sobrecarga que tenga un parámetro [StringComparison](xref:System.StringComparison) para aclarar la intención de la llamada al método. 

Pueden surgir errores imperceptibles y no tan imperceptibles cuando los datos de cadenas no lingüísticos se interpretan lingüísticamente, o cuando los datos de cadenas de una referencia cultural determinada se interpretan usando las convenciones de otra referencia cultural. El ejemplo canónico es el problema con I en turco.

Para casi todos los alfabetos latinos, incluso en inglés de EE. UU., el carácter "i" (\u0069) es la versión en minúsculas del carácter "I" (\u0049). Esta regla de mayúsculas y minúsculas se convierte rápidamente en el valor predeterminado para alguien que programe en esa referencia cultural. En cambio, el alfabeto turco ("tr-TR") incluye un carácter "I con punto" "İ" (\u0130), que es la versión en mayúsculas de "i". El turco también incluye un carácter "i sin punto" en minúscula, "ı" (\u0131), que en mayúsculas es "I". Este comportamiento también se produce en la referencia cultural de azerbaiyano ("az").

Por tanto, los supuestos sobre poner en mayúsculas "i" o escribir "I" en minúsculas no son válidas en todas las referencias culturales. Si usa las sobrecargas predeterminadas para las rutinas de comparación de cadenas, estarán sujetas a variaciones entre distintas referencias culturales. Si los datos que se van a comparar son no lingüísticos, el uso de las sobrecargas predeterminadas puede generar resultados no deseables, como ilustra el siguiente intento de realizar una comparación sin distinción entre mayúsculas y minúsculas de las cadenas "file" y "FILE".

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string fileUrl = "file";
      Thread.CurrentThread.CurrentCulture = new CultureInfo("en-US");
      Console.WriteLine("Culture = {0}",
                        Thread.CurrentThread.CurrentCulture.DisplayName);
      Console.WriteLine("(file == FILE) = {0}", 
                       fileUrl.StartsWith("FILE", true, null));
      Console.WriteLine();

      Thread.CurrentThread.CurrentCulture = new CultureInfo("tr-TR");
      Console.WriteLine("Culture = {0}",
                        Thread.CurrentThread.CurrentCulture.DisplayName);
      Console.WriteLine("(file == FILE) = {0}", 
                        fileUrl.StartsWith("FILE", true, null));
   }
}
// The example displays the following output:
//       Culture = English (United States)
//       (file == FILE) = True
//       
//       Culture = Turkish (Turkey)
//       (file == FILE) = False
```

```vb
Imports System.Globalization
Imports System.Threading

Module Example
   Public Sub Main()
      Dim fileUrl = "file"
      Thread.CurrentThread.CurrentCulture = New CultureInfo("en-US")
      Console.WriteLine("Culture = {0}", _
                        Thread.CurrentThread.CurrentCulture.DisplayName)
      Console.WriteLine("(file == FILE) = {0}", _ 
                       fileUrl.StartsWith("FILE", True, Nothing))
      Console.WriteLine()

      Thread.CurrentThread.CurrentCulture = New CultureInfo("tr-TR")
      Console.WriteLine("Culture = {0}", _
                        Thread.CurrentThread.CurrentCulture.DisplayName)
      Console.WriteLine("(file == FILE) = {0}", _ 
                        fileUrl.StartsWith("FILE", True, Nothing))
   End Sub
End Module
' The example displays the following output:
'       Culture = English (United States)
'       (file == FILE) = True
'       
'       Culture = Turkish (Turkey)
'       (file == FILE) = False
```

Esta comparación podría producir problemas importantes si la referencia cultural se usa involuntariamente en configuraciones que afectan a la seguridad, como en el ejemplo siguiente. Una llamada al método como `IsFileURI("file:")` devuelve `true` si la referencia cultural actual es inglés de EE. U.U., pero `false` si la referencia cultural actual es el turco. Así, en los sistemas turcos, alguien podría sortear las medidas de seguridad que bloquean el acceso a los URI sin distinción entre mayúsculas y minúsculas que comienzan con "FILE":.

```csharp
public static bool IsFileURI(String path) 
{
   return path.StartsWith("FILE:", true, null);
}
```

```vb
Public Shared Function IsFileURI(path As String) As Boolean 
   Return path.StartsWith("FILE:", True, Nothing)
End Function
```

En este caso, puesto que "file:" debe interpretarse como un identificador no lingüístico e independiente de la referencia cultural, el código se debe escribir como se muestra en el ejemplo siguiente.

```csharp
public static bool IsFileURI(string path) 
{
   return path.StartsWith("FILE:", StringComparison.OrdinalIgnoreCase);
}
```

```vb
Public Shared Function IsFileURI(path As String) As Boolean 
    Return path.StartsWith("FILE:", StringComparison.OrdinalIgnoreCase)
End Function
```

## <a name="ordinal-string-operations"></a>Operaciones de cadenas ordinales

Al especificar los valores [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) o [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) en una llamada al método, se indica una comparación no lingüística en la que se omiten las características de los lenguajes naturales. Los métodos que se invocan con estos valores [StringComparison](xref:System.StringComparison) basan las decisiones sobre las operaciones con cadenas en simples comparaciones de bytes en lugar de usos de mayúsculas y minúsculas o tablas de equivalencia parametrizadas por referencia cultural. En la mayoría de los casos, este enfoque se adapta mejor a la interpretación prevista de cadenas, y el código es más rápido y más confiable. 

Las comparaciones ordinales son comparaciones de cadenas en las que cada byte de cada cadena se compara sin ninguna interpretación lingüística; por ejemplo, "windows" no coincide con "Windows". Use esta comparación cuando el contexto indique que las cadenas deben coincidir exactamente o exija una directiva de coincidencia conservadora. Además, la comparación ordinal es la operación de comparación más rápida porque no aplica ninguna regla lingüística al determinar un resultado.

En .NET, las cadenas pueden contener caracteres nulos incrustados. Una de las diferencias más claras entre la comparación ordinal y dependiente de la referencia cultural (incluyendo las comparaciones que usan la referencia cultural de todos los idiomas) tiene que ver con el control de caracteres nulos incrustados en una cadena. Estos caracteres se omiten cuando usa métodos [String](xref:System.String) `Compare` y [String](xref:System.String) `Equals` para realizar comparaciones dependientes de la referencia cultural (incluidas las comparaciones que usan la referencia cultural de todos los idiomas). Por tanto, en las comparaciones dependientes de la referencia cultural, las cadenas que contienen caracteres nulos incrustados pueden considerarse iguales que las cadenas que no los contienen. 

> [!IMPORTANT]
> Aunque los métodos de comparación de cadenas hacen caso omiso de los caracteres nulos incrustados, los métodos de búsqueda de cadenas como [String.Contains](xref:System.String.Contains(System.String)), [String.EndsWith](xref:System.String.EndsWith(System.String)), [String.IndexOf](xref:System.String.IndexOf(System.Char)), [String.LastIndexOf](xref:System.String.LastIndexOf(System.String)) y [String.StartsWith](xref:System.String.StartsWith(System.String)) sí los tienen en cuenta. 

En el ejemplo siguiente se realiza una comparación dependiente de la referencia cultural de la cadena "Aa" con una cadena similar que contiene varios caracteres nulos incrustados entre "A" y "a", y se muestra cómo las dos cadenas se consideran iguales. 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string str1 = "Aa";
      string str2 = "A" + new String('\u0000', 3) + "a";
      Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", 
                        str1, ShowBytes(str1), str2, ShowBytes(str2));
      Console.WriteLine("   With String.Compare:");
      Console.WriteLine("      Current Culture: {0}", 
                        String.Compare(str1, str2, StringComparison.CurrentCulture));
      Console.WriteLine("      Invariant Culture: {0}", 
                        String.Compare(str1, str2, StringComparison.InvariantCulture));

      Console.WriteLine("   With String.Equals:");
      Console.WriteLine("      Current Culture: {0}", 
                        String.Equals(str1, str2, StringComparison.CurrentCulture));
      Console.WriteLine("      Invariant Culture: {0}", 
                        String.Equals(str1, str2, StringComparison.InvariantCulture));
   }

   private static string ShowBytes(string str)
   {
      string hexString = String.Empty;
      for (int ctr = 0; ctr < str.Length; ctr++)
      {
         string result = String.Empty;
         result = Convert.ToInt32(str[ctr]).ToString("X4");
         result = " " + result.Substring(0,2) + " " + result.Substring(2, 2);
         hexString += result;
      }
      return hexString.Trim();
   }
}
// The example displays the following output:
//    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
//       With String.Compare:
//          Current Culture: 0
//          Invariant Culture: 0
//       With String.Equals:
//          Current Culture: True
//          Invariant Culture: True
```

```vb
Module Example
   Public Sub Main()
      Dim str1 As String = "Aa"
      Dim str2 As String = "A" + New String(Convert.ToChar(0), 3) + "a"
      Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", _
                        str1, ShowBytes(str1), str2, ShowBytes(str2))
      Console.WriteLine("   With String.Compare:")
      Console.WriteLine("      Current Culture: {0}", _
                        String.Compare(str1, str2, StringComparison.CurrentCulture))
      Console.WriteLine("      Invariant Culture: {0}", _
                        String.Compare(str1, str2, StringComparison.InvariantCulture))

      Console.WriteLine("   With String.Equals:")
      Console.WriteLine("      Current Culture: {0}", _
                        String.Equals(str1, str2, StringComparison.CurrentCulture))
      Console.WriteLine("      Invariant Culture: {0}", _
                        String.Equals(str1, str2, StringComparison.InvariantCulture))
   End Sub

   Private Function ShowBytes(str As String) As String
      Dim hexString As String = String.Empty
      For ctr As Integer = 0 To str.Length - 1
         Dim result As String = String.Empty
         result = Convert.ToInt32(str.Chars(ctr)).ToString("X4")
         result = " " + result.Substring(0,2) + " " + result.Substring(2, 2)
         hexString += result
      Next
      Return hexString.Trim()
   End Function
End Module
```

Sin embargo, las cadenas no se consideran iguales cuando usa la comparación ordinal, como se muestra en el ejemplo siguiente.

```csharp
Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", 
                  str1, ShowBytes(str1), str2, ShowBytes(str2));
Console.WriteLine("   With String.Compare:");
Console.WriteLine("      Ordinal: {0}", 
                  String.Compare(str1, str2, StringComparison.Ordinal));

Console.WriteLine("   With String.Equals:");
Console.WriteLine("      Ordinal: {0}", 
                  String.Equals(str1, str2, StringComparison.Ordinal));
// The example displays the following output:
//    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
//       With String.Compare:
//          Ordinal: 97
//       With String.Equals:
//          Ordinal: False
```

```vb
Console.WriteLine("Comparing '{0}' ({1}) and '{2}' ({3}):", _
                  str1, ShowBytes(str1), str2, ShowBytes(str2))
Console.WriteLine("   With String.Compare:")
Console.WriteLine("      Ordinal: {0}", _
                  String.Compare(str1, str2, StringComparison.Ordinal))

Console.WriteLine("   With String.Equals:")
Console.WriteLine("      Ordinal: {0}", _
                  String.Equals(str1, str2, StringComparison.Ordinal))
' The example displays the following output:
'    Comparing 'Aa' (00 41 00 61) and 'A   a' (00 41 00 00 00 00 00 00 00 61):
'       With String.Compare:
'          Ordinal: 97
'       With String.Equals:
'          Ordinal: False
```

Las comparaciones ordinales sin distinción entre mayúsculas y minúsculas son el siguiente enfoque más conservador. Estas comparaciones omiten la mayor parte del uso de mayúsculas y minúsculas; por ejemplo, "windows" coincide con "Windows". A la hora de tratar con caracteres ASCII, esta directiva es equivalente a [StringComparison.Ordinal](xref:System.StringComparison.Ordinal), salvo que omite el uso de mayúsculas y minúsculas habitual de ASCII. Por tanto, cualquier carácter de [A, Z] (\u0041-\u005A) coincide con el carácter correspondiente de [a, z] (\u0061-\007A). El uso de mayúsculas y minúsculas fuera del intervalo ASCII emplea las tablas de la referencia cultural de todos los idiomas. Por tanto, la siguiente comparación:

```csharp
String.Compare(strA, strB, StringComparison.OrdinalIgnoreCase);
```

```vb
String.Compare(strA, strB, StringComparison.OrdinalIgnoreCase)
```

es equivalente a esta comparación (pero más rápida): 

```csharp
String.Compare(strA.ToUpperInvariant(), strB.ToUpperInvariant(), 
               StringComparison.Ordinal);
```

```vb
String.Compare(strA.ToUpperInvariant(), strB.ToUpperInvariant(), 
               StringComparison.Ordinal)
```

Estas comparaciones siguen siendo muy rápidas.

Tanto [StringComparison.Ordinal](xref:System.StringComparison.Ordinal) como [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) usan los valores binarios directamente y son más adecuados para la búsqueda de coincidencias. Si no sabe con seguridad qué configuración de comparación debe emplear, use uno de estos dos valores. Sin embargo, puesto que realizan una comparación byte a byte, no ordenan según un criterio de ordenación lingüístico (como un diccionario de inglés) sino según un criterio de ordenación binario. Los resultados pueden parecer extraños en la mayoría de los contextos si se muestran a los usuarios.

La semántica ordinal es el valor predeterminado para las sobrecargas de [String](xref:System.String) `Equals` que no incluyen un argumento [StringComparison](xref:System.StringComparison) (incluido el operador de igualdad). En cualquier caso, se recomienda llamar a una sobrecarga que tenga un parámetro [StringComparison](xref:System.StringComparison).

### <a name="string-operations-that-use-the-invariant-culture"></a>Operaciones de cadenas que usan la referencia cultural de todos los idiomas

Las comparaciones con la referencia cultural de todos los idiomas usan la propiedad [CompareInfo](xref:System.Globalization.CompareInfo) devuelta por la propiedad estática [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture). Este comportamiento es igual en todos los sistemas; traduce cualquier carácter que esté fuera de su intervalo en lo que cree que son caracteres invariables equivalentes. Esta directiva puede ser útil para mantener un conjunto de comportamientos de las cadenas en distintas referencias culturales, pero a menudo proporciona resultados inesperados.

Las comparaciones sin distinción entre mayúsculas y minúsculas con la referencia cultural de todos los idiomas usan también la propiedad estática [CompareInfo](xref:System.Globalization.CompareInfo) devuelta por la propiedad estática [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) para obtener información de comparación. Cualquier diferencia en el uso de mayúsculas y minúsculas entre estos caracteres traducidos se pasa por alto.

El objeto [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) hace que un método [String](xref:System.String) `Compare` interprete ciertos conjuntos de caracteres como equivalentes. Por ejemplo, la siguiente equivalencia es válida en la referencia cultural de todos los idiomas:

InvariantCulture: a + ̊ = å

El carácter letra latina A minúscula "a" (\u0061), cuando está junto al carácter anillo superior combinable "+ " ̊" (\u030a), se interpreta como el carácter letra latina minúscula A con anillo superior "å" (\u00e5). Como se muestra en el ejemplo siguiente, este comportamiento difiere de la comparación ordinal.

```csharp
string separated = "\u0061\u030a";
string combined = "\u00e5";

Console.WriteLine("Equal sort weight of {0} and {1} using InvariantCulture: {2}",
                  separated, combined, 
                  String.Compare(separated, combined, 
                                 StringComparison.InvariantCulture) == 0);

Console.WriteLine("Equal sort weight of {0} and {1} using Ordinal: {2}",
                  separated, combined,
                  String.Compare(separated, combined, 
                                 StringComparison.Ordinal) == 0);
// The example displays the following output:
//    Equal sort weight of a° and å using InvariantCulture: True
//    Equal sort weight of a° and å using Ordinal: False 
```

```vb
Dim separated As String = ChrW(&h61) + ChrW(&h30a)
Dim combined As String = ChrW(&he5)

Console.WriteLine("Equal sort weight of {0} and {1} using InvariantCulture: {2}", _
                  separated, combined, _
                  String.Compare(separated, combined, _ 
                                 StringComparison.InvariantCulture) = 0)

Console.WriteLine("Equal sort weight of {0} and {1} using Ordinal: {2}", _
                  separated, combined, _
                  String.Compare(separated, combined, _
                                 StringComparison.Ordinal) = 0)
' The example displays the following output:
'    Equal sort weight of a° and å using InvariantCulture: True
'    Equal sort weight of a° and å using Ordinal: False
```

A la hora de interpretar nombres de archivo, cookies u otros elementos donde pueda aparecer una combinación como "å", las comparaciones ordinales siguen ofreciendo el comportamiento más transparente y adecuado.

En conjunto, la referencia cultural de todos los idiomas tiene muy pocas propiedades que la hagan útil para la comparación. Realiza la comparación de manera lingüísticamente pertinente, lo que le impide garantizar una equivalencia simbólica completa, pero no es la opción ideal para la presentación en cualquier referencia cultural. Por ejemplo, si un archivo de datos grande que contiene una lista de identificadores ordenados para su presentación acompaña una aplicación, al agregar datos a esta lista se necesitaría realizar una inserción con ordenación de estilo invariable.

## <a name="choosing-a-stringcomparison-member-for-your-method-call"></a>Elegir un miembro StringComparison para la llamada al método

En la tabla siguiente, se describe la asignación del contexto de cadena semántico a un miembro de la enumeración de [StringComparison](xref:System.StringComparison).

Datos | Comportamiento | Valor de System.StringComparison correspondiente
---- | -------- | -------------------------------------------
Identificadores internos con distinción entre mayúsculas y minúsculas, identificadores con distinción entre mayúsculas y minúsculas en estándares como XML y HTTP, o configuraciones relacionadas con la seguridad con distinción entre mayúsculas y minúsculas. | Identificador no lingüístico, donde los bytes coinciden exactamente. | [StringComparison.Ordinal](xref:System.StringComparison.Ordinal)
Identificadores internos sin distinción entre mayúsculas y minúsculas, identificadores sin distinción entre mayúsculas y minúsculas en estándares como XML y HTTP, rutas de acceso a archivos, claves y valores del Registro, variables del entorno, identificadores de recursos (por ejemplo, nombres de identificadores) o configuraciones relacionadas con la seguridad sin distinción entre mayúsculas y minúsculas. | Un identificador no lingüístico, donde el uso de mayúsculas y minúsculas no es pertinente. | [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase)
Datos mostrados al usuario o la mayoría de los datos proporcionados por el usuario. | Datos que necesitan personalizaciones lingüísticas locales. | [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture) o [CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase)

## <a name="common-string-comparison-methods"></a>Métodos comunes de comparación de cadenas

En las secciones siguientes se describen los métodos que se usan con más frecuencia para la comparación de cadenas.

### <a name="stringcompare"></a>String.Compare

Interpretación predeterminada: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

Al ser la operación fundamental para la interpretación de cadenas, todas las instancias de estas llamadas al método se deben examinar para determinar si las cadenas se deben interpretar según la referencia cultural actual o se deben separar de la referencia cultural (simbólicamente). Normalmente, se trata del último caso y se debe usar en su lugar una comparación [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).

La clase [System.Globalization.CompareInfo](xref:System.Globalization.CompareInfo), devuelta por la propiedad [CultureInfo.CompareInfo](xref:System.Globalization.CultureInfo.CompareInfo), también incluye un método [Compare](xref:System.Globalization.CompareInfo.Compare(System.String,System.Int32,System.String,System.Int32,System.Globalization.CompareOptions)) que proporciona un gran número de opciones de coincidencia (ordinal, omitir el espacio en blanco, omitir el tipo de kana, etc.) por medio de la enumeración de marca [CompareOptions](xref:System.Globalization.CompareOptions). 

### <a name="stringcompareto"></a>String.CompareTo

Interpretación predeterminada: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

Este método no ofrece actualmente una sobrecarga que especifique un tipo [StringComparison](xref:System.StringComparison). Normalmente, es posible convertir este método al formato [String.Compare(String, String, StringComparison)](xref:System.String.Compare(System.String,System.String,System.StringComparison)) recomendado.

Los tipos que implementan interfaces [IComparable](xref:System.IComparable) e [IComparable&lt;T&gt;](xref:System.IComparable%601) implementan este método. Puesto que no ofrece la opción de un parámetro [StringComparison](xref:System.StringComparison), la implementación de tipos suele permitir al usuario especificar [StringComparer](xref:System.StringComparer) en su constructor. En el ejemplo siguiente, se define una clase `FileName` cuyo constructor de clase incluye un parámetro [StringComparer](xref:System.StringComparer). Este objeto [StringComparer](xref:System.StringComparer) se usa entonces en el método `FileName.CompareTo`.

```csharp
using System;

public class FileName : IComparable
{
   string fname;
   StringComparer comparer; 

   public FileName(string name, StringComparer comparer)
   {
      if (String.IsNullOrEmpty(name))
         throw new ArgumentNullException("name");

      this.fname = name;

      if (comparer != null)
         this.comparer = comparer;
      else
         this.comparer = StringComparer.OrdinalIgnoreCase;
   }

   public string Name
   {
      get { return fname; }
   }

   public int CompareTo(object obj)
   {
      if (obj == null) return 1;

      if (! (obj is FileName))
         return comparer.Compare(this.fname, obj.ToString());
      else
         return comparer.Compare(this.fname, ((FileName) obj).Name);
   }
}
```

```vb
Public Class FileName : Implements IComparable
   Dim fname As String
   Dim comparer As StringComparer 

   Public Sub New(name As String, comparer As StringComparer)
      If String.IsNullOrEmpty(name) Then
         Throw New ArgumentNullException("name")
      End If

      Me.fname = name

      If comparer IsNot Nothing Then
         Me.comparer = comparer
      Else
         Me.comparer = StringComparer.OrdinalIgnoreCase
      End If      
   End Sub

   Public ReadOnly Property Name As String
      Get
         Return fname
      End Get   
   End Property

   Public Function CompareTo(obj As Object) As Integer _
          Implements IComparable.CompareTo
      If obj Is Nothing Then Return 1

      If Not TypeOf obj Is FileName Then
         obj = obj.ToString()
      Else
         obj = CType(obj, FileName).Name
      End If         
      Return comparer.Compare(Me.fname, obj)
   End Function
End Class
```

### <a name="stringequals"></a>String.Equals

Interpretación predeterminada: [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).

La clase [String](xref:System.String) le permite comprobar la igualdad al llamar a las sobrecargas de método estático o de instancia `Equals`, o al usar el operador de igualdad estático. Las sobrecargas y el operador usan la comparación ordinal de forma predeterminada. En cambio, todavía sigue siendo recomendable llamar a una sobrecarga que especifique explícitamente el tipo [StringComparison](xref:System.StringComparison) aunque quiera realizar una comparación ordinal; esto facilita la búsqueda de cierta interpretación de la cadena en el código. 

### <a name="stringtoupper-and-stringtolower"></a>String.ToUpper y String.ToLower

Interpretación predeterminada: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

Debe tener cuidado al usar estos métodos, ya que forzar que una cadena esté en mayúsculas o en minúsculas se usa a menudo como una pequeña normalización para comparar cadenas independientemente del uso de mayúsculas y minúsculas. En tal caso, considere la posibilidad de emplear una comparación sin distinción entre mayúsculas y minúsculas. 

Los métodos [String.ToUpperInvariant](xref:System.String.ToUpperInvariant) y [String.ToLowerInvariant](xref:System.String.ToLowerInvariant) también están disponibles. [ToUpperInvariant](xref:System.String.ToUpperInvariant) es la manera estándar de normalizar el uso de mayúsculas y minúsculas. Las comparaciones realizadas mediante [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) tienen un comportamiento que es la composición de dos llamadas: llamar a [ToUpperInvariant](xref:System.String.ToUpperInvariant) en ambos argumentos de cadena y realizar una comparación mediante [StringComparison.Ordinal](xref:System.StringComparison.Ordinal).

También hay sobrecargas para convertir a mayúsculas y minúsculas en una referencia cultural concreta, al pasar al método un objeto [CultureInfo](xref:System.Globalization.CultureInfo) que representa esa referencia cultural.

### <a name="chartoupper-and-chartolower"></a>Char.ToUpper y Char.ToLower

Interpretación predeterminada: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

Estos métodos funcionan de manera similar a los métodos [String.ToUpper](xref:System.String.ToUpper) y [String.ToLower](xref:System.String.ToLower) descritos en la sección anterior.

### <a name="stringstartswith-and-stringendswith"></a>String.StartsWith y String.EndsWith

Interpretación predeterminada: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

De forma predeterminada, estos dos métodos realizan una comparación dependiente de la referencia cultural.

### <a name="stringindexof-and-stringlastindexof"></a>String.IndexOf y String.LastIndexOf

Interpretación predeterminada: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

No hay coherencia en cómo las sobrecargas predeterminadas de estos métodos realizan las comparaciones. Todos los métodos [String](xref:System.String) `IndexOf` y [String](xref:System.String) `LastIndexOf` que incluyen un parámetro [Char](xref:System.Char) realizan una comparación ordinal, pero los métodos [String](xref:System.String) `IndexOf` y [String`](xref:System.String) `LastIndexOf` predeterminados que incluyen un parámetro [String](xref:System.String) realizan una comparación dependiente de la referencia cultural. 

Si llama al método ` `IndexOf` or `LastIndexOf` y le pasa una cadena para ubicar en la instancia actual, se recomienda llamar a una sobrecarga que especifique explícitamente el tipo [StringComparison](xref:System.StringComparison). Las sobrecargas que incluyen un argumento [Char](xref:System.Char) no le permiten especificar un tipo [StringComparison](xref:System.StringComparison).

## <a name="methods-that-perform-string-comparison-indirectly"></a>Métodos que realizan la comparación de cadenas indirectamente

Algunos métodos sin cadenas que tienen la comparación de cadenas como operación fundamental usan el tipo [StringComparer](xref:System.StringComparer). La clase [StringComparer](xref:System.StringComparer) incluye cuatro propiedades estáticas que devuelven instancias de [StringComparer](xref:System.StringComparer) cuyos métodos `Compare` realizan los siguientes tipos de comparaciones de cadenas:

* Comparaciones de cadenas dependientes de la referencia cultural usando la referencia cultural actual. La propiedad [StringComparer.CurrentCulture](xref:System.StringComparer.CurrentCulture) devuelve este objeto [StringComparer](xref:System.StringComparer).

* Comparaciones sin distinción entre mayúsculas y minúsculas usando la referencia cultural actual. La propiedad [StringComparer.CurrentCultureIgnoreCase](xref:System.StringComparer.CurrentCultureIgnoreCase) devuelve este objeto [StringComparer](xref:System.StringComparer).

* Comparación ordinal. La propiedad [StringComparer.Ordinal](xref:System.StringComparer.Ordinal) devuelve este objeto [StringComparer](xref:System.StringComparer). 

* Comparación ordinal sin distinción entre mayúsculas y minúsculas. La propiedad [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase) devuelve este objeto [StringComparer](xref:System.StringComparer).

### <a name="arraysort-and-arraybinarysearch"></a>Array.Sort y Array.BinarySearch

Interpretación predeterminada: [StringComparison.CurrentCulture](xref:System.StringComparison.CurrentCulture).

Cuando se almacenan datos en una colección, o cuando se leen datos almacenados de un archivo o una base de datos en una colección, el cambio de la referencia cultural actual puede invalidar los valores invariables de la colección. El método [Array.BinarySearch](xref:System.Array.BinarySearch(System.Array,System.Object)) supone que los elementos de la matriz que se van a buscar ya están ordenados. Para ordenar cualquier elemento de cadena de la matriz, el método [Array.Sort](xref:System.Array.Sort(System.Array)) llama al método [String] `Compare` para ordenar los elementos individuales. El uso de un comparador dependiente de la referencia cultural puede ser peligroso si la referencia cultural cambia desde que se ordena la matriz hasta que se busca en su contenido. Por ejemplo, en el código siguiente, el almacenamiento y la recuperación funcionan en el comparador proporcionado implícitamente por la propiedad `Thread.CurrentThread.CurrentCulture`. Si la referencia cultural puede cambiar entre las llamadas a `StoreNames` y `DoesNameExist`, y especialmente si el contenido de la matriz se conserva en alguna parte entre las dos llamadas al método, se puede producir un error en la búsqueda binaria. 

```csharp
// Incorrect.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names); // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name) >= 0);  // Line B.
}
```

```vb
' Incorrect.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names)          ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name) >= 0      ' Line B.
End Function
```

Aparece una variación recomendada en el ejemplo siguiente, que usa el mismo método de comparación ordinal (independiente de la referencia cultural) para ordenar y buscar en la matriz. El código cambiado se refleja en las líneas etiquetadas como `Line A` y `Line B` en los dos ejemplos.

```csharp
// Correct.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names, StringComparer.Ordinal);  // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name, StringComparer.Ordinal) >= 0);  // Line B.
}
```

```vb
' Correct.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names, StringComparer.Ordinal)           ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name, StringComparer.Ordinal) >= 0      ' Line B.
End Function
```

Si estos datos se conservan y mueven entre distintas referencias culturales, y se usa la ordenación para presentar estos datos al usuario, es mejor usar `StringComparison.InvariantCulture`, que funciona lingüísticamente para obtener una mejor salida para el usuario pero no se ve afectado por los cambios en la referencia cultural. En el ejemplo siguiente se modifican los dos ejemplos anteriores para usar la referencia cultural de todos los idiomas con el fin de ordenar y buscar en la matriz.

```csharp
// Correct.
string []storedNames;

public void StoreNames(string [] names)
{
   int index = 0;
   storedNames = new string[names.Length];

   foreach (string name in names)
   {
      this.storedNames[index++] = name;
   }

   Array.Sort(names, StringComparer.InvariantCulture);  // Line A.
}

public bool DoesNameExist(string name)
{
   return (Array.BinarySearch(this.storedNames, name, StringComparer.InvariantCulture) >= 0);  // Line B.
}
```

```vb
' Correct.
Dim storedNames() As String

Public Sub StoreNames(names() As String)
   Dim index As Integer = 0
   ReDim storedNames(names.Length - 1)

   For Each name As String In names
      Me.storedNames(index) = name
      index+= 1
   Next

   Array.Sort(names, StringComparer.InvariantCulture)           ' Line A.
End Sub

Public Function DoesNameExist(name As String) As Boolean
   Return Array.BinarySearch(Me.storedNames, name, StringComparer.InvariantCulture) >= 0      ' Line B.
End Function
```

### <a name="collections-example-hashtable-constructor"></a>Ejemplo de colecciones: constructor de tabla hash

Al aplicar un algoritmo hash a las cadenas se proporciona un segundo ejemplo de una operación que se ve afectada por la forma en que se comparan las cadenas. 

En el ejemplo siguiente, se crea una instancia de un objeto [Hashtable](xref:System.Collections.Hashtable) al pasarle el objeto [StringComparer](xref:System.StringComparer) devuelto por la propiedad [StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase). Puesto que una clase [StringComparer](xref:System.StringComparer) que se deriva de [StringComparer](xref:System.StringComparer) implementa la interfaz [IEqualityComparer](xref:System.Collections.IEqualityComparer), su método [GetHashCode](xref:System.Collections.IEqualityComparer) se usa para calcular el código hash de cadenas de la tabla hash.

```csharp
const int initialTableCapacity = 100;
Hashtable h;

public void PopulateFileTable(string directory)
{
   h = new Hashtable(initialTableCapacity, 
                     StringComparer.OrdinalIgnoreCase);

   foreach (string file in Directory.GetFiles(directory))
         h.Add(file, File.GetCreationTime(file));
}

public void PrintCreationTime(string targetFile)
{
   Object dt = h[targetFile];
   if (dt != null)
   {
      Console.WriteLine("File {0} was created at time {1}.",
         targetFile, 
         (DateTime) dt);
   }
   else
   {
      Console.WriteLine("File {0} does not exist.", targetFile);
   }
}
```

```vb
Const initialTableCapacity As Integer = 100
Dim h As Hashtable

Public Sub PopulateFileTable(dir As String)
   h = New Hashtable(initialTableCapacity, _
                     StringComparer.OrdinalIgnoreCase)

   For Each filename As String In Directory.GetFiles(dir)
      h.Add(filename, File.GetCreationTime(filename))
   Next                        
End Sub

Public Sub PrintCreationTime(targetFile As String)
   Dim dt As Object = h(targetFile)
   If dt IsNot Nothing Then
      Console.WriteLine("File {0} was created at {1}.", _
         targetFile, _
         CDate(dt))
   Else
      Console.WriteLine("File {0} does not exist.", targetFile)
   End If
End Sub  
```

## <a name="displaying-and-persisting-formatted-data"></a>Mostrar y conservar datos con formato

Cuando muestre a los usuarios datos que no sean de cadena, como números, y fechas y horas, asígneles formato mediante la configuración de la referencia cultural del usuario. De manera predeterminada, el método [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) y los métodos `ToString` de los tipos numéricos y los tipos de fecha y hora usan la referencia cultural del subproceso actual para las operaciones de formato. Para especificar explícitamente que el método de formato debe usar la referencia cultural actual, puede llamar a una sobrecarga de un método de formato que tenga un parámetro provider, como [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) o [DateTime.ToString(IFormatProvider)](xref:System.DateTime.ToString(System.IFormatProvider)), y pasarle la propiedad [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture). 

Puede conservar datos que no son de cadena como datos binarios o como datos con formato. Si decide guardarlos como datos con formato, debe llamar a una sobrecarga del método de formato que incluya un parámetro *provider* y pasarle la propiedad [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture). La referencia cultural de todos los idiomas proporciona un formato coherente para los datos con formato que es independiente de la referencia cultural y del equipo. En cambio, si se conservan datos a los que se aplica formato con referencias culturales distintas de la referencia cultural de todos los idiomas, se presentan varias limitaciones: 

* Es probable que los datos no puedan usarse si se recuperan en un sistema que tiene una referencia cultural distinta, o si el usuario del sistema actual cambia la referencia cultural actual e intenta recuperar los datos. 

* Las propiedades de una referencia cultural en un equipo específico pueden diferir de los valores estándar. En cualquier momento, un usuario puede personalizar la configuración de visualización que depende de la cultural. Debido a esto, es posible que los datos con formato que se guardan en un sistema no sean legibles después de que el usuario personalice la configuración de la referencia cultural. Es posible que la portabilidad de los datos con formato entre equipos sea incluso más limitada. 

* Las normas internacionales, regionales o nacionales que rigen el formato de los números o las fechas y horas cambian con el tiempo, y estos cambios se incorporan en las actualizaciones de los sistemas operativos. Cuando cambian las convenciones de formato, los datos a los que se aplicó formato usando las convenciones anteriores pueden llegar a ser ilegibles. 

En el ejemplo siguiente se muestra la portabilidad limitada que se deriva de usar el formato dependiente de la referencia cultural para conservar los datos. En el ejemplo se guarda una matriz de valores de fecha y hora en un archivo. Se les da formato con las convenciones de la referencia cultural Inglés (Estados Unidos). Después de que la aplicación cambie la referencia cultural del subproceso actual a Francés (Suiza), intenta leer los valores guardados usando las convenciones de formato de la referencia cultural actual. El intento de leer dos de los elementos de datos genera una excepción [FormatException](xref:System.FormatException) y la matriz de fechas ahora contiene dos elementos incorrectos que son iguales a [MinValue](xref:System.DateTime.MinValue). 

```csharp
using System;
using System.Globalization;
using System.IO;
using System.Text;
using System.Threading;

public class Example
{
   private static string filename = @".\dates.dat";

   public static void Main()
   {
      DateTime[] dates = { new DateTime(1758, 5, 6, 21, 26, 0), 
                           new DateTime(1818, 5, 5, 7, 19, 0), 
                           new DateTime(1870, 4, 22, 23, 54, 0),  
                           new DateTime(1890, 9, 8, 6, 47, 0), 
                           new DateTime(1905, 2, 18, 15, 12, 0) }; 
      // Write the data to a file using the current culture.
      WriteData(dates);
      // Change the current culture.
      Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture("fr-CH");
      // Read the data using the current culture.
      DateTime[] newDates = ReadData();
      foreach (var newDate in newDates)
         Console.WriteLine(newDate.ToString("g"));
   }

   private static void WriteData(DateTime[] dates) 
   {
      StreamWriter sw = new StreamWriter(filename, false, Encoding.UTF8);    
      for (int ctr = 0; ctr < dates.Length; ctr++) {
         sw.Write("{0}", dates[ctr].ToString("g", CultureInfo.CurrentCulture));
         if (ctr < dates.Length - 1) sw.Write("|");   
      }      
      sw.Close();
   }

   private static DateTime[] ReadData() 
   {
      bool exceptionOccurred = false;

      // Read file contents as a single string, then split it.
      StreamReader sr = new StreamReader(filename, Encoding.UTF8);
      string output = sr.ReadToEnd();
      sr.Close();   

      string[] values = output.Split( new char[] { '|' } );
      DateTime[] newDates = new DateTime[values.Length]; 
      for (int ctr = 0; ctr < values.Length; ctr++) {
         try {
            newDates[ctr] = DateTime.Parse(values[ctr], CultureInfo.CurrentCulture);
         }
         catch (FormatException) {
            Console.WriteLine("Failed to parse {0}", values[ctr]);
            exceptionOccurred = true;
         }
      }      
      if (exceptionOccurred) Console.WriteLine();
      return newDates;
   }
}
// The example displays the following output:
//       Failed to parse 4/22/1870 11:54 PM
//       Failed to parse 2/18/1905 3:12 PM
//       
//       05.06.1758 21:26
//       05.05.1818 07:19
//       01.01.0001 00:00
//       09.08.1890 06:47
//       01.01.0001 00:00
//       01.01.0001 00:00
```

```vb
Imports System.Globalization
Imports System.IO
Imports System.Text
Imports System.Threading

Module Example
   Private filename As String = ".\dates.dat"

   Public Sub Main()
      Dim dates() As Date = { #5/6/1758 9:26PM#, #5/5/1818 7:19AM#, _ 
                              #4/22/1870 11:54PM#, #9/8/1890 6:47AM#, _ 
                              #2/18/1905 3:12PM# }
      ' Write the data to a file using the current culture.
      WriteData(dates)
      ' Change the current culture.
      Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture("fr-CH")
      ' Read the data using the current culture.
      Dim newDates() As Date = ReadData()
      For Each newDate In newDates
         Console.WriteLine(newDate.ToString("g"))
      Next
   End Sub

   Private Sub WriteData(dates() As Date)
      Dim sw As New StreamWriter(filename, False, Encoding.Utf8)    
      For ctr As Integer = 0 To dates.Length - 1
         sw.Write("{0}", dates(ctr).ToString("g", CultureInfo.CurrentCulture))
         If ctr < dates.Length - 1 Then sw.Write("|")   
      Next      
      sw.Close()
   End Sub

   Private Function ReadData() As Date()
      Dim exceptionOccurred As Boolean = False

      ' Read file contents as a single string, then split it.
      Dim sr As New StreamReader(filename, Encoding.Utf8)
      Dim output As String = sr.ReadToEnd()
      sr.Close()   

      Dim values() As String = output.Split( {"|"c } )
      Dim newDates(values.Length - 1) As Date 
      For ctr As Integer = 0 To values.Length - 1
         Try
            newDates(ctr) = DateTime.Parse(values(ctr), CultureInfo.CurrentCulture)
         Catch e As FormatException
            Console.WriteLine("Failed to parse {0}", values(ctr))
            exceptionOccurred = True
         End Try
      Next      
      If exceptionOccurred Then Console.WriteLine()
      Return newDates
   End Function
End Module
' The example displays the following output:
'       Failed to parse 4/22/1870 11:54 PM
'       Failed to parse 2/18/1905 3:12 PM
'       
'       05.06.1758 21:26
'       05.05.1818 07:19
'       01.01.0001 00:00
'       09.08.1890 06:47
'       01.01.0001 00:00
'       01.01.0001 00:00
'
```

En cambio, si reemplaza la propiedad [CultureInfo.CurrentCulture](xref:System.Globalization.CultureInfo.CurrentCulture) con [CultureInfo.InvariantCulture](xref:System.Globalization.CultureInfo.InvariantCulture) en las llamadas a [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) y [DateTime.Parse(String, IFormatProvider)](xref:System.DateTime.Parse(System.String,System.IFormatProvider)), los datos persistentes de fecha y hora se restauran correctamente, como se muestra en el siguiente resultado.

```
// 06.05.1758 21:26
// 05.05.1818 07:19
// 22.04.1870 23:54
// 08.09.1890 06:47
// 18.02.1905 15:12
```

## <a name="see-also"></a>Vea también

[Manipular cadenas](manipulating-strings.md)



<!--HONumber=Nov16_HO1-->


