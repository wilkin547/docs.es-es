---
title: Cadenas con formato numérico personalizado
ms.date: 06/25/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- format strings
- custom numeric format strings
- numbers [.NET Framework], formatting
- format specifiers, numeric
- formatting numbers [.NET Framework]
- format specifiers, custom numeric format strings
ms.assetid: 6f74fd32-6c6b-48ed-8241-3c2b86dea5f4
ms.openlocfilehash: 1eb9c3c189d7bba3a12fdcd0c3d600a66bf819ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "75348305"
---
# <a name="custom-numeric-format-strings"></a>Cadenas con formato numérico personalizado

Puede crear una cadena de formato numérico personalizado, formada por uno o varios especificadores numéricos personalizados, para definir cómo debe darse formato a los datos numéricos. Una cadena de formato numérico personalizado es cualquier cadena que no sea una [cadena de formato numérico estándar](../../../docs/standard/base-types/standard-numeric-format-strings.md).

Algunas sobrecargas del método `ToString` de todos los tipos numéricos admiten las cadenas de formato numérico personalizado. Por ejemplo, se puede proporcionar una cadena de formato numérico a los métodos <xref:System.Int32.ToString%28System.String%29> y <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29> del tipo <xref:System.Int32> . La [característica de formato compuesto](../../../docs/standard/base-types/composite-formatting.md) de .NET, que utilizan algunos métodos `Write` y `WriteLine` de las clases <xref:System.Console> y <xref:System.IO.StreamWriter>, el método <xref:System.String.Format%2A?displayProperty=nameWithType> y el método <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>, admite también cadenas de formato numérico personalizado. La característica [interpolación de cadenas](../../csharp/language-reference/tokens/interpolated.md) admite también cadenas de formato numérico personalizado.

