---
title: "Cadenas de formato TimeSpan estándar"
description: "Cadenas de formato TimeSpan estándar"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 4e0f02f1-4abd-47b5-8995-5c3ff45b0ce1
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: a31f0da1f5b502d8b983f4d496c4b9a520b0309c

---

# <a name="standard-timespan-format-strings"></a>Cadenas de formato TimeSpan estándar

Una cadena de formato [TimeSpan](xref:System.TimeSpan) estándar usa un único especificador de formato para definir la representación de texto de un valor [TimeSpan](xref:System.TimeSpan) resultante de una operación de formato. Cualquier cadena de formato que contenga más de un carácter, incluido el espacio en blanco, se interpreta como una cadena de formato [TimeSpan](xref:System.TimeSpan) personalizado. Para obtener más información, consulte [Cadenas con formato numérico personalizado](custom-timespan.md).

Las representaciones de cadena de los valores [TimeSpan](xref:System.TimeSpan) se generan mediante llamadas a las sobrecargas del método [TimeSpan.ToString](xref:System.TimeSpan.ToString), y también mediante métodos que admiten formatos compuestos, como [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)). Para obtener más información, consulte [Aplicar formato a tipos](formatting-types.md) y [Formatos compuestos](composite-format.md). En el siguiente ejemplo se muestra el uso de cadenas de formato estándar en operaciones de formato.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      TimeSpan duration = new TimeSpan(1, 12, 23, 62);
      string output = "Time of Travel: " + duration.ToString("c");
      Console.WriteLine(output);

      Console.WriteLine("Time of Travel: {0:c}", duration); 
   }
}
// The example displays the following output:
//       Time of Travel: 1.12:24:02
//       Time of Travel: 1.12:24:02
```

```vb
Module Example
   Public Sub Main()
      Dim duration As New TimeSpan(1, 12, 23, 62)
      Dim output As String = "Time of Travel: " + duration.ToString("c")
      Console.WriteLine(output)

      Console.WriteLine("Time of Travel: {0:c}", duration) 
   End Sub
End Module
' The example displays the following output:
'       Time of Travel: 1.12:24:02
'       Time of Travel: 1.12:24:02
```

Las cadenas de formato [TimeSpan](xref:System.TimeSpan) estándar también se usan en los métodos [TimeSpan.ParseExact](xref:System.TimeSpan.ParseExact(System.String,System.String,System.IFormatProvider)) y [TimeSpan.TryParseExact](xref:System.TimeSpan.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.TimeSpanStyles,System.TimeSpan@)) para definir el formato de las cadenas de entrada requerido para las operaciones de análisis. (Estas operaciones convierten la representación de cadena de un valor en ese valor.) En el siguiente ejemplo, se muestra el uso de cadenas de formato estándar en operaciones de análisis.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string value = "1.03:14:56.1667";
      TimeSpan interval;
      try {
         interval = TimeSpan.ParseExact(value, "c", null);
         Console.WriteLine("Converted '{0}' to {1}", value, interval);
      }   
      catch (FormatException) {
         Console.WriteLine("{0}: Bad Format", value);
      }   
      catch (OverflowException) {
         Console.WriteLine("{0}: Out of Range", value);
      }

      if (TimeSpan.TryParseExact(value, "c", null, out interval))
         Console.WriteLine("Converted '{0}' to {1}", value, interval);
      else
         Console.WriteLine("Unable to convert {0} to a time interval.", 
                           value);
   }
}
// The example displays the following output:
//       Converted '1.03:14:56.1667' to 1.03:14:56.1667000
//       Converted '1.03:14:56.1667' to 1.03:14:56.1667000
```

```vb
Module Example
   Public Sub Main()
      Dim value As String = "1.03:14:56.1667"
      Dim interval As TimeSpan
      Try
         interval = TimeSpan.ParseExact(value, "c", Nothing)
         Console.WriteLine("Converted '{0}' to {1}", value, interval)
      Catch e As FormatException
         Console.WriteLine("{0}: Bad Format", value)
      Catch e As OverflowException
         Console.WriteLine("{0}: Out of Range", value)
      End Try

      If TimeSpan.TryParseExact(value, "c", Nothing, interval) Then
         Console.WriteLine("Converted '{0}' to {1}", value, interval)
      Else
         Console.WriteLine("Unable to convert {0} to a time interval.", 
                           value)
      End If                
   End Sub
End Module
' The example displays the following output:
'       Converted '1.03:14:56.1667' to 1.03:14:56.1667000
'       Converted '1.03:14:56.1667' to 1.03:14:56.1667000
```

En la tabla siguiente se muestran los especificadores de formato de intervalo de tiempo estándar.

