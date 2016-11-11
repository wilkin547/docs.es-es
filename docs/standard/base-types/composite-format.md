---
title: Formatos compuestos
description: Formatos compuestos
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/25/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a01efc8f-c242-4535-bd32-acd0032d9590
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 9bcf2ff74237f7e7faf2890849c2d68a0a602353

---

# <a name="composite-formatting"></a>Formatos compuestos

La característica de formato compuesto de .NET toma una lista de objetos y una cadena de formato compuesto como entrada. Una cadena de formato compuesto está formada por texto fijo combinado con marcadores de posición indizados, que reciben el nombre de elementos de formato, y que se corresponden con los objetos de la lista. La operación de formato genera una cadena de resultado compuesta por el texto fijo original combinado con la representación de cadena de los objetos de la lista. 

La característica de formato compuesto se admite mediante métodos como los siguientes: 

* [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)), que devuelve una cadena de resultado con formato. 

* [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider, System.String, System.Object), que anexa una cadena de resultado con formato a un objeto [StringBuilder](xref:System.Text.StringBuilder).

* Algunas sobrecargas del método `WriteLine` de [Console](xref:System.Console), que muestran una cadena de resultado con formato en la consola.  

* Algunas sobrecargas del método `WriteLine` de [TextWriter](xref:System.IO.TextWriter), que escriben la cadena de resultado con formato en una secuencia o un archivo. Las clases derivadas de [TextWriter](xref:System.IO.TextWriter), como [StreamWriter](xref:System.IO.StreamWriter), también comparten esta funcionalidad.

* [Debug.WriteLine(String, Object[])](xref:System.Diagnostics.Debug.WriteLine(System.String,System.Object[])), que genera un mensaje con formato en los agentes de escucha de seguimiento. 

* Los métodos [Trace.TraceError(String, Object[])](xref:System.Diagnostics.Trace.TraceError(System.String,System.Object[])), [Trace.TraceInformation(String, Object[])](xref:System.Diagnostics.Trace.TraceInformation(System.String,System.Object[])) y [Trace.TraceWarning(String, Object[])](xref:System.Diagnostics.Trace.TraceWarning(System.String,System.Object[])), que generan mensajes con formato en los agentes de escucha de seguimiento. 

* El método [TraceSource.TraceInformation(String, Object[])](xref:System.Diagnostics.TraceSource.TraceInformation(System.String,System.Object[])), que escribe un método informativo en los agentes de escucha de seguimiento. 

## <a name="composite-format-string"></a>Cadena de formato compuesto

Los métodos compatibles con la característica de formato compuesto utilizan como argumentos una cadena de formato compuesto y una lista de objetos. Una cadena de formato compuesto consta de cero o más ejecuciones de texto fijo combinadas con uno o varios elementos de formato. El texto fijo es cualquier cadena que elija y cada elemento de formato se corresponde con un objeto o estructura de conversión boxing de la lista. La característica de formato compuesto devuelve una nueva cadena de resultado donde cada elemento de formato se reemplaza por la representación de cadena del objeto correspondiente de la lista.

