---
title: Procedimientos recomendados con expresiones regulares
description: Procedimientos recomendados con expresiones regulares
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 096fd614-91bf-4296-be24-12f62b062294
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 00c7228c5cb906f41df5e60a318721008ecf0bb7

---

# <a name="best-practices-for-regular-expressions"></a>Procedimientos recomendados con expresiones regulares

El motor de expresiones regulares de .NET es una herramienta eficaz y completa que procesa texto basándose en coincidencias de patrones en lugar de comparar y buscar coincidencias con texto literal. En la mayoría de los casos, realiza la coincidencia de modelos de manera rápida y eficaz. Sin embargo, en algunos casos, puede parecer que el motor de expresiones regulares es muy lento. En casos extremos, incluso puede parecer que deja de responder mientras procesa una entrada relativamente pequeña a lo largo de las horas o incluso los días. 

En este tema se describen algunos de los procedimientos recomendados que los desarrolladores pueden adoptar para garantizar que sus expresiones regulares alcancen un rendimiento óptimo. Contiene las siguientes secciones:

* [Considerar el origen de entrada](#consider-the-input-source)

* [Controlar la creación de instancias de objeto correctamente](#handle-object-instantiation-appropriately)

* [Controlar el retroceso](#take-charge-of-backtracking)

* [Usar valores de tiempo de espera](#use-time-out-values)

* [Capturar solo cuando sea necesario](#capture-only-when-necessary)

* [Temas relacionados](#related-topics)

## <a name="consider-the-input-source"></a>Considerar el origen de entrada

En general, las expresiones regulares pueden aceptar dos tipos de datos de entrada: restringidos o sin restricciones. La entrada restringida es texto que se origina en una fuente conocida o confiable y sigue un formato predefinido. La entrada sin restricciones es texto que se origina en un origen no confiable, como un usuario web, y puede no seguir un formato predefinido o esperado.

Los patrones de expresiones regulares se suelen escribir para buscar coincidencias con entradas válidas. Es decir, los desarrolladores examinan el texto que desean buscar y escriben un patrón de expresión regular que coincida con él. A continuación, los desarrolladores determinan si este patrón necesita alguna corrección o algún procesamiento adicional probándolo con varios elementos de entrada válidos. Cuando el modelo coincide con todas las entradas válidas previstas, se declara que está listo para producción y se puede incluir en una aplicación comercial. Esto hace que un patrón de expresión regular sea adecuado para entradas restringidas coincidentes. Sin embargo, no es adecuado para datos de entrada sin restricciones coincidentes.

Para buscar coincidencias con datos de entrada sin restricciones, una expresión regular debe poder administrar eficazmente tres clases de texto:

• Texto que coincide con el patrón de expresión regular.

• Texto que no coincide con el patrón de expresión regular.

• Texto que casi coincide con el patrón de expresión regular.

El último tipo de texto es especialmente problemático para una expresión regular que se ha escrito para tratar datos de entrada restringidos. Si esa expresión regular también usa mucho [retroceso](backtracking.md), el motor de expresiones regulares puede dedicar una cantidad de tiempo excesiva (en algunos casos, muchas horas o días) procesando texto aparentemente inofensivo. 

> [!WARNING]
> En el ejemplo siguiente se utiliza una expresión regular que es propensa a un retroceso excesivo y que es probable que rechace direcciones de correo electrónico válidas. No debería utilizarse en una rutina de validación de correo electrónico. Si quiere una expresión regular que valide las direcciones de correo electrónico, consulte [Cómo: Comprobar si las cadenas tienen un formato de correo electrónico válido](verify-format.md). 


Por ejemplo, considere una expresión regular de uso muy frecuente pero sumamente problemática para validar el alias de una dirección de correo electrónico. Se escribe la expresión regular `^[0-9A-Z]([-.\w]*[0-9A-Z])*$` para procesar qué se considera una dirección de correo electrónico válida, que consta de un carácter alfanumérico seguido de cero o más caracteres que pueden ser alfanuméricos, puntos o guiones. La expresión regular debe finalizar con un carácter alfanumérico. Sin embargo, como se muestra en el ejemplo siguiente, aunque esta expresión regular trata la entrada válida fácilmente, su rendimiento es muy ineficaz cuando está procesando datos de entrada casi válidos.

```csharp
using System;
using System.Diagnostics;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      Stopwatch sw;    
      string[] addresses = { "AAAAAAAAAAA@contoso.com", 
                             "AAAAAAAAAAaaaaaaaaaa!@contoso.com" };
      // The following regular expression should not actually be used to 
      // validate an email address.
      string pattern = @"^[0-9A-Z]([-.\w]*[0-9A-Z])*$";
      string input; 

      foreach (var address in addresses) {
         string mailBox = address.Substring(0, address.IndexOf("@"));       
         int index = 0;
         for (int ctr = mailBox.Length - 1; ctr >= 0; ctr--) {
            index++;

            input = mailBox.Substring(ctr, index); 
            sw = Stopwatch.StartNew();
            Match m = Regex.Match(input, pattern, RegexOptions.IgnoreCase);
            sw.Stop();
            if (m.Success)
               Console.WriteLine("{0,2}. Matched '{1,25}' in {2}", 
                                 index, m.Value, sw.Elapsed);
            else                     
               Console.WriteLine("{0,2}. Failed  '{1,25}' in {2}", 
                                 index, input, sw.Elapsed);
         }
         Console.WriteLine();
      }
   }
}

// The example displays output similar to the following:
//     1. Matched '                        A' in 00:00:00.0007122
//     2. Matched '                       AA' in 00:00:00.0000282
//     3. Matched '                      AAA' in 00:00:00.0000042
//     4. Matched '                     AAAA' in 00:00:00.0000038
//     5. Matched '                    AAAAA' in 00:00:00.0000042
//     6. Matched '                   AAAAAA' in 00:00:00.0000042
//     7. Matched '                  AAAAAAA' in 00:00:00.0000042
//     8. Matched '                 AAAAAAAA' in 00:00:00.0000087
//     9. Matched '                AAAAAAAAA' in 00:00:00.0000045
//    10. Matched '               AAAAAAAAAA' in 00:00:00.0000045
//    11. Matched '              AAAAAAAAAAA' in 00:00:00.0000045
//    
//     1. Failed  '                        !' in 00:00:00.0000447
//     2. Failed  '                       a!' in 00:00:00.0000071
//     3. Failed  '                      aa!' in 00:00:00.0000071
//     4. Failed  '                     aaa!' in 00:00:00.0000061
//     5. Failed  '                    aaaa!' in 00:00:00.0000081
//     6. Failed  '                   aaaaa!' in 00:00:00.0000126
//     7. Failed  '                  aaaaaa!' in 00:00:00.0000359
//     8. Failed  '                 aaaaaaa!' in 00:00:00.0000414
//     9. Failed  '                aaaaaaaa!' in 00:00:00.0000758
//    10. Failed  '               aaaaaaaaa!' in 00:00:00.0001462
//    11. Failed  '              aaaaaaaaaa!' in 00:00:00.0002885
//    12. Failed  '             Aaaaaaaaaaa!' in 00:00:00.0005780
//    13. Failed  '            AAaaaaaaaaaa!' in 00:00:00.0011628
//    14. Failed  '           AAAaaaaaaaaaa!' in 00:00:00.0022851
//    15. Failed  '          AAAAaaaaaaaaaa!' in 00:00:00.0045864
//    16. Failed  '         AAAAAaaaaaaaaaa!' in 00:00:00.0093168
//    17. Failed  '        AAAAAAaaaaaaaaaa!' in 00:00:00.0185993
//    18. Failed  '       AAAAAAAaaaaaaaaaa!' in 00:00:00.0366723
//    19. Failed  '      AAAAAAAAaaaaaaaaaa!' in 00:00:00.1370108
//    20. Failed  '     AAAAAAAAAaaaaaaaaaa!' in 00:00:00.1553966
//    21. Failed  '    AAAAAAAAAAaaaaaaaaaa!' in 00:00:00.3223372
```

```vb
Imports System.Diagnostics
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim sw As Stopwatch    
      Dim addresses() As String = { "AAAAAAAAAAA@contoso.com", 
                                 "AAAAAAAAAAaaaaaaaaaa!@contoso.com" }
      ' The following regular expression should not actually be used to 
      ' validate an email address.
      Dim pattern As String = "^[0-9A-Z]([-.\w]*[0-9A-Z])*$"
      Dim input As String 

      For Each address In addresses
         Dim mailBox As String = address.Substring(0, address.IndexOf("@"))       
         Dim index As Integer = 0
         For ctr As Integer = mailBox.Length - 1 To 0 Step -1
            index += 1
            input = mailBox.Substring(ctr, index) 
            sw = Stopwatch.StartNew()
            Dim m As Match = Regex.Match(input, pattern, RegexOptions.IgnoreCase)
            sw.Stop()
            if m.Success Then
               Console.WriteLine("{0,2}. Matched '{1,25}' in {2}", 
                                 index, m.Value, sw.Elapsed)
            Else                     
               Console.WriteLine("{0,2}. Failed  '{1,25}' in {2}", 
                                 index, input, sw.Elapsed)
            End If                  
         Next
         Console.WriteLine()
      Next
   End Sub
End Module
' The example displays output similar to the following:
'     1. Matched '                        A' in 00:00:00.0007122
'     2. Matched '                       AA' in 00:00:00.0000282
'     3. Matched '                      AAA' in 00:00:00.0000042
'     4. Matched '                     AAAA' in 00:00:00.0000038
'     5. Matched '                    AAAAA' in 00:00:00.0000042
'     6. Matched '                   AAAAAA' in 00:00:00.0000042
'     7. Matched '                  AAAAAAA' in 00:00:00.0000042
'     8. Matched '                 AAAAAAAA' in 00:00:00.0000087
'     9. Matched '                AAAAAAAAA' in 00:00:00.0000045
'    10. Matched '               AAAAAAAAAA' in 00:00:00.0000045
'    11. Matched '              AAAAAAAAAAA' in 00:00:00.0000045
'    
'     1. Failed  '                        !' in 00:00:00.0000447
'     2. Failed  '                       a!' in 00:00:00.0000071
'     3. Failed  '                      aa!' in 00:00:00.0000071
'     4. Failed  '                     aaa!' in 00:00:00.0000061
'     5. Failed  '                    aaaa!' in 00:00:00.0000081
'     6. Failed  '                   aaaaa!' in 00:00:00.0000126
'     7. Failed  '                  aaaaaa!' in 00:00:00.0000359
'     8. Failed  '                 aaaaaaa!' in 00:00:00.0000414
'     9. Failed  '                aaaaaaaa!' in 00:00:00.0000758
'    10. Failed  '               aaaaaaaaa!' in 00:00:00.0001462
'    11. Failed  '              aaaaaaaaaa!' in 00:00:00.0002885
'    12. Failed  '             Aaaaaaaaaaa!' in 00:00:00.0005780
'    13. Failed  '            AAaaaaaaaaaa!' in 00:00:00.0011628
'    14. Failed  '           AAAaaaaaaaaaa!' in 00:00:00.0022851
'    15. Failed  '          AAAAaaaaaaaaaa!' in 00:00:00.0045864
'    16. Failed  '         AAAAAaaaaaaaaaa!' in 00:00:00.0093168
'    17. Failed  '        AAAAAAaaaaaaaaaa!' in 00:00:00.0185993
'    18. Failed  '       AAAAAAAaaaaaaaaaa!' in 00:00:00.0366723
'    19. Failed  '      AAAAAAAAaaaaaaaaaa!' in 00:00:00.1370108
'    20. Failed  '     AAAAAAAAAaaaaaaaaaa!' in 00:00:00.1553966
'    21. Failed  '    AAAAAAAAAAaaaaaaaaaa!' in 00:00:00.3223372
```

Como muestra el resultado del ejemplo, el motor de expresiones regulares procesa el alias válido de correo electrónico casi en el mismo intervalo de tiempo independientemente de su longitud. Por otra parte, cuando la dirección de correo electrónico casi válida tiene más de cinco caracteres, el tiempo de procesamiento se duplica aproximadamente por cada carácter de la cadena. Esto significa que una cadena casi válida de 28 caracteres tardaría más de una hora en procesarse y una cadena casi válida de 33 caracteres tardaría casi un día en procesarse. 

Como esta expresión regular se desarrolló teniendo en cuenta solamente el formato de entrada que había que hacer coincidir, no tiene en cuenta los datos de entrada que no coinciden con el patrón. A su vez, esto puede permitir que unos datos de entrada sin restricciones que casi coinciden con el patrón de expresión regular reduzcan considerablemente el rendimiento.

Para resolver este problema, puede hacer lo siguiente:

* A la hora de desarrollar un modelo, debe considerar cómo puede afectar el retroceso al rendimiento del motor de expresiones regulares, especialmente si la expresión regular está diseñada para procesar datos de entrada sin restricciones. Para obtener más información, consulte la sección [Controlar el retroceso](#take-charge-of-backtracking).

* Probar exhaustivamente la expresión regular usando datos de entrada no válidos y casi válidos, así como datos de entrada válidos. Para generar de forma aleatoria la entrada para una expresión regular determinada, puede usar [Rex](http://research.microsoft.com/en-us/projects/rex/), que es una herramienta de exploración de expresiones regulares de Microsoft Research.

## <a name="handle-object-instantiation-appropriately"></a>Controlar la creación de instancias de objeto correctamente

El núcleo del modelo de objetos de expresiones regulares de .NET es la clase [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex), que representa el motor de expresiones regulares. A menudo, el mayor factor único que afecta al rendimiento de las expresiones regulares es la manera en que se emplea el motor de [Regex](xref:System.Text.RegularExpressions.Regex). La definición de una expresión regular implica acoplar estrechamente el motor de expresiones regulares con un patrón de expresión regular. Ese proceso de acoplamiento es necesariamente costoso, tanto si consiste en crear una instancia de un objeto [Regex](xref:System.Text.RegularExpressions.Regex) al pasar a su constructor una expresión regular como en llamar a un método estático al pasarle el patrón de expresión regular junto con la cadena que se va a analizar.

Puede acoplar el motor de expresiones regulares con un determinado patrón de expresión regular y, a continuación, usar el motor para buscar coincidencias con texto de varias maneras:

* Puede llamar a un método estático de coincidencia de patrones como [Regex.Match(String, String)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String)). Para ello no es necesario crear instancias de un objeto de expresión regular.

* Puede crear instancias de un objeto [Regex](xref:System.Text.RegularExpressions.Regex) y llamar a una instancia de un método de coincidencia de patrones de una expresión regular interpretada. Este es el método predeterminado para enlazar el motor de expresiones regulares a un patrón de expresión regular. Se produce cuando se crea una instancia de un objeto [Regex](xref:System.Text.RegularExpressions.Regex) sin un argumento de opciones que incluya la marca [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled).

* Puede crear instancias de un objeto [Regex](xref:System.Text.RegularExpressions.Regex) y llamar a una instancia de un método de coincidencia de patrones de una expresión regular compilada. Los objetos de expresiones regulares representan patrones compilados cuando se crea una instancia de un objeto [Regex](xref:System.Text.RegularExpressions.Regex) con un argumento de opciones que incluye la marca [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled).

> [!IMPORTANT]
> El formato de la llamada al método (estático, interpretado o compilado) afecta al rendimiento si la misma expresión regular se usa repetidamente en llamadas a métodos o si una aplicación usa muchos objetos de expresiones regulares.
 
### <a name="static-regular-expressions"></a>Expresiones regulares estáticas

Se recomienda el uso de métodos de expresiones regulares estáticas como alternativa a crear repetidamente instancias de un objeto de expresión regular con la misma expresión regular. A diferencia de los patrones de expresiones regulares usados por los objetos de expresiones regulares, el motor de expresiones regulares almacena internamente en memoria caché los códigos de operación o el lenguaje intermedio de Microsoft (MSIL) compilado de los modelos empleados en las llamadas al método de instancia. 

Por ejemplo, puede llamar a un método para validar la entrada del usuario. En este ejemplo, un método denominado `IsValidCurrency` comprueba si el usuario ha escrito un símbolo de moneda seguido al menos de un dígito decimal. En el ejemplo siguiente se muestra una implementación muy poco eficaz del método `IsValidCurrency`. Tenga en cuenta que cada llamada al método vuelve a crear una instancia de un objeto [Regex](xref:System.Text.RegularExpressions.Regex) con el mismo patrón. Esto, a su vez, significa que el patrón de expresión regular se debe volver a compilar cada vez que se llama al método.

```csharp
using System;
using System.Text.RegularExpressions;

public class RegexLib
{
   public static bool IsValidCurrency(string currencyValue)
   {
      string pattern = @"\p{Sc}+\s*\d+";
      Regex currencyRegex = new Regex(pattern);
      return currencyRegex.IsMatch(currencyValue);
   }
}
```

```vb
Public Sub OKButton_Click(sender As Object, e As EventArgs) _ 
           Handles OKButton.Click

   If Not String.IsNullOrEmpty(sourceCurrency.Text) Then
      If RegexLib.IsValidCurrency(sourceCurrency.Text) Then
         PerformConversion()
      Else
         status.Text = "The source currency value is invalid."
      End If          
   End If
End Sub
```

Debe reemplazar este código ineficaz con una llamada al método estático [Regex.IsMatch(String, String)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String)). Esto elimina la necesidad de crear instancias de un objeto [Regex](xref:System.Text.RegularExpressions.Regex) cada vez que quiera llamar a un método de coincidencia de patrones y permite que el motor de expresiones regulares recupere una versión compilada de la expresión regular de su memoria caché.

```csharp
using System;
using System.Text.RegularExpressions;

public class RegexLib
{
   public static bool IsValidCurrency(string currencyValue)
   {
      string pattern = @"\p{Sc}+\s*\d+";
      return Regex.IsMatch(currencyValue, pattern); 
   }
}
```

```vb
Imports System.Text.RegularExpressions

Public Module RegexLib
   Public Function IsValidCurrency(currencyValue As String) As Boolean
      Dim pattern As String = "\p{Sc}+\s*\d+"
      Return Regex.IsMatch(currencyValue, pattern)
   End Function
End Module
```

De forma predeterminada, se almacenan en caché los 15 últimos patrones de expresiones regulares estáticas usados recientemente. En el caso de las aplicaciones que necesitan un mayor número de expresiones regulares estáticas almacenadas en caché, el tamaño de la memoria caché se puede ajustar al establecer la propiedad [Regex.CacheSize](xref:System.Text.RegularExpressions.Regex.CacheSize).

La expresión regular `\p{Sc}+\s*\d+` que se usa en este ejemplo comprueba que la cadena de entrada consta de un símbolo de moneda y al menos un dígito decimal. El patrón se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`\p{Sc}+` | Buscar coincidencias con uno o más caracteres de la categoría Símbolo Unicode, Moneda.
`\s*` | Busca coincidencias con cero o más caracteres de espacio en blanco.
`\d+` | Buscar coincidencias con uno o más dígitos decimales.
 
### <a name="interpreted-vs-compiled-regular-expressions"></a>Expresiones regulares interpretadas y compiladas

Se interpretan los patrones de expresiones regulares que no están enlazados al motor de expresiones regulares mediante la especificación de la opción [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled). Cuando se crea una instancia de un objeto de expresión regular, el motor de expresiones regulares convierte la expresión regular en un conjunto de códigos de operación. Cuando se llama a un método de instancia, el compilador JIT ejecuta y convierte a MSIL los códigos de operación. Del mismo modo, cuando se llama a un método estático de expresión regular y la expresión regular no se encuentra en la memoria caché, el motor de expresiones regulares convierte la expresión regular en un conjunto de códigos de operación y los almacena en memoria caché. A continuación, convierte estos códigos de operación a MSIL para que el compilador JIT pueda ejecutarlos. Las expresiones regulares interpretadas reducen el tiempo de inicio a costa de un tiempo de ejecución más lento. Por eso, son más adecuadas cuando la expresión regular se usa en un número reducido de llamadas a métodos o si el número exacto de llamadas a métodos de expresión regular es desconocido pero se espera que sea pequeño. A medida que aumenta el número de llamadas al método, la mejora de rendimiento del tiempo de inicio reducido queda oscurecida por una velocidad de ejecución más lenta.

Se compilan los patrones de expresiones regulares que están enlazados al motor de expresiones regulares mediante la especificación de la opción [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled). Esto significa que, cuando se crea una instancia de un objeto de expresión regular, o cuando se llama a un método estático de expresión regular y la expresión regular no se encuentra en la memoria caché, el motor de expresiones regulares convierte la expresión regular a un conjunto intermedio de códigos de operación que, a continuación, convierte a MSIL. Cuando se llama a un método, el compilador JIT ejecuta el código MSIL. A diferencia de las expresiones regulares interpretadas, las expresiones regulares compiladas aumentan el tiempo de inicio pero ejecutan más deprisa los métodos individuales de coincidencia de patrones. Por tanto, la ventaja de rendimiento resultante de compilar la expresión regular aumenta en proporción al número de métodos de expresiones regulares llamados.

En resumen, se recomienda usar expresiones regulares interpretadas al llamar a métodos de expresión regular con una expresión regular concreta con poca frecuencia relativamente. Debe usar expresiones regulares compiladas al llamar a métodos de expresión regular con una expresión regular concreta con relativa frecuencia. Es difícil determinar el umbral exacto en el que las velocidades de ejecución más lentas de las expresiones regulares interpretadas superan las mejoras de su menor tiempo de inicio, o el umbral en el que los tiempos de inicio más lentos de las expresiones regulares compiladas superan las mejoras de sus velocidades de ejecución más rápidas. Depende de diversos factores, como la complejidad de la expresión regular y los datos específicos que procesa. Para determinar si las expresiones regulares interpretadas o compiladas ofrecen el mejor rendimiento para el escenario de su aplicación concreta, puede usar la clase [Stopwatch](xref:System.Diagnostics.Stopwatch) para comparar sus tiempos de ejecución.

En el ejemplo siguiente, se compara el rendimiento de las expresiones regulares compiladas e interpretadas al leer las diez primeras frases y al leer todas las frases del texto The Financier de Theodore Dreiser. Como muestra el resultado del ejemplo, cuando solo se realizan diez llamadas a métodos de coincidencia de expresión regular, una expresión regular interpreta proporciona un rendimiento mejor que una expresión regular compilada. Sin embargo, una expresión regular compilada ofrece mejor rendimiento cuando se realiza un gran número de llamadas (en este caso, más de 13000). 

```csharp
using System;
using System.Diagnostics;
using System.IO;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]";
      Stopwatch sw;
      Match match;
      int ctr;

      StreamReader inFile = new StreamReader(@".\Dreiser_TheFinancier.txt");
      string input = inFile.ReadToEnd();
      inFile.Close();

      // Read first ten sentences with interpreted regex.
      Console.WriteLine("10 Sentences with Interpreted Regex:");
      sw = Stopwatch.StartNew();
      Regex int10 = new Regex(pattern, RegexOptions.Singleline);
      match = int10.Match(input);
      for (ctr = 0; ctr <= 9; ctr++) {
         if (match.Success)
            // Do nothing with the match except get the next match.
            match = match.NextMatch();
         else
            break;
      }
      sw.Stop();
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed);

      // Read first ten sentences with compiled regex.
      Console.WriteLine("10 Sentences with Compiled Regex:");
      sw = Stopwatch.StartNew();
      Regex comp10 = new Regex(pattern, 
                   RegexOptions.Singleline | RegexOptions.Compiled);
      match = comp10.Match(input);
      for (ctr = 0; ctr <= 9; ctr++) {
         if (match.Success)
            // Do nothing with the match except get the next match.
            match = match.NextMatch();
         else
            break;
      }
      sw.Stop();
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed);

      // Read all sentences with interpreted regex.
      Console.WriteLine("All Sentences with Interpreted Regex:");
      sw = Stopwatch.StartNew();
      Regex intAll = new Regex(pattern, RegexOptions.Singleline);
      match = intAll.Match(input);
      int matches = 0;
      while (match.Success) {
         matches++;
         // Do nothing with the match except get the next match.
         match = match.NextMatch();
      }
      sw.Stop();
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed);

      // Read all sentnces with compiled regex.
      Console.WriteLine("All Sentences with Compiled Regex:");
      sw = Stopwatch.StartNew();
      Regex compAll = new Regex(pattern, 
                      RegexOptions.Singleline | RegexOptions.Compiled);
      match = compAll.Match(input);
      matches = 0;
      while (match.Success) {
         matches++;
         // Do nothing with the match except get the next match.
         match = match.NextMatch();
      }
      sw.Stop();
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed);      
   }
}
// The example displays the following output:
//       10 Sentences with Interpreted Regex:
//          10 matches in 00:00:00.0047491
//       10 Sentences with Compiled Regex:
//          10 matches in 00:00:00.0141872
//       All Sentences with Interpreted Regex:
//          13,443 matches in 00:00:01.1929928
//       All Sentences with Compiled Regex:
//          13,443 matches in 00:00:00.7635869
//       
//       >compare1
//       10 Sentences with Interpreted Regex:
//          10 matches in 00:00:00.0046914
//       10 Sentences with Compiled Regex:
//          10 matches in 00:00:00.0143727
//       All Sentences with Interpreted Regex:
//          13,443 matches in 00:00:01.1514100
//       All Sentences with Compiled Regex:
//          13,443 matches in 00:00:00.7432921
```

```vb
Imports System.Diagnostics
Imports System.IO
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]"
      Dim sw As Stopwatch
      Dim match As Match
      Dim ctr As Integer

      Dim inFile As New StreamReader(".\Dreiser_TheFinancier.txt")
      Dim input As String = inFile.ReadToEnd()
      inFile.Close()

      ' Read first ten sentences with interpreted regex.
      Console.WriteLine("10 Sentences with Interpreted Regex:")
      sw = Stopwatch.StartNew()
      Dim int10 As New Regex(pattern, RegexOptions.SingleLine)
      match = int10.Match(input)
      For ctr = 0 To 9
         If match.Success Then
            ' Do nothing with the match except get the next match.
            match = match.NextMatch()
         Else
            Exit For
         End If
      Next
      sw.Stop()
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed)

      ' Read first ten sentences with compiled regex.
      Console.WriteLine("10 Sentences with Compiled Regex:")
      sw = Stopwatch.StartNew()
      Dim comp10 As New Regex(pattern, 
                   RegexOptions.SingleLine Or RegexOptions.Compiled)
      match = comp10.Match(input)
      For ctr = 0 To 9
         If match.Success Then
            ' Do nothing with the match except get the next match.
            match = match.NextMatch()
         Else
            Exit For
         End If
      Next
      sw.Stop()
      Console.WriteLine("   {0} matches in {1}", ctr, sw.Elapsed)

      ' Read all sentences with interpreted regex.
      Console.WriteLine("All Sentences with Interpreted Regex:")
      sw = Stopwatch.StartNew()
      Dim intAll As New Regex(pattern, RegexOptions.SingleLine)
      match = intAll.Match(input)
      Dim matches As Integer = 0
      Do While match.Success
         matches += 1
         ' Do nothing with the match except get the next match.
         match = match.NextMatch()
      Loop
      sw.Stop()
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed)

      ' Read all sentnces with compiled regex.
      Console.WriteLine("All Sentences with Compiled Regex:")
      sw = Stopwatch.StartNew()
      Dim compAll As New Regex(pattern, 
                     RegexOptions.SingleLine Or RegexOptions.Compiled)
      match = compAll.Match(input)
      matches = 0
      Do While match.Success
         matches += 1
         ' Do nothing with the match except get the next match.
         match = match.NextMatch()
      Loop
      sw.Stop()
      Console.WriteLine("   {0:N0} matches in {1}", matches, sw.Elapsed)      
   End Sub
End Module
' The example displays output like the following:
'       10 Sentences with Interpreted Regex:
'          10 matches in 00:00:00.0047491
'       10 Sentences with Compiled Regex:
'          10 matches in 00:00:00.0141872
'       All Sentences with Interpreted Regex:
'          13,443 matches in 00:00:01.1929928
'       All Sentences with Compiled Regex:
'          13,443 matches in 00:00:00.7635869
'       
'       >compare1
'       10 Sentences with Interpreted Regex:
'          10 matches in 00:00:00.0046914
'       10 Sentences with Compiled Regex:
'          10 matches in 00:00:00.0143727
'       All Sentences with Interpreted Regex:
'          13,443 matches in 00:00:01.1514100
'       All Sentences with Compiled Regex:
'          13,443 matches in 00:00:00.7432921
```

El patrón de expresión regular usado en el ejemplo, `\b(\w+((\r?\n)|,?\s))*\w+[.?:;!]`, se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`\b` | Iniciar la búsqueda de coincidencias en un límite de palabras.
`\w+` | Buscar coincidencias con uno o más caracteres alfabéticos.
`(\r?\n)|,?\s)` | Buscar una coincidencia con cero o un retorno de carro seguido de un carácter de nueva línea, o cero o una coma seguida de un carácter de espacio en blanco.
`(\w+((\r?\n)|,?\s))*` | Buscar coincidencias con cero o más apariciones de uno o más caracteres alfabéticos que van seguidos de cero o un retorno de carro y un carácter de nueva línea, o de cero o una coma seguida de un carácter de espacio en blanco.
`\w+` | Buscar coincidencias con uno o más caracteres alfabéticos.
`[.?:;!]` | Buscar una coincidencia con un punto, un signo de interrogación, dos puntos, punto y coma o un signo de exclamación.
 
## <a name="take-charge-of-backtracking"></a>Controlar el retroceso

Normalmente, el motor de expresiones regulares usa la progresión lineal para desplazarse a través de una cadena de entrada y compararla con un patrón de expresión regular. En cambio, cuando se usan cuantificadores indeterminados como __*__, **+** y **?** en un patrón de expresión regular, el motor de expresiones regulares puede abandonar una parte de las coincidencias parciales correctas y volver a un estado guardado previamente para buscar una coincidencia correcta de todo el patrón. Este proceso se denomina retroceso.

> [!NOTE]
> Para obtener más información sobre el retroceso, consulte [Detalles del comportamiento de expresiones regulares](regex-behavior.md) y [Retroceso en expresiones regulares](backtracking.md).
 
La compatibilidad con el retroceso aporta a las expresiones regulares eficacia y flexibilidad. También deja la responsabilidad de controlar el funcionamiento del motor de expresiones regulares en manos de los desarrolladores de expresiones regulares. Puesto que los desarrolladores no suelen ser conscientes de esta responsabilidad, su uso incorrecto del retroceso o su dependencia de un retroceso excesivo suele desempeñar el rol más significativo en la degradación del rendimiento de las expresiones regulares. En un escenario de caso peor, el tiempo de ejecución puede duplicarse por cada carácter adicional de la cadena de entrada. De hecho, usando excesivamente el retroceso, es fácil crear el equivalente en programación de un bucle infinito si la entrada coincide casi con el patrón de expresiones regulares; el motor de expresiones regulares puede tardar horas o incluso días en procesar una cadena de entrada relativamente corta.

A menudo, las aplicaciones sufren una reducción del rendimiento por usar el retroceso a pesar de que el retroceso no es esencial para una coincidencia. Por ejemplo, la expresión regular `\b\p{Lu}\w*\b` busca una coincidencia con todas las palabras que comienzan por un carácter en mayúsculas, como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`\b` | Iniciar la búsqueda de coincidencias en un límite de palabras.
`\p{Lu}` | Busca una coincidencia con un carácter en mayúsculas.
`\w*` | Buscar una coincidencia con cero o más caracteres alfabéticos.
`\b` | Finalizar la búsqueda de coincidencias en un límite de palabras.
 
Puesto que un límite de palabra no es igual, o un subconjunto de, que un carácter alfabético, no hay ninguna posibilidad de que el motor de expresiones regulares cruce un límite de palabra cuando busca coincidencias con caracteres alfabéticos. Esto significa que para esta expresión regular, el retroceso nunca puede contribuir al éxito global de cualquier coincidencia; solo puede degradar el rendimiento, ya que se fuerza que el motor de expresiones regulares guarde su estado para cada coincidencia preliminar correcta de un carácter alfabético.

Si determina que el retroceso no es necesario, puede deshabilitarlo mediante el elemento de lenguaje **(?>**_subexpression_**)**. En el ejemplo siguiente se analiza una cadena de entrada usando dos expresiones regulares. La primera, `\b\p{Lu}\w*\b`, se basa en el retroceso. La segunda, `\b\p{Lu}(?>\w*)\b`, deshabilita el retroceso. Como muestra el resultado del ejemplo, ambas producen el mismo resultado.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This this word Sentence name Capital";
      string pattern = @"\b\p{Lu}\w*\b";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);

      Console.WriteLine();

      pattern = @"\b\p{Lu}(?>\w*)\b";   
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       This
//       Sentence
//       Capital
//       
//       This
//       Sentence
//       Capital
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This this word Sentence name Capital"
      Dim pattern As String = "\b\p{Lu}\w*\b"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next
      Console.WriteLine()

      pattern = "\b\p{Lu}(?>\w*)\b"   
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       This
'       Sentence
'       Capital
'       
'       This
'       Sentence
'       Capital
```

En muchos casos, el retroceso es esencial para buscar una coincidencia de un patrón de expresión regular con el texto de entrada. Sin embargo, el retroceso excesivo puede degradar gravemente el rendimiento y dar la impresión de que una aplicación ha dejado de responder. En concreto, esto ocurre cuando se anidan los cuantificadores y el texto que coincide con la subexpresión externa es un subconjunto del texto que coincide con la subexpresión interna. 

> [!WARNING]
> Además de evitar el retroceso excesivo, se debe utilizar la característica de tiempo de espera para garantizar que el retroceso excesivo no reduzca gravemente el rendimiento de la expresión regular. Para obtener más información, consulte la sección [Usar valores de tiempo de espera](#use-time-out-values).
 
Por ejemplo, el patrón de expresión regular `^[0-9A-Z]([-.\w]*[0-9A-Z])*\$$` está diseñado para buscar coincidencias con un número de pieza que contiene al menos un carácter alfanumérico. Cualquier carácter adicional puede constar de un carácter alfanumérico, un guión, un carácter de subrayado o un punto, aunque el último carácter debe ser alfanumérico. El número de pieza termina con un signo de dólar. En algunos casos, este patrón de expresión regular puede presentar un rendimiento muy deficiente porque los cuantificadores están anidados y porque la subexpresión `[0-9A-Z]` es un subconjunto de la subexpresión `[-.\w]*`.

En estos casos, puede optimizar el rendimiento de la expresión regular quitando los cuantificadores anidados y reemplazando la subexpresión externa con una aserción de búsqueda anticipada o de búsqueda tardía de ancho cero. Las aserciones de búsqueda anticipada y de búsqueda tardía son delimitadores; no mueven el puntero en la cadena de entrada, sino que realizan una búsqueda hacia delante o hacia atrás para comprobar si se cumple una condición especificada. Por ejemplo, la expresión regular de número de pieza se puede volver a escribir como `^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$`. Este patrón de expresión regular se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | -----------
`^` | Iniciar la búsqueda de coincidencias con el principio de la cadena de entrada.
`[0-9A-Z]` | Buscar coincidencias de un carácter alfanumérico. El número de pieza debe constar al menos de este carácter.
`[-.\w]*` | Buscar coincidencias con cero o más apariciones de cualquier carácter alfabético, guión o punto.
`\$] | Buscar coincidencias con un signo de dólar.
`(?<=[0-9A-Z])` | Realizar una búsqueda anticipada del signo de dólar final para asegurarse de que el carácter anterior es alfanumérico.
`$` Finalizar la búsqueda de coincidencias al final de la cadena de entrada.
 
En el ejemplo siguiente se muestra el uso de esta expresión regular para encontrar una matriz que contiene los números de pieza posibles.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$";
      string[] partNos = { "A1C$", "A4", "A4$", "A1603D$", "A1603D#" };

      foreach (var input in partNos) {
         Match match = Regex.Match(input, pattern);
         if (match.Success)
            Console.WriteLine(match.Value);
         else
            Console.WriteLine("Match not found.");
      }      
   }
}
// The example displays the following output:
//       A1C$
//       Match not found.
//       A4$
//       A1603D$
//       Match not found.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "^[0-9A-Z][-.\w]*(?<=[0-9A-Z])\$$"
      Dim partNos() As String = { "A1C$", "A4", "A4$", "A1603D$", 
                                  "A1603D#" }

      For Each input As String In partNos
         Dim match As Match = Regex.Match(input, pattern)
         If match.Success Then
            Console.WriteLine(match.Value)
         Else
            Console.WriteLine("Match not found.")
         End If
      Next      
   End Sub
End Module
' The example displays the following output:
'       A1C$
'       Match not found.
'       A4$
'       A1603D$
'       Match not found.
```

El lenguaje de expresiones regulares de .NET incluye los elementos del lenguaje siguientes, que puede usar para eliminar cuantificadores anidados. Para obtener más información, consulte [Construcciones de agrupamiento en expresiones regulares](grouping.md).

Elemento del lenguaje | Descripción
---------------- | ----------- 
**(?**=_subexpression_**)** | Búsqueda anticipada positiva de ancho cero. Realizar una búsqueda anticipada de la posición actual para determinar si *subexpression* coincide con la cadena de entrada.
**(?!**_subexpression_**)** | Búsqueda anticipada negativa de ancho cero. Realizar una búsqueda anticipada de la posición actual para determinar si *subexpression* no coincide con la cadena de entrada.
**(?<**=_subexpression_**)** | Búsqueda tardía positiva de ancho cero. Realizar una búsqueda tardía de la posición actual para determinar si *subexpression* coincide con la cadena de entrada.
**(?<!**_subexpression_**)** | Búsqueda tardía negativa de ancho cero. Realizar una búsqueda tardía de la posición actual para determinar si *subexpression* no coincide con la cadena de entrada.
 
## <a name="use-timeout-values"></a>Usar valores de tiempo de espera

Si sus expresiones regulares procesan datos de entrada que prácticamente coinciden con el patrón de expresiones regulares, normalmente se puede usar el retroceso excesivo, que afecta enormemente al rendimiento. Además de analizar cuidadosamente el uso del retroceso y probar la expresión regular en entradas casi coincidentes, debe establecer siempre un valor de tiempo de espera para garantizar que el impacto del retroceso excesivo, si aparece, se reduzca al mínimo.

El intervalo de tiempo de espera de la expresión regular define el período de tiempo que el motor de expresiones regulares buscará una coincidencia única antes de que el tiempo se agote. El intervalo de tiempo de espera predeterminado es [Regex.InfiniteMatchTimeout](xref:System.Text.RegularExpressions.Regex.InfiniteMatchTimeout), que significa que no se agotará el tiempo de la expresión regular. Puede invalidar este valor y definir un intervalo de tiempo de espera de la siguiente manera: 

* Al proporcionar un valor de tiempo de espera al crear una instancia del objeto [Regex](xref:System.Text.RegularExpressions.Regex) llamando al constructor [Regex(String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.%23ctor(System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)).

* Al llamar a un método estático de coincidencia de patrones, como [Regex.Match(String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)) o [Regex.Replace(String, String, String, RegexOptions, TimeSpan)](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions,System.TimeSpan)), que incluya un parámetro *matchTimeout*.

Si ha definido un intervalo de tiempo de espera y no se encuentra ninguna coincidencia al final del intervalo, el método de expresiones regulares produce una excepción [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException). En el controlador de excepciones, puede elegir reintentar la búsqueda de coincidencias con un intervalo de tiempo de espera más largo, abandonar el intento de búsqueda de coincidencias y asumir que no hay ninguna coincidencia o abandonar el intento de búsqueda de coincidencias y registrar la información de excepción para futuros análisis.

En el ejemplo siguiente se define un método `GetWordData` que crea una instancia de una expresión regular con un tiempo de espera de 350 milisegundos para calcular el número de palabras y el promedio de caracteres de una palabra en un documento de texto. Si se agota el tiempo de espera de la operación de coincidencia, el intervalo de tiempo de espera aumenta en 350 milisegundos y se vuelve a crear una instancia del objeto [Regex](xref:System.Text.RegularExpressions.Regex). Si el nuevo intervalo de tiempo de espera es mayor de 1 segundo, el método vuelve a producir la excepción y se la envía al llamador.

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      RegexUtilities util = new RegexUtilities();
      string title = "Doyle - The Hound of the Baskervilles.txt";
      try {
         var info = util.GetWordData(title);
         Console.WriteLine("Words:               {0:N0}", info.Item1);
         Console.WriteLine("Average Word Length: {0:N2} characters", info.Item2); 
      }
      catch (IOException e) {
         Console.WriteLine("IOException reading file '{0}'", title);
         Console.WriteLine(e.Message);
      }
      catch (RegexMatchTimeoutException e) {
         Console.WriteLine("The operation timed out after {0:N0} milliseconds", 
                           e.MatchTimeout.TotalMilliseconds);
      }
   }
}

public class RegexUtilities
{
   public Tuple<int, double> GetWordData(string filename)
   { 
      const int MAX_TIMEOUT = 1000;   // Maximum timeout interval in milliseconds.
      const int INCREMENT = 350;      // Milliseconds increment of timeout.

      List<string> exclusions = new List<string>( new string[] { "a", "an", "the" });
      int[] wordLengths = new int[29];        // Allocate an array of more than ample size.
      string input = null;
      StreamReader sr = null;
      try { 
         sr = new StreamReader(filename);
         input = sr.ReadToEnd();
      }
      catch (FileNotFoundException e) {
         string msg = String.Format("Unable to find the file '{0}'", filename);
         throw new IOException(msg, e);
      }
      catch (IOException e) {
         throw new IOException(e.Message, e);
      }
      finally {
         if (sr != null) sr.Close(); 
      }

      int timeoutInterval = INCREMENT;
      bool init = false;
      Regex rgx = null;
      Match m = null;
      int indexPos = 0;  
      do {
         try {
            if (! init) {
               rgx = new Regex(@"\b\w+\b", RegexOptions.None, 
                               TimeSpan.FromMilliseconds(timeoutInterval));
               m = rgx.Match(input, indexPos);
               init = true;
            }
            else { 
               m = m.NextMatch();
            }
            if (m.Success) {    
               if ( !exclusions.Contains(m.Value.ToLower()))
                  wordLengths[m.Value.Length]++;

               indexPos += m.Length + 1;   
            }
         }
         catch (RegexMatchTimeoutException e) {
            if (e.MatchTimeout.TotalMilliseconds < MAX_TIMEOUT) {
               timeoutInterval += INCREMENT;
               init = false;
            }
            else {
               // Rethrow the exception.
               throw; 
            }   
         }          
      } while (m.Success);

      // If regex completed successfully, calculate number of words and average length.
      int nWords = 0; 
      long totalLength = 0;

      for (int ctr = wordLengths.GetLowerBound(0); ctr <= wordLengths.GetUpperBound(0); ctr++) {
         nWords += wordLengths[ctr];
         totalLength += ctr * wordLengths[ctr];
      }
      return new Tuple<int, double>(nWords, totalLength/nWords);
   }
}
```

```vb
Imports System.Collections.Generic
Imports System.IO
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim util As New RegexUtilities()
      Dim title As String = "Doyle - The Hound of the Baskervilles.txt"
      Try
         Dim info = util.GetWordData(title)
         Console.WriteLine("Words:               {0:N0}", info.Item1)
         Console.WriteLine("Average Word Length: {0:N2} characters", info.Item2) 
      Catch e As IOException
         Console.WriteLine("IOException reading file '{0}'", title)
         Console.WriteLine(e.Message)
      Catch e As RegexMatchTimeoutException
         Console.WriteLine("The operation timed out after {0:N0} milliseconds", 
                           e.MatchTimeout.TotalMilliseconds)
      End Try
   End Sub
End Module

Public Class RegexUtilities
   Public Function GetWordData(filename As String) As Tuple(Of Integer, Double) 
      Const MAX_TIMEOUT As Integer = 1000  ' Maximum timeout interval in milliseconds.
      Const INCREMENT As Integer = 350     ' Milliseconds increment of timeout.

      Dim exclusions As New List(Of String)({"a", "an", "the" })
      Dim wordLengths(30) As Integer        ' Allocate an array of more than ample size.
      Dim input As String = Nothing
      Dim sr As StreamReader = Nothing
      Try 
         sr = New StreamReader(filename)
         input = sr.ReadToEnd()
      Catch e As FileNotFoundException
         Dim msg As String = String.Format("Unable to find the file '{0}'", filename)
         Throw New IOException(msg, e)
      Catch e As IOException
         Throw New IOException(e.Message, e)
      Finally
         If sr IsNot Nothing Then sr.Close() 
      End Try

      Dim timeoutInterval As Integer = INCREMENT
      Dim init As Boolean = False
      Dim rgx As Regex = Nothing
      Dim m As Match = Nothing
      Dim indexPos As Integer = 0  
      Do
         Try
            If Not init Then
               rgx = New Regex("\b\w+\b", RegexOptions.None, 
                               TimeSpan.FromMilliseconds(timeoutInterval))
               m = rgx.Match(input, indexPos)
               init = True
            Else 
               m = m.NextMatch()
            End If
            If m.Success Then    
               If Not exclusions.Contains(m.Value.ToLower()) Then
                  wordLengths(m.Value.Length) += 1
               End If
               indexPos += m.Length + 1   
            End If
         Catch e As RegexMatchTimeoutException
            If e.MatchTimeout.TotalMilliseconds < MAX_TIMEOUT Then
               timeoutInterval += INCREMENT
               init = False
            Else
               ' Rethrow the exception.
               Throw 
            End If   
         End Try          
      Loop While m.Success

      ' If regex completed successfully, calculate number of words and average length.
      Dim nWords As Integer
      Dim totalLength As Long

      For ctr As Integer = wordLengths.GetLowerBound(0) To wordLengths.GetUpperBound(0)
         nWords += wordLengths(ctr)
         totalLength += ctr * wordLengths(ctr)
      Next
      Return New Tuple(Of Integer, Double)(nWords, totalLength/nWords)
   End Function
End Class
```

## <a name="capture-only-when-necessary"></a>Capturar solo cuando sea necesario

Las expresiones regulares de .NET admiten varias construcciones de agrupación, que permiten agrupar un patrón de expresión regular en una o más subexpresiones. Las construcciones de agrupación que más se usan en el lenguaje de expresiones regulares de .NET son **(**_subexpression_**)**, que define un grupo de captura numerado, y **(?<*_name_**>**_subexpression_**)**, que define un grupo de captura con nombre. Las construcciones de agrupación son esenciales para crear referencias inversas y para definir una subexpresión a la que se aplica un cuantificador. 

Sin embargo, el uso de estos elementos de lenguaje tiene un costo. Hacen que el objeto [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) devuelto por la propiedad [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) se rellene con las capturas sin nombre o con nombre más recientes, y si una única construcción de agrupación ha capturado varias subcadenas en la cadena de entrada, también rellenan el objeto [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) devuelto por la propiedad [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) de un grupo de captura determinado con varios objetos [Capture](xref:System.Text.RegularExpressions.Capture).

A menudo, las construcciones de agrupación se usan en una expresión regular solo para poder aplicarles cuantificadores y los grupos capturados por estas subexpresiones no se usan posteriormente. Por ejemplo, la expresión regular `\b(\w+[;,]?\s?)+[.?!]` está diseñada para capturar una frase completa. En la tabla siguiente, se describen los elementos del lenguaje de este patrón de expresión regular y su efecto sobre las colecciones [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) y [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) del objeto [Match](xref:System.Text.RegularExpressions.Match).

Modelo | Descripción
------- | -----------
`\b` | Iniciar la búsqueda de coincidencias en un límite de palabras.
`\w+` | Buscar coincidencias con uno o más caracteres alfabéticos.
`[;,]?` | Buscar coincidencias con cero o una coma o un punto y coma.
`\s?` | Busca coincidencias con cero o un carácter de espacio en blanco.
`(\w+[;,]?\s?)+` | Buscar coincidencias con una o más apariciones de uno o más caracteres alfabéticos seguidos de una coma o un punto y coma opcional, seguido de un carácter opcional de espacio en blanco. Esto define al primer grupo de captura, que es necesario para que la combinación de varios caracteres alfabéticos (es decir, una palabra) seguidos de un signo de puntuación opcional se repita hasta que el motor de expresiones regulares llegue al final de una frase.
`[.?!]` | Buscar coincidencias con un punto, un signo de interrogación o un signo de exclamación.
 
Como se muestra en el ejemplo siguiente, cuando se encuentra una coincidencia, los objetos [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) y [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) se rellenan con capturas de la coincidencia. En este caso, el grupo de captura `(\w+[;,]?\s?)` existe para que se le pueda aplicar el cuantificador **+**, que permite que el patrón de expresión regular coincida con cada palabra de una frase. De lo contrario, coincidiría con la última palabra de una frase.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is one sentence. This is another.";
      string pattern = @"\b(\w+[;,]?\s?)+[.?!]";

      foreach (Match match in Regex.Matches(input, pattern)) {
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index);
         int grpCtr = 0;
         foreach (Group grp in match.Groups) {
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index);
            int capCtr = 0;
            foreach (Capture cap in grp.Captures) {
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index);
               capCtr++;
            }
            grpCtr++;
         }          
         Console.WriteLine();        
      }
   }
}
// The example displays the following output:
//       Match: 'This is one sentence.' at index 0.
//          Group 0: 'This is one sentence.' at index 0.
//             Capture 0: 'This is one sentence.' at 0.
//          Group 1: 'sentence' at index 12.
//             Capture 0: 'This ' at 0.
//             Capture 1: 'is ' at 5.
//             Capture 2: 'one ' at 8.
//             Capture 3: 'sentence' at 12.
//       
//       Match: 'This is another.' at index 22.
//          Group 0: 'This is another.' at index 22.
//             Capture 0: 'This is another.' at 22.
//          Group 1: 'another' at index 30.
//             Capture 0: 'This ' at 22.
//             Capture 1: 'is ' at 27.
//             Capture 2: 'another' at 30.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is one sentence. This is another."
      Dim pattern As String = "\b(\w+[;,]?\s?)+[.?!]"

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index)
         Dim grpCtr As Integer = 0
         For Each grp As Group In match.Groups
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index)
            Dim capCtr As Integer = 0
            For Each cap As Capture In grp.Captures
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index)
               capCtr += 1
            Next
            grpCtr += 1
         Next          
         Console.WriteLine()        
      Next    
   End Sub