Especificador de formato | Name | Descripción | Ejemplos
---------------- | ---- | ----------- | --------
"c" | Formato constante (invariable) | Este especificador no tiene en cuenta la referencia cultural. Adopta la forma [-][d’.’]hh’:’mm’:’ss[‘.’fffffff]. (Las cadenas de formato "t" y "T" producen los mismos resultados). | `TimeSpan.Zero -> 00:00:00`; `New TimeSpan(0, 0, 30, 0) -> 00:30:00`; `New TimeSpan(3, 17, 25, 30, 500) -> 3.17:25:30.5000000`
"g" | Formato corto general | Este especificador solo genera lo necesario. Responde a la referencia cultural y adopta la forma [-][d’:’]h’:’mm’:’ss[.FFFFFFF]. | `New TimeSpan(1, 3, 16, 50, 500) -> 1:3:16:50.5 (en-US)`; `New TimeSpan(1, 3, 16, 50, 500) -> 1:3:16:50,5 (fr-FR)`; `New TimeSpan(1, 3, 16, 50, 599) -> 1:3:16:50.599 (en-US)`; `New TimeSpan(1, 3, 16, 50, 599) -> 1:3:16:50,599 (fr-FR)`
"G" | Formato general largo | Este especificador siempre genera días y siete dígitos fraccionarios. Responde a la referencia cultural y adopta la forma [-]d’:’hh’:’mm’:’ss.fffffff. | `New TimeSpan(18, 30, 0) -> 0:18:30:00.0000000 (en-US)`; `New TimeSpan(18, 30, 0) -> 0:18:30:00,0000000 (fr-FR)` 

## <a name="the-constant-c-format-specifier"></a>Especificador de formato constante ("c")

El especificador de formato "c" devuelve la representación de cadena de un valor [TimeSpan](xref:System.TimeSpan) de la siguiente forma:

[-][_d_.]_hh_:_mm_:_ss_[._fffffff_]

Los elementos de los corchetes ([ y ]) son opcionales. El punto (.) y los dos puntos (:) son símbolos literales. En la siguiente tabla se describen los elementos restantes. 

Elemento | Descripción
------- | -----------
- | Signo negativo opcional, que indica un intervalo de tiempo negativo.
*d* | Número opcional de días, sin ceros a la izquierda.
*hh* | Número de horas, entre "00" y "23".
*mm* | Número de minutos, entre "00" y "59".
*ss* | Número de segundos, entre "00" y "59".
*fffffff* | La parte fraccionaria opcional de un segundo. Su valor puede oscilar entre "0000001" (un tic o una diez millonésima de segundo) y "9999999" (9.999.999 diez millonésimas de segundo, o un segundo menos un tic). 

A diferencia de los especificadores de formato de "g" y "G", el especificador de formato "c" no tiene en cuenta la referencia cultural. Produce la representación de cadena de un valor [TimeSpan](xref:System.TimeSpan) que es invariable y común a todas las versiones anteriores de .NET previas a .NET Framework 4. "c" es la cadena de formato [TimeSpan](xref:System.TimeSpan) predeterminado; el método [TimeSpan.ToString](xref:System.TimeSpan.ToString) da formato a un valor de intervalo de tiempo mediante la cadena de formato "c".

> [!NOTE]
> [TimeSpan](xref:System.TimeSpan) también admite las cadenas de formato estándar "t" y "T", cuyo comportamiento es idéntico al de la cadena de formato estándar "c".

En el ejemplo siguiente se crea una instancia de dos objetos [TimeSpan](xref:System.TimeSpan), que se usan para realizar operaciones aritméticas, y se muestra el resultado. En cada caso, se usa un formato compuesto para mostrar el valor [TimeSpan](xref:System.TimeSpan) mediante el especificador de formato "c".

```csharp
using System;

public class Example
{
   public static void Main()
   {
      TimeSpan interval1, interval2;
      interval1 = new TimeSpan(7, 45, 16);
      interval2 = new TimeSpan(18, 12, 38);

      Console.WriteLine("{0:c} - {1:c} = {2:c}", interval1, 
                        interval2, interval1 - interval2);
      Console.WriteLine("{0:c} + {1:c} = {2:c}", interval1, 
                        interval2, interval1 + interval2);

      interval1 = new TimeSpan(0, 0, 1, 14, 365);
      interval2 = TimeSpan.FromTicks(2143756);  
      Console.WriteLine("{0:c} + {1:c} = {2:c}", interval1, 
                        interval2, interval1 + interval2);
   }
}
// The example displays the following output:
//       07:45:16 - 18:12:38 = -10:27:22
//       07:45:16 + 18:12:38 = 1.01:57:54
//       00:01:14.3650000 + 00:00:00.2143756 = 00:01:14.5793756
```