Tenga en cuenta el siguiente fragmento de código [Format](xref:System.String.Format(System.String.Format(System.IFormatProvider,System.String,System.Object)).

```csharp
string name = "Fred";
String.Format("Name = {0}, hours = {1:hh}", name, DateTime.Now);
```

```vb
Dim name As String = "Fred"
String.Format("Name = {0}, hours = {1:hh}", name, DateTime.Now)
```

El texto fijo es `"Name = "` y `", hours = "`. Los elementos de formato son `"{0}"`, cuyo índice es 0, que corresponde al objeto `name`, y `"{1:hh}"`, cuyo índice es 1, que corresponde al objeto `DateTime.Now`.

## <a name="format-item-syntax"></a>Sintaxis de elemento de formato

Cada elemento de formato presenta la siguiente sintaxis, formada por los siguientes componentes:

__{__*index*[,*alignment*][:*formatString*]__}__

Las llaves ("{" y "}") son necesarias. 
 
### <a name="index-component"></a>Index (Componente)

El componente *index* obligatorio, denominado también especificador de parámetros, es un número que empieza por 0 que identifica un elemento correspondiente de la lista de objetos. O sea, el elemento de formato cuyo especificador de parámetro es 0 da formato al primer objeto de la lista, el elemento de formato cuyo especificador de parámetro es 1 da formato al segundo objeto de la lista, etc. En el ejemplo siguiente se incluyen cuatro especificadores de parámetros, numerados del cero al tres, para representar números primos menores que diez: 

```csharp
string primes;
primes = String.Format("Prime numbers less than 10: {0}, {1}, {2}, {3}",
                       2, 3, 5, 7 );
Console.WriteLine(primes);
// The example displays the following output:
//      Prime numbers less than 10: 2, 3, 5, 7
```

```vb
Dim primes As String
primes = String.Format("Prime numbers less than 10: {0}, {1}, {2}, {3}",
                       2, 3, 5, 7 )
Console.WriteLine(primes)
' The example displays the following output:
'      Prime numbers less than 10: 2, 3, 5, 7
```

Los elementos de formato múltiple se pueden referir al mismo elemento de la lista de objetos mediante la especificación del mismo especificador de parámetro. Por ejemplo, para dar al mismo valor numérico un formato hexadecimal, científico y numérico, especifique una cadena de formato compuesto como: "0x{0:X} {0:E} {0:N}", como se muestra en el siguiente ejemplo. 

```csharp
string multiple = String.Format("0x{0:X} {0:E} {0:N}",
                                Int64.MaxValue);
Console.WriteLine(multiple);
// The example displays the following output:
//      0x7FFFFFFFFFFFFFFF 9.223372E+018 9,223,372,036,854,775,807.00
```

```vb
Dim multiple As String = String.Format("0x{0:X} {0:E} {0:N}",
                                       Int64.MaxValue)
Console.WriteLine(multiple)
' The example displays the following output:
'      0x7FFFFFFFFFFFFFFF 9.223372E+018 9,223,372,036,854,775,807.00
```

Cada elemento de formato puede hacer referencia a cualquier objeto de la lista. Por ejemplo, si existen tres objetos, se puede dar formato al segundo, primero y tercer objeto mediante la especificación de una cadena de formato compuesto como ésta: "{1} {0} {2}". Un objeto al que no hace referencia ningún elemento de formato se omite. Se inicia una [FormatException](xref:System.FormatException) en tiempo de ejecución si un especificador de parámetro designa un elemento fuera de los límites de la lista de objetos.

### <a name="alignment-component"></a>Alignment (Componente)

El componente opcional *alignment* es un entero con signo que indica el ancho de campo con formato preferido. Si el valor de *alignment* es menor que la longitud de la cadena con formato, se omite *alignment* y se usa la longitud de la cadena con formato como el ancho de campo. Los datos con formato del campo están alineados a la derecha si *alignment* es positivo y a la izquierda si *alignment* es negativo. Si hace falta relleno, se utiliza un espacio en blanco. Si se especifica *alignment*, es necesaria la coma.

El siguiente ejemplo define dos matrices, que contiene los nombres de empleados y otra contiene las horas que han trabajado en un período de dos semanas. La cadena de formato compuesto alinea a la izquierda los nombres en un campo de 20 caracteres y alinea a la derecha las horas en un campo de 5 caracteres. Tenga en cuenta que la cadena de formato estándar "N1" también se usa para dar formato a las horas con un dígito fraccionario. 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string[] names = { "Adam", "Bridgette", "Carla", "Daniel",
                         "Ebenezer", "Francine", "George" };
      decimal[] hours = { 40, 6.667m, 40.39m, 82, 40.333m, 80,
                                 16.75m };

      Console.WriteLine("{0,-20} {1,5}\n", "Name", "Hours");
      for (int ctr = 0; ctr < names.Length; ctr++)
         Console.WriteLine("{0,-20} {1,5:N1}", names[ctr], hours[ctr]);

   }
}
// The example displays the following output:
//       Name                 Hours
//
//       Adam                  40.0
//       Bridgette              6.7
//       Carla                 40.4
//       Daniel                82.0
//       Ebenezer              40.3
//       Francine              80.0
//       George                16.8
```

```vb
Module Example
   Public Sub Main()
      Dim names() As String = { "Adam", "Bridgette", "Carla", "Daniel",
                                "Ebenezer", "Francine", "George" }
      Dim hours() As Decimal = { 40, 6.667d, 40.39d, 82, 40.333d, 80,
                                 16.75d }

      Console.WriteLine("{0,-20} {1,5}", "Name", "Hours")
      Console.WriteLine()
      For ctr As Integer = 0 To names.Length - 1
         Console.WriteLine("{0,-20} {1,5:N1}", names(ctr), hours(ctr))
      Next
   End Sub
