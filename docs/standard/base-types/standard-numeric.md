---
title: "Cadenas con formato numérico estándar"
description: "Cadenas con formato numérico estándar"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 285faf73-466a-4af0-8eba-7e509958f240
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 5f5ee73c7c9e0ecdce8aa0d75a630decea57704b

---

# <a name="standard-numeric-format-strings"></a>Cadenas con formato numérico estándar

Las cadenas de formato numérico estándar se utilizan para dar formato a tipos numéricos comunes. La forma de una cadena de formato numérico estándar es **A**_xx_, donde: 

* **A** es un carácter alfabético único denominado *especificador de formato*. Cualquier cadena de formato numérico que contenga más de un carácter alfabético, incluido el espacio en blanco, se interpreta como una cadena de formato numérico personalizado. Para obtener más información, consulte [Cadenas con formato numérico personalizado](custom-numeric.md). 

* *xx* es un entero opcional denominado *especificador de precisión*. El especificador de precisión está comprendido entre el 0 y el 99 y afecta al número de dígitos del resultado. Observe que el especificador de precisión controla el número de dígitos en la representación de cadena de un número. No redondea el número en sí. Para realizar una operación de redondeo, use los métodos [Math.Ceiling](xref:System.Math), [Math.Floor](xref:System.Math) o [Math.Round](xref:System.Math). 

Cuando el *especificador de precisión* controla el número de dígitos fraccionarios en la cadena de resultado, las cadenas de resultado reflejan números que se redondean alejándose de cero (es decir, usando [MidpointRounding.AwayFromZero](xref:System.MidpointRounding.AwayFromZero)). 

> [!NOTE]
> El especificador de precisión determina el número de dígitos de la cadena de resultado. Para rellenar una cadena de resultado con espacios iniciales o finales, use la característica [formatos compuestos](composite-format.md) y defina un *componente de alineación* en el elemento de formato. 

Algunas sobrecargas del método `ToString` de todos los tipos numéricos admiten las cadenas de formato numérico estándar. Por ejemplo, puede proporcionar una cadena de formato numérico a los métodos [ToString(String)](xref:System.Int32.ToString(System.String)) y [ToString(String, IFormatProvider)](xref:System.Int32.ToString(System.String,System.IFormatProvider)) del tipo [Int32](xref:System.Int32). Las cadenas con formato numérico estándar también son compatibles con la característica [formatos compuestos](composite-format.md) de .NET, que usan algunos métodos `Write` y `WriteLine` de las clases [Console](xref:System.Console) y [StreamWriter](xref:System.IO.StreamWriter), el método [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) y el método [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)). La característica de formato compuesto permite incluir la representación de varios elementos de datos en una sola cadena a fin de especificar el ancho de campo y alinear números en un campo. Para obtener más información, consulte [Formatos compuestos](composite-format.md). 