```vb
Module Example
   Public Sub Main()
      Dim interval1, interval2 As TimeSpan
      interval1 = New TimeSpan(7, 45, 16)
      interval2 = New TimeSpan(18, 12, 38)

      Console.WriteLine("{0:c} - {1:c} = {2:c}", interval1, 
                        interval2, interval1 - interval2)
      Console.WriteLine("{0:c} + {1:c} = {2:c}", interval1, 
                        interval2, interval1 + interval2)

      interval1 = New TimeSpan(0, 0, 1, 14, 365)
      interval2 = TimeSpan.FromTicks(2143756)      
      Console.WriteLine("{0:c} + {1:c} = {2:c}", interval1, 
                        interval2, interval1 + interval2)
   End Sub
End Module
' The example displays the following output:
'       07:45:16 - 18:12:38 = -10:27:22
'       07:45:16 + 18:12:38 = 1.01:57:54
'       00:01:14.3650000 + 00:00:00.2143756 = 00:01:14.5793756
```

## <a name="the-general-short-g-format-specifier"></a>Especificador de formato corto general ("g")

El especificador de formato [TimeSpan](xref:System.TimeSpan) "g" devuelve la representación de cadena de un valor [TimeSpan](xref:System.TimeSpan) en una forma compacta, incluyendo únicamente los elementos que sean necesarios. Tiene la forma siguiente:

[-][_d_:]_h_:_mm_:_ss_[._FFFFFFF_]

Los elementos de los corchetes ([ y ]) son opcionales. Los dos puntos (:) son un símbolo literal. En la siguiente tabla se describen los elementos restantes.

Elemento | Descripción
------- | -----------
- | Signo negativo opcional, que indica un intervalo de tiempo negativo.
*d* | Número opcional de días, sin ceros a la izquierda.
*hh* | El número de horas, entre "0" a "23", sin ceros a la izquierda. 
*mm* | Número de minutos, entre "00" y "59".
*ss* | Número de segundos, entre "00" y "59".
. | Separador de fracciones de segundo.
*FFFFFFF* | Fracciones de segundo. Se muestra la menor cantidad de dígitos posible.

Al igual que el especificador de formato "G", el especificador de formato "g" se localiza. Su separador de fracciones de segundo se basa en la referencia cultural actual.

En el ejemplo siguiente se crea una instancia de dos objetos [TimeSpan](xref:System.TimeSpan), que se usan para realizar operaciones aritméticas, y se muestra el resultado. En cada caso, se usa un formato compuesto para mostrar el valor [TimeSpan](xref:System.TimeSpan) mediante el especificador de formato "g". Además, se da formato al valor [TimeSpan](xref:System.TimeSpan) mediante las convenciones de formato de la referencia cultural del sistema actual (que, en este caso, es inglés - Estados Unidos o en-US) y la referencia cultural de francés de Francia (fr-FR).

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      TimeSpan interval1, interval2;
      interval1 = new TimeSpan(7, 45, 16);
      interval2 = new TimeSpan(18, 12, 38);

      Console.WriteLine("{0:g} - {1:g} = {2:g}", interval1, 
                        interval2, interval1 - interval2);
      Console.WriteLine(String.Format(new CultureInfo("fr-FR"), 
                        "{0:g} + {1:g} = {2:g}", interval1, 
                        interval2, interval1 + interval2));

      interval1 = new TimeSpan(0, 0, 1, 14, 36);
      interval2 = TimeSpan.FromTicks(2143756);      
      Console.WriteLine("{0:g} + {1:g} = {2:g}", interval1, 
                        interval2, interval1 + interval2);
   }
}
// The example displays the following output:
//       7:45:16 - 18:12:38 = -10:27:22
//       7:45:16 + 18:12:38 = 1:1:57:54
//       0:01:14.036 + 0:00:00.2143756 = 0:01:14.2503756
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim interval1, interval2 As TimeSpan
      interval1 = New TimeSpan(7, 45, 16)
      interval2 = New TimeSpan(18, 12, 38)

      Console.WriteLine("{0:g} - {1:g} = {2:g}", interval1, 
                        interval2, interval1 - interval2)
      Console.WriteLine(String.Format(New CultureInfo("fr-FR"), 
                        "{0:g} + {1:g} = {2:g}", interval1, 
                        interval2, interval1 + interval2))

      interval1 = New TimeSpan(0, 0, 1, 14, 36)
      interval2 = TimeSpan.FromTicks(2143756)      
      Console.WriteLine("{0:g} + {1:g} = {2:g}", interval1, 
                        interval2, interval1 + interval2)
   End Sub
