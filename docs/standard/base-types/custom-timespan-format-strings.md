---
title: Cadenas de formato TimeSpan personalizado
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- format specifiers, custom time interval
- format strings
- formatting [.NET Framework], time interval
- custom time interval format strings
- formatting [.NET Framework], time
- custom TimeSpan format strings
ms.assetid: a63ebf55-7269-416b-b4f5-286f6c03bf0e
ms.openlocfilehash: a5963f9afe422206627a1baea47339ecb81becf0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "75348320"
---
# <a name="custom-timespan-format-strings"></a>Cadenas de formato TimeSpan personalizado

Una cadena de formato <xref:System.TimeSpan> define la representación de cadena de un valor <xref:System.TimeSpan> generado por una operación de formato. Una cadena de formato personalizado consta de uno o varios especificadores de formato <xref:System.TimeSpan> personalizado, además de un número de caracteres literales. Cualquier cadena que no sea una [cadena de formato TimeSpan estándar](standard-timespan-format-strings.md) se interpreta como una cadena de formato <xref:System.TimeSpan> personalizado.

> [!IMPORTANT]
> Los especificadores de formato <xref:System.TimeSpan> personalizado no incluyen símbolos de separador de marcadores de posición, como los símbolos que separan los días de las horas, las horas de los minutos o los segundos de las fracciones de segundo. Estos símbolos deben incluirse en la cadena de formato personalizado como literales de cadena. Por ejemplo, `"dd\.hh\:mm"` define un punto (.) como separador entre los días y las horas, y un signo de dos puntos (:) como separador entre las horas y los minutos.
>
> Los especificadores de formato <xref:System.TimeSpan> personalizado tampoco incluyen un símbolo de signo que permita distinguir entre los intervalos de tiempo negativos y positivos. Para incluir un símbolo de signo, es necesario construir una cadena de formato utilizando lógica condicional. En la sección [Otros caracteres](#other-characters) se incluye un ejemplo.

Las representaciones de cadena de los valores <xref:System.TimeSpan> se generan mediante llamadas a las sobrecargas del método <xref:System.TimeSpan.ToString%2A?displayProperty=nameWithType>, y también mediante métodos que admiten formatos compuestos, como <xref:System.String.Format%2A?displayProperty=nameWithType>. Para obtener más información, consulte [Aplicar formato a tipos](formatting-types.md) y [Formatos compuestos](composite-formatting.md). En el siguiente ejemplo, se muestra el uso de cadenas de formato personalizado en operaciones de formato.

[!code-csharp[Conceptual.TimeSpan.Custom#1](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customformatexample1.cs#1)]
[!code-vb[Conceptual.TimeSpan.Custom#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customformatexample1.vb#1)]

Los métodos <xref:System.TimeSpan> y <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> también usan cadenas de formato <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> personalizadas para definir el formato que deben tener las cadenas de entrada de las operaciones de análisis. (Estas operaciones convierten la representación de cadena de un valor en ese valor.) En el siguiente ejemplo, se muestra el uso de cadenas de formato estándar en operaciones de análisis.

[!code-csharp[Conceptual.TimeSpan.Custom#2](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customparseexample1.cs#2)]
[!code-vb[Conceptual.TimeSpan.Custom#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customparseexample1.vb#2)]

<a name="table"></a> En la siguiente tabla se describen los especificadores de formato de fecha y hora personalizado.

| Especificador de formato | Descripción | Ejemplo |
|----------------------|-----------------|-------------|
|"d", "%d"|Número de días completos de un intervalo de tiempo.<br /><br /> Más información: [Especificador de formato personalizado "d"](#dSpecifier).|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `%d` --> "6"<br /><br /> `d\.hh\:mm` --> "6.14:32"|
|"dd"-"dddddddd"|Número de días completos de un intervalo de tiempo, que se completa con tantos ceros iniciales como sean necesarios.<br /><br /> Más información: [Especificadores de formato personalizado "dd"-"dddddddd"](#ddSpecifier).|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `ddd` --> "006"<br /><br /> `dd\.hh\:mm` --> "06.14:32"|
|"h", "%h"|Número de horas completas de un intervalo de tiempo que no se cuentan como parte de los días. Las horas con un solo dígito no se escriben con un cero a la izquierda.<br /><br /> Más información: [Especificador de formato personalizado "h"](#hSpecifier).|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `%h` --> "14"<br /><br /> `hh\:mm` --> "14:32"|
|"hh"|Número de horas completas de un intervalo de tiempo que no se cuentan como parte de los días. Las horas con un solo dígito se escriben con un cero a la izquierda.<br /><br /> Más información: [Especificador de formato personalizado "hh"](#hhSpecifier).|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `hh` --> "14"<br /><br /> `new TimeSpan(6, 8, 32, 17, 685):`<br /><br /> `hh` --> 08|
|"m", "%m"|Número de minutos completos de un intervalo de tiempo que no se incluyen como parte de las horas o los días. Los minutos con un solo dígito no se escriben con un cero a la izquierda.<br /><br /> Más información: [Especificador de formato personalizado "m"](#mSpecifier).|`new TimeSpan(6, 14, 8, 17, 685):`<br /><br /> `%m` --> "8"<br /><br /> `h\:m` --> "14:8"|
|"mm"|Número de minutos completos de un intervalo de tiempo que no se incluyen como parte de las horas o los días. Los minutos con un solo dígito se escriben con un cero a la izquierda.<br /><br /> Más información: [Especificador de formato personalizado "mm"](#mmSpecifier).|`new TimeSpan(6, 14, 8, 17, 685):`<br /><br /> `mm` --> "08"<br /><br /> `new TimeSpan(6, 8, 5, 17, 685):`<br /><br /> `d\.hh\:mm\:ss` --> 6.08:05:17|
|"s", "%s"|Número de segundos completos de un intervalo de tiempo que no se incluyen como parte de las horas, los días o los minutos. Los segundos con un solo dígito no se escriben con un cero a la izquierda.<br /><br /> Más información: [Especificador de formato personalizado "s"](#sSpecifier).|`TimeSpan.FromSeconds(12.965)`:<br /><br /> `%s` --> 12<br /><br /> `s\.fff` --> 12.965|
|"ss"|Número de segundos completos de un intervalo de tiempo que no se incluyen como parte de las horas, los días o los minutos.  Los segundos con un solo dígito se escriben con un cero a la izquierda.<br /><br /> Más información: [Especificador de formato personalizado "ss"](#ssSpecifier).|`TimeSpan.FromSeconds(6.965)`:<br /><br /> `ss` --> 06<br /><br /> `ss\.fff` --> 06.965|
|"f", "%f"|Décimas de segundo de un intervalo de tiempo.<br /><br /> Más información: [Especificador de formato personalizado "f"](#fSpecifier).|`TimeSpan.FromSeconds(6.895)`:<br /><br /> `f` --> 8<br /><br /> `ss\.f` --> 06.8|
|"ff"|Centésimas de segundo de un intervalo de tiempo.<br /><br /> Más información: [Especificador de formato personalizado "ff"](#ffSpecifier).|`TimeSpan.FromSeconds(6.895)`:<br /><br /> `ff` --> 89<br /><br /> `ss\.ff` --> 06.89|
|"fff"|Milisegundos de un intervalo de tiempo.<br /><br /> Más información: [Especificador de formato personalizado "fff"](#f3Specifier).|`TimeSpan.FromSeconds(6.895)`:<br /><br /> `fff` --> 895<br /><br /> `ss\.fff` --> 06.895|
|"ffff"|Diezmilésimas de segundo de un intervalo de tiempo.<br /><br /> Más información: [Especificador de formato personalizado "ffff"](#f4Specifier).|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `ffff` --> 8954<br /><br /> `ss\.ffff` --> 06.8954|
|"fffff"|Cienmilésimas de segundo de un intervalo de tiempo.<br /><br /> Más información: [Especificador de formato personalizado "fffff"](#f5Specifier).|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `fffff` --> 89543<br /><br /> `ss\.fffff` --> 06.89543|
|"ffffff"|Millonésimas de segundo de un intervalo de tiempo.<br /><br /> Más información: [Especificador de formato personalizado "ffffff"](#f6Specifier).|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `ffffff` --> 895432<br /><br /> `ss\.ffffff` --> 06.895432|
|"fffffff"|Diezmillonésimas de segundo (o fracciones de paso) de un intervalo de tiempo.<br /><br /> Más información: [Especificador de formato personalizado "fffffff"](#f7Specifier).|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `fffffff` --> 8954321<br /><br /> `ss\.fffffff` --> 06.8954321|
|"F", "%F"|Décimas de segundo de un intervalo de tiempo. Si el dígito es cero, no se muestra nada.<br /><br /> Más información: [Especificador de formato personalizado "F"](#F_Specifier).|`TimeSpan.Parse("00:00:06.32")`:<br /><br /> `%F`: 3<br /><br /> `TimeSpan.Parse("0:0:3.091")`:<br /><br /> `ss\.F`: 03.|
|"FF"|Centésimas de segundo de un intervalo de tiempo. No se incluyen los ceros finales fraccionarios ni los dígitos de dos ceros.<br /><br /> Más información: [Especificador de formato personalizado "FF"](#FF_Specifier).|`TimeSpan.Parse("00:00:06.329")`:<br /><br /> `FF`: 32<br /><br /> `TimeSpan.Parse("0:0:3.101")`:<br /><br /> `ss\.FF`: 03.1|
|"FFF"|Milisegundos de un intervalo de tiempo. No se incluyen los ceros finales fraccionarios.<br /><br /> Más información:|`TimeSpan.Parse("00:00:06.3291")`:<br /><br /> `FFF`: 329<br /><br /> `TimeSpan.Parse("0:0:3.1009")`:<br /><br /> `ss\.FFF`: 03.1|
|"FFFF"|Diezmilésimas de segundo de un intervalo de tiempo. No se incluyen los ceros finales fraccionarios.<br /><br /> Más información: [Especificador de formato personalizado "FFFF"](#F4_Specifier).|`TimeSpan.Parse("00:00:06.32917")`:<br /><br /> `FFFFF`: 3291<br /><br /> `TimeSpan.Parse("0:0:3.10009")`:<br /><br /> `ss\.FFFF`: 03.1|
|"FFFFF"|Cienmilésimas de segundo de un intervalo de tiempo. No se incluyen los ceros finales fraccionarios.<br /><br /> Más información: [Especificador de formato personalizado "FFFFF"](#F5_Specifier).|`TimeSpan.Parse("00:00:06.329179")`:<br /><br /> `FFFFF`: 32917<br /><br /> `TimeSpan.Parse("0:0:3.100009")`:<br /><br /> `ss\.FFFFF`: 03.1|
|"FFFFFF"|Millonésimas de segundo de un intervalo de tiempo. No se muestran los ceros finales fraccionarios.<br /><br /> Más información: [Especificador de formato personalizado "FFFFFF"](#F6_Specifier).|`TimeSpan.Parse("00:00:06.3291791")`:<br /><br /> `FFFFFF`: 329179<br /><br /> `TimeSpan.Parse("0:0:3.1000009")`:<br /><br /> `ss\.FFFFFF`: 03.1|
|"FFFFFFF"|Diezmillonésimas de segundo de un intervalo de tiempo. No se muestran los ceros finales fraccionarios ni los dígitos de siete ceros.<br /><br /> Más información: [Especificador de formato personalizado "FFFFFFF"](#F7_Specifier).|`TimeSpan.Parse("00:00:06.3291791")`:<br /><br /> `FFFFFF`: 3291791<br /><br /> `TimeSpan.Parse("0:0:3.1900000")`:<br /><br /> `ss\.FFFFFF`: 03.19|
|'*cadena*'|Delimitador de cadena literal.<br /><br /> Más información: [Otros caracteres](#other-characters).|`new TimeSpan(14, 32, 17):`<br /><br /> `hh':'mm':'ss` --> "14:32:17"|
|&#92;|El carácter de escape.<br /><br /> Más información: [Otros caracteres](#other-characters).|`new TimeSpan(14, 32, 17):`<br /><br /> `hh\:mm\:ss` --> "14:32:17"|
|Cualquier otro carácter|Cualquier otro carácter sin escape se interpreta como especificador de formato personalizado.<br /><br /> Más información: [Otros caracteres](#other-characters).|`new TimeSpan(14, 32, 17):`<br /><br /> `hh\:mm\:ss` --> "14:32:17"|

## <a name="dSpecifier"></a> Especificador de formato personalizado "d"

El especificador de formato personalizado "d" presenta el valor de la propiedad <xref:System.TimeSpan.Days%2A?displayProperty=nameWithType>, que representa el número de días completos de un intervalo de tiempo. Presenta el número completo de días de un valor <xref:System.TimeSpan>, incluso si el valor tiene más de un dígito. Si el valor de la propiedad <xref:System.TimeSpan.Days%2A?displayProperty=nameWithType> es cero, el especificador presentará "0".

Si el especificador de formato personalizado "d" se utiliza solo, especifique "%d" de modo que no se interprete por error como una cadena de formato estándar. Esto se muestra en el ejemplo siguiente.

[!code-csharp[Conceptual.TimeSpan.Custom#3](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#3)]
[!code-vb[Conceptual.TimeSpan.Custom#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#3)]

En el siguiente ejemplo, se muestra el uso del especificador de formato personalizado "d".

[!code-csharp[Conceptual.TimeSpan.Custom#4](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#4)]
[!code-vb[Conceptual.TimeSpan.Custom#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#4)]

[Volver a la tabla](#table)

## <a name="ddSpecifier"></a> Especificadores de formato personalizado "dd"-"dddddddd"

Los especificadores de formato personalizado "dd", "ddd", "dddd", "ddddd", "dddddd", "ddddddd" y "dddddddd" presentan el valor de la propiedad <xref:System.TimeSpan.Days%2A?displayProperty=nameWithType>, que representa el número de días completos de un intervalo de tiempo.

La cadena de salida incluye un número mínimo de dígitos que viene determinado por el número de caracteres "d" en el especificador de formato y se completa con tantos ceros iniciales como sean necesarios. Si los dígitos del número de días superan el número de caracteres "d" en el especificador de formato, la cadena de resultado mostrará el número completo de días.

En el siguiente ejemplo, se utilizan estos especificadores de formato para mostrar la representación de cadena de dos valores <xref:System.TimeSpan>. El valor del componente de días en el primer intervalo de tiempo es cero; el valor del componente de días en el segundo es 365.

[!code-csharp[Conceptual.TimeSpan.Custom#5](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#5)]
[!code-vb[Conceptual.TimeSpan.Custom#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#5)]

[Volver a la tabla](#table)

## <a name="hSpecifier"></a> Especificador de formato personalizado "h"

El especificador de formato personalizado "h" presenta el valor de la propiedad <xref:System.TimeSpan.Hours%2A?displayProperty=nameWithType>, que representa el número de horas completas de un intervalo de tiempo que no se cuentan como parte del componente de días. Devuelve un valor de cadena de un dígito si el valor de la propiedad <xref:System.TimeSpan.Hours%2A?displayProperty=nameWithType> es de 0 a 9; devuelve un valor de cadena de dos dígitos si el valor de la propiedad <xref:System.TimeSpan.Hours%2A?displayProperty=nameWithType> es de 10 a 23.

Si el especificador de formato personalizado "h" se utiliza solo, especifique "%h" de modo que no se interprete por error como una cadena de formato estándar. Esto se muestra en el ejemplo siguiente.

[!code-csharp[Conceptual.TimeSpan.Custom#6](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#6)]
[!code-vb[Conceptual.TimeSpan.Custom#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#6)]

Normalmente, en las operaciones de análisis, una cadena de entrada que incluye solamente un número se interpreta como número de días. Se puede utilizar el especificador de formato personalizado "%h"" para que la cadena numérica se interprete como número de horas. Esto se muestra en el ejemplo siguiente.

[!code-csharp[Conceptual.TimeSpan.Custom#8](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#8)]
[!code-vb[Conceptual.TimeSpan.Custom#8](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#8)]

En el siguiente ejemplo, se muestra el uso del especificador de formato personalizado "h".

[!code-csharp[Conceptual.TimeSpan.Custom#7](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#7)]
[!code-vb[Conceptual.TimeSpan.Custom#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#7)]

[Volver a la tabla](#table)

## <a name="hhSpecifier"></a> Especificador de formato personalizado "hh"

El especificador de formato personalizado "hh" presenta el valor de la propiedad <xref:System.TimeSpan.Hours%2A?displayProperty=nameWithType>, que representa el número de horas completas de un intervalo de tiempo que no se cuentan como parte del componente de días. Para los valores de 0 a 9, la cadena de salida incluye un cero inicial.

Normalmente, en las operaciones de análisis, una cadena de entrada que incluye solamente un número se interpreta como número de días. Se puede utilizar el especificador de formato personalizado "hh"" para que la cadena numérica se interprete como número de horas. Esto se muestra en el ejemplo siguiente.

[!code-csharp[Conceptual.TimeSpan.Custom#9](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#9)]
[!code-vb[Conceptual.TimeSpan.Custom#9](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#9)]

En el siguiente ejemplo, se muestra el uso del especificador de formato personalizado "hh".

[!code-csharp[Conceptual.TimeSpan.Custom#10](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#10)]
[!code-vb[Conceptual.TimeSpan.Custom#10](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#10)]

[Volver a la tabla](#table)

## <a name="mSpecifier"></a> Especificador de formato personalizado "m"

El especificador de formato personalizado "m" presenta el valor de la propiedad <xref:System.TimeSpan.Minutes%2A?displayProperty=nameWithType>, que representa el número de minutos completos de un intervalo de tiempo que no se cuentan como parte del componente de días. Devuelve un valor de cadena de un dígito si el valor de la propiedad <xref:System.TimeSpan.Minutes%2A?displayProperty=nameWithType> es de 0 a 9; devuelve un valor de cadena de dos dígitos si el valor de la propiedad <xref:System.TimeSpan.Minutes%2A?displayProperty=nameWithType> es de 10 a 59.

Si el especificador de formato personalizado "m" se utiliza solo, especifique "%m" de modo que no se interprete por error como una cadena de formato estándar. Esto se muestra en el ejemplo siguiente.

[!code-csharp[Conceptual.TimeSpan.Custom#6](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#6)]
[!code-vb[Conceptual.TimeSpan.Custom#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#6)]

Normalmente, en las operaciones de análisis, una cadena de entrada que incluye solamente un número se interpreta como número de días. Se puede utilizar el especificador de formato personalizado "%m"" para que la cadena numérica se interprete como número de minutos. Esto se muestra en el ejemplo siguiente.

[!code-csharp[Conceptual.TimeSpan.Custom#11](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#11)]
[!code-vb[Conceptual.TimeSpan.Custom#11](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#11)]

En el siguiente ejemplo, se muestra el uso del especificador de formato personalizado "m".

[!code-csharp[Conceptual.TimeSpan.Custom#12](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#12)]
[!code-vb[Conceptual.TimeSpan.Custom#12](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#12)]

[Volver a la tabla](#table)

## <a name="mmSpecifier"></a> Especificador de formato personalizado "mm"

El especificador de formato personalizado "mm" presenta el valor de la propiedad <xref:System.TimeSpan.Minutes%2A?displayProperty=nameWithType>, que representa el número de minutos completos de un intervalo de tiempo que no se cuentan como parte del componente de horas o días. Para los valores de 0 a 9, la cadena de salida incluye un cero inicial.

Normalmente, en las operaciones de análisis, una cadena de entrada que incluye solamente un número se interpreta como número de días. Se puede utilizar el especificador de formato personalizado "mm"" para que la cadena numérica se interprete como número de minutos. Esto se muestra en el ejemplo siguiente.

[!code-csharp[Conceptual.TimeSpan.Custom#13](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#13)]
[!code-vb[Conceptual.TimeSpan.Custom#13](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#13)]

En el siguiente ejemplo, se muestra el uso del especificador de formato personalizado "mm".

[!code-csharp[Conceptual.TimeSpan.Custom#14](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#14)]
[!code-vb[Conceptual.TimeSpan.Custom#14](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#14)]

[Volver a la tabla](#table)

## <a name="sSpecifier"></a> Especificador de formato personalizado "s"

El especificador de formato personalizado "s" presenta el valor de la propiedad <xref:System.TimeSpan.Seconds%2A?displayProperty=nameWithType>, que representa el número de segundos completos de un intervalo de tiempo que no se cuentan como parte del componente de horas, días o minutos. Devuelve un valor de cadena de un dígito si el valor de la propiedad <xref:System.TimeSpan.Seconds%2A?displayProperty=nameWithType> es de 0 a 9; devuelve un valor de cadena de dos dígitos si el valor de la propiedad <xref:System.TimeSpan.Seconds%2A?displayProperty=nameWithType> es de 10 a 59.

Si el especificador de formato personalizado "s" se utiliza solo, especifique "%s" de modo que no se interprete por error como una cadena de formato estándar. Esto se muestra en el ejemplo siguiente.

[!code-csharp[Conceptual.TimeSpan.Custom#15](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#15)]
[!code-vb[Conceptual.TimeSpan.Custom#15](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#15)]

Normalmente, en las operaciones de análisis, una cadena de entrada que incluye solamente un número se interpreta como número de días. Se puede utilizar el especificador de formato personalizado "%s"" para que la cadena numérica se interprete como número de segundos. Esto se muestra en el ejemplo siguiente.

[!code-csharp[Conceptual.TimeSpan.Custom#17](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#17)]
[!code-vb[Conceptual.TimeSpan.Custom#17](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#17)]

En el siguiente ejemplo, se muestra el uso del especificador de formato personalizado "s".

[!code-csharp[Conceptual.TimeSpan.Custom#16](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#16)]
[!code-vb[Conceptual.TimeSpan.Custom#16](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#16)]

[Volver a la tabla](#table)

## <a name="ssSpecifier"></a> Especificador de formato personalizado "ss"

El especificador de formato personalizado "ss" presenta el valor de la propiedad <xref:System.TimeSpan.Seconds%2A?displayProperty=nameWithType>, que representa el número de segundos completos de un intervalo de tiempo que no se cuentan como parte del componente de horas, días o minutos. Para los valores de 0 a 9, la cadena de salida incluye un cero inicial.

Normalmente, en las operaciones de análisis, una cadena de entrada que incluye solamente un número se interpreta como número de días. Se puede utilizar el especificador de formato personalizado "ss"" para que la cadena numérica se interprete como número de segundos. Esto se muestra en el ejemplo siguiente.

[!code-csharp[Conceptual.TimeSpan.Custom#18](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#18)]
[!code-vb[Conceptual.TimeSpan.Custom#18](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#18)]

En el siguiente ejemplo, se muestra el uso del especificador de formato personalizado "ss".

[!code-csharp[Conceptual.TimeSpan.Custom#19](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#19)]
[!code-vb[Conceptual.TimeSpan.Custom#19](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#19)]

[Volver a la tabla](#table)

## <a name="fSpecifier"></a> Especificador de formato personalizado "f"

El especificador de formato personalizado "f" presenta las décimas de segundo de un intervalo de tiempo. En una operación de formato, se truncan los dígitos fraccionarios restantes. En una operación de análisis que llama al método <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>, la cadena de entrada debe contener exactamente un dígito fraccionario.

Si el especificador de formato personalizado "f" se utiliza solo, especifique "%f" de modo que no se interprete por error como una cadena de formato estándar.

En el siguiente ejemplo, se utiliza el especificador de formato personalizado "f" para mostrar las décimas de segundo de un valor <xref:System.TimeSpan>. "f" se usa primero solo y luego junto con el especificador "s" en una cadena de formato personalizado.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Volver a la tabla](#table)

## <a name="ffSpecifier"></a> Especificador de formato personalizado "ff"

El especificador de formato personalizado "ff" presenta las centésimas de segundo de un intervalo de tiempo. En una operación de formato, se truncan los dígitos fraccionarios restantes. En una operación de análisis que llama al método <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>, la cadena de entrada debe contener exactamente dos dígitos fraccionarios.

En el siguiente ejemplo, se utiliza el especificador de formato personalizado "ff" para mostrar las centésimas de segundo de un valor <xref:System.TimeSpan>. "ff" se usa primero solo luego junto con el especificador "s" en una cadena de formato personalizado.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Volver a la tabla](#table)

## <a name="f3Specifier"></a> Especificador de formato personalizado "fff"

El especificador de formato personalizado "fff" (tres caracteres "f") presenta las milésimas de segundo de un intervalo de tiempo. En una operación de formato, se truncan los dígitos fraccionarios restantes. En una operación de análisis que llama al método <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>, la cadena de entrada debe contener exactamente tres dígitos fraccionarios.

En el siguiente ejemplo, se utiliza el especificador de formato personalizado "fff" para mostrar los milisegundos de un valor <xref:System.TimeSpan>. "fff" se usa primero solo y luego junto con el especificador "s" en una cadena de formato personalizado.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Volver a la tabla](#table)

## <a name="f4Specifier"></a> Especificador de formato personalizado "ffff"

El especificador de formato personalizado "ffff" (cuatro caracteres "f") presenta las diezmilésimas de segundo de un intervalo de tiempo. En una operación de formato, se truncan los dígitos fraccionarios restantes. En una operación de análisis que llama al método <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>, la cadena de entrada debe contener exactamente cuatro dígitos fraccionarios.

En el siguiente ejemplo, se utiliza el especificador de formato personalizado "ffff" para mostrar las diezmilésimas de segundo de un valor <xref:System.TimeSpan>. "ffff" se usa primero solo y luego junto con el especificador "s" en una cadena de formato personalizado.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Volver a la tabla](#table)

## <a name="f5Specifier"></a> Especificador de formato personalizado "fffff"

El especificador de formato personalizado "fffff" (cinco caracteres "f") presenta las cienmilésimas de segundo de un intervalo de tiempo. En una operación de formato, se truncan los dígitos fraccionarios restantes. En una operación de análisis que llama al método <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>, la cadena de entrada debe contener exactamente cinco dígitos fraccionarios.

En el siguiente ejemplo, se utiliza el especificador de formato personalizado "fffff" para mostrar las cienmilésimas de segundo de un valor <xref:System.TimeSpan>. "fffff" se usa primero solo y luego junto con el especificador "s" en una cadena de formato personalizado.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Volver a la tabla](#table)

## <a name="f6Specifier"></a> Especificador de formato personalizado "ffffff"

El especificador de formato personalizado "ffffff" (seis caracteres "f") presenta las millonésimas de segundo de un intervalo de tiempo. En una operación de formato, se truncan los dígitos fraccionarios restantes. En una operación de análisis que llama al método <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>, la cadena de entrada debe contener exactamente seis dígitos fraccionarios.

En el siguiente ejemplo, se utiliza el especificador de formato personalizado "ffffff" para mostrar las millonésimas de segundo de un valor <xref:System.TimeSpan>. Este especificador de formato se utiliza primero solo y, a continuación, junto con el especificador "s" en una cadena de formato personalizado.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Volver a la tabla](#table)

## <a name="f7Specifier"></a> Especificador de formato personalizado "fffffff"

El especificador de formato personalizado "fffffff" (siete caracteres "f") presenta las diezmillonésimas de segundo (o fracciones de paso) de un intervalo de tiempo. En una operación de análisis que llama al método <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>, la cadena de entrada debe contener exactamente siete dígitos fraccionarios.

En el siguiente ejemplo, se utiliza el especificador de formato personalizado "fffffff" para mostrar las fracciones de paso de un valor <xref:System.TimeSpan>. Este especificador de formato se utiliza primero solo y, a continuación, junto con el especificador "s" en una cadena de formato personalizado.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Volver a la tabla](#table)

## <a name="F_Specifier"></a> Especificador de formato personalizado "F"

El especificador de formato personalizado "F" presenta las décimas de segundo de un intervalo de tiempo. En una operación de formato, se truncan los dígitos fraccionarios restantes. Si el valor de las décimas de segundo de un intervalo de tiempo es cero, no se incluirá en la cadena de resultado. En una operación de análisis que llama al método <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>, la presencia de las décimas de segundo es opcional.

Si el especificador de formato personalizado "F" se utiliza solo, especifique "%F" de modo que no se interprete por error como una cadena de formato estándar.

En el siguiente ejemplo, se utiliza el especificador de formato personalizado "F" para mostrar las décimas de segundo de un valor <xref:System.TimeSpan>. También se utiliza este especificador de formato personalizado en una operación de análisis.

[!code-csharp[Conceptual.TimeSpan.Custom#21](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#21)]
[!code-vb[Conceptual.TimeSpan.Custom#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#21)]

[Volver a la tabla](#table)

## <a name="FF_Specifier"></a> Especificador de formato personalizado "FF"

El especificador de formato personalizado "FF" presenta las centésimas de segundo de un intervalo de tiempo. En una operación de formato, se truncan los dígitos fraccionarios restantes. Si hay ceros fraccionarios finales, estos no se incluyen en la cadena de resultado. En una operación de análisis que llama al método <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>, la presencia de las décimas y centésimas de segundo es opcional.

En el siguiente ejemplo, se utiliza el especificador de formato personalizado "FF" para mostrar las centésimas de segundo de un valor <xref:System.TimeSpan>. También se utiliza este especificador de formato personalizado en una operación de análisis.

[!code-csharp[Conceptual.TimeSpan.Custom#22](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#22)]
[!code-vb[Conceptual.TimeSpan.Custom#22](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#22)]

[Volver a la tabla](#table)

## <a name="F3_Specifier"></a> Especificador de formato personalizado "FFF"

El especificador de formato personalizado "FFF" (tres caracteres "F") presenta las milésimas de segundo de un intervalo de tiempo. En una operación de formato, se truncan los dígitos fraccionarios restantes. Si hay ceros fraccionarios finales, estos no se incluyen en la cadena de resultado. En una operación de análisis que llama al método <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>, la presencia de las décimas, centésimas y milésimas de segundo es opcional.

En el siguiente ejemplo, se utiliza el especificador de formato personalizado "FFF" para mostrar las milésimas de segundo de un valor <xref:System.TimeSpan>. También se utiliza este especificador de formato personalizado en una operación de análisis.

[!code-csharp[Conceptual.TimeSpan.Custom#23](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#23)]
[!code-vb[Conceptual.TimeSpan.Custom#23](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#23)]

[Volver a la tabla](#table)

## <a name="F4_Specifier"></a> Especificador de formato personalizado "FFFF"

El especificador de formato personalizado "FFFF" (cuatro caracteres "F") presenta las diezmilésimas de segundo de un intervalo de tiempo. En una operación de formato, se truncan los dígitos fraccionarios restantes. Si hay ceros fraccionarios finales, estos no se incluyen en la cadena de resultado. En una operación de análisis que llama al método <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>, la presencia de las décimas, centésimas, milésimas y diezmilésimas de segundo es opcional.

En el siguiente ejemplo, se utiliza el especificador de formato personalizado "FFFF" para mostrar las diezmilésimas de segundo de un valor <xref:System.TimeSpan>. También se utiliza este especificador de formato personalizado en una operación de análisis.

[!code-csharp[Conceptual.TimeSpan.Custom#24](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#24)]
[!code-vb[Conceptual.TimeSpan.Custom#24](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#24)]

[Volver a la tabla](#table)

## <a name="F5_Specifier"></a> Especificador de formato personalizado "FFFFF"

El especificador de formato personalizado "FFFFF" (cinco caracteres "F") presenta las cienmilésimas de segundo de un intervalo de tiempo. En una operación de formato, se truncan los dígitos fraccionarios restantes. Si hay ceros fraccionarios finales, estos no se incluyen en la cadena de resultado. En una operación de análisis que llama al método <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>, la presencia de las décimas, centésimas, milésimas, diezmilésimas y cienmilésimas de segundo es opcional.

En el siguiente ejemplo, se utiliza el especificador de formato personalizado "FFFFF" para mostrar las cienmilésimas de segundo de un valor <xref:System.TimeSpan>. También se utiliza este especificador de formato personalizado en una operación de análisis.

[!code-csharp[Conceptual.TimeSpan.Custom#25](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#25)]
[!code-vb[Conceptual.TimeSpan.Custom#25](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#25)]

[Volver a la tabla](#table)

## <a name="F6_Specifier"></a> Especificador de formato personalizado "FFFFFF"

El especificador de formato personalizado "FFFFFF" (seis caracteres "F") presenta las millonésimas de segundo de un intervalo de tiempo. En una operación de formato, se truncan los dígitos fraccionarios restantes. Si hay ceros fraccionarios finales, estos no se incluyen en la cadena de resultado. En una operación de análisis que llama al método <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> o <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>, la presencia de las décimas, centésimas, milésimas, diezmilésimas, cienmilésimas y millonésimas de segundo es opcional.

En el siguiente ejemplo, se utiliza el especificador de formato personalizado "FFFFFF" para mostrar las millonésimas de segundo de un valor <xref:System.TimeSpan>. También se utiliza este especificador de formato personalizado en una operación de análisis.

[!code-csharp[Conceptual.TimeSpan.Custom#26](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#26)]
[!code-vb[Conceptual.TimeSpan.Custom#26](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#26)]

[Volver a la tabla](#table)

## <a name="F7_Specifier"></a> Especificador de formato personalizado "FFFFFFF"

El especificador de formato personalizado "FFFFFFF" (siete caracteres "F") presenta las diezmillonésimas de segundo (o fracciones de paso) de un intervalo de tiempo. Si hay ceros fraccionarios finales, estos no se incluyen en la cadena de resultado. En una operación de análisis que llama al método <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> or <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>, la presencia de los siete dígitos fraccionarios en la cadena de entrada es opcional.

En el siguiente ejemplo, se utiliza el especificador de formato personalizado "FFFFFFF" para mostrar las fracciones de segundo de un valor <xref:System.TimeSpan>. También se utiliza este especificador de formato personalizado en una operación de análisis.

[!code-csharp[Conceptual.TimeSpan.Custom#27](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#27)]
[!code-vb[Conceptual.TimeSpan.Custom#27](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#27)]

[Volver a la tabla](#table)

## <a name="other-characters"></a>Otros caracteres

Cualquier otro carácter sin escape de una cadena de formato, incluido el carácter de espacio en blanco, se interpreta como especificador de formato personalizado. En la mayoría de los casos, la presencia de cualquier otro carácter sin escape da lugar a una excepción <xref:System.FormatException>.

Para incluir un carácter literal en una cadena de formato, se puede proceder de dos formas:

- Se puede escribirlo entre comillas sencillas (delimitador de cadena literal).

- Se puede anteponer una barra diagonal inversa ("\\"), que se interpreta como un carácter de escape. En C#, esto significa que la cadena de formato debe ser @-quoted o que el carácter literal debe ir precedido de una barra diagonal inversa adicional.

  En algunos casos, puede que sea necesario usar lógica condicional para incluir un carácter literal de escape en una cadena de formato. En el ejemplo siguiente se usa lógica condicional para incluir un símbolo de signo para los intervalos de tiempo negativos.

  [!code-csharp[Conceptual.TimeSpan.Custom#29](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/negativevalues1.cs#29)]
  [!code-vb[Conceptual.TimeSpan.Custom#29](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/negativevalues1.vb#29)]

.NET no define ninguna gramática para los separadores en los intervalos de tiempo. Esto significa que los separadores entre los días y las horas, las horas y los minutos, los minutos y los segundos, y los segundos y las fracciones de segundo deben tratarse todos como literales de carácter en una cadena de formato.

En el siguiente ejemplo, se utilizan el carácter de escape y la comilla simple para definir una cadena de formato personalizado que incluye la palabra "minutes" en la cadena de salida.

[!code-csharp[Conceptual.TimeSpan.Custom#28](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/literal1.cs#28)]
[!code-vb[Conceptual.TimeSpan.Custom#28](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/literal1.vb#28)]

[Volver a la tabla](#table)

## <a name="see-also"></a>Vea también

- [Aplicación de formato a tipos](formatting-types.md)
- [Cadenas de formato TimeSpan estándar](standard-timespan-format-strings.md)