En la tabla siguiente se describen los especificadores de formato numérico estándar y se muestran los resultados de ejemplo generados por cada especificador de formato. Consulte la sección [Notas](#notes) para obtener información adicional sobre cómo usar las cadenas con formato numérico estándar y la sección [Ejemplo](#example) para ver una ilustración completa de su uso.

|Especificador de formato|Name|Descripción|Ejemplos|  
|----------------------|----------|-----------------|--------------|  
|"C" o "c"|Moneda|Resultado: un valor de divisa.<br /><br /> Compatible con: todos los tipos numéricos.<br /><br /> Especificador de precisión: número de dígitos decimales.<br /><br /> Especificador de precisión predeterminado: definido por [NumberFormatInfo.CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits).<br /><br /> |123.456 ("C", en-US) -> $123.46<br /><br /> 123.456 ("C", fr-FR) -> 123,46 €<br /><br /> 123.456 ("C", ja-JP) -> ¥123<br /><br /> -123.456 ("C3", en-US) -> ($123.456)<br /><br /> -123.456 ("C3", fr-FR) -> -123,456 €<br /><br /> -123.456 ("C3", ja-JP) -> -¥123.456|  
|"D" o "d"|Decimal|Resultado: dígitos enteros con signo negativo opcional.<br /><br /> Compatible con: solo tipos enteros.<br /><br /> Especificador de precisión: número mínimo de dígitos.<br /><br /> Especificador de precisión predeterminado: número mínimo de dígitos necesarios.<br /><br /> |1234 ("D") -> 1234<br /><br /> -1234 ("D6") -> -001234|  
|"E" o "e"|Exponencial (científico)|Resultado: notación exponencial.<br /><br /> Compatible con: todos los tipos numéricos.<br /><br /> Especificador de precisión: número de dígitos decimales.<br /><br /> Especificador de precisión predeterminado: 6.<br /><br /> |1052.0329112756 ("E", en-US) -> 1.052033E+003<br /><br /> 1052.0329112756 ("e", fr-FR) -> 1,052033e+003<br /><br /> -1052.0329112756 ("e2", en-US) -> -1.05e+003<br /><br /> -1052.0329112756 ("E2", fr_FR) -> -1,05E+003|  
|"F" o "f"|Punto fijo|Resultado: dígitos integrales y decimales con signo negativo opcional.<br /><br /> Compatible con: todos los tipos numéricos.<br /><br /> Especificador de precisión: número de dígitos decimales.<br /><br /> Especificador de precisión predeterminado: definido por [NumberFormatInfo.NumberDecimalDigits](xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits).<br /><br /> |1234.567 ("F", en-US) -> 1234.57<br /><br /> 1234.567 ("F", de-DE) -> 1234,57<br /><br /> 1234 ("F1", en-US) -> 1234.0<br /><br /> 1234 ("F1", de-DE) -> 1234,0<br /><br /> -1234.56 ("F4", en-US) -> -1234.5600<br /><br /> -1234.56 ("F4", de-DE) -> -1234,5600|  
|"G" o "g"|General|Resultado: notación de punto fijo o científica, la que sea más compacta.<br /><br /> Compatible con: todos los tipos numéricos.<br /><br /> Especificador de precisión: número de dígitos significativos.<br /><br /> Especificador de precisión predeterminado: depende del tipo numérico.<br /><br /> |-123.456 ("G", en-US) -> -123.456<br /><br /> -123.456 ("G", sv-SE) -> -123,456<br /><br /> 123.4546 ("G4", en-US) -> 123.5<br /><br /> 123.4546 ("G4", sv-SE) -> 123,5<br /><br /> -1.234567890e-25 ("G", en-US) -> -1.23456789E-25<br /><br /> -1.234567890e-25 ("G", sv-SE) -> -1,23456789E-25|  
|"N" o "n"|Número|Resultado: dígitos integrales y decimales, separadores de grupos y un separador decimal con signo negativo opcional.<br /><br /> Compatible con: todos los tipos numéricos.<br /><br /> Especificador de precisión: número deseado de decimales.<br /><br /> Especificador de precisión predeterminado: definido por [NumberFormatInfo.NumberDecimalDigits](xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits).<br /><br /> |1234.567 ("N", en-US) -> 1,234.57<br /><br /> 1234.567 ("N", ru-RU) -> 1 234,57<br /><br /> 1234 ("N1", en-US) -> 1,234.0<br /><br /> 1234 ("N1", ru-RU) -> 1 234,0<br /><br /> -1234.56 ("N3", en-US) -> -1,234.560<br /><br /> -1234.56 ("N3", ru-RU) -> -1 234,560|  
|"P" o "p"|Porcentaje|Resultado: número multiplicado por 100 y mostrado con un símbolo de porcentaje.<br /><br /> Compatible con: todos los tipos numéricos.<br /><br /> Especificador de precisión: número deseado de decimales.<br /><br /> Especificador de precisión predeterminado: definido por [NumberFormatInfo.PercentDecimalDigits](assetId:///P:System.Globalization.NumberFormatInfo.PercentDecimalDigits?qualifyHint=True&autoUpgrade=True).<br /><br /> |1 ("P", en-US) -> 100.00 %<br /><br /> 1 ("P", fr-FR) -> 100,00 %<br /><br /> -0.39678 ("P1", en-US) -> -39.7 %<br /><br /> -0.39678 ("P1", fr-FR) -> -39,7 %|  
|"R" o "r"|Acción de ida y vuelta|Resultado: cadena que puede aplicar acciones de ida y vuelta (round-trip) a un número idéntico.<br /><br /> Compatible con: [Single](xref:System.Single), [Double](xref:System.Double) y [BigInteger](xref:System.Numerics.BigInteger).<br /><br /> Especificador de precisión: se omite.<br /><br /> |123456789.12345678 ("R") -> 123456789.12345678<br /><br /> -1234567890.12345678 ("R") -> -1234567890.1234567|  
|"X" o "x"|Hexadecimal|Resultado: cadena hexadecimal.<br /><br /> Compatible con: solo tipos enteros.<br /><br /> Especificador de precisión: número de dígitos en la cadena de resultado.<br /><br /> |255 ("X") -> FF<br /><br /> -1 ("x") -> ff<br /><br /> 255 ("x4") -> 00ff<br /><br /> -1 ("X4") -> 00FF|  
|Cualquier otro carácter único|Especificador desconocido|Resultado: se produce una excepción [FormatException](xref:System.FormatException) en tiempo de ejecución.|| 

## <a name="using-standard-numeric-format-strings"></a>Usar cadenas de formato numérico estándar

Una cadena de formato numérico estándar se puede usar para definir el formato de un valor numérico de una de dos maneras:

* Se puede pasar a una sobrecarga del método `ToString` que tiene un parámetro *format*. En el ejemplo siguiente se da formato a un valor numérico como una cadena de divisa en la referencia cultural actual (en este caso, en-US). 

  ```csharp
  decimal value = 123.456m;
  Console.WriteLine(value.ToString("C2"));
  // Displays $123.46
  ```

  ```vb
  Dim value As Decimal = 123.456d
  Console.WriteLine(value.ToString("C2"))         
  ' Displays $123.46
  ```
  
* Se puede proporcionar como argumento *formatString* en un elemento de formato usado con métodos como [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)), [Console.WriteLine](xref:System.Console.WriteLine) y [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)). Para obtener más información, consulte [Formatos compuestos](composite-format.md). En el ejemplo siguiente se usa un elemento de formato para insertar un valor de divisa en una cadena.

  ```csharp
  decimal value = 123.456m;
  Console.WriteLine("Your account balance is {0:C2}.", value);
  // Displays "Your account balance is $123.46."
  ```

  ```vb
  Dim value As Decimal = 123.456d
  Console.WriteLine("Your account balance is {0:C2}.", value)
  ' Displays "Your account balance is $123.46."
  ```
  
  Opcionalmente, puede facilitar un argumento de alineación para especificar el ancho del campo numérico y si su valor está alineado a izquierda o derecha. En el ejemplo siguiente se alinea a la izquierda un valor de moneda en un campo de 28 caracteres y se alinea a la derecha un valor de moneda en un campo de 14 caracteres.
  
  ```csharp
  decimal[] amounts = { 16305.32m, 18794.16m };
  Console.WriteLine("   Beginning Balance           Ending Balance");
  Console.WriteLine("   {0,-28:C2}{1,14:C2}", amounts[0], amounts[1]);
  // Displays:
  //        Beginning Balance           Ending Balance
  //        $16,305.32                      $18,794.16
  ```

  ```vb
  Dim amounts() As Decimal = { 16305.32d, 18794.16d }
  Console.WriteLine("   Beginning Balance           Ending Balance")
  Console.WriteLine("   {0,-28:C2}{1,14:C2}", amounts(0), amounts(1))
  ' Displays:
  '        Beginning Balance           Ending Balance
  '        $16,305.32                      $18,794.16
  ```
  
