---
title: Cadenas con formato numérico estándar
ms.date: 06/10/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- standard format strings, numeric
- format strings
- numbers [.NET Framework], formatting
- format specifiers, numeric
- standard numeric format strings
- formatting numbers [.NET Framework]
- format specifiers, standard numeric format strings
ms.openlocfilehash: 93f93574e6a3c24fc03a2cbc6c7d0f11f4fe61f6
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83440881"
---
# <a name="standard-numeric-format-strings"></a>Cadenas con formato numérico estándar

Las cadenas de formato numérico estándar se utilizan para dar formato a tipos numéricos comunes. La forma de una cadena de formato numérico estándar es `Axx`, donde:

- `A` es un carácter alfabético único denominado *especificador de formato*. Cualquier cadena de formato numérico que contenga más de un carácter alfabético, incluido el espacio en blanco, se interpreta como una cadena de formato numérico personalizado. Para obtener más información, consulte [Cadenas con formato numérico personalizado](../../../docs/standard/base-types/custom-numeric-format-strings.md).

- `xx` es un entero opcional denominado *especificador de precisión*. El especificador de precisión está comprendido entre el 0 y el 99 y afecta al número de dígitos del resultado. Observe que el especificador de precisión controla el número de dígitos en la representación de cadena de un número. No redondea el número en sí. Para realizar una operación de redondeo, use el método <xref:System.Math.Ceiling%2A?displayProperty=nameWithType>, <xref:System.Math.Floor%2A?displayProperty=nameWithType> o <xref:System.Math.Round%2A?displayProperty=nameWithType>.

  Cuando el *especificador de precisión* controla el número de dígitos fraccionarios de la cadena de resultado, esta refleja un número redondeado al resultado representable más cercano al resultado de precisión infinita. En el caso de que haya dos resultados representables igualmente cercanos:
  - **En .NET Framework y .NET Core (hasta la versión 2.0)** , el runtime selecciona el resultado con el dígito menos significativo más elevado (es decir, usando <xref:System.MidpointRounding.AwayFromZero?displayProperty=nameWithType>).
  - **En .NET Core 2.1 y versiones posteriores**, el runtime selecciona el resultado con un dígito menos significativo par (es decir, usando <xref:System.MidpointRounding.ToEven?displayProperty=nameWithType>).

  > [!NOTE]
  > El especificador de precisión determina el número de dígitos de la cadena de resultado. Para rellenar una cadena de resultado con espacios iniciales o finales, use la característica [formatos compuestos](../../../docs/standard/base-types/composite-formatting.md) y defina un *componente de alineación* en el elemento de formato.

Las cadenas con formato numérico estándar son compatibles con:

- Algunas sobrecargas del método `ToString` de todos los tipos numéricos. Por ejemplo, se puede proporcionar una cadena de formato numérico a los métodos <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> y <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>.

- La [característica de formato compuesto](../../../docs/standard/base-types/composite-formatting.md) de .NET, que utilizan algunos métodos `Write` y `WriteLine` de las clases <xref:System.Console> y <xref:System.IO.StreamWriter>, el método <xref:System.String.Format%2A?displayProperty=nameWithType> y el método <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>. La característica de formato compuesto permite incluir la representación de varios elementos de datos en una sola cadena a fin de especificar el ancho de campo y alinear números en un campo. Para obtener más información, consulte [Formatos compuestos](../../../docs/standard/base-types/composite-formatting.md).

- [Cadenas interpoladas](../../csharp/language-reference/tokens/interpolated.md) en C# y Visual Basic, que proporcionan una sintaxis simplificada cuando se comparan con las cadenas de formato compuesto.

