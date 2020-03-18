---
title: Aplicar formato a tipos en .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data formatting [.NET Framework]
- dates [.NET Framework], formatting
- date formatting [.NET Framework]
- number formatting [.NET Framework]
- ToString method
- custom cultural settings [.NET Framework]
- numbers [.NET Framework], formatting
- formatting strings [.NET Framework]
- time [.NET Framework], formatting
- currency [.NET Framework], formatting
- types [.NET Framework], formatting
- format specifiers [.NET Framework]
- times [.NET Framework], formatting
- culture [.NET Framework], formatting
- formatting [.NET Framework], types supported
- base types [.NET Framework], formatting
- custom formatting [.NET Framework]
- strings [.NET Framework], formatting
ms.assetid: 0d1364da-5b30-4d42-8e6b-03378343343f
ms.openlocfilehash: a1f4d9107427140bcfa6b49bc8a850432fb204f7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "75348255"
---
# <a name="format-types-in-net"></a>Tipos de formato en .NET

Aplicar formato es el proceso de convertir una instancia de una clase, una estructura o un valor de enumeración en su representación de cadena, a menudo para que la cadena resultante se pueda mostrar a los usuarios o deserializar para restaurar el tipo de datos original. Esta conversión puede plantear varios desafíos:

- La forma en que se almacenan internamente los valores no refleja necesariamente la manera en que los usuarios desean verlos. Por ejemplo, un número de teléfono podría almacenarse con el formato 8009999999, que no es fácil de usar. Se debería mostrar en su lugar como 800-999-9999. Consulte la sección [Cadenas de formato personalizado](#custom-format-strings) para obtener un ejemplo en el que da formato a un número de esta forma.

- A veces, la conversión de un objeto en su representación de cadena no es intuitiva. Por ejemplo, no está claro cómo debe aparecer la representación de cadena de un objeto Temperature o un objeto Person. Para obtener un ejemplo en el que se da formato a un objeto Temperature de varias formas, consulte la sección [Cadenas de formato estándar](#standard-format-strings) .

- A menudo, los valores requieren un formato dependiente de la referencia cultural. Por ejemplo, en una aplicación en la que se usan números para reflejar los valores monetarios, las cadenas numéricas deben incluir el símbolo de divisa, el separador de grupo (que en la mayoría de las referencias culturales es el separador de miles) y el símbolo decimal correspondientes a la referencia cultural actual. Para ver un ejemplo, consulte la sección [Formato según la referencia cultural con proveedores de formato](#culture-sensitive-formatting-with-format-providers).

- Puede que una aplicación muestre el mismo valor de diferentes maneras. Por ejemplo, es posible que una aplicación represente un miembro de enumeración mostrando una representación de cadena de su nombre o mostrando su valor subyacente. Para obtener un ejemplo en el que se da formato a un miembro de la enumeración <xref:System.DayOfWeek> de maneras diferentes, consulte la sección [Cadenas de formato estándar](#standard-format-strings) .

> [!NOTE]
> La aplicación de formato convierte el valor de un tipo en una representación de cadena. El análisis es lo contrario que la aplicación de formato. Una operación de análisis crea una instancia de un tipo de datos a partir de su representación de cadena. Para información sobre cómo convertir cadenas en otros tipos de datos, vea [Analizar cadenas en .NET](../../../docs/standard/base-types/parsing-strings.md).

.NET proporciona compatibilidad de formato enriquecida que permite a los desarrolladores hacer frente a estos requisitos.

## <a name="formatting-in-net"></a>Formato en .NET

El mecanismo básico para aplicar formato es la implementación predeterminada del método <xref:System.Object.ToString%2A?displayProperty=nameWithType>, que se explica en la sección [Formato predeterminado mediante el método ToString](#default-formatting-using-the-tostring-method) más adelante en este tema. Pero .NET proporciona varias formas de modificar y extender su compatibilidad de formato predeterminado. Entre ellas se incluyen las siguientes:

- Invalidar el método <xref:System.Object.ToString%2A?displayProperty=nameWithType> para definir una representación de cadena personalizada del valor de un objeto. Para obtener más información, consulte la sección [Invalidación del método ToString](#override-the-tostring-method) más adelante en este tema.

- Definir especificadores de formato que permitan que la representación de cadena del valor de un objeto adopte varios formatos. Por ejemplo, el especificador de formato "X" en la siguiente instrucción convierte un entero en la representación de cadena de un valor hexadecimal.

     [!code-csharp[Conceptual.Formatting.Overview#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/specifier1.cs#3)]
     [!code-vb[Conceptual.Formatting.Overview#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/specifier1.vb#3)]

     Para obtener más información sobre los especificadores de formato, vea la sección [Método ToString y cadenas de formato](#the-tostring-method-and-format-strings) .

- Usar proveedores de formato para aprovechar las convenciones de formato de una referencia cultural concreta. Por ejemplo, la instrucción siguiente muestra un valor de divisa usando las convenciones de formato de la referencia cultural en-US.

     [!code-csharp[Conceptual.Formatting.Overview#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/specifier1.cs#10)]
     [!code-vb[Conceptual.Formatting.Overview#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/specifier1.vb#10)]

     Para obtener más información sobre cómo aplicar formato con proveedores de formato, consulte la sección [Proveedores de formato](#culture-sensitive-formatting-with-format-providers).

- Implementar la interfaz <xref:System.IFormattable> para admitir tanto la conversión de cadenas con la clase <xref:System.Convert> como formatos compuestos. Para obtener más información, vea la sección [Interfaz IFormattable](#the-iformattable-interface) .

- Usar formatos compuestos para incrustar la representación de cadena de un valor en una cadena más larga. Para obtener más información, vea la sección [Formatos compuestos](#composite-formatting) .

- Implementar <xref:System.ICustomFormatter> y <xref:System.IFormatProvider> para proporcionar una solución de formato personalizado completa. Para obtener más información, vea la sección [Formato personalizado con ICustomFormatter](#custom-formatting-with-icustomformatter) .

En las secciones siguientes se examinan estos métodos para convertir un objeto en su representación de cadena.

## <a name="default-formatting-using-the-tostring-method"></a>Formato predeterminado mediante el método ToString

Cada tipo derivado de <xref:System.Object?displayProperty=nameWithType> hereda automáticamente un método `ToString` sin parámetros, que devuelve el nombre del tipo de forma predeterminada. En el ejemplo siguiente se ilustra el método `ToString` predeterminado. Se define una clase denominada `Automobile` que no tiene ninguna implementación. Cuando se crea una instancia de la clase y se llama a su método `ToString` , se muestra el nombre de su tipo. Observe que en el ejemplo no se llama explícitamente al método `ToString` . El método <xref:System.Console.WriteLine%28System.Object%29?displayProperty=nameWithType> llama implícitamente al método `ToString` del objeto pasado como argumento.

[!code-csharp[Conceptual.Formatting.Overview#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/default1.cs#1)]
[!code-vb[Conceptual.Formatting.Overview#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/default1.vb#1)]

> [!WARNING]
> A partir de Windows 8.1, Windows Runtime incluye una interfaz <xref:Windows.Foundation.IStringable> con un solo método, [IStringable.ToString](xref:Windows.Foundation.IStringable.ToString%2A), que ofrece compatibilidad con el formato predeterminado. Sin embargo, es recomendable que los tipos administrados no implementen la interfaz `IStringable` . Para obtener más información, vea la sección "Windows Runtime y la interfaz `IStringable`" de la página de referencia <xref:System.Object.ToString%2A?displayProperty=nameWithType>.

Puesto que todos los tipos distintos de las interfaces se derivan de <xref:System.Object>, esta funcionalidad se proporciona automáticamente a sus clases o estructuras personalizadas. Si bien, la funcionalidad que ofrece el método `ToString` predeterminado es limitada: Aunque identifica el tipo, no proporciona ninguna información sobre una instancia del tipo. Para proporcionar una representación de cadena de un objeto que proporciona información sobre ese objeto, debe invalidar el método `ToString` .

> [!NOTE]
> Las estructuras heredan de <xref:System.ValueType>, que a su vez se deriva de <xref:System.Object>. Aunque <xref:System.ValueType> invalida <xref:System.Object.ToString%2A?displayProperty=nameWithType>, su implementación es idéntica.

## <a name="override-the-tostring-method"></a>Invalidación del método ToString

La presentación del nombre de un tipo suele tener un uso limitado y no permite a los consumidores de sus tipos diferenciar una instancia de otra. Sin embargo, puede invalidar el método `ToString` para proporcionar una representación más útil del valor de un objeto. En el ejemplo siguiente se define un objeto `Temperature` y se invalida su método `ToString` para mostrar la temperatura en grados centígrados.

[!code-csharp[Conceptual.Formatting.Overview#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/overrides1.cs#2)]
[!code-vb[Conceptual.Formatting.Overview#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/overrides1.vb#2)]

En .NET, el método `ToString` de cada tipo de valor primitivo se ha invalidado para que se muestre el valor del objeto en lugar de su nombre. En la tabla siguiente se muestra la invalidación para cada tipo primitivo. Observe que la mayoría de los métodos invalidados llaman a otra sobrecarga del método `ToString` y le pasan el especificador de formato "G", que define el formato general de su tipo, y un objeto <xref:System.IFormatProvider> que representa la referencia cultural actual.

|Tipo|Invalidación de ToString|
|----------|-----------------------|
|<xref:System.Boolean>|Devuelve <xref:System.Boolean.TrueString?displayProperty=nameWithType> o <xref:System.Boolean.FalseString?displayProperty=nameWithType>.|
|<xref:System.Byte>|Llama a `Byte.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo <xref:System.Byte> correspondiente a la referencia cultural actual.|
|<xref:System.Char>|Devuelve el carácter como una cadena.|
|<xref:System.DateTime>|Llama a `DateTime.ToString("G", DatetimeFormatInfo.CurrentInfo)` para dar formato al valor de fecha y hora correspondiente a la referencia cultural actual.|
|<xref:System.Decimal>|Llama a `Decimal.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo <xref:System.Decimal> correspondiente a la referencia cultural actual.|
|<xref:System.Double>|Llama a `Double.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo <xref:System.Double> correspondiente a la referencia cultural actual.|
|<xref:System.Int16>|Llama a `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo <xref:System.Int16> correspondiente a la referencia cultural actual.|
|<xref:System.Int32>|Llama a `Int32.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo <xref:System.Int32> correspondiente a la referencia cultural actual.|
|<xref:System.Int64>|Llama a `Int64.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo <xref:System.Int64> correspondiente a la referencia cultural actual.|
|<xref:System.SByte>|Llama a `SByte.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo <xref:System.SByte> correspondiente a la referencia cultural actual.|
|<xref:System.Single>|Llama a `Single.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo <xref:System.Single> correspondiente a la referencia cultural actual.|
|<xref:System.UInt16>|Llama a `UInt16.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo <xref:System.UInt16> correspondiente a la referencia cultural actual.|
|<xref:System.UInt32>|Llama a `UInt32.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo <xref:System.UInt32> correspondiente a la referencia cultural actual.|
|<xref:System.UInt64>|Llama a `UInt64.ToString("G", NumberFormatInfo.CurrentInfo)` para dar formato al valor de tipo <xref:System.UInt64> correspondiente a la referencia cultural actual.|

## <a name="the-tostring-method-and-format-strings"></a>Método ToString y cadenas de formato

Recurrir al método `ToString` predeterminado o invalidar `ToString` resulta apropiado cuando un objeto tiene una única representación de cadena. Sin embargo, el valor de un objeto tiene a menudo varias representaciones. Por ejemplo, una temperatura puede expresarse en grados Fahrenheit, grados centígrados o grados Kelvin. De manera similar, el valor entero 10 puede representarse de numerosas maneras; por ejemplo, 10, 10,0, 1,0e01 o $10,00.

Para que un valor pueda tener varias representaciones de cadena, .NET usa cadenas de formato. Una cadena de formato es una cadena que contiene uno o varios especificadores de formato predefinidos, que son caracteres individuales o grupos de caracteres que definen cómo el método `ToString` debe dar formato a su salida. A continuación, se pasa la cadena de formato como un parámetro al método `ToString` del objeto, por lo que determina cómo debe mostrarse la representación de cadena del valor de ese objeto.

Todos los tipos numéricos, de fecha y hora, y de enumeración de .NET admiten un conjunto predefinido de especificadores de formato. Las cadenas de formato también se pueden emplear para definir varias representaciones de cadena de los tipos de datos definidos por una aplicación.

### <a name="standard-format-strings"></a>Cadenas de formato estándar

Una cadena de formato estándar contiene un único especificador de formato, que es un carácter alfabético que define la representación de cadena del objeto al que se aplica, junto con un especificador de precisión opcional que afecta a cuántos dígitos se muestran en la cadena de resultado. Si el especificador de precisión se omite o no se admite, un especificador de formato estándar es equivalente a una cadena de formato estándar.

.NET define un conjunto de especificadores de formato estándar para todos los tipos numéricos, de fecha y hora, y de enumeración. Por ejemplo, cada una de estas categorías admite un especificador de formato estándar "G", que define una representación de cadena general de un valor de ese tipo.

Las cadenas de formato estándar para los tipos de enumeración controlan directamente la representación de cadena de un valor. Las cadenas de formato que se pasan al método `ToString` de un valor de enumeración determinan si el valor se muestra con su nombre de cadena (especificadores de formato "G" y "F"), su valor integral subyacente (especificador de formato "D") o su valor hexadecimal (especificador de formato "X"). En el ejemplo siguiente se muestra el uso de cadenas de formato estándar para dar formato a un valor de enumeración <xref:System.DayOfWeek> .

[!code-csharp[Conceptual.Formatting.Overview#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/standard1.cs#4)]
[!code-vb[Conceptual.Formatting.Overview#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/standard1.vb#4)]

Para información sobre las cadenas de formato de enumeración, vea [Enumeration Format Strings](../../../docs/standard/base-types/enumeration-format-strings.md).

Las cadenas de formato estándar para tipos numéricos normalmente definen una cadena de resultado cuya apariencia exacta está controlada por uno o más valores de propiedad. Por ejemplo, el especificador de formato "C" da formato a un número como un valor de divisa. Al llamar al método `ToString` con el especificador de formato "C" como único parámetro, se usan los siguientes valores de propiedad del objeto <xref:System.Globalization.NumberFormatInfo> de la referencia cultural actual para definir la representación de cadena del valor numérico:

- La propiedad <xref:System.Globalization.NumberFormatInfo.CurrencySymbol%2A> , que especifica el símbolo de divisa de la referencia cultural actual.

- La propiedad <xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern%2A> o <xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern%2A> , que devuelve un entero que determina lo siguiente:

  - La posición del símbolo de divisa.

  - Si los valores negativos se indican mediante un signo negativo inicial, un signo negativo final o paréntesis.

  - Si aparece un espacio entre el valor numérico y el símbolo de divisa.

- La propiedad <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits%2A> , que define el número de dígitos fraccionarios en la cadena de resultado.

- La propiedad <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator%2A> , que define el símbolo del separador decimal en la cadena de resultado.

- La propiedad <xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator%2A> , que define el símbolo del separador de grupo.

- La propiedad <xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes%2A> , que define el número de dígitos de cada grupo que hay a la izquierda del decimal.

- La propiedad <xref:System.Globalization.NumberFormatInfo.NegativeSign%2A> , que determina el signo negativo usado en la cadena de resultado si no se emplean paréntesis para indicar valores negativos.

Además, las cadenas de formato numérico pueden incluir un especificador de precisión. El significado de este especificador depende de la cadena de formato con la que se usa, pero suele indicar el número total de dígitos o el número de dígitos fraccionarios que deben aparecer en la cadena de resultado. Por ejemplo, en el ejemplo siguiente se usa la cadena numérica estándar "X4" y un especificador de precisión para crear un valor de cadena que tiene cuatro dígitos hexadecimales.

[!code-csharp[Conceptual.Formatting.Overview#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/precisionspecifier1.cs#6)]
[!code-vb[Conceptual.Formatting.Overview#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/precisionspecifier1.vb#6)]

Para más información sobre las cadenas de formato numérico estándar, vea [Standard Numeric Format Strings](../../../docs/standard/base-types/standard-numeric-format-strings.md).

Las cadenas de formato estándar para valores de fecha y hora son alias de las cadenas de formato personalizado almacenadas por una propiedad <xref:System.Globalization.DateTimeFormatInfo> determinada. Por ejemplo, al llamar al método `ToString` de un valor de fecha y hora con el especificador de formato "D" se muestran la fecha y la hora usando la cadena de formato personalizado que está almacenada en la propiedad <xref:System.Globalization.DateTimeFormatInfo.LongDatePattern%2A?displayProperty=nameWithType> de la referencia cultural actual. (Para obtener más información sobre las cadenas de formato personalizado, vea la [próxima sección](#custom-format-strings)). En el ejemplo siguiente se ilustra esta relación.

[!code-csharp[Conceptual.Formatting.Overview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/alias1.cs#5)]
[!code-vb[Conceptual.Formatting.Overview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/alias1.vb#5)]

Para más información sobre las cadenas de formato de fecha y hora estándar, vea [Standard Date and Time Format Strings](../../../docs/standard/base-types/standard-date-and-time-format-strings.md).

También se pueden emplear las cadenas de formato estándar para definir la representación de cadena de un objeto definido por la aplicación generado por el método `ToString(String)` del objeto. Puede definir los especificadores de formato estándar concretos que su objeto admite y determinar si distinguen entre mayúsculas y minúsculas o no. Su implementación del método `ToString(String)` debe aceptar lo siguiente:

- Un especificador de formato "G" que representa un formato personalizado o común del objeto. La sobrecarga sin parámetros del método `ToString` del objeto debe llamar a su sobrecarga de `ToString(String)` y pasarle la cadena de formato estándar "G".

- Compatibilidad con un especificador de formato que sea igual a una referencia nula (`Nothing` en Visual Basic). Un especificador de formato que es igual a una referencia nula debe considerarse equivalente al especificador de formato "G".

Por ejemplo, una clase `Temperature` puede almacenar internamente la temperatura en grados centígrados y usar especificadores de formato para representar el valor del objeto `Temperature` en grados centígrados, grados Fahrenheit y grados Kelvin. Esto se muestra en el ejemplo siguiente.

[!code-csharp[Conceptual.Formatting.Overview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/appstandard1.cs#7)]
[!code-vb[Conceptual.Formatting.Overview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/appstandard1.vb#7)]

### <a name="custom-format-strings"></a>Cadenas de formato personalizado

Además de las cadenas de formato estándar, .NET define cadenas de formato personalizado tanto para los valores numéricos como para los valores de fecha y hora. Una cadena de formato personalizado se compone de uno o varios especificadores de formato personalizado que definen la representación de cadena de un valor. Por ejemplo, la cadena de formato personalizado de fecha y hora “yyyy/mm/dd hh:mm:ss.ffff t zzz” convierte una fecha en su representación de cadena con el formato "2008/11/15 07:45:00.0000 P -08:00" para la referencia cultural en-US. Del mismo modo, la cadena de formato personalizado “0000” convierte el valor entero 12 en “0012”. Para una lista completa de las cadenas de formato personalizado, vea [Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md) y [Custom Numeric Format Strings](../../../docs/standard/base-types/custom-numeric-format-strings.md).

Si una cadena de formato consta de un único especificador de formato personalizado, el especificador de formato debe ir precedido del símbolo de porcentaje (%) para evitar la confusión con un especificador de formato estándar. En el ejemplo siguiente, se usa el especificador de formato personalizado "M" para mostrar un número de un dígito o de dos dígitos del mes de una fecha determinada.

[!code-csharp[Conceptual.Formatting.Overview#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/singlecustom1.cs#8)]
[!code-vb[Conceptual.Formatting.Overview#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/singlecustom1.vb#8)]

Muchas cadenas de formato estándar para valores de fecha y hora son alias para cadenas de formato personalizado definidas por propiedades del objeto <xref:System.Globalization.DateTimeFormatInfo> . Las cadenas de formato personalizado también ofrecen una gran flexibilidad a la hora de proporcionar formatos definidos por la aplicación para los valores numéricos o de fecha y hora. Puede definir sus propias cadenas de resultado personalizadas para los valores numéricos y de fecha y hora si combina varios especificadores de formato personalizados en una única cadena de formato personalizado. En el ejemplo siguiente se define una cadena de formato personalizado que muestra el día de la semana entre paréntesis después del nombre de mes, el día y el año.

[!code-csharp[Conceptual.Formatting.Overview#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/custom1.cs#9)]
[!code-vb[Conceptual.Formatting.Overview#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/custom1.vb#9)]

En el ejemplo siguiente se define una cadena de formato personalizado que muestra un valor de <xref:System.Int64> como un número de teléfono de Estados Unidos estándar de siete dígitos con el código de área.

[!code-csharp[Conceptual.Formatting.Overview#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/telnumber1.cs#21)]
[!code-vb[Conceptual.Formatting.Overview#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/telnumber1.vb#21)]

Aunque las cadenas de formato estándar pueden satisfacer generalmente la mayoría de las necesidades de formato para los tipos definidos por la aplicación, también puede definir especificadores de formato personalizados para dar formato a sus tipos.

### <a name="format-strings-and-net-types"></a>Cadenas de formato y tipos de .NET

Todos los tipos numéricos (es decir, los tipos <xref:System.Byte>, <xref:System.Decimal>, <xref:System.Double>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.SByte>, <xref:System.Single>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64> y <xref:System.Numerics.BigInteger>), así como <xref:System.DateTime>, <xref:System.DateTimeOffset>, <xref:System.TimeSpan>, <xref:System.Guid>y todos los tipos de enumeración, son compatibles con el formato con cadenas de formato. Para obtener información sobre las cadenas de formato específicas que admite cada tipo, consulte los temas siguientes:

|Title|Definición|
|-----------|----------------|
|[Standard Numeric Format Strings](../../../docs/standard/base-types/standard-numeric-format-strings.md)|Describe cadenas de formato estándar que crean representaciones de cadena usadas con frecuencia de valores numéricos.|
|[Custom Numeric Format Strings](../../../docs/standard/base-types/custom-numeric-format-strings.md)|Describe cadenas de formato personalizado que crean formatos específicos de la aplicación para valores numéricos.|
|[Cadenas con formato de fecha y hora estándar](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)|Describe cadenas de formato estándar que crean representaciones de cadena usadas con frecuencia de valores <xref:System.DateTime> y <xref:System.DateTimeOffset>.|
|[Cadenas con formato de fecha y hora personalizado](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)|Describe cadenas de formato personalizado que crean formatos específicos de la aplicación para valores <xref:System.DateTime> y <xref:System.DateTimeOffset>.|
|[Cadenas de formato TimeSpan estándar](../../../docs/standard/base-types/standard-timespan-format-strings.md)|Describe cadenas de formato estándar que crean representaciones de cadena usadas con frecuencia de intervalos de tiempo.|
|[Cadenas de formato TimeSpan personalizado](../../../docs/standard/base-types/custom-timespan-format-strings.md)|Describe cadenas de formato personalizado que crean formatos específicos de la aplicación para intervalos de tiempo.|
|[Enumeration Format Strings](../../../docs/standard/base-types/enumeration-format-strings.md)|Describe cadenas de formato estándar que se usan para crear representaciones de cadena de valores de enumeración.|
|<xref:System.Guid.ToString%28System.String%29?displayProperty=nameWithType>|Describe cadenas de formato estándar para los valores de <xref:System.Guid> .|

## <a name="culture-sensitive-formatting-with-format-providers"></a>Formato según la referencia cultural con proveedores de formato

Si bien los especificadores de formato permiten personalizar el formato de los objetos, la generación de una representación de cadena significativa de los objetos requiere a menudo información de formato adicional. Por ejemplo, cuando se da formato a un número como un valor de divisa mediante la cadena de formato estándar "C" o la cadena de formato personalizado “$ #,#.00”, se necesita como mínimo información sobre el símbolo de divisa, el separador de grupos y el separador decimal correctos para incluirla en la cadena con formato. En .NET, esta información de formato adicional está disponible mediante la interfaz <xref:System.IFormatProvider>, que se proporciona como un parámetro a una o más sobrecargas del método `ToString` de los tipos numéricos y de fecha y hora. Las implementaciones de <xref:System.IFormatProvider> se usan en .NET para admitir el formato específico de una referencia cultural. En el siguiente ejemplo se muestra cómo cambia la representación en forma de cadena de un objeto cuando se le da formato con tres objetos <xref:System.IFormatProvider> que representan referencias culturales diferentes.

[!code-csharp[Conceptual.Formatting.Overview#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/iformatprovider1.cs#11)]
[!code-vb[Conceptual.Formatting.Overview#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/iformatprovider1.vb#11)]

La interfaz <xref:System.IFormatProvider> incluye un método, <xref:System.IFormatProvider.GetFormat%28System.Type%29>, que tiene un único parámetro que especifica el tipo de objeto que proporciona información de formato. Si el método puede proporcionar un objeto de ese tipo, lo devuelve. De lo contrario, devuelve una referencia nula (`Nothing` en Visual Basic).

<xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> es un método de devolución de llamada. Al llamar a una sobrecarga del método `ToString` que incluye un parámetro de <xref:System.IFormatProvider> , se llama al método <xref:System.IFormatProvider.GetFormat%2A> de ese objeto <xref:System.IFormatProvider> . El método <xref:System.IFormatProvider.GetFormat%2A> devuelve un objeto que proporciona al método `formatType` la información de formato necesaria especificada por su parámetro `ToString` .

Varios métodos de formato o de conversión de cadenas incluyen un parámetro de tipo <xref:System.IFormatProvider>pero, en muchos casos, se omite el valor del parámetro cuando se llama al método. En la tabla siguiente se muestran algunos métodos de formato que usan el parámetro y el tipo del objeto <xref:System.Type> que pasan al método <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> .

|Método|Tipo de parámetro `formatType`|
|------------|------------------------------------|
|Método`ToString` de tipos numéricos|<xref:System.Globalization.NumberFormatInfo?displayProperty=nameWithType>|
|Método`ToString` de tipos de fecha y hora|<xref:System.Globalization.DateTimeFormatInfo?displayProperty=nameWithType>|
|<xref:System.String.Format%2A?displayProperty=nameWithType>|<xref:System.ICustomFormatter?displayProperty=nameWithType>|
|<xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>|<xref:System.ICustomFormatter?displayProperty=nameWithType>|

> [!NOTE]
> Los métodos `ToString` de los tipos numéricos y los tipos de fecha y hora se sobrecargan y solo algunas de las sobrecargas incluyen un parámetro <xref:System.IFormatProvider> . Si un método no tiene un parámetro de tipo <xref:System.IFormatProvider>, se pasa en su lugar el objeto devuelto por la propiedad <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> . Por ejemplo, una llamada al método <xref:System.Int32.ToString?displayProperty=nameWithType> predeterminado resultará finalmente en una llamada similar a esta: `Int32.ToString("G", System.Globalization.CultureInfo.CurrentCulture)`.

.NET proporciona tres clases que implementan <xref:System.IFormatProvider>:

- <xref:System.Globalization.DateTimeFormatInfo>, una clase que proporciona información de formato para los valores de fecha y hora para una referencia cultural concreta. Su implementación de <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> devuelve una instancia de sí misma.

- <xref:System.Globalization.NumberFormatInfo>, una clase que proporciona información de formato numérico para una referencia cultural concreta. Su implementación de <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> devuelve una instancia de sí misma.

- <xref:System.Globalization.CultureInfo>. Su implementación de <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> puede devolver un objeto <xref:System.Globalization.NumberFormatInfo> para proporcionar información de formato numérico o un objeto <xref:System.Globalization.DateTimeFormatInfo> para proporcionar información de formato para los valores de fecha y hora.

También se puede implementar un proveedor de formato propio para reemplazar cualquiera de estas clases. Sin embargo, el método <xref:System.IFormatProvider.GetFormat%2A> de la implementación debe devolver un objeto del tipo mostrado en la tabla anterior si debe proporcionar información de formato al método `ToString`.

### <a name="culture-sensitive-formatting-of-numeric-values"></a>Formato que tiene en cuenta las referencias culturales de valores numéricos

De forma predeterminada, el formato de los valores numéricos depende de la referencia cultural. Si no especifica una referencia cultural cuando llama a un método de formato, se utilizan las convenciones de formato de la referencia cultural del subproceso actual. Esto se muestra en el ejemplo siguiente, que cambia la referencia cultural del subproceso actual cuatro veces y después llama al método <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType> . En cada caso, la cadena resultante refleja las convenciones de formato de la referencia cultural actual. Esto se debe a que los métodos `ToString` y `ToString(String)` incluyen llamadas a cada tipo numérico del método `ToString(String, IFormatProvider)` .

[!code-csharp[Conceptual.Formatting.Overview#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/culturespecific3.cs#19)]
[!code-vb[Conceptual.Formatting.Overview#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/culturespecific3.vb#19)]

También se puede dar formato a un valor numérico para una referencia cultural concreta llamando a una sobrecarga de `ToString` que tenga un parámetro `provider` y pasándole uno de los elementos siguientes:

- Un objeto <xref:System.Globalization.CultureInfo> que representa la referencia cultural cuyas convenciones de formato se van a usar. El método <xref:System.Globalization.CultureInfo.GetFormat%2A?displayProperty=nameWithType> devuelve el valor de la propiedad <xref:System.Globalization.CultureInfo.NumberFormat%2A?displayProperty=nameWithType> , que es el objeto <xref:System.Globalization.NumberFormatInfo> que proporciona información sobre el formato de la referencia cultural para los valores numéricos.

- Un objeto <xref:System.Globalization.NumberFormatInfo> que define las convenciones de formato de la referencia cultural que se van a usar. Su método <xref:System.Globalization.NumberFormatInfo.GetFormat%2A> devuelve una instancia de sí mismo.

En el siguiente ejemplo se utilizan objetos <xref:System.Globalization.NumberFormatInfo> que representan las referencias culturales de inglés (Estados Unidos) e inglés (Reino Unido), y las referencias culturales neutras de francés y ruso para dar formato a un número de punto flotante.

[!code-csharp[Conceptual.Formatting.Overview#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/culturespecific4.cs#20)]
[!code-vb[Conceptual.Formatting.Overview#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/culturespecific4.vb#20)]

### <a name="culture-sensitive-formatting-of-date-and-time-values"></a>Formato que tiene en cuenta las referencias culturales de valores de fecha y hora

De forma predeterminada, el formato de los valores de fecha y hora tiene en cuenta las referencias culturales. Si no especifica una referencia cultural cuando llama a un método de formato, se utilizan las convenciones de formato de la referencia cultural del subproceso actual. Esto se muestra en el ejemplo siguiente, que cambia la referencia cultural del subproceso actual cuatro veces y después llama al método <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> . En cada caso, la cadena resultante refleja las convenciones de formato de la referencia cultural actual. Esto se debe a que los métodos <xref:System.DateTime.ToString?displayProperty=nameWithType>, <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ToString?displayProperty=nameWithType>y <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> encapsulan llamadas a los métodos <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> y <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> .

[!code-csharp[Conceptual.Formatting.Overview#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/culturespecific1.cs#17)]
[!code-vb[Conceptual.Formatting.Overview#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/culturespecific1.vb#17)]

También se puede dar formato a un valor de fecha y hora para una referencia cultural concreta llamando a una sobrecarga de <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> o <xref:System.DateTimeOffset.ToString%2A?displayProperty=nameWithType> que tenga un parámetro `provider` y pasándole uno de los elementos siguientes:

- Un objeto <xref:System.Globalization.CultureInfo> que representa la referencia cultural cuyas convenciones de formato se van a usar. Su método <xref:System.Globalization.CultureInfo.GetFormat%2A?displayProperty=nameWithType> devuelve el valor de la propiedad <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> , que es el objeto <xref:System.Globalization.DateTimeFormatInfo> que proporciona información sobre el formato de una referencia cultural específica para valores de fecha y hora.

- Un objeto <xref:System.Globalization.DateTimeFormatInfo> que define las convenciones de formato de la referencia cultural que se van a usar. Su método <xref:System.Globalization.DateTimeFormatInfo.GetFormat%2A> devuelve una instancia de sí mismo.

En el siguiente ejemplo se utilizan objetos <xref:System.Globalization.DateTimeFormatInfo> que representan las referencias culturales de inglés (Estados Unidos) e inglés (Reino Unido), y las referencias culturales neutras de francés y ruso para dar formato a una fecha.

[!code-csharp[Conceptual.Formatting.Overview#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/culturespecific2.cs#18)]
[!code-vb[Conceptual.Formatting.Overview#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/culturespecific2.vb#18)]

## <a name="the-iformattable-interface"></a>Interfaz IFormattable

Normalmente, los tipos que sobrecargan el método `ToString` con una cadena de formato y un parámetro <xref:System.IFormatProvider> también implementan la interfaz <xref:System.IFormattable> . Esta interfaz tiene un solo miembro, <xref:System.IFormattable.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, que incluye una cadena de formato y un proveedor de formato como parámetros.

La implementación de la interfaz <xref:System.IFormattable> para su clase definida por la aplicación ofrece dos ventajas:

- Compatibilidad con la conversión de cadenas por la clase <xref:System.Convert> . Las llamadas a los métodos <xref:System.Convert.ToString%28System.Object%29?displayProperty=nameWithType> y <xref:System.Convert.ToString%28System.Object%2CSystem.IFormatProvider%29?displayProperty=nameWithType> llaman automáticamente a su implementación de <xref:System.IFormattable> .

- Compatibilidad con formatos compuestos. Si se usa un elemento de formato que incluye una cadena de formato para dar formato a su tipo personalizado, Common Language Runtime llama automáticamente a su implementación de <xref:System.IFormattable> y le pasa la cadena de formato. Para obtener más información sobre los formatos compuestos con métodos como <xref:System.String.Format%2A?displayProperty=nameWithType> o <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, vea la sección [Formatos compuestos](#composite-formatting) .

En el ejemplo siguiente se define una clase `Temperature` que implementa la interfaz <xref:System.IFormattable> . Admite los especificadores de formato "C" o "G" para mostrar la temperatura en grados centígrados, el especificador de formato "F" para mostrar la temperatura en grados Fahrenheit y el especificador de formato "K" para mostrar la temperatura en grados Kelvin.

[!code-csharp[Conceptual.Formatting.Overview#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/iformattable.cs#12)]
[!code-vb[Conceptual.Formatting.Overview#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/iformattable.vb#12)]

En el ejemplo siguiente se crea una instancia de un objeto `Temperature` . A continuación, llama al método <xref:System.Convert.ToString%2A> y usa varias cadenas de formato compuesto para obtener representaciones de cadena diferentes de un objeto `Temperature` . Cada una de estas llamadas al método, a su vez, llama a la implementación de <xref:System.IFormattable> de la clase `Temperature` .

[!code-csharp[Conceptual.Formatting.Overview#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/iformattable.cs#13)]
[!code-vb[Conceptual.Formatting.Overview#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/iformattable.vb#13)]

## <a name="composite-formatting"></a>Formatos compuestos

Algunos métodos, como <xref:System.String.Format%2A?displayProperty=nameWithType> y <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>, admiten formatos compuestos. Una cadena de formato compuesto es un tipo de plantilla que devuelve una sola cadena que incorpora la representación de cadena de cero, uno o más objetos. Cada objeto se representa en la cadena de formato compuesto mediante un elemento de formato indizado. El índice del elemento de formato corresponde a la posición del objeto que representa en la lista de parámetros del método. Los índices son de base cero. Por ejemplo, en la siguiente llamada al método <xref:System.String.Format%2A?displayProperty=nameWithType> , el primer elemento de formato, `{0:D}`se reemplaza con la representación de cadena de `thatDate`; el segundo elemento de formato, `{1}`, se reemplaza con la representación de cadena de `item1`y el tercer elemento de formato, `{2:C2}`, se reemplaza con la representación de cadena de `item1.Value`.

[!code-csharp[Conceptual.Formatting.Overview#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/composite1.cs#14)]
[!code-vb[Conceptual.Formatting.Overview#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/composite1.vb#14)]

Además de reemplazar un elemento de formato con la representación de cadena de su objeto correspondiente, los elementos de formato también permiten controlar lo siguiente:

- La forma específica en que un objeto se representa como una cadena, si el objeto implementa la interfaz <xref:System.IFormattable> y admite cadenas de formato. Para ello, siga el índice del elemento de formato con un signo `:` (dos puntos) seguido de una cadena de formato válida. En el ejemplo anterior, esto se hacía dando formato a un valor de fecha con la cadena de formato "d" (patrón de fecha corta) (por ejemplo, `{0:d}`) y dando formato a un valor numérico con la cadena de formato "C2" (por ejemplo, `{2:C2}` ) para representar el número como un valor de moneda con dos decimales fraccionarios.

- El ancho del campo que contiene la representación de cadena del objeto y la alineación de la representación de cadena en ese campo. Para ello, escriba una coma ( `,` ) seguida del ancho del campo. La cadena se alinea a la derecha en el campo si el ancho del campo es un valor positivo, y se alinea a la izquierda si el ancho del campo es un valor negativo. En el ejemplo siguiente los valores de fecha se alinean a la izquierda en un campo de 20 caracteres y los valores decimales con un dígito fraccionario se alinean a la derecha en un campo de 11 caracteres.

     [!code-csharp[Conceptual.Formatting.Overview#22](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/composite2.cs#22)]
     [!code-vb[Conceptual.Formatting.Overview#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/composite2.vb#22)]

     Tenga en cuenta que, si están presentes tanto el componente de cadena de alineación como el componente de cadena de formato, el primero precede al último (por ejemplo, `{0,-20:g}`).

Para más información sobre los formatos compuestos, vea [Formatos compuestos](../../../docs/standard/base-types/composite-formatting.md).

## <a name="custom-formatting-with-icustomformatter"></a>Formato personalizado con ICustomFormatter

Dos métodos de formato compuesto, <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> y <xref:System.Text.StringBuilder.AppendFormat%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>, incluyen un parámetro de proveedor de formato que admite formatos personalizados. Cuando se llama a alguno de estos métodos de formato, se pasa un objeto <xref:System.Type> que representa una interfaz <xref:System.ICustomFormatter> al método <xref:System.IFormatProvider.GetFormat%2A> del proveedor de formato. A continuación, el método <xref:System.IFormatProvider.GetFormat%2A> devuelve la implementación de <xref:System.ICustomFormatter> que proporciona el formato personalizado.

La interfaz <xref:System.ICustomFormatter> tiene un único método, <xref:System.ICustomFormatter.Format%28System.String%2CSystem.Object%2CSystem.IFormatProvider%29>, al que un método de formato compuesto llama automáticamente una vez para cada elemento de formato de una cadena de formato compuesto. El método <xref:System.ICustomFormatter.Format%28System.String%2CSystem.Object%2CSystem.IFormatProvider%29> tiene tres parámetros: una cadena de formato, que representa el argumento `formatString` de un elemento de formato, un objeto para dar formato y un objeto <xref:System.IFormatProvider> que proporciona servicios de formato. Normalmente, la clase que implementa <xref:System.ICustomFormatter> también implementa <xref:System.IFormatProvider>, de modo que este último parámetro es una referencia a la propia clase de formato personalizado. El método devuelve una representación de cadena con formato personalizado del objeto al que se va a dar formato. Si el método no puede dar formato al objeto, debe devolver una referencia nula (`Nothing` en Visual Basic).

En el ejemplo siguiente se proporciona una implementación de <xref:System.ICustomFormatter> denominada `ByteByByteFormatter` que muestra los valores enteros como una secuencia de valores hexadecimales de dos dígitos seguidos de un espacio.

[!code-csharp[Conceptual.Formatting.Overview#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/icustomformatter1.cs#15)]
[!code-vb[Conceptual.Formatting.Overview#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/icustomformatter1.vb#15)]

En el ejemplo siguiente se usa la clase `ByteByByteFormatter` para dar formato a valores enteros. Observe que en el ejemplo no se llama explícitamente al método <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> más de una vez en la segunda llamada al método <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> y que el proveedor <xref:System.Globalization.NumberFormatInfo> predeterminado se usa en la tercera llamada al método porque el método`ByteByByteFormatter.Format` no reconoce la cadena de formato "N0" y devuelve una referencia nula (`Nothing` en Visual Basic).

[!code-csharp[Conceptual.Formatting.Overview#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.formatting.overview/cs/icustomformatter1.cs#16)]
[!code-vb[Conceptual.Formatting.Overview#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.formatting.overview/vb/icustomformatter1.vb#16)]

## <a name="related-topics"></a>Temas relacionados

|Title|Definición|
|-----------|----------------|
|[Standard Numeric Format Strings](../../../docs/standard/base-types/standard-numeric-format-strings.md)|Describe cadenas de formato estándar que crean representaciones de cadena usadas con frecuencia de valores numéricos.|
|[Custom Numeric Format Strings](../../../docs/standard/base-types/custom-numeric-format-strings.md)|Describe cadenas de formato personalizado que crean formatos específicos de la aplicación para valores numéricos.|
|[Cadenas con formato de fecha y hora estándar](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)|Describe cadenas de formato estándar que crean representaciones de cadena usadas con frecuencia de valores <xref:System.DateTime> .|
|[Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)|Describe cadenas de formato personalizado que crean formatos específicos de la aplicación para valores <xref:System.DateTime> .|
|[Cadenas de formato TimeSpan estándar](../../../docs/standard/base-types/standard-timespan-format-strings.md)|Describe cadenas de formato estándar que crean representaciones de cadena usadas con frecuencia de intervalos de tiempo.|
|[Cadenas de formato TimeSpan personalizado](../../../docs/standard/base-types/custom-timespan-format-strings.md)|Describe cadenas de formato personalizado que crean formatos específicos de la aplicación para intervalos de tiempo.|
|[Enumeration Format Strings](../../../docs/standard/base-types/enumeration-format-strings.md)|Describe cadenas de formato estándar que se usan para crear representaciones de cadena de valores de enumeración.|
|[Formatos compuestos](../../../docs/standard/base-types/composite-formatting.md)|Describe cómo incrustar uno o más valores con formato en una cadena. Posteriormente se puede mostrar la cadena en la consola o escrita en una secuencia.|
|[Efectuar operaciones de formato](../../../docs/standard/base-types/performing-formatting-operations.md)|Muestra los temas en los que se proporcionan instrucciones paso a paso para realizar operaciones de formato concretas.|
|[Analizar cadenas en .NET](../../../docs/standard/base-types/parsing-strings.md)|Describe cómo inicializar objetos en los valores descritos por representaciones de cadena de dichos objetos. El análisis es la operación inversa de la aplicación de formato.|

## <a name="reference"></a>Referencia

- <xref:System.IFormattable?displayProperty=nameWithType>
- <xref:System.IFormatProvider?displayProperty=nameWithType>
- <xref:System.ICustomFormatter?displayProperty=nameWithType>