En las secciones siguientes se proporciona información detallada sobre cada una de las cadenas de formato numérico estándar.

## <a name="the-currency-c-format-specifier"></a>Especificador de formato de divisa ("C")

El especificador de formato "C" (divisa) convierte un número en una cadena que representa una cantidad de divisa. El especificador de precisión indica el número deseado de posiciones decimales en la cadena de resultado. Si se omite el especificador de precisión, la precisión predeterminada está definida por la propiedad [NumberFormatInfo.CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits).

Si el valor al que se va a dar formato tiene más posiciones decimales que el número especificado o predeterminado, el valor fraccionario se redondea en la cadena de resultado. Si el valor situado a la derecha del número de posiciones decimales especificadas es 5 o superior, el último dígito de la cadena de resultado se redondea desde cero.

La información de formato del objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) actual afecta a la cadena de resultado. En la tabla siguiente se enumeran las propiedades del objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) que controlan el formato de la cadena devuelta.

Propiedad de NumberFormatInfo | Descripción
------------------------- | -----------
[CurrencyPositivePattern](xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern) | Define la posición del símbolo de divisa para los valores positivos.
[CurrencyNegativePattern](xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern) | Define la posición del símbolo de divisa para los valores negativos y especifica si el signo negativo está representado por paréntesis o por la propiedad [NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign).
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Define el signo negativo usado si [CurrencyNegativePattern](xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern) indica que no se emplean paréntesis. 
[CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol) | Define el símbolo de divisa.
[CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits) | Define el número predeterminado de dígitos decimales en un valor de divisa. Este valor puede reemplazarse por el uso del especificador de precisión.
[CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator) | Define la cadena que separa los dígitos integrales y decimales.
[CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator) | Define la cadena que separa los grupos de números integrales. 
[CurrencyGroupSizes](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes) | Define el número de dígitos enteros que aparecen en un grupo.

En el ejemplo siguiente se da formato a un valor [Double](xref:System.Double) con el especificador de formato de divisa. 

```csharp
double value = 12345.6789;
Console.WriteLine(value.ToString("C", CultureInfo.CurrentCulture));

Console.WriteLine(value.ToString("C3", CultureInfo.CurrentCulture));

Console.WriteLine(value.ToString("C3", 
                  CultureInfo.CreateSpecificCulture("da-DK")));
// The example displays the following output on a system whose
// current culture is English (United States):
//       $12,345.68
//       $12,345.679
//       kr 12.345,679
```

```vb
Dim value As Double = 12345.6789
Console.WriteLine(value.ToString("C", CultureInfo.CurrentCulture))

Console.WriteLine(value.ToString("C3", CultureInfo.CurrentCulture))

Console.WriteLine(value.ToString("C3", _
                  CultureInfo.CreateSpecificCulture("da-DK")))
' The example displays the following output on a system whose
' current culture is English (United States):
'       $12,345.68
'       $12,345.679
'       kr 12.345,679
```

## <a name="the-decimal-d-format-specifier"></a>Especificador de formato decimal ("D")

El especificador de formato "D" (o decimal) convierte un número en una cadena de dígitos decimales (0-9), precedida por un signo menos si el número es negativo. Este formato sólo es compatible con los tipos enteros.

El especificador de precisión indica el número mínimo de dígitos deseado en la cadena resultante. Si es preciso, el número se rellena con ceros a la izquierda para generar el número de dígitos que aporta el especificador de precisión. Si no se indica ningún especificador de precisión, el valor predeterminado es el valor mínimo necesario para representar el entero sin ceros iniciales.

La información de formato del objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) actual afecta a la cadena de resultado. Como se muestra en la tabla siguiente, una única propiedad afecta al formato de la cadena de resultado. 

Propiedad de NumberFormatInfo | Descripción
------------------------- | -----------
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Define la cadena que indica que un número es negativo. 

En el ejemplo siguiente se da formato a un valor [Int32](xref:System.Int32) con el especificador de formato decimal.

```csharp
int value; 

value = 12345;
Console.WriteLine(value.ToString("D"));
// Displays 12345
Console.WriteLine(value.ToString("D8"));
// Displays 00012345

value = -12345;
Console.WriteLine(value.ToString("D"));
// Displays -12345
Console.WriteLine(value.ToString("D8"));
// Displays -00012345
```

```vb
Dim value As Integer 

value = 12345
Console.WriteLine(value.ToString("D"))
' Displays 12345   
Console.WriteLine(value.ToString("D8"))
' Displays 00012345

value = -12345
Console.WriteLine(value.ToString("D"))
' Displays -12345
Console.WriteLine(value.ToString("D8"))
' Displays -00012345
```

