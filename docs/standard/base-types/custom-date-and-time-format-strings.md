---
title: Cadenas con formato de fecha y hora personalizado
description: Aprenda a usar cadenas de formato de fecha y hora personalizado para convertir valores DateTime o DateTimeOffset en representaciones de texto, o bien para analizar cadenas para fechas y horas.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [.NET Framework], dates
- custom DateTime format string
- format specifiers, custom date and time
- format strings
- custom date and time format strings
- formatting [.NET Framework], time
- date and time strings
ms.assetid: 98b374e3-0cc2-4c78-ab44-efb671d71984
ms.openlocfilehash: 89601d0628e4f5f00ec02d5cdd6fb79216b1469d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2020
ms.locfileid: "84447256"
---
# <a name="custom-date-and-time-format-strings"></a>Cadenas con formato de fecha y hora personalizado

Una cadena con formato de fecha y hora define la representación de texto de un valor <xref:System.DateTime> o <xref:System.DateTimeOffset> que es el resultado de una operación de formato. También puede definir la representación de un valor de fecha y hora que se necesite en una operación de análisis para convertir correctamente la cadena en una fecha y hora. Una cadena de formato personalizado consta de uno o varios especificadores de formato de fecha y hora personalizado. Una cadena que no sea una [cadena con formato de fecha y hora estándar](standard-date-and-time-format-strings.md) se interpreta como una cadena con formato de fecha y hora personalizado.