> [!TIP]
> Puede descargar la **Utilidad de formato**, que es una aplicación de .NET Core Windows Forms que permite aplicar cadenas de formato a valores numéricos o de fecha y hora, y que muestra la cadena de resultado. El código fuente está disponible para [C#](https://docs.microsoft.com/samples/dotnet/samples/windowsforms-formatting-utility-cs) y [Visual Basic](https://docs.microsoft.com/samples/dotnet/samples/windowsforms-formatting-utility-vb).

<a name="table"></a> En la tabla siguiente se describen los especificadores de formato numérico estándar y se muestran los resultados de ejemplo generados por cada especificador de formato. Consulte la sección [Notas](#NotesStandardFormatting) para obtener información adicional sobre cómo usar las cadenas con formato numérico estándar y la sección [Ejemplo](#example) para ver una ilustración completa de su uso.

|Especificador de formato|Name|Description|Ejemplos|
|----------------------|----------|-----------------|--------------|
|"C" o "c"|Moneda|Resultado: un valor de divisa.<br /><br /> Compatible con: todos los tipos numéricos.<br /><br /> Especificador de precisión: número de dígitos decimales.<br /><br /> Especificador de precisión predeterminado: definido por <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits%2A?displayProperty=nameWithType>.<br /><br /> Más información: [Especificador de formato de divisa ("C")](#CFormatString).|123.456 ("C", en-US) -> \\$123.46<br /><br /> 123.456 ("C", fr-FR) -> 123,46 €<br /><br /> 123.456 ("C", ja-JP) -> ¥123<br /><br /> -123.456 ("C3", en-US) -> (\\$123.456)<br /><br /> -123.456 ("C3", fr-FR) -> -123,456 €<br /><br /> -123.456 ("C3", ja-JP) -> -¥123.456|
|"D" o "d"|Decimal|Resultado: dígitos enteros con signo negativo opcional.<br /><br /> Compatible con: solo tipos enteros.<br /><br /> Especificador de precisión: número mínimo de dígitos.<br /><br /> Especificador de precisión predeterminado: número mínimo de dígitos necesarios.<br /><br /> Más información: [Especificador de formato decimal ("D")](#DFormatString).|1234 ("D") -> 1234<br /><br /> -1234 ("D6") -> -001234|
|"E" o "e"|Exponencial (científico)|Resultado: notación exponencial.<br /><br /> Compatible con: todos los tipos numéricos.<br /><br /> Especificador de precisión: número de dígitos decimales.<br /><br /> Especificador de precisión predeterminado: 6.<br /><br /> Más información: [Especificador de formato exponencial ("E")](#EFormatString).|1052.0329112756 ("E", en-US) -> 1.052033E+003<br /><br /> 1052.0329112756 ("e", fr-FR) -> 1,052033e+003<br /><br /> -1052.0329112756 ("e2", en-US) -> -1.05e+003<br /><br /> -1052.0329112756 ("E2", fr-FR) -> -1,05E+003|
|"F" o "f"|Punto fijo|Resultado: dígitos integrales y decimales con signo negativo opcional.<br /><br /> Compatible con: todos los tipos numéricos.<br /><br /> Especificador de precisión: número de dígitos decimales.<br /><br /> Especificador de precisión predeterminado: definido por <xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A?displayProperty=nameWithType>.<br /><br /> Más información: [Especificador de formato de punto fijo ("F")](#FFormatString).|1234.567 ("F", en-US) -> 1234.57<br /><br /> 1234.567 ("F", de-DE) -> 1234,57<br /><br /> 1234 ("F1", en-US) -> 1234.0<br /><br /> 1234 ("F1", de-DE) -> 1234,0<br /><br /> -1234.56 ("F4", en-US) -> -1234.5600<br /><br /> -1234.56 ("F4", de-DE) -> -1234,5600|
|"G" o "g"|General|Resultado: notación de punto fijo o científica, la que sea más compacta.<br /><br /> Compatible con: todos los tipos numéricos.<br /><br /> Especificador de precisión: número de dígitos significativos.<br /><br /> Especificador de precisión predeterminado: depende del tipo numérico.<br /><br /> Más información: [Especificador de formato general ("G")](#GFormatString).|-123.456 ("G", en-US) -> -123.456<br /><br /> -123.456 ("G", sv-SE) -> -123,456<br /><br /> 123.4546 ("G4", en-US) -> 123.5<br /><br /> 123.4546 ("G4", sv-SE) -> 123,5<br /><br /> -1.234567890e-25 ("G", en-US) -> -1.23456789E-25<br /><br /> -1.234567890e-25 ("G", sv-SE) -> -1,23456789E-25|
|"N" o "n"|número|Resultado: dígitos integrales y decimales, separadores de grupos y un separador decimal con signo negativo opcional.<br /><br /> Compatible con: todos los tipos numéricos.<br /><br /> Especificador de precisión: número deseado de decimales.<br /><br /> Especificador de precisión predeterminado: definido por <xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A?displayProperty=nameWithType>.<br /><br /> Más información: [Especificador de formato numérico ("N")](#NFormatString).|1234.567 ("N", en-US) -> 1,234.57<br /><br /> 1234.567 ("N", ru-RU) -> 1 234,57<br /><br /> 1234 ("N1", en-US) -> 1,234.0<br /><br /> 1234 ("N1", ru-RU) -> 1 234,0<br /><br /> -1234.56 ("N3", en-US) -> -1,234.560<br /><br /> -1234.56 ("N3", ru-RU) -> -1 234,560|
|"P" o "p"|Porcentaje|Resultado: número multiplicado por 100 y mostrado con un símbolo de porcentaje.<br /><br /> Compatible con: todos los tipos numéricos.<br /><br /> Especificador de precisión: número deseado de decimales.<br /><br /> Especificador de precisión predeterminado: definido por <xref:System.Globalization.NumberFormatInfo.PercentDecimalDigits%2A?displayProperty=nameWithType>.<br /><br /> Más información: [Especificador de formato de porcentaje ("P")](#PFormatString).|1 ("P", en-US) -> 100.00 %<br /><br /> 1 ("P", fr-FR) -> 100,00 %<br /><br /> -0.39678 ("P1", en-US) -> -39.7 %<br /><br /> -0.39678 ("P1", fr-FR) -> -39,7 %|
|"R" o "r"|Acción de ida y vuelta|Resultado: cadena que puede aplicar acciones de ida y vuelta (round-trip) a un número idéntico.<br /><br /> Compatible con: <xref:System.Single>, <xref:System.Double> y <xref:System.Numerics.BigInteger>.<br /><br /> Nota: Se recomienda solo para el tipo <xref:System.Numerics.BigInteger>. Para los tipos <xref:System.Double>, use "G17"; para los tipos <xref:System.Single>, use "G9". <br> Especificador de precisión: se omite.<br /><br /> Más información: [Especificador de formato de operación de ida y vuelta ("R")](#RFormatString).|123456789.12345678 ("R") -> 123456789.12345678<br /><br /> -1234567890.12345678 ("R") -> -1234567890.1234567|
|"X" o "x"|Hexadecimal|Resultado: cadena hexadecimal.<br /><br /> Compatible con: solo tipos enteros.<br /><br /> Especificador de precisión: número de dígitos en la cadena de resultado.<br /><br /> Más información: [Especificador de formato hexadecimal ("X")](#XFormatString).|255 ("X") -> FF<br /><br /> -1 ("x") -> ff<br /><br /> 255 ("x4") -> 00ff<br /><br /> -1 ("X4") -> 00FF|
|Cualquier otro carácter único|Especificador desconocido|Resultado: Produce <xref:System.FormatException> en tiempo de ejecución.||

<a name="Using"></a>

## <a name="using-standard-numeric-format-strings"></a>Usar cadenas de formato numérico estándar

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

Una cadena de formato numérico estándar se puede usar para definir el formato de un valor numérico de una de dos maneras:

- Se puede pasar a una sobrecarga del método `ToString` que tiene un parámetro `format`. En el ejemplo siguiente se da formato a un valor numérico como una cadena de divisa en la referencia cultural actual (en este caso, en-US).

  [!code-cpp[Formatting.Numeric.Standard#10](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/standardusage1.cpp#10)]
  [!code-csharp-interactive[Formatting.Numeric.Standard#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/standardusage1.cs#10)]
  [!code-vb[Formatting.Numeric.Standard#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/standardusage1.vb#10)]

- Se puede proporcionar como el argumento `formatString` de un elemento de formato usado con métodos como <xref:System.String.Format%2A?displayProperty=nameWithType>, <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> y <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>. Para obtener más información, consulte [Formatos compuestos](../../../docs/standard/base-types/composite-formatting.md). En el ejemplo siguiente se usa un elemento de formato para insertar un valor de divisa en una cadena.

  [!code-cpp[Formatting.Numeric.Standard#11](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/standardusage1.cpp#11)]
  [!code-csharp-interactive[Formatting.Numeric.Standard#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/standardusage1.cs#11)]
  [!code-vb[Formatting.Numeric.Standard#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/standardusage1.vb#11)]

  Opcionalmente, puede facilitar un argumento `alignment` para especificar el ancho del campo numérico y si su valor está alineado a izquierda o derecha. En el ejemplo siguiente se alinea a la izquierda un valor de moneda en un campo de 28 caracteres y se alinea a la derecha un valor de moneda en un campo de 14 caracteres.

  [!code-cpp[Formatting.Numeric.Standard#12](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/standardusage1.cpp#12)]
  [!code-csharp-interactive[Formatting.Numeric.Standard#12](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/standardusage1.cs#12)]
  [!code-vb[Formatting.Numeric.Standard#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/standardusage1.vb#12)]

- Se puede proporcionar como el argumento `formatString` en un elemento de la expresión interpolada de una cadena interpolada. Para más información, vea el tema [$ (Referencia de C#)](../../csharp/language-reference/tokens/interpolated.md) en la referencia de C# o el tema [Interpolated Strings (Visual Basic Reference)](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) [Cadenas interpoladas (Referencia de Visual Basic)] en la referencia de Visual Basic.

En las secciones siguientes se proporciona información detallada sobre cada una de las cadenas de formato numérico estándar.

<a name="CFormatString"></a>

## <a name="the-currency-c-format-specifier"></a>Especificador de formato de divisa ("C")

El especificador de formato "C" (divisa) convierte un número en una cadena que representa una cantidad de divisa. El especificador de precisión indica el número deseado de posiciones decimales en la cadena de resultado. Si se omite el especificador de precisión, la precisión predeterminada está definida por la propiedad <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits%2A?displayProperty=nameWithType>.

Si el valor al que se va a dar formato tiene más posiciones decimales que el número especificado o predeterminado, el valor fraccionario se redondea en la cadena de resultado. Si el valor situado a la derecha del número de posiciones decimales especificadas es 5 o superior, el último dígito de la cadena de resultado se redondea desde cero.

La información de formato del objeto <xref:System.Globalization.NumberFormatInfo> actual afecta a la cadena de resultado. En la tabla siguiente se enumeran las propiedades de <xref:System.Globalization.NumberFormatInfo> que controlan el formato de la cadena devuelta.

|Propiedad de NumberFormatInfo|Description|
|-------------------------------|-----------------|
|<xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern%2A>|Define la posición del símbolo de divisa para los valores positivos.|
|<xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern%2A>|Define la posición del símbolo de divisa para los valores negativos y especifica si el signo negativo está representado por paréntesis o por la propiedad <xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>.|
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Define el signo negativo usado si <xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern%2A> indica que no se emplean paréntesis.|
|<xref:System.Globalization.NumberFormatInfo.CurrencySymbol%2A>|Define el símbolo de divisa.|
|<xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits%2A>|Define el número predeterminado de dígitos decimales en un valor de divisa. Este valor puede reemplazarse por el uso del especificador de precisión.|
|<xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator%2A>|Define la cadena que separa los dígitos integrales y decimales.|
|<xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator%2A>|Define la cadena que separa los grupos de números integrales.|
|<xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes%2A>|Define el número de dígitos enteros que aparecen en un grupo.|

En el ejemplo siguiente se da formato a un valor <xref:System.Double> con el especificador de formato de divisa:

[!code-cpp[Formatting.Numeric.Standard#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#1)]
[!code-csharp[Formatting.Numeric.Standard#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#1)]
[!code-vb[Formatting.Numeric.Standard#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#1)]

[Volver a la tabla](#table)

<a name="DFormatString"></a>

## <a name="the-decimal-d-format-specifier"></a>Especificador de formato decimal ("D")

El especificador de formato "D" (o decimal) convierte un número en una cadena de dígitos decimales (0-9), precedida por un signo menos si el número es negativo. Este formato sólo es compatible con los tipos enteros.

El especificador de precisión indica el número mínimo de dígitos deseado en la cadena resultante. Si es preciso, el número se rellena con ceros a la izquierda para generar el número de dígitos que aporta el especificador de precisión. Si no se indica ningún especificador de precisión, el valor predeterminado es el valor mínimo necesario para representar el entero sin ceros iniciales.

La información de formato del objeto <xref:System.Globalization.NumberFormatInfo> actual afecta a la cadena de resultado. Como se muestra en la tabla siguiente, una única propiedad afecta al formato de la cadena de resultado.

|Propiedad de NumberFormatInfo|Description|
|-------------------------------|-----------------|
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Define la cadena que indica que un número es negativo.|

En el ejemplo siguiente se da formato a un valor <xref:System.Int32> con el especificador de formato decimal.

[!code-cpp[Formatting.Numeric.Standard#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#2)]
[!code-csharp-interactive[Formatting.Numeric.Standard#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#2)]
[!code-vb[Formatting.Numeric.Standard#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#2)]

[Volver a la tabla](#table)

<a name="EFormatString"></a>

## <a name="the-exponential-e-format-specifier"></a>Especificador de formato exponencial ("E")

El especificador de formato exponencial ("E") convierte un número en una cadena con el formato "-d.ddd…E+ddd" o "-d.ddd…e+ddd", donde cada "d" indica un dígito (0-9). La cadena comienza con un signo menos si el número es negativo. El separador decimal siempre va precedido por exactamente un dígito.

El especificador de precisión indica el número deseado de dígitos después del separador decimal. Si se omite el especificador de precisión, se emplea uno predeterminado que tiene seis dígitos después del separador decimal.

El modelo de mayúsculas o minúsculas del especificador de formato indica si se debe prefijar el exponente con una "E" o con una "e". El exponente siempre consta de un signo más o menos y de un mínimo de tres dígitos. El exponente se rellena con ceros para adaptarlo a este mínimo, si es necesario.

La información de formato del objeto <xref:System.Globalization.NumberFormatInfo> actual afecta a la cadena de resultado. En la tabla siguiente se enumeran las propiedades de <xref:System.Globalization.NumberFormatInfo> que controlan el formato de la cadena devuelta.

|Propiedad de NumberFormatInfo|Description|
|-------------------------------|-----------------|
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Define la cadena que indica que un número es negativo tanto para el coeficiente como para el exponente.|
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A>|Define la cadena que separa el dígito integral de los dígitos decimales en el coeficiente.|
|<xref:System.Globalization.NumberFormatInfo.PositiveSign%2A>|Define la cadena que indica que un exponente es positivo.|

En el ejemplo siguiente se da formato a un valor <xref:System.Double> con el especificador de formato exponencial:

[!code-cpp[Formatting.Numeric.Standard#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#3)]
[!code-csharp[Formatting.Numeric.Standard#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#3)]
[!code-vb[Formatting.Numeric.Standard#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#3)]

[Volver a la tabla](#table)

<a name="FFormatString"></a>

## <a name="the-fixed-point-f-format-specifier"></a>Especificador de formato de punto fijo ("F")

El especificador de formato de punto fijo ("F") convierte un número en una cadena con el formato "-ddd.ddd…", donde cada "d" indica un dígito (0-9). La cadena comienza con un signo menos si el número es negativo.

El especificador de precisión indica el número deseado de cifras decimales. Si se omite el especificador de precisión, la propiedad <xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A?displayProperty=nameWithType> actual proporciona la precisión numérica.

La información de formato del objeto <xref:System.Globalization.NumberFormatInfo> actual afecta a la cadena de resultado. En la tabla siguiente se enumeran las propiedades del objeto <xref:System.Globalization.NumberFormatInfo> que controlan el formato de la cadena de resultado.

|Propiedad de NumberFormatInfo|Description|
|-------------------------------|-----------------|
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Define la cadena que indica que un número es negativo.|
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A>|Define la cadena que separa los dígitos integrales de los decimales.|
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A>|Define el número predeterminado de dígitos decimales. Este valor puede reemplazarse por el uso del especificador de precisión.|

En el ejemplo siguiente se da formato a un valor <xref:System.Double> e <xref:System.Int32> con el especificador de formato de punto fijo:

[!code-cpp[Formatting.Numeric.Standard#4](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#4)]
[!code-csharp[Formatting.Numeric.Standard#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#4)]
[!code-vb[Formatting.Numeric.Standard#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#4)]

[Volver a la tabla](#table)

<a name="GFormatString"></a>

## <a name="the-general-g-format-specifier"></a>Especificador de formato general ("G")

El especificador de formato general ("G") convierte un número a la notación de punto fijo o científica más compacta, dependiendo del tipo del número y de si hay un especificador de precisión o no. El especificador de precisión define el número máximo de dígitos significativos que pueden aparecer en la cadena de resultado. Si el especificador de precisión se omite o es cero, el tipo del número determina la precisión predeterminada, como se indica en la tabla siguiente.

|Tipo numérico|Precisión predeterminada|
|------------------|-----------------------|
|<xref:System.Byte> o <xref:System.SByte>|3 dígitos|
|<xref:System.Int16> o <xref:System.UInt16>|5 dígitos|
|<xref:System.Int32> o <xref:System.UInt32>|10 dígitos|
|<xref:System.Int64>|19 dígitos|
|<xref:System.UInt64>|20 dígitos|
|<xref:System.Numerics.BigInteger>|Sin límite (igual que ["R"](#RFormatString))|
|<xref:System.Single>|7 dígitos|
|<xref:System.Double>|15 dígitos|
|<xref:System.Decimal>|29 dígitos|

La notación de punto fijo se utiliza si el exponente que resultaría de la expresión del número en notación científica es mayor que -5 y menor que el especificador de precisión, de lo contrario se utiliza la notación científica. El resultado contiene un separador decimal si es necesario y se omiten los ceros finales después de ese separador. Si el especificador de precisión está presente y el número de dígitos significativos del resultado supera la precisión especificada, los dígitos finales sobrantes se quitan mediante redondeo.

Sin embargo, si el número es <xref:System.Decimal> y se omite el especificador de precisión, siempre se usa la notación de punto fijo y se conservan los ceros finales.

Si se usa la notación científica, el exponente del resultado lleva el prefijo "E" si el especificador de formato es "G", o "e" si el especificador de formato es "g". El exponente contiene un mínimo de dos dígitos. Esto difiere del formato para la notación científica que genera el especificador de formato exponencial, que incluye un mínimo de tres dígitos en el exponente.

Tenga en cuenta que, cuando se usa con un valor <xref:System.Double>, el especificador de formato "G17" garantiza que el valor <xref:System.Double> original realice un recorrido de ida y vuelta correctamente. Esto se debe a que <xref:System.Double> es un número de punto flotante de doble precisión compatible con IEEE 754-2008 (`binary64`) que ofrece un máximo de 17 dígitos de precisión significativos. Se recomienda su uso en lugar del [especificador de formato "R"](#RFormatString), ya que, en algunos casos, "R" no logra realizar un recorrido de ida y vuelta correcto por los valores de números de punto flotante de doble precisión. Esto se ilustra en el siguiente ejemplo.

[!code-csharp-interactive[Round-tripping a Double](../../../samples/snippets/standard/base-types/format-strings/csharp/g17.cs#GeneralFormatSpecifier)]
[!code-vb[Round-tripping a Double](../../../samples/snippets/standard/base-types/format-strings/vb/g17.vb)]

Cuando se usa con un valor <xref:System.Single>, el especificador de formato "G9" garantiza que el valor <xref:System.Single> original realice un recorrido de ida y vuelta correctamente. Esto se debe a que <xref:System.Single> es un número de punto flotante de precisión sencilla compatible con IEEE 754-2008 (`binary32`) que ofrece hasta nueve dígitos de precisión significativos. Por motivos de rendimiento, se recomienda su uso en lugar del [especificador de formato "R"](#RFormatString).

La información de formato del objeto <xref:System.Globalization.NumberFormatInfo> actual afecta a la cadena de resultado. En la tabla siguiente se enumeran las propiedades de <xref:System.Globalization.NumberFormatInfo> que controlan el formato de la cadena de resultado.

|Propiedad de NumberFormatInfo|Description|
|-------------------------------|-----------------|
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Define la cadena que indica que un número es negativo.|
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A>|Define la cadena que separa los dígitos integrales de los decimales.|
|<xref:System.Globalization.NumberFormatInfo.PositiveSign%2A>|Define la cadena que indica que un exponente es positivo.|

En el ejemplo siguiente se da formato a valores de punto flotante ordenados con el especificador de formato general:

[!code-cpp[Formatting.Numeric.Standard#5](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#5)]
[!code-csharp[Formatting.Numeric.Standard#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#5)]
[!code-vb[Formatting.Numeric.Standard#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#5)]

[Volver a la tabla](#table)

<a name="NFormatString"></a>

## <a name="the-numeric-n-format-specifier"></a>Especificador de formato numérico ("N")

El especificador de formato numérico ("N") convierte un número en una cadena con el formato "-d,ddd,ddd.ddd…", donde "-" indica el símbolo de número negativo, si es necesario; "d", representa cada dígito (0-9); "," es el separador de grupo; y "." es el símbolo de punto decimal. El especificador de precisión indica el número deseado de dígitos después del separador decimal. Si se omite el especificador de precisión, el número de posiciones decimales está definido por la propiedad <xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A?displayProperty=nameWithType> actual.

La información de formato del objeto <xref:System.Globalization.NumberFormatInfo> actual afecta a la cadena de resultado. En la tabla siguiente se enumeran las propiedades de <xref:System.Globalization.NumberFormatInfo> que controlan el formato de la cadena de resultado.

|Propiedad de NumberFormatInfo|Description|
|-------------------------------|-----------------|
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Define la cadena que indica que un número es negativo.|
|<xref:System.Globalization.NumberFormatInfo.NumberNegativePattern%2A>|Define el formato de los valores negativos y especifica si el signo negativo se representa mediante paréntesis o por la propiedad <xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>.|
|<xref:System.Globalization.NumberFormatInfo.NumberGroupSizes%2A>|Define el número de dígitos enteros que aparecen entre los separadores de grupos.|
|<xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator%2A>|Define la cadena que separa los grupos de números integrales.|
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A>|Define la cadena que separa los dígitos integrales y decimales.|
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A>|Define el número predeterminado de dígitos decimales. Este valor puede reemplazarse por el uso de un especificador de precisión.|

En el ejemplo siguiente se da formato a valores de punto flotante ordenados con el especificador de formato numérico:

[!code-cpp[Formatting.Numeric.Standard#6](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#6)]
[!code-csharp[Formatting.Numeric.Standard#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#6)]
[!code-vb[Formatting.Numeric.Standard#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#6)]

[Volver a la tabla](#table)

<a name="PFormatString"></a>

## <a name="the-percent-p-format-specifier"></a>Especificador de formato de porcentaje ("P")

El especificador de formato de porcentaje ("P") multiplica un número por 100 y lo convierte en una cadena que representa un porcentaje. El especificador de precisión indica el número deseado de cifras decimales. Si se omite el especificador de precisión, se usará la precisión numérica predeterminada proporcionada por la propiedad <xref:System.Globalization.NumberFormatInfo.PercentDecimalDigits%2A> actual.

En la tabla siguiente se enumeran las propiedades de <xref:System.Globalization.NumberFormatInfo> que controlan el formato de la cadena devuelta.

|Propiedad de NumberFormatInfo|Description|
|-------------------------------|-----------------|
|<xref:System.Globalization.NumberFormatInfo.PercentPositivePattern%2A>|Define la posición del símbolo de porcentaje para los valores positivos.|
|<xref:System.Globalization.NumberFormatInfo.PercentNegativePattern%2A>|Define la posición del símbolo de porcentaje y del símbolo negativo para los valores negativos.|
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Define la cadena que indica que un número es negativo.|
|<xref:System.Globalization.NumberFormatInfo.PercentSymbol%2A>|Define el símbolo de porcentaje.|
|<xref:System.Globalization.NumberFormatInfo.PercentDecimalDigits%2A>|Define el número predeterminado de dígitos decimales en un valor de porcentaje. Este valor puede reemplazarse por el uso del especificador de precisión.|
|<xref:System.Globalization.NumberFormatInfo.PercentDecimalSeparator%2A>|Define la cadena que separa los dígitos integrales y decimales.|
|<xref:System.Globalization.NumberFormatInfo.PercentGroupSeparator%2A>|Define la cadena que separa los grupos de números integrales.|
|<xref:System.Globalization.NumberFormatInfo.PercentGroupSizes%2A>|Define el número de dígitos enteros que aparecen en un grupo.|

En el ejemplo siguiente se da formato a valores de punto flotante con el especificador de formato de porcentaje:

[!code-cpp[Formatting.Numeric.Standard#7](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#7)]
[!code-csharp[Formatting.Numeric.Standard#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#7)]
[!code-vb[Formatting.Numeric.Standard#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#7)]

[Volver a la tabla](#table)

<a name="RFormatString"></a>

## <a name="the-round-trip-r-format-specifier"></a>Especificador de formato de operación de ida y vuelta ("R")

El especificador de formato de operación de ida y vuelta ("R") intenta garantizar que un valor numérico que se convierte en una cadena vuelva a tomar el mismo valor numérico. Este formato solo es compatible para los tipos <xref:System.Single>, <xref:System.Double> y <xref:System.Numerics.BigInteger>.

Para los valores <xref:System.Double>, el especificador de formato "R", en algunos casos, no logra realizar un recorrido de ida y vuelta correcto por el valor original. Para los dos valores <xref:System.Double> y <xref:System.Single>, también ofrece un rendimiento relativamente bajo. En su lugar, se recomienda usar el especificador de formato ["G17"](#GFormatString) para los valores <xref:System.Double> y el especificador de formato ["G9"](#GFormatString) para realizar un recorrido de ida y vuelta correcto por los valores <xref:System.Single>.

Cuando se da formato a un valor <xref:System.Numerics.BigInteger> mediante este especificador, su representación de cadena contiene todos los dígitos significativos del valor <xref:System.Numerics.BigInteger>.

Aunque puede incluir un especificador de precisión, se omite. Los especificadores de ida y vuelta tienen prioridad sobre la precisión al utilizar este especificador.
La información de formato del objeto <xref:System.Globalization.NumberFormatInfo> actual afecta a la cadena de resultado. En la tabla siguiente se enumeran las propiedades de <xref:System.Globalization.NumberFormatInfo> que controlan el formato de la cadena de resultado.

|Propiedad de NumberFormatInfo|Description|
|-------------------------------|-----------------|
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Define la cadena que indica que un número es negativo.|
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A>|Define la cadena que separa los dígitos integrales de los decimales.|
|<xref:System.Globalization.NumberFormatInfo.PositiveSign%2A>|Define la cadena que indica que un exponente es positivo.|

En el ejemplo siguiente se da formato a un valor <xref:System.Numerics.BigInteger> con el especificador de formato de ida y vuelta.

[!code-cpp[R format specifier with a BigInteger](../../../samples/snippets/standard/base-types/format-strings/biginteger-r.cpp)]
[!code-csharp[R format specifier with a BigInteger](../../../samples/snippets/standard/base-types/format-strings/biginteger-r.cs)]
[!code-vb[R format specifier with a BigInteger](../../../samples/snippets/standard/base-types/format-strings/biginteger-r.vb)]

> [!IMPORTANT]
> En algunos casos, los valores <xref:System.Double> con el formato de cadena numérica estándar "R" no realizan correctamente la operación de ida y vuelta si se compilan usando los modificadores `/platform:x64` o `/platform:anycpu` y se ejecutan en sistemas de 64 bits. Para más información, consulte el siguiente párrafo.

Para solucionar el problema de los valores <xref:System.Double> con formato de cadena numérico estándar “R” que no hacen correctamente el viaje de ida y vuelta si se compilan con conmutadores `/platform:x64` o `/platform:anycpu` y se ejecutan en sistemas de 64 bits, puede dar formato a los valores <xref:System.Double> usando la cadena de formato numérico estándar “G17”. En el ejemplo siguiente se usa la cadena de formato "R" con un valor <xref:System.Double> que no realiza correctamente la operación de ida y vuelta, y usa también la cadena de formato "G17" para realizar correctamente la operación de ida y vuelta del valor original:

[!code-csharp[System.Double.ToString#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Double.ToString/cs/roundtripex1.cs#RoundTrip)]
[!code-vb[System.Double.ToString#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Double.ToString/vb/roundtripex1.vb#5)]

[Volver a la tabla](#table)

<a name="XFormatString"></a>

## <a name="the-hexadecimal-x-format-specifier"></a>Especificador de formato hexadecimal ("X")

El especificador de formato hexadecimal ("X") convierte un número en una cadena de dígitos hexadecimales. El modelo de mayúsculas y minúsculas del especificador de formato indica si se van a usar caracteres en mayúsculas o en minúsculas para los dígitos hexadecimales mayores de 9. Por ejemplo, use "X" para generar "ABCDEF" y "x" para generar "abcdef". Este formato sólo es compatible con los tipos enteros.

El especificador de precisión indica el número mínimo de dígitos deseado en la cadena resultante. Si es preciso, el número se rellena con ceros a la izquierda para generar el número de dígitos que aporta el especificador de precisión.

La información de formato del objeto <xref:System.Globalization.NumberFormatInfo> actual no afecta a la cadena de resultado.

En el ejemplo siguiente se da formato a valores <xref:System.Int32> con el especificador de formato hexadecimal.

[!code-cpp[Formatting.Numeric.Standard#9](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#9)]
[!code-csharp-interactive[Formatting.Numeric.Standard#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#9)]
[!code-vb[Formatting.Numeric.Standard#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#9)]

[Volver a la tabla](#table)

<a name="NotesStandardFormatting"></a>

## <a name="notes"></a>Notas

### <a name="control-panel-settings"></a>Configuración del Panel de control

Los valores de configuración del elemento **Configuración regional y de idioma** del Panel de control influyen en la cadena de resultado generada por una operación de formato. Esas configuraciones se usan para inicializar el objeto <xref:System.Globalization.NumberFormatInfo> asociado a la referencia cultural del subproceso actual, que proporciona valores que se usan para controlar el formato. Los equipos que usan configuraciones diferentes generarán cadenas de resultado distintas.

Asimismo, si se utiliza el constructor <xref:System.Globalization.CultureInfo.%23ctor%28System.String%29> para crear instancias de un nuevo objeto <xref:System.Globalization.CultureInfo> que representa la misma referencia cultural que la referencia cultural del sistema actual, cualquier personalización establecida por el elemento **Configuración regional y de idioma** del Panel de control se aplicará al nuevo objeto <xref:System.Globalization.CultureInfo>. Puede usar el constructor <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29> para crear un objeto <xref:System.Globalization.CultureInfo> que no refleje las personalizaciones de un sistema.

### <a name="numberformatinfo-properties"></a>Propiedades NumberFormatInfo

El formato se ve influenciado por las propiedades del objeto <xref:System.Globalization.NumberFormatInfo> actual, proporcionado implícitamente por la referencia cultural del subproceso actual o explícitamente por el parámetro <xref:System.IFormatProvider> del método que invoca el formato. Especifique un objeto <xref:System.Globalization.NumberFormatInfo> o <xref:System.Globalization.CultureInfo> para dicho parámetro.

> [!NOTE]
> Para obtener información sobre la personalización de patrones o cadenas que se usan para dar formato a valores numéricos, vea el tema de la clase <xref:System.Globalization.NumberFormatInfo>.

### <a name="integral-and-floating-point-numeric-types"></a>Tipos numéricos enteros y de punto flotante

Algunas descripciones de especificadores de formato numérico estándar hacen referencia a tipos numéricos enteros o de punto flotante. Los tipos numéricos integrales son <xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64> y <xref:System.Numerics.BigInteger>. Los tipos numéricos de punto flotante son <xref:System.Decimal>, <xref:System.Single> y <xref:System.Double>.

### <a name="floating-point-infinities-and-nan"></a>Infinitos de punto flotante y NaN

Independientemente de la cadena de formato, si el valor de un tipo de punto flotante <xref:System.Single> o <xref:System.Double> es infinito positivo, infinito negativo o NaN (Not a Number, no es un número), la cadena con formato será el valor de la propiedad <xref:System.Globalization.NumberFormatInfo.PositiveInfinitySymbol%2A>, <xref:System.Globalization.NumberFormatInfo.NegativeInfinitySymbol%2A> o <xref:System.Globalization.NumberFormatInfo.NaNSymbol%2A> respectiva especificada por el objeto <xref:System.Globalization.NumberFormatInfo> aplicable actualmente.

## <a name="example"></a>Ejemplo

[!INCLUDE[interactive-note](~/includes/csharp-interactive-partial-note.md)]

En el ejemplo siguiente se da formato a un valor numérico integral y de punto flotante mediante la referencia cultural en-US y todos los especificadores de formato numérico estándar. En este ejemplo se usan dos tipos numéricos concretos (<xref:System.Double> y <xref:System.Int32>), pero se obtendrían resultados similares con cualquiera de los demás tipos base numéricos (<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>, <xref:System.Numerics.BigInteger>, <xref:System.Decimal> y <xref:System.Single>).

[!code-csharp[system.x.tostring-and-culture#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.X.ToString-and-Culture/cs/xts.cs#FinalExample)]
[!code-vb[system.x.tostring-and-culture#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.X.ToString-and-Culture/vb/xts.vb#1)]

## <a name="see-also"></a>Vea también

- <xref:System.Globalization.NumberFormatInfo>
- [Cadenas con formato numérico personalizado](../../../docs/standard/base-types/custom-numeric-format-strings.md)
- [Aplicación de formato a tipos](../../../docs/standard/base-types/formatting-types.md)
- [Rellenar un número con ceros a la izquierda](../../../docs/standard/base-types/how-to-pad-a-number-with-leading-zeros.md)
- [Formatos compuestos](../../../docs/standard/base-types/composite-formatting.md)
- [Ejemplo: Utilidad de formato WinForms de .NET Core (C#)](https://docs.microsoft.com/samples/dotnet/samples/windowsforms-formatting-utility-cs)
- [Ejemplo: Utilidad de formato WinForms de .NET Core (Visual Basic)](https://docs.microsoft.com/samples/dotnet/samples/windowsforms-formatting-utility-vb)