End Module
' The example displays the following output:
'       Name                 Hours
'
'       Adam                  40.0
'       Bridgette              6.7
'       Carla                 40.4
'       Daniel                82.0
'       Ebenezer              40.3
'       Francine              80.0
'       George                16.8
```

### <a name="format-string-component"></a>Format String (Componente)

El componente *formatString* opcional es una cadena de formato adecuada para el tipo de objeto al que se da formato. Especifique una cadena de formato numérico estándar o personalizado si el objeto correspondiente es un valor numérico, una cadena de formato de fecha y hora estándar o personalizado si el objeto correspondiente es un objeto [DateTime](xref:System.DateTime) o una [cadena de formato de enumeración](enumeration-format.md) si el objeto correspondiente es un valor de enumeración. Si no se especifica *formatString*, se usa el especificador de formato general ("G") para un tipo numérico, de fecha y hora o de enumeración. Si se especifica *formatString*, son necesarios los dos puntos.

En la tabla siguiente se enumeran los tipos o las categorías de tipo de la biblioteca de clases de .NET Framework que admiten un conjunto predefinido de cadenas de formato, y se proporcionan vínculos a temas que muestran las cadenas de formato admitidas. Observe que la asignación de formato a cadenas es un mecanismo extensible que permite definir cadenas de formato nuevas para todos los tipos existentes, así como definir un conjunto de cadenas de formato admitidas por un tipo definido por la aplicación. Para obtener más información, consulte los temas de las interfaces [IFormattable](xref:System.IFormattable) e [ICustomFormatter](xref:System.ICustomFormatter). 

Tipo o categoría de tipo | Vea
--------------------- | ---
Tipos de fecha y hora ([DateTime](xref:System.DateTime), [DateTimeOffset](xref:System.DateTimeOffset)) | [Cadenas con formato de fecha y hora estándar](standard-datetime.md), [Cadenas con formato de fecha y hora personalizado](custom-datetime.md)
Tipos de enumeración (todos los tipos derivados de [System.Enum](xref:System.Enum)) | [Cadenas de formato de enumeración](enumeration-format.md)
Tipos numéricos ([BigInteger](xref:System.Numerics.BigInteger), [Byte](xref:System.Byte), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64)) | [Cadenas con formato numérico estándar](standard-numeric.md), [Cadenas con formato numérico personalizado](custom-numeric.md)
[GUID](xref:System.Guid) | [Guid.ToString(String)](xref:System.Guid.ToString(System.String))
[TimeSpan](xref:System.TimeSpan) | [Cadenas de formato TimeSpan estándar](standard-timespan.md), [Cadenas de formato TimeSpan personalizado](custom-timespan.md)

### <a name="escaping-braces"></a>Llaves de escape

Las llaves de apertura y de cierre se interpretan como el inicio y el final de un elemento de formato. Por lo tanto, debe utilizar una secuencia de escape para que se muestre una llave de apertura o de cierre literal. Especifique dos llaves de apertura ("{{") en el texto fijo para que se muestre una llave de apertura ("{"), o dos llaves de cierre ("}}") para que se muestre una llave de cierre ("}"). Las llaves de un elemento de formato se interpretan secuencialmente, en el orden en que se encuentran. No se admite la interpretación de llaves anidadas. 

El modo de interpretar las llaves de escape puede dar lugar a resultados inesperados. Tomemos como ejemplo el elemento de formato "{{{0:D}}}", cuyo propósito es mostrar una llave de apertura, un valor numérico con formato de número decimal y una llave de cierre; pero que, en la práctica, se interpreta de la siguiente forma: 

1. Las dos primeras llaves de apertura ("{{") son llaves de escape y dan lugar a en una llave de apertura. 

2. Los tres caracteres siguientes ("{0:") se interpretan como el inicio de un elemento de formato.

3. El siguiente carácter ("D") se interpretaría como el especificador de formato numérico estándar decimal, pero las dos llaves de escape siguientes ("}}") dan lugar a una única llave. Como la cadena resultante ("D}") no es un especificador de formato numérico estándar, se interpreta como una cadena de formato personalizado que significa que debe mostrarse la cadena literal "D}". 

4. La última llave ("}") se interpreta como el final del elemento de formato. 

5. Como resultado final, se muestra la cadena literal "{D}". No se muestra el valor numérico al que se debía dar formato.

Una forma de escribir código e impedir que las llaves de escape y los elementos de formato se malinterpreten consiste en dar formato a las llaves y elementos de formato por separado. Es decir, en la primera operación de formato mostrar una llave de apertura literal, en la siguiente operación mostrar el resultado del elemento de formato y, por último, en la operación final mostrar una llave de cierre literal. En el ejemplo siguiente se muestra este enfoque.

```csharp
int value = 6324;
string output = string.Format("{0}{1:D}{2}", 
                             "{", value, "}");
Console.WriteLine(output);
// The example displays the following output:
//       {6324} 
```

```vb
Dim value As Integer = 6324
Dim output As String = String.Format("{0}{1:D}{2}", _
                                     "{", value, "}")