## <a name="the-exponential-e-format-specifier"></a>Especificador de formato exponencial ("E")

El especificador de formato exponencial ("E") convierte un número en una cadena con el formato "-d.ddd…E+ddd" o "-d.ddd…e+ddd", donde cada "d" indica un dígito (0-9). La cadena comienza con un signo menos si el número es negativo. El separador decimal siempre va precedido por exactamente un dígito. 

El especificador de precisión indica el número deseado de dígitos después del separador decimal. Si se omite el especificador de precisión, se emplea uno predeterminado que tiene seis dígitos después del separador decimal. 

El modelo de mayúsculas o minúsculas del especificador de formato indica si se debe prefijar el exponente con una "E" o con una "e". El exponente siempre consta de un signo más o menos y de un mínimo de tres dígitos. El exponente se rellena con ceros para adaptarlo a este mínimo, si es necesario.

La información de formato del objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) actual afecta a la cadena de resultado. En la tabla siguiente se enumeran las propiedades del objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) que controlan el formato de la cadena devuelta.

Propiedad de NumberFormatInfo | Descripción
------------------------- | -----------
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Define la cadena que indica que un número es negativo tanto para el coeficiente como para el exponente. 
[NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) | Define la cadena que separa el dígito integral de los dígitos decimales en el coeficiente.
[PositiveSign](xref:System.Globalization.NumberFormatInfo.PositiveSign) | Define la cadena que indica que un exponente es positivo.

En el ejemplo siguiente se da formato a un valor [Double](xref:System.Double) con el especificador de formato exponencial. 

```csharp
double value = 12345.6789;
Console.WriteLine(value.ToString("E", CultureInfo.InvariantCulture));
// Displays 1.234568E+004

Console.WriteLine(value.ToString("E10", CultureInfo.InvariantCulture));
// Displays 1.2345678900E+004

Console.WriteLine(value.ToString("e4", CultureInfo.InvariantCulture));
// Displays 1.2346e+004

Console.WriteLine(value.ToString("E", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays 1,234568E+004
```

```vb
Dim value As Double = 12345.6789
Console.WriteLine(value.ToString("E", CultureInfo.InvariantCulture))
' Displays 1.234568E+004

Console.WriteLine(value.ToString("E10", CultureInfo.InvariantCulture))
' Displays 1.2345678900E+004

Console.WriteLine(value.ToString("e4", CultureInfo.InvariantCulture))
' Displays 1.2346e+004

Console.WriteLine(value.ToString("E", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays 1,234568E+004
```

## <a name="the-fixedpoint-f-format-specifier"></a>Especificador de formato de punto fijo ("F")

El especificador de formato de punto fijo ("F) convierte un número en una cadena con el formato "-ddd.ddd…" donde cada "d" indica un dígito (0-9). La cadena comienza con un signo menos si el número es negativo. 

El especificador de precisión indica el número deseado de cifras decimales. Si se omite el especificador de precisión, la propiedad [NumberFormatInfo.NumberDecimalDigits](xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits) actual proporciona la precisión numérica.

La información de formato del objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) actual afecta a la cadena de resultado. En la tabla siguiente se enumeran las propiedades del objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) que controlan el formato de la cadena de resultado.

Propiedad de NumberFormatInfo | Descripción
------------------------- | -----------
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Define la cadena que indica que un número es negativo.
[NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) | Define la cadena que separa los dígitos integrales de los decimales.
[NumberFormatInfo.NumberDecimalDigits](xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits) | Define el número predeterminado de dígitos decimales. Este valor puede reemplazarse por el uso del especificador de precisión.

En el ejemplo siguiente se da formato a un valor [Double](xref:System.Double) e [Int32](xref:System.Int32) con el especificador de formato de punto fijo.

```csharp
int integerNumber;
integerNumber = 17843;
Console.WriteLine(integerNumber.ToString("F", 
                  CultureInfo.InvariantCulture));
// Displays 17843.00

integerNumber = -29541;
Console.WriteLine(integerNumber.ToString("F3", 
                  CultureInfo.InvariantCulture));
// Displays -29541.000

double doubleNumber;
doubleNumber = 18934.1879;
Console.WriteLine(doubleNumber.ToString("F", CultureInfo.InvariantCulture));
// Displays 18934.19

Console.WriteLine(doubleNumber.ToString("F0", CultureInfo.InvariantCulture));
// Displays 18934

doubleNumber = -1898300.1987;
Console.WriteLine(doubleNumber.ToString("F1", CultureInfo.InvariantCulture));  
// Displays -1898300.2

Console.WriteLine(doubleNumber.ToString("F3", 
                  CultureInfo.CreateSpecificCulture("es-ES")));
// Displays -1898300,199 
```

```vb
Dim integerNumber As Integer
integerNumber = 17843
Console.WriteLine(integerNumber.ToString("F", CultureInfo.InvariantCulture))
' Displays 17843.00

integerNumber = -29541
Console.WriteLine(integerNumber.ToString("F3", CultureInfo.InvariantCulture))
' Displays -29541.000

Dim doubleNumber As Double
doubleNumber = 18934.1879
Console.WriteLine(doubleNumber.ToString("F", CultureInfo.InvariantCulture))
' Displays 18934.19

Console.WriteLine(doubleNumber.ToString("F0", CultureInfo.InvariantCulture))
' Displays 18934

doubleNumber = -1898300.1987
Console.WriteLine(doubleNumber.ToString("F1", CultureInfo.InvariantCulture))  
' Displays -1898300.2

Console.WriteLine(doubleNumber.ToString("F3", _ 
                  CultureInfo.CreateSpecificCulture("es-ES")))
' Displays -1898300,199                        
```