> [!TIP]
> Puede descargar la **Utilidad de formato**, que es una aplicación de .NET Core Windows Forms que permite aplicar cadenas de formato a valores numéricos o de fecha y hora, y que muestra la cadena de resultado. El código fuente está disponible para [C#](https://docs.microsoft.com/samples/dotnet/samples/windowsforms-formatting-utility-cs) y [Visual Basic](https://docs.microsoft.com/samples/dotnet/samples/windowsforms-formatting-utility-vb).

Las cadenas con formato de fecha y hora personalizado se pueden utilizar tanto con valores <xref:System.DateTime> como con valores <xref:System.DateTimeOffset>.

[!INCLUDE[C# interactive-note](~/includes/csharp-interactive-with-utc-partial-note.md)]

<a name="table"></a> En operaciones de formato, las cadenas de formato de fecha y hora personalizado se pueden usar con el método `ToString` de una instancia de fecha y hora o con un método que admita formato compuesto. En el ejemplo siguiente se muestran ambos usos.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#17](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/custandformatting1.cs#17)]
[!code-vb[Formatting.DateAndTime.Custom#17](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/custandformatting1.vb#17)]

En las operaciones de análisis, las cadenas de formato de fecha y hora personalizado se pueden usar con los métodos <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType> y <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType>. Estos métodos necesitan que una cadena de entrada se ajuste exactamente a un modelo determinado para que la operación de análisis se realice correctamente. En el ejemplo siguiente se muestra una llamada al método <xref:System.DateTimeOffset.ParseExact%28System.String%2CSystem.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> para analizar una fecha que debe incluir un día, un mes y un año de dos dígitos.

[!code-csharp[Formatting.DateAndTime.Custom#18](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/custandparsing1.cs#18)]
[!code-vb[Formatting.DateAndTime.Custom#18](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/custandparsing1.vb#18)]

En la tabla siguiente se describen los especificadores de formato de fecha y hora personalizados, y se muestra la cadena de resultado producida por cada especificador de formato. De forma predeterminada, las cadenas de resultado reflejan las convenciones de formato de la referencia cultural en-us. Si un especificador de formato determinado genera una cadena de resultado localizada, el ejemplo también indica la referencia cultural a la que se aplica dicha cadena. Para más información sobre cómo usar cadenas de formato de fecha y hora personalizado, vea la sección [Notas](#notes).

| Especificador de formato | Descripción | Ejemplos |
| ---------------------- | ----------------- | -------------- |
|"d"|El día del mes, de 1 a 31.<br /><br /> Más información: [Especificador de formato personalizado "d"](#dSpecifier).|2009-06-01T13:45:30 -> 1<br /><br /> 2009-06-15T13:45:30 -> 15|
|"dd"|El día del mes, de 01 a 31.<br /><br /> Más información: [Especificador de formato personalizado "dd"](#ddSpecifier).|2009-06-01T13:45:30 -> 01<br /><br /> 2009-06-15T13:45:30 -> 15|
|"ddd"|El nombre abreviado del día de la semana.<br /><br /> Más información: [Especificador de formato personalizado "ddd"](#dddSpecifier).|2009-06-15T13:45:30 -> Mon (en-US)<br /><br /> 2009-06-15T13:45:30 -> Пн (ru-RU)<br /><br /> 2009-06-15T13:45:30 -> lun. (fr-FR)|
|"dddd"|El nombre completo del día de la semana.<br /><br /> Más información: [Especificador de formato personalizado "dddd"](#ddddSpecifier).|2009-06-15T13:45:30 -> Monday (en-US)<br /><br /> 2009-06-15T13:45:30 -> понедельник (ru-RU)<br /><br /> 2009-06-15T13:45:30 -> lundi (fr-FR)|
|"f"|Las décimas de segundo de un valor de fecha y hora.<br /><br /> Más información: [Especificador de formato personalizado "f"](#fSpecifier).|2009-06-15T13:45:30.6170000 -> 6<br /><br /> 2009-06-15T13:45:30.05 -> 0|
|"ff"|Las centésimas de segundo de un valor de fecha y hora.<br /><br /> Más información: [Especificador de formato personalizado "ff"](#ffSpecifier).|2009-06-15T13:45:30.6170000 -> 61<br /><br /> 2009-06-15T13:45:30.0050000 -> 00|
|"fff"|Los milisegundos de un valor de fecha y hora.<br /><br /> Más información: [Especificador de formato personalizado "fff"](#fffSpecifier).|6/15/2009 13:45:30.617 -> 617<br /><br /> 6/15/2009 13:45:30.0005 -> 000|
|"ffff"|Las diezmilésimas de segundo de un valor de fecha y hora.<br /><br /> Más información: [Especificador de formato personalizado "ffff"](#ffffSpecifier).|2009-06-15T13:45:30.6175000 -> 6175<br /><br /> 2009-06-15T13:45:30.0000500  -> 0000|
|"fffff"|Las cienmilésimas de segundo de un valor de fecha y hora.<br /><br /> Más información: [Especificador de formato personalizado "fffff"](#fffffSpecifier).|2009-06-15T13:45:30.6175400 -> 61754<br /><br /> 6/15/2009 13:45:30.000005 -> 00000|
|"ffffff"|Las millonésimas de segundo de un valor de fecha y hora.<br /><br /> Más información: [Especificador de formato personalizado "ffffff"](#ffffffSpecifier).|2009-06-15T13:45:30.6175420 -> 617542<br /><br /> 2009-06-15T13:45:30.0000005 -> 000000|
|"fffffff"|Las diezmillonésimas de segundo de un valor de fecha y hora.<br /><br /> Más información: [Especificador de formato personalizado "fffffff"](#fffffffSpecifier).|2009-06-15T13:45:30.6175425 -> 6175425<br /><br /> 2009-06-15T13:45:30.0001150 -> 0001150|
|"F"|Si es distinto de cero, las décimas de segundo de un valor de fecha y hora.<br /><br /> Más información: [Especificador de formato personalizado "F"](#F_Specifier).|2009-06-15T13:45:30.6170000 -> 6<br /><br /> 2009-06-15T13:45:30.0500000 -> (ninguna salida)|
|"FF"|Si es distinto de cero, las centésimas de segundo de un valor de fecha y hora.<br /><br /> Más información: [Especificador de formato personalizado "FF"](#FF_Specifier).|2009-06-15T13:45:30.6170000 -> 61<br /><br /> 2009-06-15T13:45:30.0050000 -> (ninguna salida)|
|"FFF"|Si es distinto de cero, los milisegundos de un valor de fecha y hora.<br /><br /> Más información: [Especificador de formato personalizado "FFF"](#FFF_Specifier).|2009-06-15T13:45:30.6170000 -> 617<br /><br /> 2009-06-15T13:45:30.0005000 -> (ninguna salida)|
|"FFFF"|Si es distinto de cero, las diezmilésimas de segundo de un valor de fecha y hora.<br /><br /> Más información: [Especificador de formato personalizado "FFFF"](#FFFF_Specifier).|2009-06-15T13:45:30.5275000 -> 5275<br /><br /> 2009-06-15T13:45:30.0000500 -> (ninguna salida)|
|"FFFFF"|Si es distinto de cero, las cienmilésimas de segundo de un valor de fecha y hora.<br /><br /> Más información: [Especificador de formato personalizado "FFFFF"](#FFFFF_Specifier).|2009-06-15T13:45:30.6175400 -> 61754<br /><br /> 2009-06-15T13:45:30.0000050 -> (ninguna salida)|
|"FFFFFF"|Si es distinto de cero, las millonésimas de segundo de un valor de fecha y hora.<br /><br /> Más información: [Especificador de formato personalizado "FFFFFF"](#FFFFFF_Specifier).|2009-06-15T13:45:30.6175420 -> 617542<br /><br /> 2009-06-15T13:45:30.0000050 -> (ninguna salida)|
|"FFFFFFF"|Si es distinto de cero, las diezmillonésimas de segundo de un valor de fecha y hora.<br /><br /> Más información: [Especificador de formato personalizado "FFFFFFF"](#FFFFFFF_Specifier).|2009-06-15T13:45:30.6175425 -> 6175425<br /><br /> 2009-06-15T13:45:30.0001150 -> 000115|
|"g", "gg"|El período o la era.<br /><br /> Más información: [Especificador de formato personalizado "g" o "gg"](#gSpecifier).|2009-06-15T13:45:30.6170000 -> A.D.|
|"h"|La hora, usando un reloj de 12 horas de 1 a 12.<br /><br /> Más información: [Especificador de formato personalizado "h"](#hSpecifier).|2009-06-15T01:45:30 -> 1<br /><br /> 2009-06-15T13:45:30 -> 1|
|"hh"|La hora, usando un reloj de 12 horas de 01 a 12.<br /><br /> Más información: [Especificador de formato personalizado "hh"](#hhSpecifier).|2009-06-15T01:45:30 -> 01<br /><br /> 2009-06-15T13:45:30 -> 01|
|"H"|La hora, usando un reloj de 24 horas de 0 a 23.<br /><br /> Más información: [Especificador de formato personalizado "H"](#H_Specifier).|2009-06-15T01:45:30 -> 1<br /><br /> 2009-06-15T13:45:30 -> 13|
|"HH"|La hora, usando un reloj de 24 horas de 00 a 23.<br /><br /> Más información: [Especificador de formato personalizado "HH"](#HH_Specifier).|2009-06-15T01:45:30 -> 01<br /><br /> 2009-06-15T13:45:30 -> 13|
|"K"|Información de la zona horaria.<br /><br /> Más información: [Especificador de formato personalizado "K"](#KSpecifier).|Con valores <xref:System.DateTime>:<br /><br /> 2009-06-15T13:45:30, Kind Unspecified -><br /><br /> 2009-06-15T13:45:30, Kind Utc -> Z<br /><br /> 2009-06-15T13:45:30, Kind Local -> -07:00 (depende de la configuración del equipo local)<br /><br /> Con valores <xref:System.DateTimeOffset>:<br /><br /> 2009-06-15T01:45:30-07:00 --> -07:00<br /><br /> 2009-06-15T08:45:30+00:00 --> +00:00|
|"m"|Minutos, de 0 a 59.<br /><br /> Más información: [Especificador de formato personalizado "m"](#mSpecifier).|2009-06-15T01:09:30 -> 9<br /><br /> 2009-06-15T13:29:30 -> 29|
|"mm"|El minuto, de 00 a 59.<br /><br /> Más información: [Especificador de formato personalizado "mm"](#mmSpecifier).|2009-06-15T01:09:30 -> 09<br /><br /> 2009-06-15T01:45:30 -> 45|
|"M"|El mes, de 1 a 12.<br /><br /> Más información: [Especificador de formato personalizado "M"](#M_Specifier).|2009-06-15T13:45:30 -> 6|
|"MM"|El mes, de 01 a 12.<br /><br /> Más información: [Especificador de formato personalizado "MM"](#MM_Specifier).|2009-06-15T13:45:30 -> 06|
|"MMM"|El nombre abreviado del mes.<br /><br /> Más información: [Especificador de formato personalizado "MMM"](#MMM_Specifier).|2009-06-15T13:45:30 -> Jun (en-US)<br /><br /> 2009-06-15T13:45:30 -> juin (fr-FR)<br /><br /> 2009-06-15T13:45:30 -> Jun (zu-ZA)|
|"MMMM"|El nombre completo del mes.<br /><br /> Más información: [Especificador de formato personalizado "MMMM"](#MMMM_Specifier).|2009-06-15T13:45:30 -> June (en-US)<br /><br /> 2009-06-15T13:45:30 -> juni (da-DK)<br /><br /> 2009-06-15T13:45:30 -> uJuni (zu-ZA)|
|"s"|El segundo, de 0 a 59.<br /><br /> Más información: [Especificador de formato personalizado "s"](#sSpecifier).|2009-06-15T13:45:09 -> 9|
|"ss"|El segundo, de 00 a 59.<br /><br /> Más información: [Especificador de formato personalizado "ss"](#ssSpecifier).|2009-06-15T13:45:09 -> 09|
|"t"|El primer carácter del designador AM/PM.<br /><br /> Más información: [Especificador de formato personalizado "t"](#tSpecifier).|2009-06-15T13:45:30 -> P (en-US)<br /><br /> 2009-06-15T13:45:30 -> 午 (ja-JP)<br /><br /> 2009-06-15T13:45:30 ->  (fr-FR)|
|"tt"|El designador AM/PM.<br /><br /> Más información: [Especificador de formato personalizado "tt"](#ttSpecifier).|2009-06-15T13:45:30 -> PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> 午後 (ja-JP)<br /><br /> 2009-06-15T13:45:30 ->  (fr-FR)|
|"y"|El año, de 0 a 99.<br /><br /> Más información: [Especificador de formato personalizado "y"](#ySpecifier).|0001-01-01T00:00:00 -> 1<br /><br /> 0900-01-01T00:00:00 -> 0<br /><br /> 1900-01-01T00:00:00 -> 0<br /><br /> 2009-06-15T13:45:30 -> 9<br /><br /> 2019-06-15T13:45:30 -> 19|
|"yy"|El año, de 00 a 99.<br /><br /> Más información: [Especificador de formato personalizado "yy"](#yySpecifier).|0001-01-01T00:00:00 -> 01<br /><br /> 0900-01-01T00:00:00 -> 00<br /><br /> 1900-01-01T00:00:00 -> 00<br /><br /> 2019-06-15T13:45:30 -> 19|
|"yyy"|El año, con un mínimo de tres dígitos.<br /><br /> Más información: [Especificador de formato personalizado "yyy"](#yyySpecifier).|0001-01-01T00:00:00 -> 001<br /><br /> 0900-01-01T00:00:00 -> 900<br /><br /> 1900-01-01T00:00:00 -> 1900<br /><br /> 2009-06-15T13:45:30 -> 2009|
|"yyyy"|El año como un número de cuatro dígitos.<br /><br /> Más información: [Especificador de formato personalizado "yyyy"](#yyyySpecifier).|0001-01-01T00:00:00 -> 0001<br /><br /> 0900-01-01T00:00:00 -> 0900<br /><br /> 1900-01-01T00:00:00 -> 1900<br /><br /> 2009-06-15T13:45:30 -> 2009|
|"yyyyy"|El año como un número de cinco dígitos.<br /><br /> Más información: [Especificador de formato personalizado "yyyyy"](#yyyyySpecifier).|0001-01-01T00:00:00 -> 00001<br /><br /> 2009-06-15T13:45:30 -> 02009|
|"z"|Desfase de horas con respecto a la hora UTC, sin ceros iniciales.<br /><br /> Más información: [Especificador de formato personalizado "z"](#zSpecifier).|2009-06-15T13:45:30-07:00 -> -7|
|"zz"|Desfase de horas con respecto a la hora UTC, con un cero inicial para un valor de un solo dígito.<br /><br /> Más información: [Especificador de formato personalizado "zz"](#zzSpecifier).|2009-06-15T13:45:30-07:00 -> -07|
|"zzz"|Desfase de horas y minutos con respecto a la hora UTC.<br /><br /> Más información: [Especificador de formato personalizado "zzz"](#zzzSpecifier).|2009-06-15T13:45:30-07:00 -> -07:00|
|":"|El separador de hora.<br /><br /> Más información: [Especificador de formato personalizado ":"](#timeSeparator).|2009-06-15T13:45:30 -> : (en-US)<br /><br /> 2009-06-15T13:45:30 -> . (it-IT)<br /><br /> 2009-06-15T13:45:30 -> : (ja-JP)|
|"/"|El separador de fecha.<br /><br /> Más información: [Especificador de formato personalizado "/"](#dateSeparator).|2009-06-15T13:45:30 -> / (en-US)<br /><br /> 2009-06-15T13:45:30 -> - (ar-DZ)<br /><br /> 2009-06-15T13:45:30 -> . (tr-TR)|
|"*cadena*"<br /><br /> '*cadena*'|Delimitador de cadena literal.<br /><br /> Más información: [Literales de carácter](#Literals).|2009-06-15T13:45:30 ("arr:" h:m t) -> arr: 1:45 P<br /><br /> 2009-06-15T13:45:30 ('arr:' h:m t) -> arr: 1:45 P|
|%|Define el siguiente carácter como un especificador de formato personalizado.<br /><br /> Más información:[Usar especificadores de formato personalizado únicos](#UsingSingleSpecifiers).|2009-06-15T13:45:30 (%h) -> 1|
|&#92;|El carácter de escape.<br /><br /> Más información: [Literales de caracteres](#Literals) y [Usar el carácter de escape](#escape).|2009-06-15T13:45:30 (h \h) -> 1 h|
|Cualquier otro carácter|El carácter se copia en la cadena de resultado sin modificar.<br /><br /> Más información: [Literales de carácter](#Literals).|2009-06-15T01:45:30 (arr hh:mm t) -> arr 01:45 A|

En las secciones siguientes se proporciona información adicional sobre cada especificador de formato de fecha y hora personalizado. A menos que se indique lo contrario, cada especificador genera una representación de cadena idéntica independientemente de que se use con un valor <xref:System.DateTime> o <xref:System.DateTimeOffset>.

## <a name="the-d-custom-format-specifier"></a><a name="dSpecifier"></a> Especificador de formato personalizado "d"

El especificador de formato personalizado "d" representa el día del mes como un número de 1 a 31. Un día con un solo dígito tiene un formato sin un cero inicial.

Si el especificador de formato "d" se usa sin otros especificadores de formato personalizado, se interpretará como el especificador de formato de fecha y hora estándar "d". Para más información sobre cómo usar un especificador de formato único, vea [Usar especificadores de formato personalizado únicos](#UsingSingleSpecifiers) más adelante en este artículo.

En el ejemplo siguiente se incluye el especificador de formato personalizado "d" en varias cadenas de formato.

[!code-csharp[Formatting.DateAndTime.Custom#1](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#1)]
[!code-vb[Formatting.DateAndTime.Custom#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#1)]

[Volver a la tabla](#table)

## <a name="the-dd-custom-format-specifier"></a><a name="ddSpecifier"></a> Especificador de formato personalizado "dd"

La cadena de formato personalizado "dd" representa el día del mes como un número de 01 a 31. Un día con un solo dígito tiene un formato con un cero inicial.

En el ejemplo siguiente se incluye el especificador de formato personalizado "dd" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#2](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#2)]
[!code-vb[Formatting.DateAndTime.Custom#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#2)]

[Volver a la tabla](#table)

## <a name="the-ddd-custom-format-specifier"></a><a name="dddSpecifier"></a> Especificador de formato personalizado "ddd"

El especificador de formato personalizado "ddd" representa el nombre abreviado del día de la semana. El nombre abreviado adaptado del día de la semana se recupera de la propiedad <xref:System.Globalization.DateTimeFormatInfo.AbbreviatedDayNames%2A?displayProperty=nameWithType> de la referencia cultural actual o especificada.

En el ejemplo siguiente se incluye el especificador de formato personalizado "ddd" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#3](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#3)]
[!code-vb[Formatting.DateAndTime.Custom#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#3)]

[Volver a la tabla](#table)

## <a name="the-dddd-custom-format-specifier"></a><a name="ddddSpecifier"></a> Especificador de formato personalizado "dddd"

El especificador de formato personalizado "dddd" (más cualquier número de especificadores "d" adicionales) representa el nombre completo del día de la semana. El nombre adaptado del día de la semana se recupera de la propiedad <xref:System.Globalization.DateTimeFormatInfo.DayNames%2A?displayProperty=nameWithType> de la referencia cultural actual o especificada.

En el ejemplo siguiente se incluye el especificador de formato personalizado "dddd" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#4](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#4)]
[!code-vb[Formatting.DateAndTime.Custom#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#4)]

[Volver a la tabla](#table)

## <a name="the-f-custom-format-specifier"></a><a name="fSpecifier"></a> Especificador de formato personalizado "f"

El especificador de formato personalizado "f" representa el dígito más significativo de la fracción de segundos; es decir, representa las décimas de segundo de un valor de fecha y hora.

Si el especificador de formato "f" se usa sin otros especificadores de formato, se interpreta como el especificador de formato de fecha y hora estándar "f". Para más información sobre cómo usar un especificador de formato único, vea [Usar especificadores de formato personalizado únicos](#UsingSingleSpecifiers) más adelante en este artículo.

Cuando se usan especificadores de formato "f" como parte de una cadena de formato que se proporciona a los métodos <xref:System.DateTime.ParseExact%2A>, <xref:System.DateTime.TryParseExact%2A>, <xref:System.DateTimeOffset.ParseExact%2A> u <xref:System.DateTimeOffset.TryParseExact%2A>, el número de especificadores de formato "f" indica el número de dígitos más significativos de la fracción de segundos que debe haber presentes para analizar la cadena correctamente.

En el ejemplo siguiente se incluye el especificador de formato personalizado "f" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#5)]
[!code-vb[Formatting.DateAndTime.Custom#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#5)]

[Volver a la tabla](#table)

## <a name="the-ff-custom-format-specifier"></a><a name="ffSpecifier"></a> Especificador de formato personalizado "ff"

El especificador de formato personalizado "ff" representa los dos dígitos más significativos de la fracción de segundos; es decir, representa las centésimas de segundo de un valor de fecha y hora.

En el ejemplo siguiente se incluye el especificador de formato personalizado "ff" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#5)]
[!code-vb[Formatting.DateAndTime.Custom#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#5)]

[Volver a la tabla](#table)

## <a name="the-fff-custom-format-specifier"></a><a name="fffSpecifier"></a> Especificador de formato personalizado "fff"

El especificador de formato personalizado "fff" representa los tres dígitos más significativos de la fracción de segundos; es decir, representa los milisegundos de un valor de fecha y hora.

En el ejemplo siguiente se incluye el especificador de formato personalizado "fff" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#5)]
[!code-vb[Formatting.DateAndTime.Custom#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#5)]

[Volver a la tabla](#table)

## <a name="the-ffff-custom-format-specifier"></a><a name="ffffSpecifier"></a> Especificador de formato personalizado "ffff"

El especificador de formato personalizado "ffff" representa los cuatro dígitos más significativos de la fracción de segundos; es decir, representa las diezmilésimas de segundo de un valor de fecha y hora.

Si bien se puede mostrar el componente correspondiente a las diezmilésimas de segundo de un valor de hora, es muy posible que ese valor no sea significativo. La precisión de los valores de fecha y hora depende de la resolución del reloj del sistema. En los sistemas operativos Windows NT 3.5 (y versiones posteriores) y Windows Vista, la resolución del reloj es aproximadamente de 10 a 15 milisegundos.

[Volver a la tabla](#table)

## <a name="the-fffff-custom-format-specifier"></a><a name="fffffSpecifier"></a> Especificador de formato personalizado "fffff"

El especificador de formato personalizado "fffff" representa los cinco dígitos más significativos de la fracción de segundo; es decir, representa las cienmilésimas de segundo de un valor de fecha y hora.

Si bien se puede mostrar el componente correspondiente a las cienmilésimas de segundo de un valor de hora, es muy posible que ese valor no sea significativo. La precisión de los valores de fecha y hora depende de la resolución del reloj del sistema. En los sistemas operativos Windows NT 3.5 (y versiones posteriores) y Windows Vista, la resolución del reloj es aproximadamente de 10 a 15 milisegundos.

[Volver a la tabla](#table)

## <a name="the-ffffff-custom-format-specifier"></a><a name="ffffffSpecifier"></a> Especificador de formato personalizado "ffffff"

El especificador de formato personalizado "ffffff" representa los seis dígitos más significativos de la fracción de segundos; es decir, representa las millonésimas de segundo de un valor de fecha y hora.

Si bien se puede mostrar el componente correspondiente a las millonésimas de segundo de un valor de hora, es muy posible que ese valor no sea significativo. La precisión de los valores de fecha y hora depende de la resolución del reloj del sistema. En los sistemas operativos Windows NT 3.5 (y versiones posteriores) y Windows Vista, la resolución del reloj es aproximadamente de 10 a 15 milisegundos.

[Volver a la tabla](#table)

## <a name="the-fffffff-custom-format-specifier"></a><a name="fffffffSpecifier"></a> Especificador de formato personalizado "fffffff"

El especificador de formato personalizado "fffffff" representa los siete dígitos más significativos de la fracción de segundos; es decir, representa las diezmillonésimas de segundo de un valor de fecha y hora.

Si bien se puede mostrar el componente correspondiente a las diezmillonésimas de segundo de un valor de hora, es muy posible que ese valor no sea significativo. La precisión de los valores de fecha y hora depende de la resolución del reloj del sistema. En los sistemas operativos Windows NT 3.5 (y versiones posteriores) y Windows Vista, la resolución del reloj es aproximadamente de 10 a 15 milisegundos.

[Volver a la tabla](#table)

## <a name="the-f-custom-format-specifier"></a><a name="F_Specifier"></a> Especificador de formato personalizado "F"

El especificador de formato personalizado "F" representa el dígito más significativo de la fracción de segundos; es decir, representa las décimas de segundo de un valor de fecha y hora. Si el dígito es cero, no se muestra nada.

Si el especificador de formato "F" se usa sin otros especificadores de formato, se interpreta como el especificador de formato de fecha y hora estándar "F". Para más información sobre cómo usar un especificador de formato único, vea [Usar especificadores de formato personalizado únicos](#UsingSingleSpecifiers) más adelante en este artículo.

El número de especificadores de formato "F" que se usan con los métodos <xref:System.DateTime.ParseExact%2A>, <xref:System.DateTime.TryParseExact%2A>, <xref:System.DateTimeOffset.ParseExact%2A> u <xref:System.DateTimeOffset.TryParseExact%2A> indica el número máximo de dígitos más significativos de la fracción de segundos que pueden estar presentes para analizar correctamente la cadena.

En el ejemplo siguiente se incluye el especificador de formato personalizado "F" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#5)]
[!code-vb[Formatting.DateAndTime.Custom#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#5)]

[Volver a la tabla](#table)

## <a name="the-ff-custom-format-specifier"></a><a name="FF_Specifier"></a> Especificador de formato personalizado "FF"

El especificador de formato personalizado "FF" representa los dos dígitos más significativos de la fracción de segundos; es decir, representa las centésimas de segundo de un valor de fecha y hora. Sin embargo, no se muestran los ceros finales ni los dígitos de dos ceros.

En el ejemplo siguiente se incluye el especificador de formato personalizado "FF" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#5)]
[!code-vb[Formatting.DateAndTime.Custom#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#5)]

[Volver a la tabla](#table)

## <a name="the-fff-custom-format-specifier"></a><a name="FFF_Specifier"></a> Especificador de formato personalizado "FFF"

El especificador de formato personalizado "FFF" representa los tres dígitos más significativos de la fracción de segundos; es decir, representa los milisegundos de un valor de fecha y hora. Sin embargo, no se muestran los ceros finales ni los dígitos de tres ceros.

En el ejemplo siguiente se incluye el especificador de formato personalizado "FFF" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#5](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#5)]
[!code-vb[Formatting.DateAndTime.Custom#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#5)]

[Volver a la tabla](#table)

## <a name="the-ffff-custom-format-specifier"></a><a name="FFFF_Specifier"></a> Especificador de formato personalizado "FFFF"

El especificador de formato personalizado "FFFF" representa los cuatro dígitos más significativos de la fracción de segundos; es decir, representa las diezmilésimas de segundo de un valor de fecha y hora. Sin embargo, no se muestran los ceros finales ni los dígitos de cuatro ceros.

Si bien se puede mostrar el componente correspondiente a las diezmilésimas de segundo de un valor de hora, es muy posible que ese valor no sea significativo. La precisión de los valores de fecha y hora depende de la resolución del reloj del sistema. En los sistemas operativos Windows NT 3.5 (y versiones posteriores) y Windows Vista, la resolución del reloj es aproximadamente de 10 a 15 milisegundos.

[Volver a la tabla](#table)

## <a name="the-fffff-custom-format-specifier"></a><a name="FFFFF_Specifier"></a> Especificador de formato personalizado "FFFFF"

El especificador de formato personalizado "FFFFF" representa los cinco dígitos más significativos de la fracción de segundos; es decir, representa las cienmilésimas de segundo de un valor de fecha y hora. Sin embargo, no se muestran los ceros finales ni los dígitos de cinco ceros.

Si bien se puede mostrar el componente correspondiente a las cienmilésimas de segundo de un valor de hora, es muy posible que ese valor no sea significativo. La precisión de los valores de fecha y hora depende de la resolución del reloj del sistema. En los sistemas operativos Windows NT 3.5 (y versiones posteriores) y Windows Vista, la resolución del reloj es aproximadamente de 10 a 15 milisegundos.

[Volver a la tabla](#table)

## <a name="the-ffffff-custom-format-specifier"></a><a name="FFFFFF_Specifier"></a> Especificador de formato personalizado "FFFFFF"

El especificador de formato personalizado "FFFFFF" representa los seis dígitos más significativos de la fracción de segundos; es decir, representa las millonésimas de segundo de un valor de fecha y hora. Sin embargo, no se muestran los ceros finales ni los dígitos de seis ceros.

Si bien se puede mostrar el componente correspondiente a las millonésimas de segundo de un valor de hora, es muy posible que ese valor no sea significativo. La precisión de los valores de fecha y hora depende de la resolución del reloj del sistema. En los sistemas operativos Windows NT 3.5 (y versiones posteriores) y Windows Vista, la resolución del reloj es aproximadamente de 10 a 15 milisegundos.

[Volver a la tabla](#table)

## <a name="the-fffffff-custom-format-specifier"></a><a name="FFFFFFF_Specifier"></a> Especificador de formato personalizado "FFFFFFF"

El especificador de formato personalizado "FFFFFFF" representa los siete dígitos más significativos de la fracción de segundos; es decir, representa las diezmillonésimas de segundo de un valor de fecha y hora. Sin embargo, no se muestran los ceros finales ni los dígitos de siete ceros.

Si bien se puede mostrar el componente correspondiente a las diezmillonésimas de segundo de un valor de hora, es muy posible que ese valor no sea significativo. La precisión de los valores de fecha y hora depende de la resolución del reloj del sistema. En los sistemas operativos Windows NT 3.5 (y versiones posteriores) y Windows Vista, la resolución del reloj es aproximadamente de 10 a 15 milisegundos.

[Volver a la tabla](#table)

## <a name="the-g-or-gg-custom-format-specifier"></a><a name="gSpecifier"></a> Especificador de formato personalizado "g" o "gg"

Los especificadores de formato personalizado "g" o "gg" (más cualquier número de especificadores "g" adicionales) representan el período o la era, como d.C. La operación de formato hace caso omiso de este especificador si la fecha a la que se va a dar formato no tiene una cadena de período o de era asociada.

Si el especificador de formato "g" se usa sin otros especificadores de formato personalizado, se interpretará como el especificador de formato de fecha y hora estándar "g". Para más información sobre cómo usar un especificador de formato único, vea [Usar especificadores de formato personalizado únicos](#UsingSingleSpecifiers) más adelante en este artículo.

En el ejemplo siguiente se incluye el especificador de formato personalizado "g" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#6](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#6)]
[!code-vb[Formatting.DateAndTime.Custom#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#6)]

[Volver a la tabla](#table)

## <a name="the-h-custom-format-specifier"></a><a name="hSpecifier"></a> Especificador de formato personalizado "h"

El especificador de formato personalizado "h" representa la hora como un número del 1 al 12; es decir, la hora se representa como en un reloj de 12 horas que cuenta las horas enteras desde medianoche o mediodía. Una hora determinada después de la medianoche no se distingue de la misma hora después del mediodía. No se redondea la hora y las horas con un solo dígito no tienen un cero inicial. Por ejemplo, dada una hora de 5:43 de la mañana o de la tarde, este especificador de formato personalizado muestra "5".

Si el especificador de formato "h" se usa sin otros especificadores de formato personalizado, se interpretará como un especificador de formato de fecha y hora estándar y producirá una excepción <xref:System.FormatException>. Para más información sobre cómo usar un especificador de formato único, vea [Usar especificadores de formato personalizado únicos](#UsingSingleSpecifiers) más adelante en este artículo.

En el ejemplo siguiente se incluye el especificador de formato personalizado "h" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#7](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#7)]
[!code-vb[Formatting.DateAndTime.Custom#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#7)]

[Volver a la tabla](#table)

## <a name="the-hh-custom-format-specifier"></a><a name="hhSpecifier"></a> Especificador de formato personalizado "hh"

El especificador de formato personalizado "hh" (más cualquier número de especificadores "h" adicionales) representa la hora como un número del 01 al 12; es decir, la hora se representa como en un reloj de 12 horas que cuenta las horas enteras desde medianoche o mediodía. Una hora determinada después de la medianoche no se distingue de la misma hora después del mediodía. No se redondea la hora y las horas con un solo dígito tienen un cero inicial. Por ejemplo, dada una hora de 5:43 de la mañana o de la tarde, este especificador de formato muestra "05".

En el ejemplo siguiente se incluye el especificador de formato personalizado "hh" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#8](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#8)]
[!code-vb[Formatting.DateAndTime.Custom#8](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#8)]

[Volver a la tabla](#table)

## <a name="the-h-custom-format-specifier"></a><a name="H_Specifier"></a> Especificador de formato personalizado "H"

El especificador de formato personalizado "H" representa la hora como un número del 0 al 23; es decir, la hora se representa como en un reloj de 24 horas de base cero que cuenta las horas desde medianoche. Una hora con un solo dígito tiene un formato sin un cero inicial.

Si el especificador de formato "H" se usa sin otros especificadores de formato personalizado, se interpretará como un especificador de formato de fecha y hora estándar y producirá una excepción <xref:System.FormatException>. Para más información sobre cómo usar un especificador de formato único, vea [Usar especificadores de formato personalizado únicos](#UsingSingleSpecifiers) más adelante en este artículo.

En el ejemplo siguiente se incluye el especificador de formato personalizado "H" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#9](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#9)]
[!code-vb[Formatting.DateAndTime.Custom#9](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#9)]

[Volver a la tabla](#table)

## <a name="the-hh-custom-format-specifier"></a><a name="HH_Specifier"></a> Especificador de formato personalizado "HH"

El especificador de formato personalizado "HH" (más cualquier número de especificadores "H" adicionales) representa la hora como un número del 00 al 23; es decir, la hora se representa como en un reloj de 24 horas de base cero que cuenta las horas desde medianoche. Una hora con un solo dígito tiene un formato con un cero inicial.

En el ejemplo siguiente se incluye el especificador de formato personalizado "HH" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#10](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#10)]
[!code-vb[Formatting.DateAndTime.Custom#10](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#10)]

[Volver a la tabla](#table)

## <a name="the-k-custom-format-specifier"></a><a name="KSpecifier"></a> Especificador de formato personalizado "K"

El especificador de formato personalizado "K" representa la información de zona horaria de un valor de fecha y hora. Cuando este formato se usa con valores <xref:System.DateTime>, el valor de la propiedad <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> define la cadena de resultado.

- En la zona horaria local (un valor de propiedad <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> de <xref:System.DateTimeKind.Local?displayProperty=nameWithType>), este especificador es equivalente al especificador "zzz" y genera una cadena de resultado que contiene el desfase local con respecto a la hora universal coordinada (UTC); por ejemplo, "-07: 00".

- En una hora UTC (un valor de propiedad <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> de <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>), la cadena de resultado incluye un carácter "Z" para representar una fecha UTC.

- En una hora de una zona horaria no especificada (una hora cuya propiedad <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> es igual a <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>), el resultado es equivalente a <xref:System.String.Empty?displayProperty=nameWithType>.

En los valores <xref:System.DateTimeOffset>, el especificador de formato "K" es equivalente al especificador de formato "zzz" y genera una cadena de resultado que contiene el desfase del valor <xref:System.DateTimeOffset> con respecto a la hora UTC.

Si el especificador de formato "K" se usa sin otros especificadores de formato personalizado, se interpretará como un especificador de formato de fecha y hora estándar y producirá una excepción <xref:System.FormatException>. Para más información sobre cómo usar un especificador de formato único, vea [Usar especificadores de formato personalizado únicos](#UsingSingleSpecifiers) más adelante en este artículo.

En el ejemplo siguiente se muestra la cadena que se obtiene al utilizar el especificador de formato personalizado "K" con varios valores <xref:System.DateTime> y <xref:System.DateTimeOffset> en un sistema de la zona horaria del Pacífico de EE. UU.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#12](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#12)]
[!code-vb[Formatting.DateAndTime.Custom#12](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#12)]

[Volver a la tabla](#table)

## <a name="the-m-custom-format-specifier"></a><a name="mSpecifier"></a> Especificador de formato personalizado "m"

El especificador de formato personalizado "m" representa el minuto como un número de 0 a 59. El minuto representa los minutos enteros que han transcurrido desde la última hora. Un minuto con un solo dígito tiene un formato sin un cero inicial.

Si el especificador de formato "m" se usa sin otros especificadores de formato personalizado, se interpretará como el especificador de formato de fecha y hora estándar "m". Para más información sobre cómo usar un especificador de formato único, vea [Usar especificadores de formato personalizado únicos](#UsingSingleSpecifiers) más adelante en este artículo.

En el ejemplo siguiente se incluye el especificador de formato personalizado "m" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#7](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#7)]
[!code-vb[Formatting.DateAndTime.Custom#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#7)]

[Volver a la tabla](#table)

## <a name="the-mm-custom-format-specifier"></a><a name="mmSpecifier"></a> Especificador de formato personalizado "mm"

El especificador de formato personalizado "mm" (más cualquier número de especificadores "m" adicionales) representa el minuto como un número de 00 a 59. El minuto representa los minutos enteros que han transcurrido desde la última hora. Un minuto con un solo dígito tiene un formato con un cero inicial.

En el ejemplo siguiente se incluye el especificador de formato personalizado "mm" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#8](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#8)]
[!code-vb[Formatting.DateAndTime.Custom#8](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#8)]

[Volver a la tabla](#table)

## <a name="the-m-custom-format-specifier"></a><a name="M_Specifier"></a> Especificador de formato personalizado "M"

El especificador de formato personalizado "M" representa el mes como un número del 1 al 12 (o del 1 al 13 para los calendarios con 13 meses). Un mes con un solo dígito tiene un formato sin un cero inicial.

Si el especificador de formato "M" se usa sin otros especificadores de formato personalizado, se interpretará como el especificador de formato de fecha y hora estándar "M". Para más información sobre cómo usar un especificador de formato único, vea [Usar especificadores de formato personalizado únicos](#UsingSingleSpecifiers) más adelante en este artículo.

En el ejemplo siguiente se incluye el especificador de formato personalizado "M" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#11](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#11)]
[!code-vb[Formatting.DateAndTime.Custom#11](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#11)]

[Volver a la tabla](#table)

## <a name="the-mm-custom-format-specifier"></a><a name="MM_Specifier"></a> Especificador de formato personalizado "MM"

El especificador de formato personalizado "MM" representa el mes como un número del 01 al 12 (o del 1 al 13 para los calendarios con 13 meses). Un mes con un solo dígito tiene un formato con un cero inicial.

En el ejemplo siguiente se incluye el especificador de formato personalizado "MM" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#2](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#2)]
[!code-vb[Formatting.DateAndTime.Custom#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#2)]

[Volver a la tabla](#table)

## <a name="the-mmm-custom-format-specifier"></a><a name="MMM_Specifier"></a> Especificador de formato personalizado "MMM"

El especificador de formato personalizado "MMM" representa el nombre abreviado del mes. El nombre abreviado adaptado del mes se recupera de la propiedad <xref:System.Globalization.DateTimeFormatInfo.AbbreviatedMonthNames%2A?displayProperty=nameWithType> de la referencia cultural actual o especificada.

En el ejemplo siguiente se incluye el especificador de formato personalizado "MMM" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#3](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#3)]
[!code-vb[Formatting.DateAndTime.Custom#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#3)]

[Volver a la tabla](#table)

## <a name="the-mmmm-custom-format-specifier"></a><a name="MMMM_Specifier"></a> Especificador de formato personalizado "MMMM"

El especificador de formato personalizado "MMMM" representa el nombre completo del mes. El nombre adaptado del mes se recupera de la propiedad <xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A?displayProperty=nameWithType> de la referencia cultural actual o especificada.

En el ejemplo siguiente se incluye el especificador de formato personalizado "MMMM" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#4](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#4)]
[!code-vb[Formatting.DateAndTime.Custom#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#4)]

[Volver a la tabla](#table)

## <a name="the-s-custom-format-specifier"></a><a name="sSpecifier"></a> Especificador de formato personalizado "s"

El especificador de formato personalizado "s" representa los segundos como un número de 0 a 59. El resultado representa los segundos enteros que han transcurrido desde el último minuto. Un segundo con un solo dígito tiene un formato sin un cero inicial.

Si el especificador de formato "s" se usa sin otros especificadores de formato personalizado, se interpretará como el especificador de formato de fecha y hora estándar "s". Para más información sobre cómo usar un especificador de formato único, vea [Usar especificadores de formato personalizado únicos](#UsingSingleSpecifiers) más adelante en este artículo.

En el ejemplo siguiente se incluye el especificador de formato personalizado "s" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#7](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#7)]
[!code-vb[Formatting.DateAndTime.Custom#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#7)]

[Volver a la tabla](#table)

## <a name="the-ss-custom-format-specifier"></a><a name="ssSpecifier"></a> Especificador de formato personalizado "ss"

El especificador de formato personalizado "ss" (más cualquier número de especificadores "s" adicionales) representa los segundos como un número de 00 a 59. El resultado representa los segundos enteros que han transcurrido desde el último minuto. Un segundo con un solo dígito tiene un formato con un cero inicial.

En el ejemplo siguiente se incluye el especificador de formato personalizado "ss" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#8](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#8)]
[!code-vb[Formatting.DateAndTime.Custom#8](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#8)]

[Volver a la tabla](#table)

## <a name="the-t-custom-format-specifier"></a><a name="tSpecifier"></a> Especificador de formato personalizado "t"

El especificador de formato personalizado "t" representa el primer carácter del designador AM/PM. El designador adaptado adecuado se recupera de la propiedad <xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A?displayProperty=nameWithType> o <xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A?displayProperty=nameWithType> de la referencia cultural actual o especificada. El designador AM se usa para todas las horas de 0:00:00 (medianoche) a 11:59:59.999. El designador PM se usa para todas las horas de 12:00:00 (mediodía) a 23:59:59.999.

Si el especificador de formato "t" se usa sin otros especificadores de formato personalizado, se interpretará como el especificador de formato de fecha y hora estándar "t". Para más información sobre cómo usar un especificador de formato único, vea [Usar especificadores de formato personalizado únicos](#UsingSingleSpecifiers) más adelante en este artículo.

En el ejemplo siguiente se incluye el especificador de formato personalizado "t" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#7](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#7)]
[!code-vb[Formatting.DateAndTime.Custom#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#7)]

[Volver a la tabla](#table)

## <a name="the-tt-custom-format-specifier"></a><a name="ttSpecifier"></a> Especificador de formato personalizado "tt"

El especificador de formato personalizado "tt" (más cualquier número de especificadores "t" adicionales) representa designador AM/PM completo. El designador adaptado adecuado se recupera de la propiedad <xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A?displayProperty=nameWithType> o <xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A?displayProperty=nameWithType> de la referencia cultural actual o especificada. El designador AM se usa para todas las horas de 0:00:00 (medianoche) a 11:59:59.999. El designador PM se usa para todas las horas de 12:00:00 (mediodía) a 23:59:59.999.

Asegúrese de usar el especificador "tt" para aquellos idiomas en los que sea necesario mantener la distinción entre a. m. y p. m. Un ejemplo es el japonés, en el que los designadores de a.m. y p.m. se diferencian en el segundo carácter en vez de en el primero.

En el ejemplo siguiente se incluye el especificador de formato personalizado "tt" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#8](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#8)]
[!code-vb[Formatting.DateAndTime.Custom#8](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#8)]

[Volver a la tabla](#table)

## <a name="the-y-custom-format-specifier"></a><a name="ySpecifier"></a> Especificador de formato personalizado "y"

El especificador de formato personalizado "y" representa el año como un número de uno o dos dígitos. Si el año tiene más de dos dígitos, en el resultado sólo aparecen los dos dígitos de orden inferior. Si el primer dígito de un año de dos dígitos comienza con un cero (por ejemplo, 2008), se aplica formato al número sin el cero inicial.

Si el especificador de formato "y" se usa sin otros especificadores de formato personalizado, se interpretará como el especificador de formato de fecha y hora estándar "y". Para más información sobre cómo usar un especificador de formato único, vea [Usar especificadores de formato personalizado únicos](#UsingSingleSpecifiers) más adelante en este artículo.

En el ejemplo siguiente se incluye el especificador de formato personalizado "y" en una cadena de formato personalizado.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#13](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#13)]
[!code-vb[Formatting.DateAndTime.Custom#13](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#13)]

[Volver a la tabla](#table)

## <a name="the-yy-custom-format-specifier"></a><a name="yySpecifier"></a> Especificador de formato personalizado "yy"

El especificador de formato personalizado "yy" representa el año como un número de dos dígitos. Si el año tiene más de dos dígitos, en el resultado sólo aparecen los dos dígitos de orden inferior. Si el año de dos dígitos tiene menos de dos dígitos significativos, el número se rellenará con ceros iniciales hasta obtener dos dígitos.

En una operación de análisis, un año de dos dígitos que se analiza mediante el especificador de formato personalizado “yy” se interpreta basándose en la propiedad de <xref:System.Globalization.Calendar.TwoDigitYearMax%2A?displayProperty=nameWithType> del calendario actual del proveedor de formato. En el ejemplo siguiente se analiza la representación en forma de cadena de una fecha con un año de dos dígitos utilizando el calendario gregoriano predeterminado de la referencia cultural actual (en este caso, en-US). Modifica el objeto <xref:System.Globalization.CultureInfo> de la referencia cultural actual para utilizar un objeto <xref:System.Globalization.GregorianCalendar> cuya propiedad <xref:System.Globalization.GregorianCalendar.TwoDigitYearMax%2A> se ha modificado.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#19](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/parseexact2digityear1.cs#19)]
[!code-vb[Formatting.DateAndTime.Custom#19](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/parseexact2digityear1.vb#19)]

En el ejemplo siguiente se incluye el especificador de formato personalizado "yy" en una cadena de formato personalizado.

[!code-csharp[Formatting.DateAndTime.Custom#13](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#13)]
[!code-vb[Formatting.DateAndTime.Custom#13](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#13)]

[Volver a la tabla](#table)

## <a name="the-yyy-custom-format-specifier"></a><a name="yyySpecifier"></a> Especificador de formato personalizado "yyy"

El especificador de formato personalizado "yyy" representa el año con un mínimo de tres dígitos. Si el año tiene más de tres dígitos significativos, se incluyen en la cadena de resultado. Si el año tiene menos de tres dígitos, el número se rellenará con ceros iniciales hasta obtener tres dígitos.

> [!NOTE]
> Para el calendario budista tailandés, que puede tener años de cinco dígitos, este especificador de formato muestra todos los dígitos significativos.

En el ejemplo siguiente se incluye el especificador de formato personalizado "yyy" en una cadena de formato personalizado.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#13](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#13)]
[!code-vb[Formatting.DateAndTime.Custom#13](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#13)]

[Volver a la tabla](#table)

## <a name="the-yyyy-custom-format-specifier"></a><a name="yyyySpecifier"></a> Especificador de formato personalizado "yyyy"

El especificador de formato personalizado "Yyyy" representa el año con un mínimo de cuatro dígitos. Si el año tiene más de cuatro dígitos significativos, se incluyen en la cadena resultante. Si el año tiene menos de cuatro dígitos, el número se completa con ceros iniciales hasta obtener cuatro dígitos.

> [!NOTE]
> En el calendario budista tailandés, que puede tener años de cinco dígitos, este especificador de formato muestra un mínimo de cuatro dígitos.

En el ejemplo siguiente se incluye el especificador de formato personalizado "yyyy" en una cadena de formato personalizado.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#13](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#13)]
[!code-vb[Formatting.DateAndTime.Custom#13](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#13)]

[Volver a la tabla](#table)

## <a name="the-yyyyy-custom-format-specifier"></a><a name="yyyyySpecifier"></a> Especificador de formato personalizado "yyyyy"

El especificador de formato personalizado "yyyyy" (más cualquier número de especificadores "y" adicionales) representa el año con un mínimo de cinco dígitos. Si el año tiene más de cinco dígitos significativos, se incluyen en la cadena resultante. Si el año tiene menos de cinco dígitos, el número se rellenará con ceros iniciales hasta obtener cinco dígitos.

Si hay especificadores "y" adicionales, el número se rellenará con tantos ceros iniciales como sean necesarios para obtener el número de especificadores "y".

En el ejemplo siguiente se incluye el especificador de formato personalizado "yyyyy" en una cadena de formato personalizado.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#13](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#13)]
[!code-vb[Formatting.DateAndTime.Custom#13](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#13)]

[Volver a la tabla](#table)

## <a name="the-z-custom-format-specifier"></a><a name="zSpecifier"></a> Especificador de formato personalizado "z"

Con valores <xref:System.DateTime>, el especificador de formato personalizado "z" representa el desfase con signo de la zona horaria del sistema operativo local respecto a la hora universal coordinada (UTC), medido en horas. No refleja el valor de la propiedad <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> de una instancia. Por esta razón, no se recomienda usar el especificador de formato "z" con valores <xref:System.DateTime>.

Con valores <xref:System.DateTimeOffset>, este especificador de formato representa el desfase en horas del valor <xref:System.DateTimeOffset> con respecto a la hora UTC.

La diferencia horaria se muestra siempre con un signo inicial. Un signo más (+) indica las horas de adelanto y un signo menos (-) indica las horas de retraso con respecto a la hora UTC. Un desfase con un solo dígito tiene un formato sin un cero inicial.

Si el especificador de formato "z" se usa sin otros especificadores de formato personalizado, se interpretará como un especificador de formato de fecha y hora estándar y producirá una excepción <xref:System.FormatException>. Para más información sobre cómo usar un especificador de formato único, vea [Usar especificadores de formato personalizado únicos](#UsingSingleSpecifiers) más adelante en este artículo.

En el ejemplo siguiente se incluye el especificador de formato personalizado "z" en una cadena de formato personalizado.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#14](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#14)]
[!code-vb[Formatting.DateAndTime.Custom#14](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#14)]

[Volver a la tabla](#table)

## <a name="the-zz-custom-format-specifier"></a><a name="zzSpecifier"></a> Especificador de formato personalizado "zz"

Con valores <xref:System.DateTime>, el especificador de formato personalizado "zz" representa el desfase con signo de la zona horaria del sistema operativo local respecto a la hora UTC, medido en horas. No refleja el valor de la propiedad <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> de una instancia. Por esta razón, no se recomienda usar el especificador de formato "zz" con valores <xref:System.DateTime>.

Con valores <xref:System.DateTimeOffset>, este especificador de formato representa el desfase en horas del valor <xref:System.DateTimeOffset> con respecto a la hora UTC.

La diferencia horaria se muestra siempre con un signo inicial. Un signo más (+) indica las horas de adelanto y un signo menos (-) indica las horas de retraso con respecto a la hora UTC. Un desfase con un solo dígito tiene un formato con un cero inicial.

En el ejemplo siguiente se incluye el especificador de formato personalizado "zz" en una cadena de formato personalizado.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#14](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#14)]
[!code-vb[Formatting.DateAndTime.Custom#14](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#14)]

[Volver a la tabla](#table)

## <a name="the-zzz-custom-format-specifier"></a><a name="zzzSpecifier"></a> Especificador de formato personalizado "zzz"

Con valores <xref:System.DateTime>, el especificador de formato personalizado "zzz" representa el desfase con signo de la zona horaria del sistema operativo local respecto a la hora UTC, medido en horas y minutos. No refleja el valor de la propiedad <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> de una instancia. Por esta razón, no se recomienda usar el especificador de formato "zzz" con valores <xref:System.DateTime>.

Con valores <xref:System.DateTimeOffset>, este especificador de formato representa el desfase en horas y minutos del valor <xref:System.DateTimeOffset> con respecto a la hora UTC.

La diferencia horaria se muestra siempre con un signo inicial. Un signo más (+) indica las horas de adelanto y un signo menos (-) indica las horas de retraso con respecto a la hora UTC. Un desfase con un solo dígito tiene un formato con un cero inicial.

En el ejemplo siguiente se incluye el especificador de formato personalizado "zzz" en una cadena de formato personalizado.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#14](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/Custom1.cs#14)]
[!code-vb[Formatting.DateAndTime.Custom#14](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/Custom1.vb#14)]

[Volver a la tabla](#table)

## <a name="the--custom-format-specifier"></a><a name="timeSeparator"></a> Especificador de formato personalizado ":"
El especificador de formato personalizado ":" representa el separador de hora, que se usa para diferenciar horas, minutos y segundos. El separador de hora adaptado adecuado se recupera de la propiedad <xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A?displayProperty=nameWithType> de la referencia cultural actual o especificada.

> [!NOTE]
> Para cambiar el separador de hora en una determinada cadena de fecha y hora, especifique el carácter separador en un delimitador de cadena literal. Por ejemplo, la cadena de formato personalizado `hh'_'dd'_'ss` genera una cadena en que "\_" (guion bajo) siempre se utiliza como separador de hora. Para cambiar el separador de hora en todas las fechas de una referencia cultural, cambie el valor de la propiedad <xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A?displayProperty=nameWithType> de la referencia cultural actual, o cree una instancia de un objeto <xref:System.Globalization.DateTimeFormatInfo>, asigne el carácter a su propiedad <xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A> y llame a una sobrecarga del método de formato que incluya un parámetro <xref:System.IFormatProvider>.

Si el especificador de formato ":" se usa sin otros especificadores de formato personalizado, se interpretará como un especificador de formato de fecha y hora estándar y producirá una excepción <xref:System.FormatException>. Para más información sobre cómo usar un especificador de formato único, vea [Usar especificadores de formato personalizado únicos](#UsingSingleSpecifiers) más adelante en este artículo.

[Volver a la tabla](#table)

## <a name="the--custom-format-specifier"></a><a name="dateSeparator"></a> Especificador de formato personalizado "/"

El especificador de formato personalizado "/" representa el separador de fecha, que se usa para diferenciar años, meses y días. El separador de fecha adaptado adecuado se recupera de la propiedad <xref:System.Globalization.DateTimeFormatInfo.DateSeparator%2A?displayProperty=nameWithType> de la referencia cultural actual o especificada.

> [!NOTE]
> Para cambiar el separador de fecha en una determinada cadena de fecha y hora, especifique el carácter separador en un delimitador de cadena literal. Por ejemplo, la cadena de formato personalizado `mm'/'dd'/'yyyy` genera una cadena en que "/" siempre se utiliza como separador de fecha. Para cambiar el separador de fecha en todas las fechas de una referencia cultural, cambie el valor de la propiedad <xref:System.Globalization.DateTimeFormatInfo.DateSeparator%2A?displayProperty=nameWithType> de la referencia cultural actual, o cree una instancia de un objeto <xref:System.Globalization.DateTimeFormatInfo>, asigne el carácter a su propiedad <xref:System.Globalization.DateTimeFormatInfo.DateSeparator%2A> y llame a una sobrecarga del método de formato que incluya un parámetro <xref:System.IFormatProvider>.

Si el especificador de formato "/" se usa sin otros especificadores de formato personalizado, se interpretará como un especificador de formato de fecha y hora estándar y producirá una excepción <xref:System.FormatException>. Para más información sobre cómo usar un especificador de formato único, vea [Usar especificadores de formato personalizado únicos](#UsingSingleSpecifiers) más adelante en este artículo.

[Volver a la tabla](#table)

## <a name="character-literals"></a><a name="Literals"></a> Literales de carácter

Los siguientes caracteres de una cadena de formato de fecha y hora personalizado están reservados y siempre se interpretan como caracteres de formato o, en el caso de ", ', / y \\, como caracteres especiales.

||||||
|-|-|-|-|-|
|F|H|K|M|d|
|f|e|h|m|s|
|m|y|z|%|:|
|/|"|'|&#92;||

Todos los demás caracteres se interpretan siempre como literales de carácter y, en una operación de formato, se incluyen en la cadena de resultado sin modificar.  En una operación de análisis, deben coincidir exactamente con los caracteres de la cadena de entrada; la comparación distingue entre mayúsculas y minúsculas.

En el ejemplo siguiente se incluyen los caracteres literales "PST" (para hora estándar del Pacífico) y "PDT" (para horario de verano del Pacífico) para representar la zona horaria local en una cadena de formato. Tenga en cuenta que la cadena se incluye en la cadena de resultado y que una cadena que incluye la cadena de zona horaria local también se analiza correctamente.

[!code-csharp[Formatting.DateAndTime.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/LiteralsEx1.cs#20)]
[!code-vb[Formatting.DateAndTime.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/LiteralsEx1.vb#20)]

Hay dos formas de indicar que los caracteres se han de interpretar como caracteres literales y no como caracteres de reserva, para que se puedan incluir en una cadena de resultado o analizarse correctamente en una cadena de entrada:

- Al incluir un escape con cada carácter reservado. Para obtener más información, consulte [Usar el carácter de escape](#escape).

En el ejemplo siguiente se incluyen los caracteres literales "pst" (para hora estándar del Pacífico) para representar la zona horaria local en una cadena de formato. Como "s" y "t" son cadenas de formato personalizado, ambos caracteres deben incluir un escape para interpretarse como literales de carácter.

[!code-csharp[Formatting.DateAndTime.Custom#21](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/LiteralsEx2.cs#21)]
[!code-vb[Formatting.DateAndTime.Custom#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/LiteralsEx2.vb#21)]

- Al incluir toda la cadena literal entre comillas o apóstrofes. El siguiente ejemplo es igual al anterior, excepto que "pst" se incluye entre comillas para indicar que toda la cadena delimitada debe interpretarse como literales de carácter.

[!code-csharp[Formatting.DateAndTime.Custom#22](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/LiteralsEx3.cs#22)]
[!code-vb[Formatting.DateAndTime.Custom#22](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/LiteralsEx3.vb#22)]

## <a name="notes"></a>Notas

### <a name="using-single-custom-format-specifiers"></a><a name="UsingSingleSpecifiers"></a> Usar especificadores de formato personalizado únicos

Una cadena con formato de fecha y hora personalizado se compone de dos o más caracteres. Los métodos de formato de fecha y hora interpretan cualquier cadena de un único carácter como una cadena de formato de fecha y hora estándar. Si no reconocen el carácter como un especificador de formato válido, producen una excepción <xref:System.FormatException>. Por ejemplo, una cadena de formato que solo se compone del especificador "h" se interpreta como una cadena de formato de fecha y hora estándar. Sin embargo, en este caso concreto, se produce una excepción porque no existe ningún especificador de formato de fecha y hora estándar "h".

Para usar cualquiera de los especificadores de formato de fecha y hora personalizado como el único especificador en una cadena de formato (es decir, usar el especificador de formato personalizado "d", "f", "F", "g", "h", "H", "K", "m", "M", "s", "t", "y", "z", ":" o "/"), incluya un espacio delante o detrás del especificador, o incluya un especificador de formato de porcentaje ("%") delante del único especificador de fecha y hora personalizado.

Por ejemplo, "`%h"` se interpreta como una cadena de formato de fecha y hora personalizado que muestra la hora representada por el valor de fecha y hora actual. También puede usar la cadena de formato " h" o "h ", aunque esto incluye un espacio en la cadena de resultado junto con la hora. En el ejemplo siguiente se muestran estas tres cadenas de formato.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#16](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/literal1.cs#16)]
[!code-vb[Formatting.DateAndTime.Custom#16](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/literal1.vb#16)]

### <a name="using-the-escape-character"></a><a name="escape"></a> Usar el carácter de escape

Los caracteres "d", "f", "F", "g", "h", "H", "K", "m", "M", "s", "t", "y", "z", ":" o "/" en una cadena de formato se interpretan como especificadores de formato personalizado en lugar de como caracteres literales. Para evitar que un carácter se interprete como un especificador de formato, puede precederlo de una barra diagonal inversa (\\), que es el carácter de escape. El carácter de escape significa que el siguiente carácter es un carácter literal que se debe incluir en la cadena de resultado sin modificar.

Para incluir una barra diagonal inversa en una cadena de resultado, debe indicar su secuencia de escape con otra barra diagonal inversa (`\\`).

> [!NOTE]
> Algunos compiladores, como los compiladores de C# y C++, también pueden interpretar un único carácter de barra diagonal inversa como un carácter de escape. Para asegurarse de que una cadena se interpreta correctamente al darle formato, puede usar el carácter literal de cadena textual (el carácter @) antes de la cadena en C# o puede agregar otro carácter de barra diagonal inversa delante de cada barra diagonal inversa en C# y C++. En el siguiente ejemplo de C# se muestran ambos enfoques.

En el ejemplo siguiente se usa el carácter de escape para evitar que la operación de formato interprete los caracteres "h" y "m" como especificadores de formato.

[!code-csharp-interactive[Formatting.DateAndTime.Custom#15](~/samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Custom/cs/escape1.cs#15)]
[!code-vb[Formatting.DateAndTime.Custom#15](~/samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Custom/vb/escape1.vb#15)]

### <a name="control-panel-settings"></a>Configuración del Panel de control

La configuración de **Configuración regional y de idioma** del Panel de control influye en la cadena de resultado generada por una operación de formato que incluye muchos de los especificadores de formato de fecha y hora personalizado. Estas configuraciones se utilizan para inicializar el objeto <xref:System.Globalization.DateTimeFormatInfo> asociado a la referencia cultural del subproceso actual, que proporciona valores que se utilizan para controlar el formato. Los equipos que usan configuraciones diferentes generarán cadenas de resultado distintas.

Asimismo, si se usa el constructor <xref:System.Globalization.CultureInfo.%23ctor%28System.String%29> para crear instancias de un nuevo objeto <xref:System.Globalization.CultureInfo> que representa la misma referencia cultural que la referencia cultural del sistema actual, cualquier personalización establecida por el elemento **Configuración regional y de idioma** del Panel de control se aplicará al nuevo objeto <xref:System.Globalization.CultureInfo> . Puede usar el constructor <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29> para crear un objeto <xref:System.Globalization.CultureInfo> que no refleje las personalizaciones de un sistema.

### <a name="datetimeformatinfo-properties"></a>Propiedades de DateTimeFormatInfo

El formato se ve influenciado por las propiedades del objeto <xref:System.Globalization.DateTimeFormatInfo> actual, proporcionado implícitamente por la referencia cultural del subproceso actual o explícitamente por el parámetro <xref:System.IFormatProvider> del método que invoca el formato. Para el parámetro <xref:System.IFormatProvider>, debe especificar un objeto <xref:System.Globalization.CultureInfo>, que representa una referencia cultural, o un objeto <xref:System.Globalization.DateTimeFormatInfo>.

La cadena de resultado generada por muchos de los especificadores de formato de fecha y hora personalizado también depende de las propiedades del objeto <xref:System.Globalization.DateTimeFormatInfo> actual. La aplicación puede modificar el resultado generado por algunos de los especificadores de formato de fecha y hora personalizado al cambiar la propiedad <xref:System.Globalization.DateTimeFormatInfo> correspondiente. Por ejemplo, el especificador de formato "ddd" agrega a la cadena de resultado el nombre abreviado de un día de la semana que se encuentra en la matriz de cadenas <xref:System.Globalization.DateTimeFormatInfo.AbbreviatedDayNames%2A>. De igual forma, el especificador de formato "MMMM" agrega a la cadena de resultado el nombre completo de un mes que se encuentra en la matriz de cadenas <xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A>.

## <a name="see-also"></a>Vea también

- <xref:System.DateTime?displayProperty=nameWithType>
- <xref:System.IFormatProvider?displayProperty=nameWithType>
- [Aplicación de formato a tipos](formatting-types.md)
- [Cadenas con formato de fecha y hora estándar](standard-date-and-time-format-strings.md)
- [Ejemplo: Utilidad de formato WinForms de .NET Core (C#)](https://docs.microsoft.com/samples/dotnet/samples/windowsforms-formatting-utility-cs)
- [Ejemplo: Utilidad de formato WinForms de .NET Core (Visual Basic)](https://docs.microsoft.com/samples/dotnet/samples/windowsforms-formatting-utility-vb)