Console.WriteLine(output)   
' The example displays the following output:
'       {6324}
```

### <a name="processing-order"></a>Orden de procesamiento

Si la llamada al método de formato compuesto incluye un argumento [IFormatProvider](xref:System.IFormatProvider) cuyo valor no es nulo, el runtime llama a su método [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) para solicitar una implementación de [ICustomFormatter](xref:System.ICustomFormatter). Si el método puede devolver una implementación de [ICustomFormatter](xref:System.ICustomFormatter), se almacena en caché para su uso posterior. 

Cada valor de la lista de parámetros que corresponde a un elemento de formato se convierte en una cadena mediante estos pasos. Si se cumple alguna condición de los tres primeros pasos, se devolverá la representación de cadena del valor en ese paso y no se ejecutarán los pasos subsiguientes.

1. Si el valor al que se va a dar formato es `null`, se devuelve una cadena vacía (""). 

2. Si hay disponible una implementación de [ICustomFormatter](xref:System.ICustomFormatter), el runtime llama a su método [Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)). Pasa al método el valor *formatString* del elemento de formato, si lo hubiera, o `null` si no lo hubiera, junto con la implementación de [IFormatProvider](xref:System.IFormatProvider). 

3. Si el valor implementa la interfaz [IFormattable](xref:System.IFormattable), se llama al método [ToString(String,IFormatProvider)](xref:System.IFormattable.ToString(System.String,System.IFormatProvider)) de la interfaz. Se pasa al método el valor *formatString*, si hubiera uno presente en el elemento de formato, o `null` si no lo hubiera. El argumento [IFormatProvider](xref:System.IFormatProvider) se determina de la siguiente forma:

    *   Para un valor numérico, si se llama a un método de formato compuesto con un argumento [IFormatProvider](xref:System.IFormatProvider) que no sea nulo, el runtime solicita un objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) a su método [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)). En caso de no poder proporcionar uno, si el valor del argumento es `null`, o si el método de formato compuesto no tiene un parámetro [IFormatProvider](xref:System.IFormatProvider), se usa el objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo para la referencia cultural del subproceso actual. 
    
    * Para un valor de fecha y hora, si se llama a un método de formato compuesto con un argumento [IFormatProvider](xref:System.IFormatProvider) que no sea nulo, el runtime solicita un objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) a su método [IFormatProvider.GetFormat](xref:System.IFormatProvider._GetFormat(System.Type). En caso de no poder proporcionar uno, si el valor del argumento es `null`, o si el método de formato compuesto no tiene un parámetro [IFormatProvider](xref:System.IFormatProvider), se usa el objeto [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) para la referencia cultural del subproceso actual. 
    
    * Para objetos de otros tipos, si se llama a un formato compuesto con un argumento [IFormatProvider](xref:System.IFormatProvider), su valor (incluido `null`, en caso de no proporcionarse ningún objeto [IFormatProvider](xref:System.IFormatProvider)) se pasa directamente a la implementación de [IFormattable.ToString](xref:System.IFormattable.ToString(System.String,System.IFormatProvider)). De lo contrario, se pasa un objeto [CultureInfo](xref:System.Globalization.CultureInfo) que representa la referencia cultural del subproceso actual a la implementación de [IFormattable.ToString](xref:System.IFormattable.ToString(System.String,System.IFormatProvider)). 
    
4. Se llama al método sin parámetros `ToString` del tipo, que reemplaza a [Object.ToString()](xref:System.Object.ToString) o hereda el comportamiento de su clase base. En este caso, se omite la cadena de formato especificada por el componente *formatString* en el elemento de formato, si estuviera presente.

La alineación se aplica después de que se hayan realizado los pasos anteriores. 

## <a name="code-examples"></a>Ejemplos de código

En el ejemplo siguiente se muestra una cadena creada mediante formato compuesto y otra creada mediante el método `ToString` de un objeto. Los dos tipos de formato producen resultados equivalentes. 

```csharp
string FormatString1 = String.Format("{0:dddd MMMM}", DateTime.Now);
string FormatString2 = DateTime.Now.ToString("dddd MMMM");
```

```vb
Dim FormatString1 As String = String.Format("{0:dddd MMMM}", DateTime.Now)
Dim FormatString2 As String = DateTime.Now.ToString("dddd MMMM")
```

Si tomamos como día actual un jueves del mes de mayo, el valor de ambas cadenas del ejemplo anterior será `Thursday May` para la referencia cultural Inglés (Estados Unidos).

[Console.WriteLine](xref:System.Console.WriteLine) expone la misma funcionalidad que [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)). La única diferencia que existe entre estos dos métodos es que [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) devuelve el resultado como una cadena, mientras que [Console.WriteLine](xref:System.Console.WriteLine) escribe el resultado en el flujo de salida asociado al objeto [Console](xref:System.Console). En el ejemplo siguiente se usa el método [Console.WriteLine](xref:System.Console.WriteLine) para dar formato al valor de `MyInt` como un valor de divisa.

```csharp
int MyInt = 100;
Console.WriteLine("{0:C}", MyInt);
// The example displays the following output 
// if en-US is the current culture:
//        $100.00
```

```vb
Dim MyInt As Integer = 100
Console.WriteLine("{0:C}", MyInt)
' The example displays the following output
' if en-US is the current culture:
'        $100.00
```

En el siguiente ejemplo se muestra la aplicación de formato a objetos múltiples, incluida la aplicación de formato a un objeto de dos formas diferentes.

```csharp
string myName = "Fred";
Console.WriteLine(String.Format("Name = {0}, hours = {1:hh}, minutes = {1:mm}",
      myName, DateTime.Now));