## <a name="the-general-g-format-specifier"></a>Especificador de formato general ("G")

El especificador de formato general ("G") convierte un número a la notación de punto fijo o científica más compacta, dependiendo del tipo del número y de si hay un especificador de precisión o no. El especificador de precisión define el número máximo de dígitos significativos que pueden aparecer en la cadena de resultado. Si el especificador de precisión se omite o es cero, el tipo del número determina la precisión predeterminada, como se indica en la tabla siguiente. 

Tipo numérico | Precisión predeterminada
------------ | -----------------
[Byte](xref:System.Byte) o [SByte](xref:System.SByte) | 3 dígitos
[Int16](xref:System.Int16) o [UInt16](xref:System.UInt16) | 5 dígitos
[Int32](xref:System.Int32) o [UInt32](xref:System.UInt32) | 10 dígitos
[Int64](xref:System.Int64) | 19 dígitos
[UInt64](xref:System.UInt64) | 20 dígitos
[BigInteger](xref:System.Numerics.BigInteger) | Sin límite (igual que "R")
[Single](xref:System.Single) | 7 dígitos
[Double](xref:System.Double) | 15 dígitos
[Decimal](xref:System.Decimal) | 29 dígitos

La notación de punto fijo se utiliza si el exponente que resultaría de la expresión del número en notación científica es mayor que -5 y menor que el especificador de precisión, de lo contrario se utiliza la notación científica. El resultado contiene un separador decimal si es necesario y se omiten los ceros finales después de ese separador. Si el especificador de precisión está presente y el número de dígitos significativos del resultado supera la precisión especificada, los dígitos finales sobrantes se quitan mediante redondeo. 

Pero si el número es [Decimal](xref:System.Decimal) y se omite el especificador de precisión, siempre se usa la notación de punto fijo y se conservan los ceros finales.

Si se usa la notación científica, el exponente del resultado lleva el prefijo "E" si el especificador de formato es "G", o "e" si el especificador de formato es "g". El exponente contiene un mínimo de dos dígitos. Esto difiere del formato para la notación científica que genera el especificador de formato exponencial, que incluye un mínimo de tres dígitos en el exponente.

La información de formato del objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) actual afecta a la cadena de resultado. En la tabla siguiente se enumeran las propiedades de [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) que controlan el formato de la cadena de resultado.

Propiedad de NumberFormatInfo | Descripción
------------------------- | -----------
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Define la cadena que indica que un número es negativo.
[NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) | Define la cadena que separa los dígitos integrales de los decimales.
[PositiveSign](xref:System.Globalization.NumberFormatInfo.PositiveSign) | Define la cadena que indica que un exponente es positivo. 

En el ejemplo siguiente se da formato a valores de punto flotante ordenados con el especificador de formato general.

```csharp
double number;

number = 12345.6789;      
Console.WriteLine(number.ToString("G", CultureInfo.InvariantCulture));
// Displays  12345.6789
Console.WriteLine(number.ToString("G", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays 12345,6789

Console.WriteLine(number.ToString("G7", CultureInfo.InvariantCulture));
// Displays 12345.68 

number = .0000023;
Console.WriteLine(number.ToString("G", CultureInfo.InvariantCulture));
// Displays 2.3E-06       
Console.WriteLine(number.ToString("G", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays 2,3E-06

number = .0023;
Console.WriteLine(number.ToString("G", CultureInfo.InvariantCulture));
// Displays 0.0023

number = 1234;
Console.WriteLine(number.ToString("G2", CultureInfo.InvariantCulture));
// Displays 1.2E+03

number = Math.PI;
Console.WriteLine(number.ToString("G5", CultureInfo.InvariantCulture));
// Displays 3.1416    
```

```vb
Dim number As Double

number = 12345.6789      
Console.WriteLine(number.ToString("G", CultureInfo.InvariantCulture))
' Displays  12345.6789
Console.WriteLine(number.ToString("G", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays 12345,6789

Console.WriteLine(number.ToString("G7", CultureInfo.InvariantCulture))
' Displays 12345.68 

number = .0000023
Console.WriteLine(number.ToString("G", CultureInfo.InvariantCulture))
' Displays 2.3E-06       
Console.WriteLine(number.ToString("G", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays 2,3E-06

number = .0023
Console.WriteLine(number.ToString("G", CultureInfo.InvariantCulture))
' Displays 0.0023

number = 1234
Console.WriteLine(number.ToString("G2", CultureInfo.InvariantCulture))
' Displays 1.2E+03

number = Math.Pi
Console.WriteLine(number.ToString("G5", CultureInfo.InvariantCulture))
' Displays 3.1416
```

## <a name="the-numeric-n-format-specifier"></a>Especificador de formato numérico ("N")

El especificador de formato numérico ("N") convierte un número en una cadena con el formato "-d,ddd,ddd.ddd…", donde "-" indica el símbolo de número negativo, si es necesario; "d", representa cada dígito (0-9); "," es el separador de grupo; y "." es el símbolo de punto decimal. El especificador de precisión indica el número deseado de dígitos después del separador decimal. Si se omite el especificador de precisión, el número de posiciones decimales está definido por la propiedad [NumberFormatInfo.NumberDecimalDigits](xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits) actual.

