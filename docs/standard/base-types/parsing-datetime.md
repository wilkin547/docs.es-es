---
title: Conversión de cadenas en DateTime
description: Aprenda técnicas de análisis de cadenas que representan fechas y horas para crear un valor DateTime a partir de la cadena de fecha y hora.
ms.date: 02/15/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parsing strings, date and time strings
- date and time strings
- ParseExact method
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- DateTime object
- time strings
ms.openlocfilehash: 9fba80e4dbe1e4950ed24e7489ac48ea1b6ff20b
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662906"
---
# <a name="parse-date-and-time-strings-in-net"></a>Análisis de cadenas de fecha y hora en .NET

El análisis de cadenas para convertirlas en objetos <xref:System.DateTime> requiere que se especifique información sobre cómo se representan las fechas y horas en forma de texto. Las distintas referencias culturales usan distintos órdenes de día, mes y año. Algunas representaciones horarias usan el reloj de 24 horas y otras especifican "a. m." y "p. m.". Algunas aplicaciones solo necesitan la fecha. Otras solo necesitan la hora. Pero otras necesitan especificar la fecha y la hora. Los métodos que convierten cadenas a objeto <xref:System.DateTime> permiten especificar información detallada sobre los formatos esperados y los elementos de fecha y hora que precisa la aplicación. Hay tres subtareas para convertir correctamente el texto en un objeto <xref:System.DateTime>:

1. Debe especificarse el formato esperado del texto que representa una fecha y hora.
1. Es posible especificar la referencia cultural del formato de fecha y hora.
1. Puede especificarse cómo se establecen los componentes que faltan en la representación de texto en la fecha y hora.

Los métodos <xref:System.DateTime.Parse%2A> y <xref:System.DateTime.TryParse%2A> convierten varias representaciones comunes de fecha y hora. Los métodos <xref:System.DateTime.ParseExact%2A> y <xref:System.DateTime.TryParseExact%2A> convierten una representación de cadena que se ajusta al modelo especificado por una cadena de formato de fecha y hora. (Para obtener más información, vea los artículos sobre [cadenas con formato de fecha y hora estándar](standard-date-and-time-format-strings.md) y [cadenas con formato de fecha y hora personalizado](custom-date-and-time-format-strings.md)).

El objeto <xref:System.Globalization.DateTimeFormatInfo> actual proporciona más control sobre la forma en que debe interpretarse el texto como fecha y hora. Las propiedades de un objeto <xref:System.Globalization.DateTimeFormatInfo> describen los separadores de fecha y hora, los nombres de los meses, días y eras, así como el formato de las designaciones "a. m." y "p. m.". La referencia cultural del subproceso actual proporciona un objeto <xref:System.Globalization.DateTimeFormatInfo> que representa la referencia cultural actual. Si quiere una referencia cultural específica o una configuración personalizada, especifique el parámetro <xref:System.IFormatProvider> de un método de análisis. Para el parámetro <xref:System.IFormatProvider>, especifique un objeto <xref:System.Globalization.CultureInfo>, que representa una referencia cultural, o un objeto <xref:System.Globalization.DateTimeFormatInfo>.

Es posible que al texto que representa una fecha y hora le falte alguna información. Por ejemplo, la mayoría de los usuarios supondría que la fecha "12 de marzo" representa el año actual. Del mismo modo, "Marzo de 2018" representa el mes de marzo del año 2018. El texto que representa la hora a menudo solo incluye horas, minutos y una designación "a. m."/"p. m.".  Los métodos de análisis controlan esta información que falta mediante valores predeterminados razonables:

- Cuando solo se indica la hora, la parte de fecha utiliza la fecha actual.
- Cuando solo se indica la fecha, la parte de hora es la medianoche.
- Cuando no se especifica el año en una fecha, se usa el año actual.
- Cuando no se especifica el día del mes, se usa el primero del mes.

Si la fecha se indica en la cadena, debe incluir el mes y uno de los dos valores, el día o el año. Si se indica la hora, debe incluir la hora y los minutos o el designador "a. m."/"p. m.".

