---
title: Retroceso en expresiones regulares
description: Retroceso en expresiones regulares
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 8a3e6298-26b7-4c99-bd97-c9892f6c9418
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 649dfd6752f0589eb396b00e7d0b5184bb65d488

---

# <a name="backtracking-in-regular-expressions"></a>Retroceso en expresiones regulares

El retroceso se produce cuando un patrón de expresión regular contiene [cuantificadores](quantifiers.md) o [construcciones de alternancia](alternation.md) opcionales y el motor de expresiones regulares vuelve a un estado guardado anterior para continuar la búsqueda de una coincidencia. El retroceso es fundamental para la eficacia de las expresiones regulares; permite que las expresiones sean eficaces y flexibles, y que coincidan con modelos muy complejos. Al mismo tiempo, esta eficacia tiene un costo. El retroceso suele ser el factor único más importante que afecta al rendimiento del motor de expresiones regulares. Afortunadamente, el desarrollador tiene control sobre el comportamiento del motor de expresiones regulares y cómo usa el retroceso. En este tema se explica cómo funciona el retroceso y cómo se puede controlar.

> [!NOTE]
> En general, un motor NFA (autómata finito no determinista), como el motor de expresiones regulares, se encarga de crear expresiones regulares eficaces y rápidas para el desarrollador.
 
Este tema contiene las siguientes secciones:

* [Comparación lineal sin retroceso](#linear-comparison-without-backtracking)

* [Retroceso con cuantificadores o construcciones de alternancia opcionales](#backtracking-with-optional-quantifiers-or-alternation-constructs)

* [Retroceso con cuantificadores opcionales anidados](#backtracking-with-nested-optional-quantifiers)

* [Controlar el retroceso](#controlling-backtracking)

## <a name="linear-comparison-without-backtracking"></a>Comparación lineal sin retroceso

Si un patrón de expresión regular no tiene ningún cuantificador o construcción de alternancia opcional, el motor de expresiones regulares se ejecuta en tiempo lineal. Es decir, una vez que el motor de expresiones regulares hace coincidir el primer elemento de lenguaje del patrón con texto de la cadena de entrada, intenta buscar una coincidencia del siguiente elemento de lenguaje del patrón con el siguiente carácter o grupo de caracteres de la cadena de entrada. Este proceso continúa hasta que la coincidencia se realiza correctamente o se produce un error. En cualquier caso, el motor de expresiones regulares avanza de carácter en carácter por la cadena de entrada.

Esto se muestra en el ejemplo siguiente. La expresión regular `e{2}\w\b` busca dos apariciones de la letra "e" seguida de cualquier carácter alfabético seguido de un límite de palabras.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "needing a reed";
      string pattern = @"e{2}\w\b";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("{0} found at position {1}", 
                           match.Value, match.Index);
   }
}
// The example displays the following output:
//       eed found at position 11
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "needing a reed"
      Dim pattern As String = "e{2}\w\b"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("{0} found at position {1}", _
                           match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       eed found at position 11
```

Aunque esta expresión regular incluye el cuantificador `{2}`, se evalúa de manera lineal. El motor de expresiones regulares no retrocede porque `{2}` no es un cuantificador opcional, ya que especifica un número exacto y no un número variable de veces que la subexpresión anterior debe coincidir. Como resultado, el motor de expresiones regulares intenta hacer coincidir el patrón de expresión regular con la cadena de entrada como se muestra en la tabla siguiente.

Operación | Posición en el patrón | Posición en la cadena | Resultado
--------- | ------------------- | ------------------ | ------ 
1 | h | "needing a reed" (índice 0) | Ninguna coincidencia. 
2 | h | "eeding a reed" (índice 1) | Posible coincidencia. 
3 | e{2} | "eding a reed" (índice 2) | Posible coincidencia. 
4 | \w | "ding a reed" (índice 3) | Posible coincidencia.
5 | \b | "ing a reed" (índice 4) | Error en posible coincidencia. 
6 | h | "eding a reed" (índice 2) | Posible coincidencia. 
7 | e{2} | "ding a reed" (índice 3) | Error en posible coincidencia. 
8 | h | "ding a reed" (índice 3) | Se produce un error de coincidencia. 
9 | h | "ing a reed" (índice 4) | Ninguna coincidencia.
10 | h | "ng a reed" (índice 5) | Ninguna coincidencia.
11 | h | "g a reed" (índice 6) | Ninguna coincidencia.
12 | h | " a reed" (índice 7) | Ninguna coincidencia.
13 | h | “a reed” (índice 8) | Ninguna coincidencia.
14 | h | " reed" (índice 9) | Ninguna coincidencia.
15 | h | “reed” (índice 10) | Ninguna coincidencia
16 | h | "eed" (índice 11) | Posible coincidencia.
17 | e{2} | "ed" (índice 12) | Posible coincidencia.
18 | \w | "d" (índice 13) | Posible coincidencia.
19 | \b | "" (índice 14) | Coincidencia.
 

Si un patrón de expresión regular no incluye ningún cuantificador o construcción de alternancia opcional, el número máximo de comparaciones necesarias para hacer coincidir el patrón de expresión regular con la cadena de entrada es aproximadamente equivalente al número de caracteres de la cadena de entrada. En este caso, el motor de expresiones regulares usa 19 comparaciones para identificar posibles coincidencias en esta cadena de 13 caracteres. Es decir, el motor de expresiones regulares se ejecuta en tiempo prácticamente lineal si no contiene ningún cuantificador o construcción de alternancia opcional.

## <a name="backtracking-with-optional-quantifiers-or-alternation-constructs"></a>Retroceso con cuantificadores o construcciones de alternancia opcionales

Cuando una expresión regular incluye cuantificadores o construcciones de alternancia opcionales, la evaluación de la cadena de entrada ya no es lineal. La coincidencia de modelos con un motor NFA está controlada por los elementos de lenguaje de la expresión regular y no por los caracteres que se hacen coincidir en la cadena de entrada. Por tanto, el motor de expresiones regulares intenta hacer coincidir totalmente subexpresiones opcionales o alternativas. Cuando avanza al elemento de lenguaje siguiente de la subexpresión y la coincidencia no se realiza correctamente, el motor de expresiones regulares puede abandonar una parte de su coincidencia correcta y volver a un estado guardado anterior para hacer coincidir la expresión regular en su conjunto con la cadena de entrada. Este proceso de volver a un estado guardado anterior para encontrar una coincidencia se denomina retroceso.

Por ejemplo, considere el patrón de expresión regular `.*(es)`, que hace coincidir los caracteres "es" y todos los caracteres que lo preceden. Como se muestra en el ejemplo siguiente, si la cadena de entrada es "Essential services are provided by regular expressions.", el patrón coincide con toda la cadena hasta e incluyendo "es" en "expressions".

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "Essential services are provided by regular expressions.";
      string pattern = ".*(es)"; 
      Match m = Regex.Match(input, pattern, RegexOptions.IgnoreCase);
      if (m.Success) {
         Console.WriteLine("'{0}' found at position {1}", 
                           m.Value, m.Index);
         Console.WriteLine("'es' found at position {0}", 
                           m.Groups[1].Index);      
      } 
   }
}
//    'Essential services are provided by regular expres' found at position 0
//    'es' found at position 47
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "Essential services are provided by regular expressions."
      Dim pattern As String = ".*(es)" 
      Dim m As Match = Regex.Match(input, pattern, RegexOptions.IgnoreCase)
      If m.Success Then
         Console.WriteLine("'{0}' found at position {1}", _
                           m.Value, m.Index)
         Console.WriteLine("'es' found at position {0}", _
                           m.Groups(1).Index)                  
      End If     
   End Sub
End Module
'    'Essential services are provided by regular expres' found at position 0
'    'es' found at position 47
```

Para ello, el motor de expresiones regulares usa el retroceso de la manera siguiente:

* Coincide con `.*` (que coincide con cero, una o más apariciones de cualquier carácter) con la cadena de entrada completa.

* Intenta hacer coincidir "e" en el patrón de expresión regular. Sin embargo, la cadena de entrada no tiene ningún carácter restante disponible para coincidir.

* Retrocede hasta su última coincidencia correcta, "Essential services are provided by regular expressions", e intenta hacer coincidir "e" con el punto del final de la frase. Se produce un error de coincidencia.

* Sigue retrocediendo hasta una coincidencia correcta anterior, de carácter en carácter, hasta que la subcadena coincidente tentativa sea "Essential services are provided by regular expr". A continuación, compara la "e" del patrón con la segunda "e" de "expressions" y encuentra una coincidencia.

* Compara la "s" del patrón con la "s" que sigue al carácter "e" coincidente (la primera "s" de "expressions"). La coincidencia es correcta.

Cuando se usa retroceso, la coincidencia del patrón de expresión regular con la cadena de entrada, que tiene 55 caracteres de longitud, necesita 67 operaciones de comparación. Curiosamente, si el patrón de expresión regular incluyera un cuantificador diferido, `.*?(es),`, la coincidencia con la expresión regular necesitaría comparaciones adicionales. En este caso, en lugar de tener que retroceder desde el final de la cadena a la "r" de "expressions", el motor de expresiones regulares tendría que retroceder hasta el principio de la cadena para buscar coincidencias de "Es" y necesitaría 113 comparaciones. Normalmente, si un patrón de expresión regular tiene una única construcción de alternancia o un único cuantificador opcional, el número de operaciones de comparación necesarias para que coincida con el patrón es más del doble del número de caracteres de la cadena de entrada.

## <a name="backtracking-with-nested-optional-quantifiers"></a>Retroceso con cuantificadores opcionales anidados

El número de operaciones de comparación necesarias para coincidir con un patrón de expresión regular puede aumentar exponencial si el patrón incluye muchas construcciones de alternancia, si incluye construcciones de alternancia anidadas o, lo que es más frecuente, si incluye cuantificadores opcionales anidados. Por ejemplo, el patrón de expresión regular `^(a+)+$` está diseñado para coincidir con una cadena completa que contiene uno o más caracteres "a". El ejemplo proporciona dos cadenas de entrada de longitud idéntica, pero solo la primera cadena coincide con el patrón. La clase [System.Diagnostics.Stopwatch](xref:System.Diagnostics.Stopwatch) se usa para determinar cuánto tiempo tarda la operación de coincidencia. 

```csharp
using System;
using System.Diagnostics;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = "^(a+)+$";
      string[] inputs = { "aaaaaa", "aaaaa!" };
      Regex rgx = new Regex(pattern);
      Stopwatch sw;

      foreach (string input in inputs) {
         sw = Stopwatch.StartNew();   
         Match match = rgx.Match(input);
         sw.Stop();
         if (match.Success)
            Console.WriteLine("Matched {0} in {1}", match.Value, sw.Elapsed);
         else
            Console.WriteLine("No match found in {0}", sw.Elapsed);
      }
   }
}
```

```vb
Imports System.Diagnostics
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "^(a+)+$"
      Dim inputs() As String = { "aaaaaa", "aaaaa!" }
      Dim rgx As New Regex(pattern)
      Dim sw As Stopwatch

      For Each input As String In inputs
         sw = Stopwatch.StartNew()   
         Dim match As Match = rgx.Match(input)
         sw.Stop()
         If match.Success Then
            Console.WriteLine("Matched {0} in {1}", match.Value, sw.Elapsed)
         Else
            Console.WriteLine("No match found in {0}", sw.Elapsed)
         End If      
      Next
   End Sub
End Module
```

Como muestra el resultado del ejemplo, el motor de expresiones regulares tardó en descubrir que una cadena de entrada no coincidía con el patrón aproximadamente el doble que en identificar una cadena coincidente. Esto se debe a que una coincidencia infructuosa siempre representa un escenario de caso peor. El motor de expresiones regulares debe usar la expresión regular para seguir todas las rutas posibles a través de los datos antes de poder concluir que la coincidencia no es correcta y los paréntesis anidados crean muchas rutas de acceso adicionales a través de los datos. El motor de expresiones regulares concluye que la segunda cadena no coincide con el patrón; para ello, hace lo siguiente:

* Comprueba que está al principio de la cadena y después busca una coincidencia de los cinco primeros caracteres de la cadena con el patrón a+. A continuación, determina que no hay ningún grupo adicional de caracteres "a" en la cadena. Por último, comprueba que está al final de la cadena. Como en la cadena queda un carácter adicional, la coincidencia produce un error. Esta coincidencia errónea necesita 9 comparaciones. El motor de expresiones regulares también guarda información de estado de las coincidencias de "a" (que llamaremos coincidencia 1), "aa" (coincidencia 2), "aaa" (coincidencia 3) y "aaaa" (coincidencia 4).

* Vuelve a la coincidencia 4 guardada previamente. Determina que hay un carácter "a" adicional para asignar a un grupo capturado adicional. Por último, comprueba que está al final de la cadena. Como en la cadena queda un carácter adicional, la coincidencia produce un error. Esta coincidencia errónea necesita 4 comparaciones. Hasta ahora, se han realizado un total de 13 comparaciones.

* Vuelve a la coincidencia 3 guardada previamente. Determina que hay dos caracteres "a" adicionales para asignar a un grupo capturado adicional. Sin embargo, se produce un error en la prueba de fin de cadena. Vuelva a la coincidencia 3 e intenta hacer coincidir los dos caracteres "a" adicionales en dos grupos capturados adicionales. Se sigue produciendo un error en la prueba de fin de cadena. Estas coincidencias con error necesitan 12 comparaciones. Hasta ahora, se ha realizado un total de 25 comparaciones. 

La comparación de la cadena de entrada con la expresión regular continúa de esta manera hasta que el motor de expresiones regulares ha intentado todas las posibles combinaciones de coincidencias y, a continuación, concluye que no hay ninguna coincidencia. Debido a los cuantificadores anidados, esta comparación es O(2n) o una operación exponencial, donde n es el número de caracteres de la cadena de entrada. Esto significa que, en el peor de los casos, una cadena de entrada de 30 caracteres necesita aproximadamente 1.073.741.824 comparaciones y una cadena de entrada de 40 caracteres necesita aproximadamente 1.099.511.627.776 comparaciones. Si usa cadenas de estas longitudes o incluso mayores, los métodos de expresión regular pueden tardar mucho tiempo en completarse cuando procesan datos de entrada que no coinciden con el patrón de expresión regular.

## <a name="controlling-backtracking"></a>Controlar el retroceso

El retroceso permite crear expresiones regulares eficaces y flexibles. Sin embargo, como se ha mostrado en la sección anterior, estas ventajas pueden conllevar un bajo rendimiento inaceptable. Para evitar el retroceso excesivo, se debe definir un intervalo de tiempo de espera al crear una instancia de un objeto [Regex](xref:System.Text.RegularExpressions.Regex) o llamar a un método estático de coincidencia de expresión regular. Esta técnica se analiza en la sección siguiente. Además, .NET Core admite tres elementos del lenguaje de expresiones regulares que limitan o suprimen el retroceso y que admiten expresiones regulares complejas con poca o ninguna reducción del rendimiento: [subexpresiones sin retroceso](#nonbacktracking-subexpression), [aserciones de búsqueda tardía](#lookbehind-assertions) y [aserciones de búsqueda anticipada](#lookahead-assertions). Para obtener más información sobre cada elemento del lenguaje, consulte [Construcciones de agrupamiento en expresiones regulares](grouping.md).

### <a name="defining-a-time-out-interval"></a>Definición de un intervalo de tiempo de espera

Se puede establecer un valor de tiempo de espera que represente el intervalo más largo en el que el motor de expresiones regulares buscará una coincidencia única antes de abandonar el intento y generar una excepción [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException). El intervalo de tiempo de espera se especifica al proporcionar un valor [TimeSpan](xref:System.TimeSpan) al constructor `Regex(String, RegexOptions, TimeSpan)` para las expresiones regulares de instancias. Además, cada método estático de coincidencia de patrones tiene una sobrecarga con un valor [TimeSpan](xref:System.TimeSpan) al parámetro [Regex.Regex(String, RegexOptions, TimeSpan)] que permite especificar un valor de tiempo de espera. De manera predeterminada, el intervalo de tiempo de espera se establece en [Regex.InfiniteMatchTimeout](xref:System.Text.RegularExpressions.Regex.InfiniteMatchTimeout) y el motor de expresiones regulares no agota dicho tiempo. 

> [!IMPORTANT]
> Recomendamos que se establezca siempre un intervalo de tiempo de espera si la expresión regular se basa en el retroceso.
 
Una excepción [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException) indica que el motor de expresiones regulares no pudo encontrar una coincidencia en el intervalo de tiempo de espera especificado, pero no indica por qué se ha producido la excepción. La razón puede ser un retroceso excesivo, aunque también es posible que el intervalo de tiempo de espera establecido fuera demasiado bajo, dada la carga del sistema en el momento en que se produjo la excepción. Cuando se controla la excepción, se puede elegir entre abandonar otras coincidencias con la cadena de entrada o incrementar el intervalo de tiempo de espera y reintentar la operación de coincidencia. 

Por ejemplo, el código siguiente llama al constructor `Regex(String, RegexOptions, TimeSpan)` para crear instancias de un objeto Regex con un valor de tiempo de espera de un segundo. El patrón de expresión regular `(a+)+$`, que coincide con una o más secuencias de uno o varios caracteres "a" al final de una línea, está sujeto a un retroceso excesivo. Si se produce una excepción [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException), el ejemplo incrementa el valor de tiempo de espera hasta un intervalo máximo de tres segundos. Después, abandona el intento de coincidir con el patrón.

```csharp
using System;
using System.ComponentModel;
using System.Diagnostics;
using System.Security;
using System.Text.RegularExpressions;
using System.Threading; 

public class Example
{
   const int MaxTimeoutInSeconds = 3;

   public static void Main()
   {
      string pattern = @"(a+)+$";    // DO NOT REUSE THIS PATTERN.
      Regex rgx = new Regex(pattern, RegexOptions.IgnoreCase, TimeSpan.FromSeconds(1));       
      Stopwatch sw = null;

      string[] inputs= { "aa", "aaaa>", 
                         "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
                         "aaaaaaaaaaaaaaaaaaaaaa>",
                         "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa>" };

      foreach (var inputValue in inputs) {
         Console.WriteLine("Processing {0}", inputValue);
         bool timedOut = false;
         do { 
            try {
               sw = Stopwatch.StartNew();
               // Display the result.
               if (rgx.IsMatch(inputValue)) {
                  sw.Stop();
                  Console.WriteLine(@"Valid: '{0}' ({1:ss\.fffffff} seconds)", 
                                    inputValue, sw.Elapsed); 
               }
               else {
                  sw.Stop();
                  Console.WriteLine(@"'{0}' is not a valid string. ({1:ss\.fffff} seconds)", 
                                    inputValue, sw.Elapsed);
               }
            }
            catch (RegexMatchTimeoutException e) {   
               sw.Stop();
               // Display the elapsed time until the exception.
               Console.WriteLine(@"Timeout with '{0}' after {1:ss\.fffff}", 
                                 inputValue, sw.Elapsed);
               Thread.Sleep(1500);       // Pause for 1.5 seconds.

               // Increase the timeout interval and retry.
               TimeSpan timeout = e.MatchTimeout.Add(TimeSpan.FromSeconds(1));
               if (timeout.TotalSeconds > MaxTimeoutInSeconds) {
                  Console.WriteLine("Maximum timeout interval of {0} seconds exceeded.",
                                    MaxTimeoutInSeconds);
                  timedOut = false;
               }
               else {               
                  Console.WriteLine("Changing the timeout interval to {0}", 
                                    timeout); 
                  rgx = new Regex(pattern, RegexOptions.IgnoreCase, timeout);
                  timedOut = true;
               }
            }
         } while (timedOut);
         Console.WriteLine();
      }   
   }
}
// The example displays output like the following :
//    Processing aa
//    Valid: 'aa' (00.0000779 seconds)
//    
//    Processing aaaa>
//    'aaaa>' is not a valid string. (00.00005 seconds)
//    
//    Processing aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa
//    Valid: 'aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa' (00.0000043 seconds)
//    
//    Processing aaaaaaaaaaaaaaaaaaaaaa>
//    Timeout with 'aaaaaaaaaaaaaaaaaaaaaa>' after 01.00469
//    Changing the timeout interval to 00:00:02
//    Timeout with 'aaaaaaaaaaaaaaaaaaaaaa>' after 02.01202
//    Changing the timeout interval to 00:00:03
//    Timeout with 'aaaaaaaaaaaaaaaaaaaaaa>' after 03.01043
//    Maximum timeout interval of 3 seconds exceeded.
//    
//    Processing aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa>
//    Timeout with 'aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa>' after 03.01018
//    Maximum timeout interval of 3 seconds exceeded.
```

```vb
Imports System.ComponentModel
Imports System.Diagnostics
Imports System.Security
Imports System.Text.RegularExpressions
Imports System.Threading 

Module Example
   Const MaxTimeoutInSeconds As Integer = 3

   Public Sub Main()
      Dim pattern As String = "(a+)+$"    ' DO NOT REUSE THIS PATTERN.
      Dim rgx As New Regex(pattern, RegexOptions.IgnoreCase, TimeSpan.FromSeconds(1))       
      Dim sw As Stopwatch = Nothing

      Dim inputs() As String = { "aa", "aaaa>", 
                                 "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
                                 "aaaaaaaaaaaaaaaaaaaaaa>",
                                 "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa>" }

      For Each inputValue In inputs
         Console.WriteLine("Processing {0}", inputValue)
         Dim timedOut As Boolean = False
         Do 
            Try
               sw = Stopwatch.StartNew()
               ' Display the result.
               If rgx.IsMatch(inputValue) Then
                  sw.Stop()
                  Console.WriteLine("Valid: '{0}' ({1:ss\.fffffff} seconds)", 
                                    inputValue, sw.Elapsed) 
               Else
                  sw.Stop()
                  Console.WriteLine("'{0}' is not a valid string. ({1:ss\.fffff} seconds)", 
                                    inputValue, sw.Elapsed)
               End If
            Catch e As RegexMatchTimeoutException   
               sw.Stop()
               ' Display the elapsed time until the exception.
               Console.WriteLine("Timeout with '{0}' after {1:ss\.fffff}", 
                                 inputValue, sw.Elapsed)
               Thread.Sleep(1500)       ' Pause for 1.5 seconds.

               ' Increase the timeout interval and retry.
               Dim timeout As TimeSpan = e.MatchTimeout.Add(TimeSpan.FromSeconds(1))
               If timeout.TotalSeconds > MaxTimeoutInSeconds Then
                  Console.WriteLine("Maximum timeout interval of {0} seconds exceeded.",
                                    MaxTimeoutInSeconds)
                  timedOut = False
               Else                
                  Console.WriteLine("Changing the timeout interval to {0}", 
                                    timeout) 
                  rgx = New Regex(pattern, RegexOptions.IgnoreCase, timeout)
                  timedOut = True
               End If
            End Try
         Loop While timedOut
         Console.WriteLine()
      Next   
   End Sub 
End Module
' The example displays output like the following:
'    Processing aa
'    Valid: 'aa' (00.0000779 seconds)
'    
'    Processing aaaa>
'    'aaaa>' is not a valid string. (00.00005 seconds)
'    
'    Processing aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa
'    Valid: 'aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa' (00.0000043 seconds)
'    
'    Processing aaaaaaaaaaaaaaaaaaaaaa>
'    Timeout with 'aaaaaaaaaaaaaaaaaaaaaa>' after 01.00469
'    Changing the timeout interval to 00:00:02
'    Timeout with 'aaaaaaaaaaaaaaaaaaaaaa>' after 02.01202
'    Changing the timeout interval to 00:00:03
'    Timeout with 'aaaaaaaaaaaaaaaaaaaaaa>' after 03.01043
'    Maximum timeout interval of 3 seconds exceeded.
'    
'    Processing aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa>
'    Timeout with 'aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa>' after 03.01018
'    Maximum timeout interval of 3 seconds exceeded.
```

### <a name="nonbacktracking-subexpression"></a>Subexpresión sin retroceso

El elemento de lenguaje **(?>** _subexpression_**)** suprime el retroceso en una subexpresión. Es útil para evitar los problemas de rendimiento asociados a las coincidencias con error. 

En el ejemplo siguiente se muestra cómo la supresión del retroceso mejora el rendimiento cuando se usan cuantificadores anidados. Mide el tiempo necesario para que el motor de expresiones regulares determine que una cadena de entrada no coincide con dos expresiones regulares. La primera expresión regular usa el retroceso para intentar buscar una coincidencia de una cadena que contiene una o más apariciones de uno o más dígitos hexadecimales, seguidas de un signo de dos puntos, seguido de uno o más dígitos hexadecimales, seguido de dos signos de dos puntos. La segunda expresión regular es idéntica a la primera, salvo que deshabilita el retroceso. Como muestra el resultado del ejemplo, la mejora de rendimiento que supone deshabilitar el retroceso es significativa.

```csharp
using System;
using System.Diagnostics;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "b51:4:1DB:9EE1:5:27d60:f44:D4:cd:E:5:0A5:4a:D24:41Ad:";
      bool matched;
      Stopwatch sw;

      Console.WriteLine("With backtracking:");
      string backPattern = "^(([0-9a-fA-F]{1,4}:)*([0-9a-fA-F]{1,4}))*(::)$";
      sw = Stopwatch.StartNew();
      matched = Regex.IsMatch(input, backPattern);
      sw.Stop();
      Console.WriteLine("Match: {0} in {1}", Regex.IsMatch(input, backPattern), sw.Elapsed);
      Console.WriteLine();

      Console.WriteLine("Without backtracking:");
      string noBackPattern = "^((?>[0-9a-fA-F]{1,4}:)*(?>[0-9a-fA-F]{1,4}))*(::)$";
      sw = Stopwatch.StartNew();
      matched = Regex.IsMatch(input, noBackPattern);
      sw.Stop();
      Console.WriteLine("Match: {0} in {1}", Regex.IsMatch(input, noBackPattern), sw.Elapsed);
   }
}
// The example displays output like the following:
//       With backtracking:
//       Match: False in 00:00:27.4282019
//       
//       Without backtracking:
//       Match: False in 00:00:00.0001391
```

```vb
Imports System.Diagnostics
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "b51:4:1DB:9EE1:5:27d60:f44:D4:cd:E:5:0A5:4a:D24:41Ad:"
      Dim matched As Boolean
      Dim sw As Stopwatch

      Console.WriteLine("With backtracking:")
      Dim backPattern As String = "^(([0-9a-fA-F]{1,4}:)*([0-9a-fA-F]{1,4}))*(::)$"
      sw = Stopwatch.StartNew()
      matched = Regex.IsMatch(input, backPattern)
      sw.Stop()
      Console.WriteLine("Match: {0} in {1}", Regex.IsMatch(input, backPattern), sw.Elapsed)
      Console.WriteLine()

      Console.WriteLine("Without backtracking:")
      Dim noBackPattern As String = "^((?>[0-9a-fA-F]{1,4}:)*(?>[0-9a-fA-F]{1,4}))*(::)$"
      sw = Stopwatch.StartNew()
      matched = Regex.IsMatch(input, noBackPattern)
      sw.Stop()
      Console.WriteLine("Match: {0} in {1}", Regex.IsMatch(input, noBackPattern), sw.Elapsed)
   End Sub
End Module
' The example displays the following output:
'       With backtracking:
'       Match: False in 00:00:27.4282019
'       
'       Without backtracking:
'       Match: False in 00:00:00.0001391
```

### <a name="lookbehind-assertions"></a>Aserciones de búsqueda tardía

.NET incluye dos elementos de lenguaje, **(?<**=_subexpression_**)** y **(?<!**_subexpression_**)**, que buscan una coincidencia con el carácter o los caracteres anteriores de la cadena de entrada. Ambos elementos de lenguaje son aserciones de ancho cero, es decir, determinan si el carácter o los caracteres que preceden inmediatamente al carácter actual coinciden con *subexpression*, sin avanzar o retroceder. 

**(?<**=_subexpression_**)** es una aserción de búsqueda tardía positiva, es decir, el carácter o los caracteres situados antes de la posición actual deben coincidir con *subexpression*. **(?<!**_subexpression_**)** es una aserción de búsqueda tardía negativa, es decir, el carácter o los caracteres situados antes de la posición actual no deben coincidir con *subexpression*. Tanto las aserciones de búsqueda tardía positivas como las negativas son más útiles cuando *subexpression* es un subconjunto de la *subexpression* anterior. 

En el ejemplo siguiente se usan dos patrones de expresiones regulares equivalentes que validan el nombre de usuario de una dirección de correo electrónico. El primer patrón tiene un rendimiento bajo debido a un retroceso excesivo. El segundo patrón modifica la primera expresión regular reemplazando un cuantificador anidado con una aserción de búsqueda tardía positiva. El resultado del ejemplo muestra el tiempo de ejecución del método [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions)).

```csharp
using System;
using System.Diagnostics;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      Stopwatch sw;
      string input = "aaaaaaaaaaaaaaaaaaaa";
      bool result;

      string pattern = @"^[0-9A-Z]([-.\w]*[0-9A-Z])?@";
      sw = Stopwatch.StartNew();
      result = Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase);
      sw.Stop();
      Console.WriteLine("Match: {0} in {1}", result, sw.Elapsed);

      string behindPattern = @"^[0-9A-Z][-.\w]*(?<=[0-9A-Z])@";
      sw = Stopwatch.StartNew();
      result = Regex.IsMatch(input, behindPattern, RegexOptions.IgnoreCase);
      sw.Stop();
      Console.WriteLine("Match with Lookbehind: {0} in {1}", result, sw.Elapsed);
   }
}
// The example displays output similar to the following:
//       Match: True in 00:00:00.0017549
//       Match with Lookbehind: True in 00:00:00.0000659
```

```vb
Module Example
   Public Sub Main()
      Dim sw As Stopwatch
      Dim input As String = "aaaaaaaaaaaaaaaaaaaa"
      Dim result As Boolean

      Dim pattern As String = "^[0-9A-Z]([-.\w]*[0-9A-Z])?@"
      sw = Stopwatch.StartNew()
      result = Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase)
      sw.Stop()
      Console.WriteLine("Match: {0} in {1}", result, sw.Elapsed)

      Dim behindPattern As String = "^[0-9A-Z][-.\w]*(?<=[0-9A-Z])@"
      sw = Stopwatch.StartNew()
      result = Regex.IsMatch(input, behindPattern, RegexOptions.IgnoreCase)
      sw.Stop()
      Console.WriteLine("Match with Lookbehind: {0} in {1}", result, sw.Elapsed)
   End Sub
End Module
' The example displays output similar to the following:
'       Match: True in 00:00:00.0017549
'       Match with Lookbehind: True in 00:00:00.0000659
```

El primer patrón de la expresión regular, `^[0-9A-Z]([-.\w]*[0-9A-Z])*@, is defined as shown in the following table.`

Modelo | Descripción
------- | ----------- 
`^` | Iniciar la búsqueda de coincidencias en el principio de la cadena.
`[0-9A-Z]` | Buscar coincidencias de un carácter alfanumérico. Esta comparación no distingue mayúsculas de minúsculas, porque se llama al método [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) con la opción [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase).
`[-.\w]*` | Buscar coincidencias con cero, una o más apariciones de un guión, un punto o un carácter alfabético. 
`[0-9A-Z]` | Buscar coincidencias de un carácter alfanumérico. 
`([-.\w]*[0-9A-Z])*` | Buscar coincidencias con cero o más apariciones de la combinación de cero o más guiones, puntos o caracteres alfabéticos, seguidos de un carácter alfanumérico. Este es el primer grupo de captura.
`@` | Buscar coincidencias con una arroba ("@").
 
El segundo patrón de expresión regular, `^[0-9A-Z][-.\w]*(?<=[0-9A-Z])@`, emplea una aserción de búsqueda tardía positiva. Se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`^` | Iniciar la búsqueda de coincidencias en el principio de la cadena.
`[0-9A-Z]` | Buscar coincidencias de un carácter alfanumérico. Esta comparación no distingue mayúsculas de minúsculas, porque se llama al método [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) con la opción [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase).
`[-.\w]*` | Buscar coincidencias con cero o más apariciones de un guión, un punto o un carácter alfabético.
`(?<=[0-9A-Z])` | Volver a examinar el último carácter coincidente y continuar con la coincidencia si es alfanumérica. Tenga en cuenta que los caracteres alfanuméricos son un subconjunto del conjunto formado por puntos, guiones y todos los caracteres alfabéticos.
`@` | Buscar coincidencias con una arroba ("@").
 
### <a name="lookahead-assertions"></a>Aserciones de búsqueda anticipada

.NET incluye dos elementos de lenguaje, **(?**=_subexpression_**)** y **(?!**_subexpression_**)**, que buscan una coincidencia con el carácter o los caracteres siguientes de la cadena de entrada. Ambos elementos de lenguaje son aserciones de ancho cero, es decir, determinan si el carácter o los caracteres que siguen inmediatamente al carácter actual coinciden con *subexpression*, sin avanzar o retroceder. 

**(?**=_subexpression_**)** es una aserción de búsqueda anticipada positiva, es decir, el carácter o los caracteres situados después de la posición actual deben coincidir con *subexpression*. **(?!**_subexpression_**)** es una aserción de búsqueda anticipada negativa, es decir, el carácter o los caracteres situados después de la posición actual no deben coincidir con *subexpression*. Tanto las aserciones de búsqueda anticipada positivas como las negativas son más útiles cuando *subexpression* es un subconjunto de la siguiente *subexpression*. 

En el ejemplo siguiente se usan dos patrones de expresiones regulares que validan un nombre de tipo completo. El primer patrón tiene un rendimiento bajo debido a un retroceso excesivo. El segundo modifica la primera expresión regular reemplazando un cuantificador anidado con una aserción de búsqueda anticipada positiva. El resultado del ejemplo muestra el tiempo de ejecución del método [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions)).

```csharp
using System;
using System.Diagnostics;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "aaaaaaaaaaaaaaaaaaaaaa.";
      bool result;
      Stopwatch sw;

      string pattern = @"^(([A-Z]\w*)+\.)*[A-Z]\w*$";
      sw = Stopwatch.StartNew();
      result = Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase);
      sw.Stop();
      Console.WriteLine("{0} in {1}", result, sw.Elapsed);

      string aheadPattern = @"^((?=[A-Z])\w+\.)*[A-Z]\w*$";
      sw = Stopwatch.StartNew();
      result = Regex.IsMatch(input, aheadPattern, RegexOptions.IgnoreCase);
      sw.Stop();
      Console.WriteLine("{0} in {1}", result, sw.Elapsed);
   }
}
// The example displays the following output:
//       False in 00:00:03.8003793
//       False in 00:00:00.0000866
```

```vb
Imports System.Diagnostics
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "aaaaaaaaaaaaaaaaaaaaaa."
      Dim result As Boolean
      Dim sw As Stopwatch

      Dim pattern As String = "^(([A-Z]\w*)+\.)*[A-Z]\w*$"
      sw = Stopwatch.StartNew()
      result = Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase)
      sw.Stop()
      Console.WriteLine("{0} in {1}", result, sw.Elapsed)

      Dim aheadPattern As String = "^((?=[A-Z])\w+\.)*[A-Z]\w*$"
      sw = Stopwatch.StartNew()
      result = Regex.IsMatch(input, aheadPattern, RegexOptions.IgnoreCase)
      sw.Stop()
      Console.WriteLine("{0} in {1}", result, sw.Elapsed)
   End Sub
End Module
' The example displays the following output:
'       False in 00:00:03.8003793
'       False in 00:00:00.0000866
```

El primer patrón de expresión regular, `^(([A-Z]\w*)+\.)*[A-Z]\w*$`, se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`^` | Iniciar la búsqueda de coincidencias en el principio de la cadena.
`([A-Z]\w*)+\.` | Buscar coincidencias con un carácter alfabético (A-Z) seguido de cero o más caracteres alfabéticos una o más veces, seguidas de un punto. Esta comparación no distingue mayúsculas de minúsculas, porque se llama al método [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) con la opción [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase).
`(([A-Z]\w*)+\.)*` | Buscar coincidencias con el patrón anterior cero o más veces. 
`[A-Z]\w*` | Buscar coincidencias con un carácter alfabético seguido de cero o más caracteres alfabéticos.
`$` | Finalizar la búsqueda de coincidencias al final de la cadena de entrada.
 

El segundo patrón de expresión regular, `^((?=[A-Z])\w+\.)*[A-Z]\w*$`, emplea una aserción de búsqueda anticipada positiva. Se define como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`^` | Iniciar la búsqueda de coincidencias en el principio de la cadena.
`(?=[A-Z])` | Examinar hacia delante el primer carácter y continuar la búsqueda de coincidencias si es alfabético (A-Z). Esta comparación no distingue mayúsculas de minúsculas, porque se llama al método [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) con la opción [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase).
`\w+\.` | Buscar coincidencias con uno o más caracteres alfabéticos seguidos de un punto.
`((?=[A-Z])\w+\.)*` | Buscar coincidencias con el patrón de uno o varios caracteres alfabéticos seguidos de un punto una o varias veces. El carácter alfabético inicial debe ser alfabético. 
`[A-Z]\w*` | Buscar coincidencias con un carácter alfabético seguido de cero o más caracteres alfabéticos.
`$` | Finalizar la búsqueda de coincidencias al final de la cadena de entrada.
 
## <a name="see-also"></a>Vea también

[Expresiones regulares de .NET](regular-expressions.md)

[Lenguaje de expresiones regulares: referencia rápida](quick-ref.md)

[Cuantificadores en expresiones regulares](quantifiers.md)

[Construcciones de alternancia en expresiones regulares](alternation.md)

[Construcciones de agrupamiento en expresiones regulares](grouping.md)




<!--HONumber=Nov16_HO3-->