La información de formato del objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) actual afecta a la cadena de resultado. En la tabla siguiente se enumeran las propiedades de [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) que controlan el formato de la cadena de resultado.

Propiedad de NumberFormatInfo | Descripción
------------------------- | -----------
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Define la cadena que indica que un número es negativo.
[NumberNegativePattern](xref:System.Globalization.NumberFormatInfo.NumberNegativePattern) | Define el formato de los valores negativos y especifica si el signo negativo se representa mediante paréntesis o por la propiedad [NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign).
[NumberGroupSizes](xref:System.Globalization.NumberFormatInfo.NumberGroupSizes) | Define el número de dígitos enteros que aparecen entre los separadores de grupos.
[NumberGroupSeparator](xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator) | Define la cadena que separa los grupos de números integrales.
[NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) | Define la cadena que separa los dígitos integrales de los decimales.
[NumberDecimalDigits](xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits) | Define el número predeterminado de dígitos decimales. Este valor puede reemplazarse por el uso de un especificador de precisión.

En el ejemplo siguiente se da formato a valores de punto flotante ordenados con el especificador de formato numérico.

```csharp
double dblValue = -12445.6789;
Console.WriteLine(dblValue.ToString("N", CultureInfo.InvariantCulture));
// Displays -12,445.68
Console.WriteLine(dblValue.ToString("N1", 
                  CultureInfo.CreateSpecificCulture("sv-SE")));
// Displays -12 445,7

int intValue = 123456789;
Console.WriteLine(intValue.ToString("N1", CultureInfo.InvariantCulture));
// Displays 123,456,789.0 
```

```vb
Dim dblValue As Double = -12445.6789
Console.WriteLine(dblValue.ToString("N", CultureInfo.InvariantCulture))
' Displays -12,445.68
Console.WriteLine(dblValue.ToString("N1", _
                  CultureInfo.CreateSpecificCulture("sv-SE")))
' Displays -12 445,7

Dim intValue As Integer = 123456789
Console.WriteLine(intValue.ToString("N1", CultureInfo.InvariantCulture))
' Displays 123,456,789.0 
```

## <a name="the-percent-p-format-specifier"></a>Especificador de formato de porcentaje ("P")

El especificador de formato de porcentaje ("P") multiplica un número por 100 y lo convierte en una cadena que representa un porcentaje. El especificador de precisión indica el número deseado de cifras decimales. Si se omite el especificador de precisión, se usará la precisión numérica predeterminada proporcionada por la propiedad [PercentDecimalDigits](xref:System.Globalization.NumberFormatInfo.PercentDecimalDigits) actual.

En la tabla siguiente se enumeran las propiedades del objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) que controlan el formato de la cadena devuelta.

Propiedad de NumberFormatInfo | Descripción
------------------------- | -----------
[PercentPositivePattern](xref:System.Globalization.NumberFormatInfo.PercentPositivePattern) | Define la posición del símbolo de porcentaje para los valores positivos.
[PercentNegativePattern](xref:System.Globalization.NumberFormatInfo.PercentNegativePattern) | 
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Define la cadena que indica que un número es negativo.
[PercentSymbol](xref:System.Globalization.NumberFormatInfo.PercentSymbol) | Define el símbolo de porcentaje.
[PercentDecimalDigits](xref:System.Globalization.NumberFormatInfo.PercentDecimalDigits) | Define el número predeterminado de dígitos decimales en un valor de porcentaje. Este valor puede reemplazarse por el uso del especificador de precisión.
[PercentDecimalSeparator](xref:System.Globalization.NumberFormatInfo.PercentDecimalSeparator) | Define la cadena que separa los dígitos integrales y decimales.
[PercentGroupSeparator](xref:System.Globalization.NumberFormatInfo.PercentGroupSeparator) | Define la cadena que separa los grupos de números integrales. 
[PercentGroupSizes](xref:System.Globalization.NumberFormatInfo.PercentGroupSizes) | Define el número de dígitos enteros que aparecen en un grupo.

En el ejemplo siguiente se da formato a valores de punto flotante con el especificador de formato de porcentaje.

```csharp
double number = .2468013;
Console.WriteLine(number.ToString("P", CultureInfo.InvariantCulture));
// Displays 24.68 %
Console.WriteLine(number.ToString("P", 
                  CultureInfo.CreateSpecificCulture("hr-HR")));
// Displays 24,68%     
Console.WriteLine(number.ToString("P1", CultureInfo.InvariantCulture));
// Displays 24.7 %
```

```vb
Dim number As Double = .2468013
Console.WriteLine(number.ToString("P", CultureInfo.InvariantCulture))
' Displays 24.68 %
Console.WriteLine(number.ToString("P", _
                  CultureInfo.CreateSpecificCulture("hr-HR")))
' Displays 24,68%     
Console.WriteLine(number.ToString("P1", CultureInfo.InvariantCulture))
' Displays 24.7 %
```

## <a name="the-roundtrip-r-format-specifier"></a>Especificador de formato de operación de ida y vuelta ("R")

El especificador de formato de operación de ida y vuelta ("R") se usa para garantizar que un valor numérico que se convierte en una cadena volverá a tomar el mismo valor numérico. Este formato solo es compatible con los tipos [Single](xref:System.Single), [Double](xref:System.Double) y [BigInteger](xref:System.Numerics.BigInteger). 