Se puede especificar la constante <xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault> para invalidar los valores predeterminados. Cuando se usa esta constante, las propiedades de año, mes o día se establecen en el valor `1`. El [último ejemplo](#styles-example) con <xref:System.DateTime.Parse%2A> muestra este comportamiento.

Además de un componente de fecha y hora, la representación de cadena de una fecha y hora puede incluir una diferencia horaria que indica cuánto difiere la hora respecto de la hora universal coordinada (UTC). Por ejemplo, la cadena "14/2/2007 5:32:00 -7:00" define una hora que es siete horas anterior a la hora UTC. Si se omite la diferencia horaria de la representación de cadena de una hora, el análisis devuelve un objeto <xref:System.DateTime> con su propiedad <xref:System.DateTime.Kind%2A> establecida en <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>. Si se especifica la diferencia horaria, el análisis devuelve un objeto <xref:System.DateTime> con su propiedad <xref:System.DateTime.Kind%2A> establecida en <xref:System.DateTimeKind.Local?displayProperty=nameWithType> y su valor ajustado a la zona horaria local del equipo. Puede modificar este comportamiento usando un valor <xref:System.Globalization.DateTimeStyles> con el método de análisis.

El proveedor de formato también se usa para interpretar una fecha numérica ambigua. No queda claro qué componentes de la fecha representada por la cadena "02/03/04" son el mes, el día y el año. Los componentes se interpretan según el orden de formatos de fecha similares del proveedor de formato.

## <a name="parse"></a>Parse

En el ejemplo siguiente se muestra el uso del método <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> para convertir un objeto `string` en un valor <xref:System.DateTime>. En este ejemplo se usa la referencia cultural asociada al subproceso actual. Si el objeto <xref:System.Globalization.CultureInfo> asociado a la referencia cultural actual no puede analizar la cadena de entrada, se produce una excepción <xref:System.FormatException>.

> [!TIP]
> Todos los ejemplos de C# en este artículo se ejecutan en el explorador. Presione el botón **Ejecutar** para ver el resultado. También puede modificarlos para experimentar.

> [!NOTE]
> Estos ejemplos están disponibles en el repositorio de documentos de GitHub para [C#](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/conversions) y [Visual Basic](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/how-to/conversions).

[!code-csharp-interactive[Parsing.DateAndTime#1](../../../samples/snippets/csharp/how-to/conversions/StringToDateTime.cs#1)]
[!code-vb[Parsing.DateAndTime#1](../../../samples/snippets/visualbasic/how-to/conversions/Program.vb#1)]

Además, puede definir explícitamente la referencia cultural cuyas convenciones de formato se utilizan cuando se analiza una cadena. Especifique uno de los objetos <xref:System.Globalization.DateTimeFormatInfo> estándar devueltos por la propiedad <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>. En el ejemplo siguiente se usa un proveedor de formato para analizar una cadena en alemán como valor <xref:System.DateTime>. Crea un objeto <xref:System.Globalization.CultureInfo> que representa la referencia cultural `de-DE`. El objeto `CultureInfo` garantiza el análisis correcto de esta cadena concreta. Esto impide cualquier opción que se encuentre en <xref:System.Threading.Thread.CurrentCulture> de <xref:System.Threading.Thread.CurrentThread>.

[!code-csharp-interactive[Parsing.DateAndTime#2](../../../samples/snippets/csharp/how-to/conversions/StringToDateTime.cs#2)]
[!code-vb[Parsing.DateAndTime#2](../../../samples/snippets/visualbasic/how-to/conversions/Program.vb#2)]

Pero, aunque puede usar sobrecargas del método <xref:System.DateTime.Parse%2A> para especificar proveedores de formato personalizados, el método no admite el análisis de formatos no estándar. Para analizar una fecha y hora expresadas en un formato no estándar, use en su lugar el método <xref:System.DateTime.ParseExact%2A>.

<a name="styles-example"></a>En el ejemplo siguiente se usa la enumeración <xref:System.Globalization.DateTimeStyles> para especificar que no debe agregarse la información de fecha y hora actual al valor <xref:System.DateTime> en los campos no especificados.

[!code-csharp-interactive[Parsing.DateAndTime#3](../../../samples/snippets/csharp/how-to/conversions/StringToDateTime.cs#3)]
[!code-vb[Parsing.DateAndTime#3](../../../samples/snippets/visualbasic/how-to/conversions/Program.vb#3)]

## <a name="parseexact"></a>ParseExact

Si se ajusta a uno de los patrones de cadena especificados, el método <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> convierte una cadena en un objeto <xref:System.DateTime>. Cuando se pasa a este método una cadena que no tiene uno de las formas especificadas, se genera una excepción <xref:System.FormatException>. Puede definirse uno de los especificadores de formato de fecha y hora estándar o una combinación de los especificadores de formato de fecha y hora personalizados. Con el uso de especificadores de formato personalizados, es posible construir una cadena de reconocimiento personalizada. Para obtener una explicación de los especificadores, consulte los temas sobre [cadenas con formato de fecha y hora estándar](standard-date-and-time-format-strings.md) y [cadenas con formato de fecha y hora personalizado](custom-date-and-time-format-strings.md).

En el ejemplo siguiente, se pasa al método <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> un objeto de cadena para que lo analice, seguido de un especificador de formato y luego de un objeto <xref:System.Globalization.CultureInfo>. Este método <xref:System.DateTime.ParseExact%2A> solo puede analizar cadenas que sigan el patrón de fecha larga en la referencia cultural `en-US`.

[!code-csharp-interactive[Parsing.DateAndTime#4](../../../samples/snippets/csharp/how-to/conversions/StringToDateTime.cs#4)]
[!code-vb[Parsing.DateAndTime#4](../../../samples/snippets/visualbasic/how-to/conversions/Program.vb#4)]

Cada sobrecarga de los métodos <xref:System.DateTime.Parse%2A> y <xref:System.DateTime.ParseExact%2A> tiene también un parámetro <xref:System.IFormatProvider> que proporciona información específica de la referencia cultural sobre el formato de la cadena. Este objeto <xref:System.IFormatProvider> es un objeto <xref:System.Globalization.CultureInfo> que representa una referencia cultural estándar o un objeto <xref:System.Globalization.DateTimeFormatInfo> devuelto por la propiedad <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>.  <xref:System.DateTime.ParseExact%2A> usa también una cadena o un argumento de matriz de cadena adicional que define uno o más formatos de fecha y hora personalizados.

## <a name="see-also"></a>Vea también

- [Análisis de cadenas](parsing-strings.md)
- [Aplicar formato a tipos](formatting-types.md)
- [Conversión de tipos en .NET](type-conversion.md)
- [Cadenas con formato de fecha y hora estándar](standard-date-and-time-format-strings.md)
- [Cadenas con formato de fecha y hora personalizado](custom-date-and-time-format-strings.md)