// Depending on the current time, the example displays output like the following:
//    Name = Fred, hours = 11, minutes = 30                 
```

```vb
Dim myName As String = "Fred"
Console.WriteLine(String.Format("Name = {0}, hours = {1:hh}, minutes = {1:mm}", _
                  myName, DateTime.Now))
' Depending on the current time, the example displays output like the following:
'    Name = Fred, hours = 11, minutes = 30
```

En el ejemplo siguiente se muestra el uso de la alineación en la aplicación de formato. Los argumentos a los que se da formato se colocan entre caracteres verticales (|) para resaltar la alineación resultante.

```csharp
string myFName = "Fred";
string myLName = "Opals";
int myInt = 100;
string FormatFName = String.Format("First Name = |{0,10}|", myFName);
string FormatLName = String.Format("Last Name = |{0,10}|", myLName);
string FormatPrice = String.Format("Price = |{0,10:C}|", myInt); 
Console.WriteLine(FormatFName);
Console.WriteLine(FormatLName);
Console.WriteLine(FormatPrice);
Console.WriteLine();

FormatFName = String.Format("First Name = |{0,-10}|", myFName);
FormatLName = String.Format("Last Name = |{0,-10}|", myLName);
FormatPrice = String.Format("Price = |{0,-10:C}|", myInt);
Console.WriteLine(FormatFName);
Console.WriteLine(FormatLName);
Console.WriteLine(FormatPrice);
// The example displays the following output on a system whose current
// culture is en-US:
//          First Name = |      Fred|
//          Last Name = |     Opals|
//          Price = |   $100.00|
//
//          First Name = |Fred      |
//          Last Name = |Opals     |
//          Price = |$100.00   |
```

```vb
Dim myFName As String = "Fred"
Dim myLName As String = "Opals"

Dim myInt As Integer = 100
Dim FormatFName As String = String.Format("First Name = |{0,10}|", myFName)
Dim FormatLName As String = String.Format("Last Name = |{0,10}|", myLName)
Dim FormatPrice As String = String.Format("Price = |{0,10:C}|", myInt)
Console.WriteLine(FormatFName)
Console.WriteLine(FormatLName)
Console.WriteLine(FormatPrice)
Console.WriteLine()

FormatFName = String.Format("First Name = |{0,-10}|", myFName)
FormatLName = String.Format("Last Name = |{0,-10}|", myLName)
FormatPrice = String.Format("Price = |{0,-10:C}|", myInt)
Console.WriteLine(FormatFName)
Console.WriteLine(FormatLName)
Console.WriteLine(FormatPrice)
' The example displays the following output on a system whose current
' culture is en-US:
'          First Name = |      Fred|
'          Last Name = |     Opals|
'          Price = |   $100.00|
'
'          First Name = |Fred      |
'          Last Name = |Opals     |
'          Price = |$100.00   |
```

## <a name="see-also"></a>Vea también

[Console.WriteLine](xref:System.Console.WriteLine)

[String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))

[Aplicar formato a tipos](formatting-types.md)

[Cadenas con formato de fecha y hora estándar](standard-datetime.md)

[Cadenas con formato de fecha y hora personalizado](custom-datetime.md)

[Cadenas de formato de enumeración](enumeration-format.md)

[Cadenas con formato numérico estándar](standard-numeric.md)

[Cadenas con formato numérico personalizado](custom-numeric.md)

[Cadenas de formato TimeSpan estándar](standard-timespan.md)

[Cadenas de formato TimeSpan personalizado](custom-timespan.md)



<!--HONumber=Nov16_HO1-->