Cuando se da formato a un valor [BigInteger](xref:System.Numerics.BigInteger) mediante este especificador, su representación de cadena contiene todos los dígitos significativos del valor [BigInteger](xref:System.Numerics.BigInteger). Cuando se da formato a un valor [Single](xref:System.Single) o [Double](xref:System.Double) mediante este especificador, primero se comprueba empleando el formato general, con 15 dígitos de precisión para un tipo [Double](xref:System.Double) y 7 dígitos de precisión para un tipo [Single](xref:System.Single). Si el valor recupera correctamente el mismo valor numérico al analizarse, se le aplica formato mediante el especificador de formato general. Si el valor no recupera correctamente el mismo valor numérico, se le da formato usando 17 dígitos de precisión para un tipo [Double](xref:System.Double) y 9 para un tipo [Single](xref:System.Single). 

Aunque puede incluir un especificador de precisión, se omite. Los especificadores de ida y vuelta tienen prioridad sobre la precisión al utilizar este especificador. 

La información de formato del objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) actual afecta a la cadena de resultado. En la tabla siguiente se enumeran las propiedades de [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) que controlan el formato de la cadena de resultado.

Propiedad de NumberFormatInfo | Descripción
------------------------- | -----------
[NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) | Define la cadena que indica que un número es negativo.
[NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) | Define la cadena que separa los dígitos integrales de los decimales.
[PositiveSign](xref:System.Globalization.NumberFormatInfo.PositiveSign) | Define la cadena que indica que un exponente es positivo.

 En el ejemplo siguiente se da formato a valores [Double](xref:System.Double) con el especificador de formato de ida y vuelta.

```csharp
double value;

value = Math.PI;
Console.WriteLine(value.ToString("r"));
// Displays 3.1415926535897931
Console.WriteLine(value.ToString("r", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays 3,1415926535897931
value = 1.623e-21;
Console.WriteLine(value.ToString("r"));
// Displays 1.623E-21
```

```vb
Dim value As Double

value = Math.Pi
Console.WriteLine(value.ToString("r"))
' Displays 3.1415926535897931
Console.WriteLine(value.ToString("r", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays 3,1415926535897931
value = 1.623e-21
Console.WriteLine(value.ToString("r"))
' Displays 1.623E-21
```

## <a name="the-hexadecimal-x-format-specifier"></a>Especificador de formato hexadecimal ("X")

El especificador de formato hexadecimal ("X") convierte un número en una cadena de dígitos hexadecimales. El modelo de mayúsculas y minúsculas del especificador de formato indica si se van a usar caracteres en mayúsculas o en minúsculas para los dígitos hexadecimales mayores de 9. Por ejemplo, use "X" para generar "ABCDEF" y "x" para generar "abcdef". Este formato sólo es compatible con los tipos enteros.

El especificador de precisión indica el número mínimo de dígitos deseado en la cadena resultante. Si es preciso, el número se rellena con ceros a la izquierda para generar el número de dígitos que aporta el especificador de precisión.

La información de formato del objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) actual no afecta a la cadena de resultado. 

En el ejemplo siguiente se da formato a valores [Int32](xref:System.Int32) con el especificador de formato hexadecimal.

```csharp
int value; 

value = 0x2045e;
Console.WriteLine(value.ToString("x"));
// Displays 2045e
Console.WriteLine(value.ToString("X"));
// Displays 2045E
Console.WriteLine(value.ToString("X8"));
// Displays 0002045E

value = 123456789;
Console.WriteLine(value.ToString("X"));
// Displays 75BCD15
Console.WriteLine(value.ToString("X2"));
// Displays 75BCD15
```

```vb
Dim value As Integer 

value = &h2045e
Console.WriteLine(value.ToString("x"))
' Displays 2045e
Console.WriteLine(value.ToString("X"))
' Displays 2045E
Console.WriteLine(value.ToString("X8"))
' Displays 0002045E

value = 123456789
Console.WriteLine(value.ToString("X"))
' Displays 75BCD15
Console.WriteLine(value.ToString("X2"))
' Displays 75BCD15
```

## <a name="notes"></a>Notas

### <a name="numberformatinfo-properties"></a>Propiedades NumberFormatInfo

El formato se ve influenciado por las propiedades del objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) actual, proporcionado implícitamente por la referencia cultural del subproceso actual o explícitamente por el parámetro [IFormatProvider](xref:System.IFormatProvider) del método que invoca el formato. Especifique un objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) o [CultureInfo](xref:System.Globalization.CultureInfo) para ese parámetro. 

### <a name="integral-and-floatingpoint-numeric-types"></a>Tipos numéricos enteros y de punto flotante

Algunas descripciones de especificadores de formato numérico estándar hacen referencia a tipos numéricos enteros o de punto flotante. Los tipos numéricos enteros son [Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64) y [BigInteger](xref:System.Numerics.BigInteger). Los tipos numéricos de punto flotante son [Decimal](xref:System.Decimal), [Single](xref:System.Single) y [Double](xref:System.Double). 

### <a name="floatingpoint-infinities-and-nan"></a>Infinitos de punto flotante y NaN