End Module
' The example displays the following output:
'       7:45:16 - 18:12:38 = -10:27:22
'       7:45:16 + 18:12:38 = 1:1:57:54
'       0:01:14.036 + 0:00:00.2143756 = 0:01:14.2503756
```

## <a name="the-general-long-g-format-specifier"></a>Especificador de formato largo general ("G")

El especificador de formato [TimeSpan](xref:System.TimeSpan) "G" devuelve la representación de cadena de un valor [TimeSpan](xref:System.TimeSpan) en un formato largo que siempre incluye los días y las fracciones de segundo. La cadena resultante del especificador de formato estándar "G" tiene la forma siguiente:

[-]*d*:*hh*:*mm*:*ss*.*fffffff*

Los elementos de los corchetes ([ y ]) son opcionales. Los dos puntos (:) son un símbolo literal. En la siguiente tabla se describen los elementos restantes.

Elemento | Descripción
------- | -----------
- | Signo negativo opcional, que indica un intervalo de tiempo negativo.
*d* | Número opcional de días, sin ceros a la izquierda.
*hh* | Número de horas, entre "0" y "23". 
*mm* | Número de minutos, entre "00" y "59".
*ss* | Número de segundos, entre "00" y "59".
. | Separador de fracciones de segundo.
*fffffff* | Fracciones de segundo.

Al igual que el especificador de formato "G", el especificador de formato "g" se localiza. Su separador de fracciones de segundo se basa en la referencia cultural actual.

En el ejemplo siguiente se crea una instancia de dos objetos [TimeSpan](xref:System.TimeSpan), que se usan para realizar operaciones aritméticas, y se muestra el resultado. En cada caso, se usa un formato compuesto para mostrar el valor [TimeSpan](xref:System.TimeSpan) mediante el especificador de formato "G". Además, se da formato al valor [TimeSpan](xref:System.TimeSpan) mediante las convenciones de formato de la referencia cultural del sistema actual (que, en este caso, es inglés - Estados Unidos o en-US) y la referencia cultural de francés de Francia (fr-FR). 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      TimeSpan interval1, interval2;
      interval1 = new TimeSpan(7, 45, 16);
      interval2 = new TimeSpan(18, 12, 38);

      Console.WriteLine("{0:G} - {1:G} = {2:G}", interval1, 
                        interval2, interval1 - interval2);
      Console.WriteLine(String.Format(new CultureInfo("fr-FR"), 
                        "{0:G} + {1:G} = {2:G}", interval1, 
                        interval2, interval1 + interval2));

      interval1 = new TimeSpan(0, 0, 1, 14, 36);
      interval2 = TimeSpan.FromTicks(2143756);      
      Console.WriteLine("{0:G} + {1:G} = {2:G}", interval1, 
                        interval2, interval1 + interval2);
   }
}
// The example displays the following output:
//       0:07:45:16.0000000 - 0:18:12:38.0000000 = -0:10:27:22.0000000
//       0:07:45:16,0000000 + 0:18:12:38,0000000 = 1:01:57:54,0000000
//       0:00:01:14.0360000 + 0:00:00:00.2143756 = 0:00:01:14.2503756
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim interval1, interval2 As TimeSpan
      interval1 = New TimeSpan(7, 45, 16)
      interval2 = New TimeSpan(18, 12, 38)

      Console.WriteLine("{0:G} - {1:G} = {2:G}", interval1, 
                        interval2, interval1 - interval2)
      Console.WriteLine(String.Format(New CultureInfo("fr-FR"), 
                        "{0:G} + {1:G} = {2:G}", interval1, 
                        interval2, interval1 + interval2))

      interval1 = New TimeSpan(0, 0, 1, 14, 36)
      interval2 = TimeSpan.FromTicks(2143756)      
      Console.WriteLine("{0:G} + {1:G} = {2:G}", interval1, 
                        interval2, interval1 + interval2)
   End Sub
End Module
' The example displays the following output:
'       0:07:45:16.0000000 - 0:18:12:38.0000000 = -0:10:27:22.0000000
'       0:07:45:16,0000000 + 0:18:12:38,0000000 = 1:01:57:54,0000000
'       0:00:01:14.0360000 + 0:00:00:00.2143756 = 0:00:01:14.2503756
```

## <a name="see-also"></a>Vea también

[Aplicar formato a tipos](formatting-types.md)

[Formatos compuestos](composite-format.md)

[Analizar cadenas](parsing-strings.md)




<!--HONumber=Nov16_HO1-->