End Module
' The example displays the following output:
'       Match: 'This is one sentence.' at index 0.
'          Group 0: 'This is one sentence.' at index 0.
'             Capture 0: 'This is one sentence.' at 0.
'          Group 1: 'sentence' at index 12.
'             Capture 0: 'This ' at 0.
'             Capture 1: 'is ' at 5.
'             Capture 2: 'one ' at 8.
'             Capture 3: 'sentence' at 12.
'       
'       Match: 'This is another.' at index 22.
'          Group 0: 'This is another.' at index 22.
'             Capture 0: 'This is another.' at 22.
'          Group 1: 'another' at index 30.
'             Capture 0: 'This ' at 22.
'             Capture 1: 'is ' at 27.
'             Capture 2: 'another' at 30.
```

Cuando use subexpresiones solo para aplicarles cuantificadores y no le interese el texto capturado, debe deshabilitar las capturas de grupo. Por ejemplo, el elemento de lenguaje **(?:**_subexpression_**)** impide al grupo al que se aplica que capture subcadenas coincidentes. En el ejemplo siguiente, el patrón de expresión regular del ejemplo anterior se cambia a `\b(?:\w+[;,]?\s?)+[.?!]`. Como muestra el resultado, evita que el motor de expresiones regulares rellene las colecciones [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) y [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection).

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is one sentence. This is another.";
      string pattern = @"\b(?:\w+[;,]?\s?)+[.?!]";

      foreach (Match match in Regex.Matches(input, pattern)) {
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index);
         int grpCtr = 0;
         foreach (Group grp in match.Groups) {
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index);
            int capCtr = 0;
            foreach (Capture cap in grp.Captures) {
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index);
               capCtr++;
            }
            grpCtr++;
         }          
         Console.WriteLine();        
      }
   }
}
// The example displays the following output:
//       Match: 'This is one sentence.' at index 0.
//          Group 0: 'This is one sentence.' at index 0.
//             Capture 0: 'This is one sentence.' at 0.
//       
//       Match: 'This is another.' at index 22.
//          Group 0: 'This is another.' at index 22.
//             Capture 0: 'This is another.' at 22.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is one sentence. This is another."
      Dim pattern As String = "\b(?:\w+[;,]?\s?)+[.?!]"

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Match: '{0}' at index {1}.", 
                           match.Value, match.Index)
         Dim grpCtr As Integer = 0
         For Each grp As Group In match.Groups
            Console.WriteLine("   Group {0}: '{1}' at index {2}.",
                              grpCtr, grp.Value, grp.Index)
            Dim capCtr As Integer = 0
            For Each cap As Capture In grp.Captures
               Console.WriteLine("      Capture {0}: '{1}' at {2}.",
                                 capCtr, cap.Value, cap.Index)
               capCtr += 1
            Next
            grpCtr += 1
         Next          
         Console.WriteLine()        
      Next    
   End Sub
End Module
' The example displays the following output:
'       Match: 'This is one sentence.' at index 0.
'          Group 0: 'This is one sentence.' at index 0.
'             Capture 0: 'This is one sentence.' at 0.
'       
'       Match: 'This is another.' at index 22.
'          Group 0: 'This is another.' at index 22.
'             Capture 0: 'This is another.' at 22.
```