Independientemente de la cadena de formato, si el valor de un tipo de punto flotante [Single](xref:System.Single) o [Double](xref:System.Double) es infinito positivo, infinito negativo o no es un número (NaN), la cadena con formato es el valor de la propiedad [PositiveInfinitySymbol](xref:System.Globalization.NumberFormatInfo.PositiveInfinitySymbol), [NegativeInfinitySymbol](xref:System.Globalization.NumberFormatInfo.NegativeInfinitySymbol) o [NaNSymbol](xref:System.Globalization.NumberFormatInfo.NaNSymbol) respectiva que haya especificado el objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) correspondiente.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se da formato a un valor numérico integral y de punto flotante mediante la referencia cultural en-US y todos los especificadores de formato numérico estándar. Este ejemplo usa dos tipos numéricos concretos ([Double](xref:System.Double) e [Int32](xref:System.Int32)), pero se obtendrían resultados similares para cualquiera de los tipos base numéricos ([Byte](xref:System.Byte), [SByte](xref:System.SByte), [Int16](xref:System.Int16), [Int64](xref:System.Int64), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64), [BigInteger](xref:System.Numerics.BigInteger), [Decimal](xref:System.Decimal) y [Single](xref:System.Single)). 

```csharp
using System;
using System.Globalization;
using System.Threading;

public class NumericFormats
{
   public static void Main()
   {
      // Display string representations of numbers for en-us culture
      CultureInfo ci = new CultureInfo("en-us");

      // Output floating point values
      double floating = 10761.937554;
      Console.WriteLine("C: {0}", 
              floating.ToString("C", ci));           // Displays "C: $10,761.94"
      Console.WriteLine("E: {0}", 
              floating.ToString("E03", ci));         // Displays "E: 1.076E+004"
      Console.WriteLine("F: {0}", 
              floating.ToString("F04", ci));         // Displays "F: 10761.9376"         
      Console.WriteLine("G: {0}",  
              floating.ToString("G", ci));           // Displays "G: 10761.937554"
      Console.WriteLine("N: {0}", 
              floating.ToString("N03", ci));         // Displays "N: 10,761.938"
      Console.WriteLine("P: {0}", 
              (floating/10000).ToString("P02", ci)); // Displays "P: 107.62 %"
      Console.WriteLine("R: {0}", 
              floating.ToString("R", ci));           // Displays "R: 10761.937554"            
      Console.WriteLine();

      // Output integral values
      int integral = 8395;
      Console.WriteLine("C: {0}", 
              integral.ToString("C", ci));           // Displays "C: $8,395.00"
      Console.WriteLine("D: {0}", 
              integral.ToString("D6", ci));          // Displays "D: 008395" 
      Console.WriteLine("E: {0}", 
              integral.ToString("E03", ci));         // Displays "E: 8.395E+003"
      Console.WriteLine("F: {0}", 
              integral.ToString("F01", ci));         // Displays "F: 8395.0"    
      Console.WriteLine("G: {0}",  
              integral.ToString("G", ci));           // Displays "G: 8395"
      Console.WriteLine("N: {0}", 
              integral.ToString("N01", ci));         // Displays "N: 8,395.0"
      Console.WriteLine("P: {0}", 
              (integral/10000.0).ToString("P02", ci)); // Displays "P: 83.95 %"
      Console.WriteLine("X: 0x{0}", 
              integral.ToString("X", ci));           // Displays "X: 0x20CB"
      Console.WriteLine();
   }
}
```

```vb
Option Strict On

Imports System.Globalization
Imports System.Threading

Module NumericFormats
   Public Sub Main()
      ' Display string representations of numbers for en-us culture
      Dim ci As New CultureInfo("en-us")

      ' Output floating point values
      Dim floating As Double = 10761.937554
      Console.WriteLine("C: {0}", _
              floating.ToString("C", ci))           ' Displays "C: $10,761.94"
      Console.WriteLine("E: {0}", _
              floating.ToString("E03", ci))         ' Displays "E: 1.076E+004"
      Console.WriteLine("F: {0}", _
              floating.ToString("F04", ci))         ' Displays "F: 10761.9376"         
      Console.WriteLine("G: {0}", _ 
              floating.ToString("G", ci))           ' Displays "G: 10761.937554"
      Console.WriteLine("N: {0}", _
              floating.ToString("N03", ci))         ' Displays "N: 10,761.938"
      Console.WriteLine("P: {0}", _
              (floating/10000).ToString("P02", ci)) ' Displays "P: 107.62 %"
      Console.WriteLine("R: {0}", _
              floating.ToString("R", ci))           ' Displays "R: 10761.937554"            
      Console.WriteLine()

      ' Output integral values
      Dim integral As Integer = 8395
      Console.WriteLine("C: {0}", _
              integral.ToString("C", ci))           ' Displays "C: $8,395.00"
      Console.WriteLine("D: {0}", _
              integral.ToString("D6"))              ' Displays "D: 008395" 
      Console.WriteLine("E: {0}", _
              integral.ToString("E03", ci))         ' Displays "E: 8.395E+003"
      Console.WriteLine("F: {0}", _
              integral.ToString("F01", ci))         ' Displays "F: 8395.0"    
      Console.WriteLine("G: {0}", _ 
              integral.ToString("G", ci))           ' Displays "G: 8395"
      Console.WriteLine("N: {0}", _
              integral.ToString("N01", ci))         ' Displays "N: 8,395.0"
      Console.WriteLine("P: {0}", _
              (integral/10000).ToString("P02", ci)) ' Displays "P: 83.95 %"
      Console.WriteLine("X: 0x{0}", _
              integral.ToString("X", ci))           ' Displays "X: 0x20CB"
      Console.WriteLine()
   End Sub
End Module
```

## <a name="see-also"></a>Vea también

[System.Globalization.NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)

[Cadenas con formato numérico personalizado](custom-numeric.md)

[Aplicar formato a tipos](formatting-types.md)

[Cómo: Rellenar un número con ceros a la izquierda](pad-number.md)

[Formatos compuestos](composite-format.md)



<!--HONumber=Nov16_HO1-->