> [!TIP]
> Puede descargar la **Utilidad de formato**, que es una aplicación de .NET Core Windows Forms que permite aplicar cadenas de formato a valores numéricos o de fecha y hora, y que muestra la cadena de resultado. El código fuente está disponible para [C#](https://docs.microsoft.com/samples/dotnet/samples/winforms-formatting-utility-cs) y [Visual Basic](https://docs.microsoft.com/samples/dotnet/samples/winforms-formatting-utility-vb).

<a name="table"></a> En la tabla siguiente se describen los especificadores de formato numérico personalizado y se muestran las salidas de ejemplo generadas por cada especificador de formato. Consulte la sección [Notas](#NotesCustomFormatting) para obtener más información sobre cómo usar las cadenas con formato numérico personalizado y la sección [Ejemplo](#example) para ver una ilustración completa de su uso.

|Especificador de formato|Name|Description|Ejemplos|
|----------------------|----------|-----------------|--------------|
|"0"|Marcador de posición cero|Reemplaza el cero con el dígito correspondiente si hay alguno presente; de lo contrario, el cero aparece en la cadena de resultado.<br /><br /> Más información: [El especificador personalizado "0"](#Specifier0).|1234.5678 ("00000") -> 01235<br /><br /> 0.45678 ("0.00", en-US) -> 0.46<br /><br /> 0.45678 ("0.00", fr-FR) -> 0,46|
|"#"|Marcador de posición de dígito.|Reemplaza el símbolo "#" por el dígito correspondiente si hay alguno presente; de lo contrario, no aparece ningún dígito en la cadena de resultado.<br /><br /> Tenga en cuenta que no se mostrará ningún dígito en la cadena de resultado si el dígito que se encuentra en la cadena de entrada es un 0 no significativo. Por ejemplo, 0003 ("####") -> 3.<br /><br /> Más información: [El especificador personalizado "#"](#SpecifierD).|1234.5678 ("#####") -> 1235<br /><br /> 0.45678 ("#.##", en-US) -> .46<br /><br /> 0.45678 ("#.##", fr-FR) -> ,46|
|"."|Separador decimal|Determina la ubicación del separador decimal en la cadena de resultado.<br /><br /> Más información: [El "." Especificador personalizado](#SpecifierPt).|0.45678 ("0.00", en-US) -> 0.46<br /><br /> 0.45678 ("0.00", fr-FR) -> 0,46|
|","|Separador de grupos y escala numérica|Actúa como separador de grupos y como especificador de escala numérica. Como separador de grupos, inserta un carácter separador de grupos adaptado entre cada grupo. Como especificador de escala numérica, divide un número por 1000 por cada coma especificada.<br /><br /> Más información: [El especificador personalizado ","](#SpecifierTh).|Especificador de separador de grupos:<br /><br /> 2147483647 ("##,#", en-US) -> 2,147,483,647<br /><br /> 2147483647 ("##,#", es-ES) -> 2.147.483.647<br /><br /> Especificador de escala:<br /><br /> 2147483647 ("#,#,,", en-US) -> 2,147<br /><br /> 2147483647 ("#,#,,", es-ES) -> 2.147|
|"%"|Marcador de posición de porcentaje.|Multiplica un número por 100 e inserta un símbolo de porcentaje adaptado en la cadena de resultado.<br /><br /> Más información: [El especificador personalizado "%"](#SpecifierPct).|0.3697 ("%#0.00", en-US) -> %36.97<br /><br /> 0.3697 ("%#0.00", el-GR) -> %36,97<br /><br /> 0.3697 ("##.0 %", en-US) -> 37.0 %<br /><br /> 0.3697 ("##.0 %", el-GR) -> 37,0 %|
|"‰"|Marcador de posición de "por mil"|Multiplica un número por 1000 e inserta un símbolo de "por mil" adaptado en la cadena de resultado.<br /><br /> Más información: [El especificador personalizado "‰"](#SpecifierPerMille).|0.03697 ("#0.00‰", en-US) -> 36.97‰<br /><br /> 0.03697 ("#0.00‰", ru-RU) -> 36,97‰|
|"E0"<br /><br /> "E+0"<br /><br /> "E-0"<br /><br /> "E0"<br /><br /> "E+0"<br /><br /> "E-0"|Notación exponencial|Si va seguido al menos de un 0 (cero), da formato al resultado usando notación exponencial. El modelo de mayúsculas de "E" o "e" indica el modelo de mayúsculas del símbolo de exponente en la cadena de resultado. El número de ceros que siguen al carácter "E" o "e" determina el número mínimo de dígitos en el exponente. Un signo más (+) indica que un carácter de signo precede siempre al exponente. Un signo menos (-) indica que un carácter de signo solo precede a los exponentes negativos.<br /><br /> Más información: [Los especificadores personalizados "E" y "e"](#SpecifierExponent).|987654 ("#0.0e0") -> 98.8e4<br /><br /> 1503.92311 ("0.0##e+00") -> 1.504e+03<br /><br /> 1.8901385E-16 ("0.0e+00") -> 1.9e-16|
|"\\"|Carácter de escape|Hace que el carácter siguiente se interprete como un literal en lugar de como un especificador de formato personalizado.<br /><br /> Más información: [El carácter de escape "\\"](#SpecifierEscape).|987654 ("\\###00\\#") -> #987654#|
|'*cadena*'<br /><br /> "*cadena*"|Delimitador de cadena literal|Indica que los caracteres que encierra se deben copiar en la cadena de resultado sin modificar.<br/><br/>Más información: [Literales de caracteres](#character-literals).|68 ("# ' grados'") -> 68 grados<br /><br /> 68 ("# ' grados'") -> 68 grados|
|;|Separador de secciones|Define secciones con cadenas de formato diferentes para los números positivos, negativos y cero.<br /><br /> Más información: [El separador de sección ";"](#SectionSeparator).|12.345 ("#0.0#;(#0.0#);-\0-") -> 12.35<br /><br /> 0 ("#0.0#;(#0.0#);-\0-") -> -0-<br /><br /> -12.345 ("#0.0#;(#0.0#);-\0-") -> (12.35)<br /><br /> 12.345 ("#0.0#;(#0.0#)") -> 12.35<br /><br /> 0 ("#0.0#;(#0.0#)") -> 0.0<br /><br /> -12.345 ("#0.0#;(#0.0#)") -> (12.35)|
|Otro|Todos los demás caracteres|El carácter se copia en la cadena de resultado sin modificar.<br/><br/>Más información: [Literales de caracteres](#character-literals).|68 ("# °") -> 68 °|

En las secciones siguientes se proporciona información detallada sobre cada uno de los especificadores de formato numérico personalizado.

[!INCLUDE[C# interactive-note](~/includes/csharp-interactive-partial-note.md)]

<a name="Specifier0"></a>

## <a name="the-0-custom-specifier"></a>Especificador personalizado "0"

El especificador de formato personalizado "0" actúa como un símbolo de marcador de posición cero. Si el valor al que se está dando formato tiene un dígito en la posición donde aparece el cero en la cadena de formato, se copia ese dígito a la cadena de resultado; de lo contrario, aparecerá un cero en la cadena de resultado. La posición del cero que aparece más a la izquierda antes del separador decimal y la del cero que está más a la derecha después del separador decimal determinan el intervalo de dígitos que están siempre presentes en la cadena de resultado.

El especificador "00" hace que el valor se redondee al dígito más próximo que precede al decimal, donde siempre se utiliza el redondeo para evitar el cero. Por ejemplo, al aplicar el formato a 34.5 con "00" el resultado del valor es 35.

En el ejemplo siguiente se muestran varios valores a los que se les ha aplicado cadenas de formato personalizado que incluyen marcadores de posición cero.

[!code-cpp[Formatting.Numeric.Custom#1](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/custom.cpp#1)]
[!code-csharp[Formatting.Numeric.Custom#1](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/custom.cs#1)]
[!code-vb[Formatting.Numeric.Custom#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/Custom.vb#1)]

[Volver a la tabla](#table)

<a name="SpecifierD"></a>

## <a name="the--custom-specifier"></a>Especificador personalizado "#"

El especificador de formato personalizado "#" actúa como un símbolo de marcador de posición de dígitos. Si el valor al que se está dando formato tiene un dígito en la posición donde aparece el símbolo "#" en la cadena de formato, ese dígito se copia a la cadena de resultado. En caso contrario, no se almacena nada en esa posición de la cadena de resultado.

Tenga en cuenta que este especificador nunca muestra un cero que no sea un dígito significativo, incluso aunque el cero sea el único dígito de la cadena. Solo mostrará cero si es un dígito significativo del número que se está mostrando.

La cadena de formato "##" hace que el valor se redondee al dígito más próximo que precede al decimal, donde siempre se utiliza el redondeo para evitar el cero. Por ejemplo, al aplicar el formato a 34.5 con "##" el resultado del valor es 35.

En el ejemplo siguiente se muestran varios valores a los que se les ha aplicado cadenas de formato personalizado que incluyen marcadores de posición de dígitos.

[!code-cpp[Formatting.Numeric.Custom#2](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/custom.cpp#2)]
[!code-csharp[Formatting.Numeric.Custom#2](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/custom.cs#2)]
[!code-vb[Formatting.Numeric.Custom#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/Custom.vb#2)]

Para devolver una cadena de resultado en la que los dígitos que faltan o los ceros iniciales se reemplazan por espacios, use la [característica de formato compuesto](../../../docs/standard/base-types/composite-formatting.md) y especifique un ancho de campo, como se muestra en el ejemplo siguiente.

[!code-cpp[Formatting.Numeric.Custom#12](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/SpaceOrDigit1.cpp#12)]
[!code-csharp[Formatting.Numeric.Custom#12](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/SpaceOrDigit1.cs#12)]
[!code-vb[Formatting.Numeric.Custom#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/SpaceOrDigit1.vb#12)]

[Volver a la tabla](#table)

<a name="SpecifierPt"></a>

## <a name="the--custom-specifier"></a>Especificador personalizado "."

El especificador de formato personalizado "." inserta un separador decimal localizado en la cadena del resultado. El primer punto de la cadena de formato determina la ubicación del separador decimal en el valor con formato y se omite cualquier punto adicional.

El carácter que se usa como separador decimal en la cadena de resultado no es siempre un punto; viene determinado por la propiedad <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A> del objeto <xref:System.Globalization.NumberFormatInfo> que controla la aplicación de formato.

En el ejemplo siguiente se utiliza el especificador de formato "." para definir la ubicación del separador decimal en varias cadenas de resultado.

[!code-cpp[Formatting.Numeric.Custom#3](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/custom.cpp#3)]
[!code-csharp[Formatting.Numeric.Custom#3](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/custom.cs#3)]
[!code-vb[Formatting.Numeric.Custom#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/Custom.vb#3)]

[Volver a la tabla](#table)

<a name="SpecifierTh"></a>

## <a name="the--custom-specifier"></a>Especificador personalizado ","

El carácter "," actúa como separador de grupos y como especificador de escala numérica.

- Separador de grupos: si se especifican una o varias comas dos marcadores de posición de dígitos (0 ó #) que dan formato a los dígitos enteros de un número, se insertará un carácter separador de grupos entre cada grupo de números en la parte entera de la salida.

  Las propiedades <xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator%2A> y <xref:System.Globalization.NumberFormatInfo.NumberGroupSizes%2A> del objeto <xref:System.Globalization.NumberFormatInfo> actual determinan el carácter utilizado como separador de grupos de números y el tamaño de cada grupo de números. Por ejemplo, si se utiliza la cadena "#,#" y la referencia cultural de todos los idiomas para dar formato al número 1000, el resultado será "1,000".

- Especificador de escala numérica: si se especifican una o varias comas inmediatamente a la izquierda del punto decimal explícito o implícito, el número al que se va a dar formato se divide por 1000 por cada coma. Por ejemplo, si se utiliza la cadena "0,," para dar formato al número 100 millones, el resultado será "100".

Puede usar especificadores de separador de grupos y de escala numérica en la misma cadena de formato. Por ejemplo, si se utiliza la cadena "#,0,," y la referencia cultural de todos los idiomas para dar formato al número mil millones, el resultado será "1,000".

En el ejemplo siguiente se muestra el uso de la coma como separador de grupos.

[!code-cpp[Formatting.Numeric.Custom#4](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/custom.cpp#4)]
[!code-csharp[Formatting.Numeric.Custom#4](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/custom.cs#4)]
[!code-vb[Formatting.Numeric.Custom#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/Custom.vb#4)]

En el ejemplo siguiente se muestra el uso de la coma como especificador de escala numérica.

[!code-cpp[Formatting.Numeric.Custom#5](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/custom.cpp#5)]
[!code-csharp[Formatting.Numeric.Custom#5](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/custom.cs#5)]
[!code-vb[Formatting.Numeric.Custom#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/Custom.vb#5)]

[Volver a la tabla](#table)

<a name="SpecifierPct"></a>

## <a name="the--custom-specifier"></a>Especificador personalizado "%"

Un signo de porcentaje (%) en una cadena de formato hace que se multiplique un número por 100 antes de darle formato. El símbolo de porcentaje adaptado se inserta en el número en la ubicación donde aparece % en la cadena de formato. La propiedad <xref:System.Globalization.NumberFormatInfo.PercentSymbol%2A> del objeto <xref:System.Globalization.NumberFormatInfo> actual define el carácter de porcentaje empleado.

En el ejemplo siguiente se definen varias cadenas de formato personalizado que incluyen el especificador personalizado "%".

[!code-cpp[Formatting.Numeric.Custom#6](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/custom.cpp#6)]
[!code-csharp[Formatting.Numeric.Custom#6](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/custom.cs#6)]
[!code-vb[Formatting.Numeric.Custom#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/Custom.vb#6)]

[Volver a la tabla](#table)

<a name="SpecifierPerMille"></a>

## <a name="the--custom-specifier"></a>Especificador personalizado "‰"

Un carácter de "por mil" (‰ o \u2030) en una cadena de formato hace que un número se multiplique por 1000 antes de darle formato. El símbolo de "por mil" adecuado se inserta en la cadena devuelta, en la ubicación de la cadena de formato en la que aparece el símbolo ‰. La propiedad <xref:System.Globalization.NumberFormatInfo.PerMilleSymbol%2A?displayProperty=nameWithType> del objeto que proporciona la información de formato específica de la referencia cultural es la que determina el carácter de "por mil" que se utiliza.

En el ejemplo siguiente se define una cadena de formato personalizado que incluye el especificador personalizado "‰".

[!code-cpp[Formatting.Numeric.Custom#9](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/custom.cpp#9)]
[!code-csharp[Formatting.Numeric.Custom#9](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/custom.cs#9)]
[!code-vb[Formatting.Numeric.Custom#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/Custom.vb#9)]

[Volver a la tabla](#table)

<a name="SpecifierExponent"></a>

## <a name="the-e-and-e-custom-specifiers"></a>Especificadores personalizados "E" y "e"

Si alguna de las cadenas "E", "E+", "E-", "e", "e+", o "e-" está presente en la cadena de formato y va seguida inmediatamente de al menos un cero, se da formato al número mediante notación científica con una 'E' o una 'e' insertadas entre el número y el exponente. El número de ceros que hay a continuación del indicador de notación científica determina el número mínimo de dígitos para el exponente. Los formatos 'E+' y 'e+' indican que un signo más o un signo menos debe preceder siempre al exponente. Los formatos 'E', 'E-', 'e' o 'e-' indican que un carácter de signo debe preceder solo a exponentes negativos.

En el ejemplo siguiente se da formato a varios valores numéricos utilizando los especificadores de notación científica.

[!code-cpp[Formatting.Numeric.Custom#7](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/custom.cpp#7)]
[!code-csharp[Formatting.Numeric.Custom#7](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/custom.cs#7)]
[!code-vb[Formatting.Numeric.Custom#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/Custom.vb#7)]

[Volver a la tabla](#table)

<a name="SpecifierEscape"></a>

## <a name="the--escape-character"></a>Carácter de escape "\\"

Los símbolos "#", "0", ".", ",", "%" y "‰" en una cadena de formato se interpretan como especificadores de formato en lugar de como caracteres literales. Dependiendo de su posición en una cadena de formato personalizado, la "E" en mayúsculas y minúsculas así como los símbolos + y - también se pueden interpretar como especificadores de formato.

Para evitar que un carácter se interprete como un especificador de formato, puede precederlo con una barra diagonal inversa, que es el carácter de escape. El carácter de escape significa que el siguiente carácter es un carácter literal que se debe incluir en la cadena de resultado sin modificar.

Para incluir una barra diagonal inversa en una cadena de resultado, debe indicar su secuencia de escape con otra barra diagonal inversa (`\\`).

> [!NOTE]
> Algunos compiladores, como los compiladores de C# y C++, también pueden interpretar un único carácter de barra diagonal inversa como un carácter de escape. Para asegurarse de que una cadena se interpreta correctamente al darle formato, puede usar el carácter literal de cadena textual (el carácter @) antes de la cadena en C# o puede agregar otro carácter de barra diagonal inversa delante de cada barra diagonal inversa en C# y C++. En el siguiente ejemplo de C# se muestran ambos enfoques.

En el ejemplo siguiente se usa el carácter de escape para evitar que la operación de formato interprete los caracteres "#", "0" y "\\" como caracteres de escape o especificadores de formato. En el ejemplo de C# se usa una barra diagonal inversa adicional para asegurarse de que una barra diagonal inversa se interprete como un carácter literal.

[!code-cpp[Formatting.Numeric.Custom#11](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/escape1.cpp#11)]
[!code-csharp-interactive[Formatting.Numeric.Custom#11](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/escape1.cs#11)]
[!code-vb[Formatting.Numeric.Custom#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/escape1.vb#11)]

[Volver a la tabla](#table)

<a name="SectionSeparator"></a>

## <a name="the--section-separator"></a>Separador de sección ";"

El punto y coma (;) es un especificador de formato condicional que aplica distinto formato a un número dependiendo de si su valor es positivo, negativo o cero. Para generar este comportamiento, una cadena de formato personalizado puede contener hasta tres secciones separadas por signos de punto y coma. Estas secciones se describen en la siguiente tabla.

|Número de secciones|Description|
|------------------------|-----------------|
|Una sección|La cadena de formato se aplica a todos los valores.|
|Dos secciones|La primera sección se aplica a valores positivos y ceros, y la segunda, sólo a valores negativos.<br /><br /> Si el número al que se va a dar formato es negativo, pero se convierte en cero después de redondearlo según el formato de la segunda sección, se da formato al cero resultante según la primera sección.|
|Tres secciones.|La primera sección se aplica a valores positivos y ceros, la segunda, sólo a valores negativos, y la tercera, a ceros.<br /><br /> La segunda sección se puede dejar vacía (no dejando nada entre los signos de punto y coma) y, en ese caso, la primera sección se aplica a los valores distintos de cero.<br /><br /> Si el número al que se va a dar formato es distinto de cero, pero se convierte en cero después de redondearlo según el formato de la primera o la segunda sección, se da formato al cero resultante según la tercera sección.|

Los separadores de sección omiten cualquier formato preexistente asociado a un número al dar formato al valor final. Por ejemplo, los valores negativos se muestran siempre con signo menos cuando se utilizan separadores de sección. Si se desea que el valor con formato final tenga un signo menos, debe incluir explícitamente el signo menos como parte del especificador de formato personalizado.

En el ejemplo siguiente se usa el especificador de formato ";" para aplicar un formato diferente a los números positivos, negativos y cero.

[!code-cpp[Formatting.Numeric.Custom#8](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/custom.cpp#8)]
[!code-csharp-interactive[Formatting.Numeric.Custom#8](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/custom.cs#8)]
[!code-vb[Formatting.Numeric.Custom#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/Custom.vb#8)]

[Volver a la tabla](#table)

## <a name="character-literals"></a>Literales de carácter

Los especificadores de formato que aparecen en una cadena de formato numérico personalizado siempre se interpretan como caracteres de formato y no como caracteres literales. Se incluyen los caracteres siguientes:

- [0](#Specifier0)
- [\#](#SpecifierD)
- [%](#SpecifierPct)
- [‰](#SpecifierPerMille)
- '
- [\\](#SpecifierEscape)
- [.](#SpecifierPt)
- [,](#SpecifierTh)
- [E o e](#SpecifierExponent), según su posición en la cadena de formato.

Todos los demás caracteres se interpretan siempre como literales de carácter y, en una operación de formato, se incluyen en la cadena de resultado sin modificar.  En una operación de análisis, deben coincidir exactamente con los caracteres de la cadena de entrada; la comparación distingue entre mayúsculas y minúsculas.

En el ejemplo siguiente se muestra un uso habitual de las unidades de carácter literal (en este caso, los millares):

[!code-csharp-interactive[literal characters](~/samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/literal2.cs#1)]
[!code-vb[literal characters](~/samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/literal2.vb#1)]

Hay dos formas de indicar que los caracteres se han de interpretar como caracteres literales y no como caracteres de formato, para que se puedan incluir en una cadena de resultado o analizarse correctamente en una cadena de entrada:

- Mediante el escape de un carácter de formato. Para obtener más información, vea [Carácter de escape "\\"](#SpecifierEscape).

- Mediante la inclusión de toda la cadena literal entre comillas o apóstrofes.

En el ejemplo siguiente se usan los dos enfoques para incluir caracteres reservados en una cadena de formato numérico personalizada.

[!code-csharp-interactive[including reserved characters](~/samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/literal1.cs#1)]
[!code-vb[including reserved characters](~/samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/literal1.vb#1)]

<a name="NotesCustomFormatting"></a>

## <a name="notes"></a>Notas

### <a name="floating-point-infinities-and-nan"></a>Infinitos de punto flotante y NaN

Independientemente de la cadena de formato, si el valor de un tipo de punto flotante <xref:System.Single> o <xref:System.Double> es infinito positivo, infinito negativo o NaN (Not a Number, no es un número), la cadena con formato será el valor de la propiedad <xref:System.Globalization.NumberFormatInfo.PositiveInfinitySymbol%2A>, <xref:System.Globalization.NumberFormatInfo.NegativeInfinitySymbol%2A>o <xref:System.Globalization.NumberFormatInfo.NaNSymbol%2A> respectiva especificada por el objeto <xref:System.Globalization.NumberFormatInfo> aplicable actualmente.

### <a name="control-panel-settings"></a>Configuración del Panel de control

Los valores de configuración del elemento **Configuración regional y de idioma** del Panel de control influyen en la cadena de resultado generada por una operación de formato. Estos valores de configuración se utilizan para inicializar el objeto <xref:System.Globalization.NumberFormatInfo> asociado a la referencia cultural del subproceso actual, y la referencia cultural del subproceso actual proporciona valores que se utilizan para controlar el formato. Los equipos que usan configuraciones diferentes generarán cadenas de resultado distintas.

Asimismo, si se usa el constructor <xref:System.Globalization.CultureInfo.%23ctor%28System.String%29?displayProperty=nameWithType> para crear instancias de un nuevo objeto <xref:System.Globalization.CultureInfo> que representa la misma referencia cultural que la referencia cultural del sistema actual, cualquier personalización establecida por el elemento **Configuración regional y de idioma** del Panel de control se aplicará al nuevo objeto <xref:System.Globalization.CultureInfo> . Puede usar el constructor <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> para crear un objeto <xref:System.Globalization.CultureInfo> que no refleje las personalizaciones de un sistema.

### <a name="rounding-and-fixed-point-format-strings"></a>Cadenas de formato de punto fijo y redondeo

Para las cadenas de formato de punto fijo (es decir, las cadenas de formato que no contienen caracteres de formato de notación científica), los números se redondean hasta tantos decimales como marcadores de posición de dígitos haya a la derecha del separador decimal. Si la cadena de formato no contiene ningún separador decimal, el número se redondea al entero más próximo. Si el número tiene más dígitos que marcadores de posición de dígitos a la izquierda del separador decimal, los dígitos adicionales se copian en la cadena de resultado justo antes del primer marcador de posición de dígitos.

[Volver a la tabla](#table)

<a name="example"></a>

## <a name="example"></a>Ejemplo

En el siguiente ejemplo se muestran dos cadenas de formato numérico personalizado. En ambos casos, el marcador de posición de dígitos (`#`) muestra los datos numéricos, y todos los demás caracteres se copian en la cadena de resultado.

[!code-cpp[Formatting.Numeric.Custom#10](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/example1.cpp#10)]
[!code-csharp-interactive[Formatting.Numeric.Custom#10](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/example1.cs#10)]
[!code-vb[Formatting.Numeric.Custom#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/example1.vb#10)]

[Volver a la tabla](#table)

## <a name="see-also"></a>Vea también

- <xref:System.Globalization.NumberFormatInfo?displayProperty=nameWithType>
- [Aplicación de formato a tipos](../../../docs/standard/base-types/formatting-types.md)
- [Cadenas con formato numérico estándar](../../../docs/standard/base-types/standard-numeric-format-strings.md)
- [Rellenar un número con ceros a la izquierda](../../../docs/standard/base-types/how-to-pad-a-number-with-leading-zeros.md)
- [Ejemplo: Utilidad de formato WinForms de .NET Core (C#)](https://docs.microsoft.com/samples/dotnet/samples/winforms-formatting-utility-cs)
- [Ejemplo: Utilidad de formato WinForms de .NET Core (Visual Basic)](https://docs.microsoft.com/samples/dotnet/samples/winforms-formatting-utility-vb)