Puede deshabilitar las capturas de una de las maneras siguientes:

* Use el elemento de lenguaje **(?:**_subexpression_**)**. Este elemento impide la captura de subcadenas coincidentes en el grupo al que se aplica. No deshabilita las capturas de subcadenas en ningún grupo anidado.

* Use la opción [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture). Deshabilita todas las capturas sin nombre o implícitas en el patrón de expresión regular. Cuando se usa esta opción, solo se pueden capturar las subcadenas que coinciden con grupos con nombre definidos con el elemento de lenguaje **(?<**_name_**>**_subexpression_**)**. La marca [ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) puede pasarse al parámetro de opciones de un constructor de clase [Regex](xref:System.Text.RegularExpressions.Regex) o al parámetro de opciones de un método coincidente estático [Regex](xref:System.Text.RegularExpressions.Regex).

* Use la opción **n** del elemento de lenguaje **(?imnsx)**. Esta opción deshabilita todas las capturas sin nombre o implícitas desde el punto del patrón de expresión regular en el que aparece el elemento. Las capturas se deshabilitan hasta el final del patrón o hasta que la opción **(-n)** habilita las capturas sin nombre o implícitas. Para obtener más información, consulte [Construcciones misceláneas en expresiones regulares](miscellaneous.md).

* Use la opción **n** del elemento de lenguaje **(?imnsx:**_subexpression_**)**. Esta opción deshabilita todas las capturas sin nombre o implícitas en *subexpression*. Las capturas por grupos de captura anidados sin nombre o implícitos también se deshabilitan.

## <a name="related-topics"></a>Temas relacionados

Título | Descripción
----- | ----------- 
[Detalles del comportamiento de expresiones regulares](regex-behavior.md) | Examina la implementación del motor de expresiones regulares de .NET. El tema se centra en la flexibilidad de las expresiones regulares y explica la responsabilidad del desarrollador para garantizar un funcionamiento eficaz y sólido del motor de expresiones regulares.
[Retroceso en expresiones regulares](backtracking.md) | Explica qué es el retroceso y cómo afecta al rendimiento de las expresiones regulares, y examine los elementos del lenguaje que proporcionan alternativas al retroceso.
[Lenguaje de expresiones regulares: referencia rápida](quick-ref.md) | Describe los elementos del lenguaje de expresiones regulares de .NET y proporciona vínculos a documentación detallada sobre cada elemento del lenguaje.
 




<!--HONumber=Nov16_HO1-->


