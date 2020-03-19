---
title: Trabajar con calendarios
ms.date: 04/01/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- globalization [.NET], calendars
- calendars, global applications
- global applications, calendars
- world-ready applications, calendars
- international applications [.NET], calendars
- culture, calendars
ms.assetid: 0c1534e5-979b-4c8a-a588-1c24301aefb3
ms.openlocfilehash: de8e5a03c769a22f3320c7785706555898bf8c1c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401236"
---
# <a name="work-with-calendars"></a>Trabajar con calendarios

Aunque un valor de fecha y hora representa un momento en el tiempo, su representación de cadena tiene en cuenta la referencia cultural y depende tanto de las convenciones empleadas para mostrar los valores de fecha y hora por una referencia cultural específica como del calendario usado por esa referencia cultural. En este tema se explora la compatibilidad con calendarios en .NET y se describe el uso de las clases de calendario al trabajar con valores de fecha.

## <a name="calendars-in-net"></a>Calendarios en .NET

Todos los calendarios de <xref:System.Globalization.Calendar?displayProperty=nameWithType> .NET derivan de la clase, que proporciona la implementación del calendario base. Una de las clases que hereda de la clase <xref:System.Globalization.Calendar> es <xref:System.Globalization.EastAsianLunisolarCalendar>, que es la clase base para todos los calendarios lunisolares. .NET incluye las siguientes implementaciones de calendario:

- <xref:System.Globalization.ChineseLunisolarCalendar>, que representa el calendario lunisolar chino.

- <xref:System.Globalization.GregorianCalendar>, que representa el calendario gregoriano. Este calendario se divide a su vez en subtipos (como el árabe y el francés de Oriente Medio) definidos por la enumeración <xref:System.Globalization.GregorianCalendarTypes?displayProperty=nameWithType>. La propiedad <xref:System.Globalization.GregorianCalendar.CalendarType%2A?displayProperty=nameWithType> especifica el subtipo del calendario Gregoriano.

- <xref:System.Globalization.HebrewCalendar>, que representa el calendario hebreo.

- <xref:System.Globalization.HijriCalendar>, que representa el calendario Hijri.

- <xref:System.Globalization.JapaneseCalendar>, que representa el calendario japonés.

- <xref:System.Globalization.JapaneseLunisolarCalendar>, que representa el calendario lunisolar japonés.

- <xref:System.Globalization.JulianCalendar>, que representa el calendario juliano.

- <xref:System.Globalization.KoreanCalendar>, que representa el calendario coreano.

- <xref:System.Globalization.KoreanLunisolarCalendar>, que representa el calendario lunisolar coreano.

- <xref:System.Globalization.PersianCalendar>, que representa el calendario persa.

- <xref:System.Globalization.TaiwanCalendar>, que representa el calendario taiwanés.

- <xref:System.Globalization.TaiwanLunisolarCalendar>, que representa el calendario lunisolar taiwanés.

- <xref:System.Globalization.ThaiBuddhistCalendar>, que representa el calendario budista tailandés.

- <xref:System.Globalization.UmAlQuraCalendar>, que representa el calendario Um-Al-Qura.

Un calendario se puede usar de dos maneras:

- Como el calendario empleado por una referencia cultural específica. Cada objeto <xref:System.Globalization.CultureInfo> tiene un calendario actual, que es el calendario que el objeto está usando actualmente. Las representaciones de cadena de todos los valores de fecha y hora reflejan automáticamente la referencia cultural actual y su calendario actual. Normalmente, el calendario actual es el calendario predeterminado de la referencia cultural. <xref:System.Globalization.CultureInfo>los objetos también tienen calendarios opcionales, que incluyen calendarios adicionales que la referencia cultural puede usar.

- Como calendario independiente de una referencia cultural concreta. En este caso, los métodos de <xref:System.Globalization.Calendar> se emplean para expresar las fechas como valores que reflejen el calendario.

Tenga en cuenta que seis clases de calendario (<xref:System.Globalization.ChineseLunisolarCalendar>, <xref:System.Globalization.JapaneseLunisolarCalendar>, <xref:System.Globalization.JulianCalendar>, <xref:System.Globalization.KoreanLunisolarCalendar>, <xref:System.Globalization.PersianCalendar> y <xref:System.Globalization.TaiwanLunisolarCalendar>) solo se pueden usar como calendarios independientes. Ninguna referencia cultural los usa como calendario predeterminado ni como calendario opcional.

## <a name="calendars-and-cultures"></a>Calendarios y culturas

Cada referencia cultural tiene un calendario predeterminado, que está definido por la propiedad <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType>. La propiedad <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType> devuelve una matriz de objetos <xref:System.Globalization.Calendar> que especifica todos los calendarios admitidos por una referencia cultural determinada, incluido el calendario predeterminado de esa referencia cultural.

En el ejemplo siguiente se muestra cómo usar las propiedades <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType> y <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>. Crea objetos `CultureInfo` para las referencias culturales de tailandés (Tailandia) y japonés (Japón), y muestra sus calendarios predeterminados y opcionales. Tenga en cuenta que, en ambos casos, el calendario predeterminado de la referencia cultural también se incluye en la colección <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>.

[!code-csharp[Conceptual.Calendars#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/calendarinfo1.cs#1)]
[!code-vb[Conceptual.Calendars#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/calendarinfo1.vb#1)]

El calendario en uso actualmente por un objeto <xref:System.Globalization.CultureInfo> determinado está definido por la propiedad <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType> de la referencia cultural. La propiedad <xref:System.Globalization.DateTimeFormatInfo> devuelve el objeto <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> de la referencia cultural. Cuando se crea una referencia cultural, su valor predeterminado es igual que el valor de la propiedad <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType>. Sin embargo, puede cambiar el calendario actual de la referencia cultural a cualquier calendario contenido en la matriz devuelta por la propiedad <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>. Si intenta establecer el calendario actual en un calendario que no está incluido en el valor de propiedad <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>, se produce <xref:System.ArgumentException>.

En el ejemplo siguiente se cambia el calendario usado por la referencia cultural Árabe (Arabia Saudí). Primero, se crean instancias de un valor <xref:System.DateTime> y se muestra usando la referencia cultural actual que, en este caso, es inglés (Estados Unidos), y el calendario de la referencia cultural actual (que en este caso es el calendario gregoriano). A continuación, cambia la referencia cultural actual a Árabe (Arabia Saudí) y muestra la fecha usando su calendario predeterminado Um-Al-Qura. Después, llama al método `CalendarExists` para determinar si la referencia cultural Árabe (Arabia Saudí) admite el calendario Hijri. Puesto que se admite el calendario, cambia el calendario actual a Hijri y vuelve a mostrar la fecha. Tenga en cuenta que en cada caso la fecha se muestra usando el calendario actual de la referencia cultural actual.

[!code-csharp[Conceptual.Calendars#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/changecalendar2.cs#2)]
[!code-vb[Conceptual.Calendars#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/changecalendar2.vb#2)]

## <a name="dates-and-calendars"></a>Fechas y calendarios

Salvo los constructores que incluyen un parámetro de tipo <xref:System.Globalization.Calendar> y permiten que los elementos de una fecha (es decir, el mes, el día y el año) reflejen los valores de un calendario designado, los valores <xref:System.DateTime> y <xref:System.DateTimeOffset> siempre se basan en el calendario gregoriano. Esto significa, por ejemplo, que la propiedad <xref:System.DateTime.Year%2A?displayProperty=nameWithType> devuelve el año en el calendario gregoriano y la propiedad <xref:System.DateTime.Day%2A?displayProperty=nameWithType> devuelve el día del mes en el calendario gregoriano.

> [!IMPORTANT]
> Es importante recordar que existe una diferencia entre un valor de fecha y su representación de cadena. El primero se basa en el calendario gregoriano, mientras que la última se basa en el calendario actual de una referencia cultural concreta.

En el ejemplo siguiente se muestra esta diferencia entre las propiedades de <xref:System.DateTime> y sus métodos <xref:System.Globalization.Calendar> correspondientes. En el ejemplo, la referencia cultural actual es Árabe (Egipto) y el calendario actual es Um-Al-Qura. Un valor <xref:System.DateTime> se establece en el decimoquinto día del séptimo mes de 2011. Está claro que esto se interpreta como una fecha gregoriana, ya que el método <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> devuelve estos mismos valores cuando se usan las convenciones de la referencia cultural para todos los idiomas. La representación de cadena de la fecha a la que se aplica formato con las convenciones de la referencia cultural actual es 14/08/32, que es la fecha equivalente en el calendario Um-Al-Qura. Después, se usan miembros de `DateTime` y `Calendar` para devolver el día, el mes y el año del valor <xref:System.DateTime>. En cada caso, los valores devueltos por los miembros de <xref:System.DateTime> reflejan los valores en el calendario gregoriano, mientras que los valores devueltos por los miembros de <xref:System.Globalization.UmAlQuraCalendar> reflejan los valores en el calendario Uum-al-Qura.

[!code-csharp[Conceptual.Calendars#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/datesandcalendars2.cs#3)]
[!code-vb[Conceptual.Calendars#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/datesandcalendars2.vb#3)]

### <a name="instantiate-dates-based-on-a-calendar"></a>Crear fechas basadas en un calendario

Puesto que los valores <xref:System.DateTime> y <xref:System.DateTimeOffset> se basan en el calendario gregoriano, debe llamar a un constructor sobrecargado que incluya un parámetro de tipo <xref:System.Globalization.Calendar> para crear instancias de un valor de fecha si desea usar los valores de día, mes o año de otro calendario. También puede llamar a una de las sobrecargas del método <xref:System.Globalization.Calendar.ToDateTime%2A?displayProperty=nameWithType> de un calendario específico para crear instancias de un objeto <xref:System.DateTime> basándose en los valores de un calendario determinado.

En el ejemplo siguiente se crean instancias de un valor <xref:System.DateTime> pasando un objeto <xref:System.Globalization.HebrewCalendar> a un constructor <xref:System.DateTime> y se crean instancias de un segundo valor <xref:System.DateTime> llamando al método <xref:System.Globalization.HebrewCalendar.ToDateTime%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>. Como los dos valores se crean con valores idénticos del calendario hebreo, la llamada al método <xref:System.DateTime.Equals%2A?displayProperty=nameWithType> muestra que los dos valores <xref:System.DateTime> son iguales.

[!code-csharp[Conceptual.Calendars#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatehcdate1.cs#4)]
[!code-vb[Conceptual.Calendars#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatehcdate1.vb#4)]

### <a name="represent-dates-in-the-current-calendar"></a>Representar fechas en el calendario actual

Los métodos de formato de fecha y hora siempre usan el calendario actual al convertir fechas en cadenas. Esto significa que la representación de cadena del año, el mes y el día del mes refleja el calendario actual, y no refleja necesariamente el calendario gregoriano.

En el ejemplo siguiente se muestra cómo afecta el calendario actual a la representación de cadena de una fecha. Cambia la referencia cultural actual a Chino (tradicional, Taiwán) y crea instancias de un valor de fecha. Después muestra el calendario actual y la fecha, cambia el calendario actual a <xref:System.Globalization.TaiwanCalendar> y vuelve a mostrar la fecha y el calendario actual. La primera vez que se muestra la fecha, se representa como una fecha del calendario gregoriano. La segunda vez que se muestra, se representa como una fecha del calendario taiwanés.

[!code-csharp[Conceptual.Calendars#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/currentcalendar1.cs#5)]
[!code-vb[Conceptual.Calendars#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/currentcalendar1.vb#5)]

### <a name="represent-dates-in-a-non-current-calendar"></a>Representar fechas en un calendario no actual

Para representar una fecha mediante un calendario que no es el calendario actual de una referencia cultural determinada, debe llamar a métodos de ese objeto <xref:System.Globalization.Calendar>. Por ejemplo, los métodos <xref:System.Globalization.Calendar.GetYear%2A?displayProperty=nameWithType>, <xref:System.Globalization.Calendar.GetMonth%2A?displayProperty=nameWithType> y <xref:System.Globalization.Calendar.GetDayOfMonth%2A?displayProperty=nameWithType> convierten el año, el mes y el día a los valores que reflejan un calendario determinado.

> [!WARNING]
> Puesto que algunos calendarios no son calendarios opcionales de ninguna referencia cultural, para representar fechas en estos calendarios siempre es necesario llamar a métodos de calendario. Esto es cierto para todos los calendarios que se derivan de las clases <xref:System.Globalization.EastAsianLunisolarCalendar>, <xref:System.Globalization.JulianCalendar> y <xref:System.Globalization.PersianCalendar>.

En el ejemplo siguiente se usa un objeto <xref:System.Globalization.JulianCalendar> para crear instancias de una fecha, el 9 de enero de 1905, en el calendario juliano. Cuando esta fecha se muestra usando el calendario predeterminado (gregoriano), se representa como el 22 de enero de 1905. Las llamadas a métodos individuales de <xref:System.Globalization.JulianCalendar> permiten representar la fecha en el calendario juliano.

[!code-csharp[Conceptual.Calendars#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/noncurrentcalendar1.cs#6)]
[!code-vb[Conceptual.Calendars#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/noncurrentcalendar1.vb#6)]

### <a name="calendars-and-date-ranges"></a>Calendarios y rangos de fechas

La fecha más temprana admitida por un calendario se indica mediante la propiedad <xref:System.Globalization.Calendar.MinSupportedDateTime%2A?displayProperty=nameWithType> de dicho calendario. Para la clase <xref:System.Globalization.GregorianCalendar>, esa fecha es el 1 de enero del año 1 de la era cristiana. La mayoría de los otros calendarios de .NET admiten una fecha posterior. Al intentar trabajar con un valor de fecha y hora anterior a la fecha compatible más temprana de un calendario, se produce una excepción <xref:System.ArgumentOutOfRangeException>.

Sin embargo, hay una excepción importante. El valor (sin inicializar) predeterminado de un objeto <xref:System.DateTime> y un objeto <xref:System.DateTimeOffset> es igual al valor <xref:System.Globalization.GregorianCalendar.MinSupportedDateTime%2A?displayProperty=nameWithType>. Si intenta dar formato a esta fecha en un calendario que no admite el 1 de enero de 0001 C.E. y no proporciona un especificador de formato, el método de formato utiliza el especificador de formato "s" (patrón de fecha/hora sortable) en lugar del especificador de formato "G" (patrón general de fecha y hora). Como resultado, la operación de formato no produce una excepción <xref:System.ArgumentOutOfRangeException>. En su lugar, devuelve la fecha no compatible. Esto se ilustra en el ejemplo siguiente, que muestra el valor de <xref:System.DateTime.MinValue?displayProperty=nameWithType> cuando la referencia cultural actual se establece en japonés (Japón) con el calendario japonés y en árabe (Egipto) con el calendario Um-Al-Qura. También establece la referencia cultural actual en inglés (Estados Unidos) y llama al método <xref:System.DateTime.ToString%28System.IFormatProvider%29?displayProperty=nameWithType> con cada uno de estos objetos <xref:System.Globalization.CultureInfo>. En cada caso, la fecha se muestra mediante el patrón de fecha y hora que se puede ordenar.

[!code-csharp[Conceptual.Calendars#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/minsupporteddatetime1.cs#11)]
[!code-vb[Conceptual.Calendars#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/minsupporteddatetime1.vb#11)]

## <a name="work-with-eras"></a>Trabajar con épocas

Los calendarios suelen dividir las fechas en eras. Sin <xref:System.Globalization.Calendar> embargo, las clases de .NET no admiten <xref:System.Globalization.Calendar> todas las eras definidas por un calendario y la mayoría de las clases solo admiten una sola era. Únicamente las clases <xref:System.Globalization.JapaneseCalendar> y <xref:System.Globalization.JapaneseLunisolarCalendar> admiten varias eras.

> [!IMPORTANT]
> La era Reiwa, una <xref:System.Globalization.JapaneseCalendar> nueva <xref:System.Globalization.JapaneseLunisolarCalendar>era en el y , comienza el 1 de mayo de 2019. Este cambio afecta a todas las aplicaciones que usan estos calendarios. Para obtener más información, consulte los siguientes artículos:
>
> - [Controlar una nueva era en el calendario japonés en .NET](https://devblogs.microsoft.com/dotnet/handling-a-new-era-in-the-japanese-calendar-in-net/), que documenta las características agregadas a .NET para admitir calendarios con varias eras y describe las prácticas recomendadas que se deben usar al controlar calendarios de varias eras.
> - [Prepare la aplicación para el cambio](/windows/uwp/design/globalizing/japanese-era-change)de la era japonesa, que proporciona información sobre cómo probar las aplicaciones en Windows para garantizar su preparación para el cambio de era.
> - [Resumen de las nuevas actualizaciones](https://support.microsoft.com/help/4477957/new-japanese-era-updates-for-net-framework)de la era japonesa para .NET Framework , que enumera las actualizaciones de .NET Framework para versiones individuales de Windows relacionadas con la nueva era del calendario japonés, toma nota de las nuevas características de .NET Framework para la compatibilidad con varias eras e incluye aspectos que debe buscar para probar las aplicaciones.

Una era en la mayoría de los calendarios denota un período de tiempo extremadamente largo. En el calendario gregoriano, por ejemplo, la era actual abarca más de dos milenios. Para <xref:System.Globalization.JapaneseCalendar> el <xref:System.Globalization.JapaneseLunisolarCalendar>y el , los dos calendarios que admiten varias eras, este no es el caso. Una era corresponde al período del reinado de un emperador. El soporte para múltiples eras, especialmente cuando el límite superior de la era actual es desconocido, plantea desafíos especiales.

### <a name="eras-and-era-names"></a>Eras y nombres de era

En .NET, los enteros que representan las eras admitidas por <xref:System.Globalization.Calendar.Eras%2A?displayProperty=nameWithType> una implementación de calendario determinada se almacenan en orden inverso en la matriz. La era actual (que es la era con el último <xref:System.Globalization.Calendar> intervalo de tiempo) está en el índice cero, y para las clases que admiten varias eras, cada índice sucesivo refleja la era anterior. La propiedad estática <xref:System.Globalization.Calendar.CurrentEra?displayProperty=nameWithType> define el índice de la era actual en la matriz de <xref:System.Globalization.Calendar.Eras%2A?displayProperty=nameWithType>; es una constante cuyo valor es siempre cero. Las clases individuales de <xref:System.Globalization.Calendar> también incluyen campos estáticos que devuelven el valor de la era actual. Se muestran en la tabla siguiente.

| Clase de calendario                                        | Campo de era actual                                                 |
| ----------------------------------------------------- | ----------------------------------------------------------------- |
| <xref:System.Globalization.ChineseLunisolarCalendar>  | <xref:System.Globalization.ChineseLunisolarCalendar.ChineseEra>   |
| <xref:System.Globalization.GregorianCalendar>         | <xref:System.Globalization.GregorianCalendar.ADEra>               |
| <xref:System.Globalization.HebrewCalendar>            | <xref:System.Globalization.HebrewCalendar.HebrewEra>              |
| <xref:System.Globalization.HijriCalendar>             | <xref:System.Globalization.HijriCalendar.HijriEra>                |
| <xref:System.Globalization.JapaneseLunisolarCalendar> | <xref:System.Globalization.JapaneseLunisolarCalendar.JapaneseEra> |
| <xref:System.Globalization.JulianCalendar>            | <xref:System.Globalization.JulianCalendar.JulianEra>              |
| <xref:System.Globalization.KoreanCalendar>            | <xref:System.Globalization.KoreanCalendar.KoreanEra>              |
| <xref:System.Globalization.KoreanLunisolarCalendar>   | <xref:System.Globalization.KoreanLunisolarCalendar.GregorianEra>  |
| <xref:System.Globalization.PersianCalendar>           | <xref:System.Globalization.PersianCalendar.PersianEra>            |
| <xref:System.Globalization.ThaiBuddhistCalendar>      | <xref:System.Globalization.ThaiBuddhistCalendar.ThaiBuddhistEra>  |
| <xref:System.Globalization.UmAlQuraCalendar>          | <xref:System.Globalization.UmAlQuraCalendar.UmAlQuraEra>          |

El nombre correspondiente a un número de era determinado se puede recuperar pasando el número de era al método <xref:System.Globalization.DateTimeFormatInfo.GetEraName%2A?displayProperty=nameWithType> o <xref:System.Globalization.DateTimeFormatInfo.GetAbbreviatedEraName%2A?displayProperty=nameWithType>. En el ejemplo siguiente se llama a estos métodos para recuperar información sobre la compatibilidad de eras de la clase <xref:System.Globalization.GregorianCalendar>. Muestra la fecha del calendario gregoriano que corresponde al 1 de enero del segundo año de la era actual, así como la fecha del calendario gregoriano que corresponde al 1 de enero del segundo año de cada era de calendario japonesa compatible.

[!code-csharp[Conceptual.Calendars#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatewithera1.cs)]
[!code-vb[Conceptual.Calendars#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatewithera1.vb)]

Además, la cadena de formato de fecha y hora personalizado "g" incluye el nombre de era de un calendario en la representación de cadena de una fecha y hora. Para obtener más información, consulte Cadenas de formato de [fecha y hora personalizadas.](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)

### <a name="instantiatie-a-date-with-an-era"></a>Instantiatie una cita con una era

Para las <xref:System.Globalization.Calendar> dos clases que admiten varias eras, una fecha que consta de un valor determinado de año, mes y día del mes puede ser ambigua. Por ejemplo, todas las <xref:System.Globalization.JapaneseCalendar> eras soportadas por los años tienen cuyo número es 1. Normalmente, si no se especifica ninguna era, los métodos de fecha y hora y de calendario suponen que los valores pertenecen a la era actual. Esto es cierto <xref:System.DateTime.%23ctor%2A> <xref:System.DateTimeOffset.%23ctor%2A> para los constructores <xref:System.Globalization.Calendar>y que incluyen parámetros de tipo , así como el [JapaneseCalendar.ToDateTime](xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)) y [JapaneseLunisolarCalendar.ToDateTime](xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)) métodos. En el ejemplo siguiente se crea una instancia de una fecha que representa el 1 de enero del segundo año de una era no especificada. Si ejecuta el ejemplo cuando la era Reiwa es la era actual, la fecha se interpreta como el segundo año de la era Reiwa. La era, el valor de la era, <xref:System.DateTime.ToString(System.String,System.IFormatProvider)?displayProperty=nameWithType> precede al año en la cadena devuelta por el método y corresponde al 1 de enero de 2020, en el calendario gregoriano. (La era Reiwa comienza en el año 2019 del calendario gregoriano.)

[!code-csharp[A date in the current era](~/samples/snippets/standard/datetime/calendars/current-era/cs/program.cs)]
[!code-vb[A date in the current era](~/samples/snippets/standard/datetime/calendars/current-era/vb/program.vb)]

Sin embargo, si la era cambia, la intención de este código se vuelve ambigua. ¿Está destinada la fecha a representar el segundo año de la era actual, o está destinada a representar el segundo año de la era Heisei? Hay dos maneras de evitar esta ambiguedad:

- Cree una instancia del valor <xref:System.Globalization.GregorianCalendar> de fecha y hora mediante la clase predeterminada. A continuación, puede utilizar el calendario japonés o el calendario Lunisolar japonés para la representación de cadena de fechas, como se muestra en el ejemplo siguiente.

  [!code-csharp[Insantiating a Gregorian date](~/samples/snippets/standard/datetime/calendars/gregorian/cs/program.cs)]
  [!code-vb[Instantiating a Gregorian date](~/samples/snippets/standard/datetime/calendars/gregorian/vb/program.vb)]

- Llame a un método de fecha y hora que especifique explícitamente una era. Esto incluye los siguientes métodos:

  - El <xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)> método <xref:System.Globalization.JapaneseCalendar> de <xref:System.Globalization.JapaneseLunisolarCalendar> la clase o.

  - Un <xref:System.DateTime> <xref:System.DateTimeOffset> método o método de <xref:System.DateTime.Parse%2A> <xref:System.DateTime.TryParse%2A>análisis, como , <xref:System.DateTime.ParseExact%2A>, , <xref:System.DateTime.TryParseExact%2A>o , <xref:System.Globalization.DateTimeStyles> que incluye la cadena que se va a analizar y, opcionalmente, un argumento si la referencia cultural actual es japonés-japonés ("ja-JP") y el calendario de esa referencia cultural es el <xref:System.Globalization.JapaneseCalendar>archivo . La cadena que se va a analizar debe incluir la era.

  - Un <xref:System.DateTime> <xref:System.DateTimeOffset> método de análisis `provider` que incluye <xref:System.IFormatProvider>un parámetro de tipo . `provider`debe ser <xref:System.Globalization.CultureInfo> un objeto que represente la referencia cultural japonés-japonés ("ja-JP") cuyo calendario actual <xref:System.Globalization.JapaneseCalendar> sea o <xref:System.Globalization.DateTimeFormatInfo> un objeto cuya <xref:System.Globalization.DateTimeFormatInfo.Calendar> propiedad sea <xref:System.Globalization.JapaneseCalendar>. La cadena que se va a analizar debe incluir la era.

  En el ejemplo siguiente se utilizan tres de estos métodos para crear instancias de una fecha y hora en la era Meiji, que comenzó el 8 de septiembre de 1868 y terminó el 29 de julio de 1912.

  [!code-csharp[A date in a specified era](~/samples/snippets/standard/datetime/calendars/specify-era/cs/program.cs)]
  [!code-vb[A date in a specified era](~/samples/snippets/standard/datetime/calendars/specify-era/vb/program.vb)]

> [!TIP]
> Cuando trabaje con calendarios que admitan varias eras, utilice *siempre* la fecha gregoriana para crear una instancia de una fecha o especifique la era cuando cree una instancia de una fecha y hora basadas en ese calendario.

Al especificar una era <xref:System.Globalization.Calendar.ToDateTime(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32)> para el método, se proporciona el <xref:System.Globalization.Calendar.Eras> índice de la era en la propiedad del calendario. Para los calendarios cuyas eras están sujetas a cambios, sin embargo, estos índices no son valores constantes; la era actual está en el índice 0, y la era más antigua está en el índice. `Eras.Length - 1` Cuando se agrega una nueva era a un calendario, los índices de las eras anteriores aumentan en uno. Puede proporcionar el índice de era adecuado de la siguiente manera:

- Para las fechas de la era <xref:System.Globalization.Calendar.CurrentEra> actual, utilice siempre la propiedad del calendario.

- Para las fechas de una <xref:System.Globalization.DateTimeFormatInfo.GetEraName%2A?displayProperty=nameWithType> era especificada, utilice el método para recuperar el índice que corresponde a un nombre de era especificado. Esto requiere que <xref:System.Globalization.JapaneseCalendar> sea el calendario <xref:System.Globalization.CultureInfo> actual del objeto que representa la referencia cultural ja-JP.  (Esta técnica también <xref:System.Globalization.JapaneseLunisolarCalendar> funciona para el, ya que <xref:System.Globalization.JapaneseCalendar>soporta las mismas eras que el .) El ejemplo anterior ilustra este enfoque.

### <a name="calendars-eras-and-date-ranges-relaxed-range-checks"></a>Calendarios, borrar y intervalos de fechas: comprobaciones de rango relajado

Al igual que los calendarios individuales han <xref:System.Globalization.JapaneseCalendar> admitido <xref:System.Globalization.JapaneseLunisolarCalendar> intervalos de fechas, las eras en las clases y también tienen rangos admitidos. Anteriormente, .NET usaba comprobaciones de intervalo de era estrictas para asegurarse de que una fecha específica de la era estaba dentro del intervalo de esa era. Es decir, si una fecha está fuera del intervalo de la <xref:System.ArgumentOutOfRangeException>era especificada, el método produce un archivo . Actualmente, .NET usa la comprobación de intervalos relajada de forma predeterminada. Las actualizaciones de todas las versiones de .NET introdujeron comprobaciones de rango de era relajada; el intento de crear instancias de una fecha específica de la era que está fuera del intervalo de la era especificada "se desborda" en la siguiente era y no se produce ninguna excepción.

El siguiente ejemplo intenta crear una instancia de una fecha en el año 65 de la era Showa, que comenzó el 25 de diciembre de 1926 y terminó el 7 de enero de 1989. Esta fecha corresponde al 9 de enero de 1990, que está <xref:System.Globalization.JapaneseCalendar>fuera del rango de la era Showa en el . Como se ilustra en la salida del ejemplo, la fecha que muestra el ejemplo es el 9 de enero de 1990, en el segundo año de la era Heisei.

  [!code-csharp[Relaxed range checks](~/samples/snippets/standard/datetime/calendars/relaxed-range/cs/program.cs)]
  [!code-vb[Relaxed range checks](~/samples/snippets/standard/datetime/calendars/relaxed-range/vb/program.vb)]

Si las comprobaciones de rango relajado no son deseables, puede restaurar comprobaciones de rango estrictas de varias maneras, dependiendo de la versión de .NET en la que se ejecuta la aplicación:

- **.NET Core:** Agregue lo siguiente al archivo de configuración *.netcore.runtime.json:*

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.EnforceJapaneseEraYearRanges": true
    }
  }
  ```

- **.NET Framework 4.6 o posterior:** Establezca el siguiente modificador AppContext en el archivo *app.config:*

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.EnforceJapaneseEraYearRanges=true" />
    </runtime>
  </configuration>
  ```

- **.NET Framework 4.5.2 o anterior:** Establezca el siguiente valor del Registro:

   |  |  |
   |--|--|
   | **Clave** | **HKEY_LOCAL_MACHINE,Software,\\Microsoft . NETFramework-AppContext** |
   | **Nombre** | Switch.System.Globalization.EnforceJapaneseEraYearRanges |
   | **Tipo** | REG_SZ |
   | **Valor** | true |

Con las comprobaciones de rango estrictas <xref:System.ArgumentOutOfRangeException> habilitadas, el ejemplo anterior produce un y muestra el siguiente resultado:

```console
Unhandled Exception: System.ArgumentOutOfRangeException: Valid values are between 1 and 64, inclusive.
Parameter name: year
   at System.Globalization.GregorianCalendarHelper.GetYearOffset(Int32 year, Int32 era, Boolean throwOnError)
   at System.Globalization.GregorianCalendarHelper.ToDateTime(Int32 year, Int32 month, Int32 day, Int32 hour, Int32 minute, Int32 second, Int32 millisecond, Int32 era)
   at Example.Main()
```

### <a name="represent-dates-in-calendars-with-multiple-eras"></a>Representar fechas en calendarios con múltiples épocas

Si un objeto <xref:System.Globalization.Calendar> admite eras y es el calendario actual de un objeto <xref:System.Globalization.CultureInfo>, la era se incluye en la representación de cadena de un valor de fecha y hora para los modelos de fecha y hora completa, fecha larga y fecha corta. En el ejemplo siguiente se muestran estos modelos de fecha cuando la referencia cultural actual es Japonés (Japón) y el calendario actual es el calendario japonés.

[!code-csharp[Conceptual.Calendars#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings1.cs#8)]
[!code-vb[Conceptual.Calendars#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings1.vb#8)]

> [!WARNING]
> La <xref:System.Globalization.JapaneseCalendar> clase es la única clase de calendario en .NET que admite fechas <xref:System.Globalization.CultureInfo> en más de una <xref:System.Globalization.CultureInfo> era y que puede ser el calendario actual de un objeto, específicamente, de un objeto que representa la referencia cultural japonesa (Japón).

Para todos los demás calendarios, el especificador de formato personalizado "g" incluye la era en la cadena de resultado. En el ejemplo siguiente se usa la cadena de formato personalizada "MM-dd-yyyy g" para incluir la era en la cadena de resultado cuando el calendario actual es el calendario gregoriano.

[!code-csharp[Conceptual.Calendars#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings2.cs#9)]
[!code-vb[Conceptual.Calendars#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings2.vb#9)]

En aquellos casos donde la representación de cadena de una fecha se expresa en un calendario que no es el actual, la clase <xref:System.Globalization.Calendar> incluye un método <xref:System.Globalization.Calendar.GetEra%2A?displayProperty=nameWithType> que se puede usar junto con los métodos <xref:System.Globalization.Calendar.GetYear%2A?displayProperty=nameWithType>, <xref:System.Globalization.Calendar.GetMonth%2A?displayProperty=nameWithType> y <xref:System.Globalization.Calendar.GetDayOfMonth%2A?displayProperty=nameWithType> para indicar de forma inequívoca una fecha y la era a la que pertenece. En el ejemplo siguiente se usa la clase <xref:System.Globalization.JapaneseLunisolarCalendar> para proporcionar una ilustración. Sin embargo, tenga en cuenta que para incluir un nombre descriptivo o una abreviatura en lugar de un entero para la era en la cadena de resultado hay que crear una instancia de un objeto <xref:System.Globalization.DateTimeFormatInfo> y convertir <xref:System.Globalization.JapaneseCalendar> en su calendario actual. (El calendario <xref:System.Globalization.JapaneseLunisolarCalendar> no puede ser el calendario actual de ninguna referencia cultural, pero en este caso los dos calendarios comparten las mismas eras.)

[!code-csharp[Conceptual.Calendars#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings3.cs#10)]
[!code-vb[Conceptual.Calendars#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings3.vb#10)]

En los calendarios japoneses, el primer año de una época se llama Gannen. Por ejemplo, en lugar de Heisei 1, el primer año de la era Heisei se puede describir como Heisei Gannen. .NET adopta esta convención en las operaciones de formato para fechas y horas formateadas con las siguientes cadenas de formato de fecha y hora estándar o personalizadas cuando se utilizan con un <xref:System.Globalization.CultureInfo> objeto que representa la referencia cultural japonés-japonés ("ja-JP") con la <xref:System.Globalization.JapaneseCalendar> clase:

- [El patrón](../base-types/standard-date-and-time-format-strings.md#LongDate)de fecha larga, indicado por la cadena de formato de fecha y hora estándar "D".
- [El patrón](../base-types/standard-date-and-time-format-strings.md#FullDateLongTime)de larga hora de fecha completa, indicado por la cadena de formato de fecha y hora estándar "F".
- [El patrón](../base-types/standard-date-and-time-format-strings.md#FullDateShortTime)de tiempo corto de fecha completa, indicado por la cadena de formato de fecha y hora estándar "f".
- [El patrón de año/mes](../base-types/standard-date-and-time-format-strings.md#YearMonth), indicado por la cadena de formato de fecha y hora estándar Y" o "y".
- [La cadena de formato de fecha y [hora personalizada](../base-types/custom-date-and-time-format-strings.md)"ggy'' o "ggy".

Por ejemplo, en el ejemplo siguiente se muestra una fecha en <xref:System.Globalization.JapaneseCalendar>el primer año de la era Heisei en el archivo .

  [!code-csharp[gannen](~/samples/snippets/standard/datetime/calendars/gannen/cs/program.cs)]
  [!code-vb[gannen](~/samples/snippets/standard/datetime/calendars/gannen/vb/gannen-fmt.vb)]

Si este comportamiento no es deseable en las operaciones de formato, puede restaurar el comportamiento anterior, que siempre representa el primer año de una era como "1" en lugar de "Gannen", haciendo lo siguiente, dependiendo de la versión de .NET:

- **.NET Core:** Agregue lo siguiente al archivo de configuración *.netcore.runtime.json:*

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.FormatJapaneseFirstYearAsANumber": true
    }
  }
  ```

- **.NET Framework 4.6 o posterior:** Establezca el siguiente modificador AppContext en el archivo *app.config:*

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.FormatJapaneseFirstYearAsANumber=true" />
    </runtime>
  </configuration>
  ```

- **.NET Framework 4.5.2 o anterior:** Establezca el siguiente valor del Registro:

   |  |  |
   |--|--|
   | **Clave** | **HKEY_LOCAL_MACHINE,Software,\\Microsoft . NETFramework-AppContext** |
   | **Nombre** | Switch.System.Globalization.FormatJapaneseFirstYearAsANumber |
   | **Tipo** | REG_SZ |
   | **Valor** | true |

Con la compatibilidad de gannen en las operaciones de formato deshabilitada, el ejemplo anterior muestra el siguiente resultado:

```console
Japanese calendar date: 平成1年8月18日 (Gregorian: Friday, August 18, 1989)
```

.NET también se ha actualizado para que las operaciones de análisis de fecha y hora admitan cadenas que contienen el año representado como "1" o Gannen. Aunque no debería necesitar hacer esto, puede restaurar el comportamiento anterior para reconocer solo "1" como el primer año de una era. Puede hacerlo de la siguiente manera, dependiendo de la versión de .NET:

- **.NET Core:** Agregue lo siguiente al archivo de configuración *.netcore.runtime.json:*

  ```json
  "runtimeOptions": {
    "configProperties": {
        "Switch.System.Globalization.EnforceLegacyJapaneseDateParsing": true
    }
  }
  ```

- **.NET Framework 4.6 o posterior:** Establezca el siguiente modificador AppContext en el archivo *app.config:*

  ```xml
  <?xml version="1.0" encoding="utf-8"?>
  <configuration>
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.EnforceLegacyJapaneseDateParsing=true" />
    </runtime>
  </configuration>
  ```

- **.NET Framework 4.5.2 o anterior:** Establezca el siguiente valor del Registro:

   |  |  |
   |--|--|
   | **Clave** | **HKEY_LOCAL_MACHINE,Software,\\Microsoft . NETFramework-AppContext** |
   | **Nombre** | Switch.System.Globalization.EnforceLegacyJapaneseDateParsing |
   | **Tipo** | REG_SZ |
   | **Valor** | true |

## <a name="see-also"></a>Consulte también

- [Cómo: Mostrar fechas en calendarios no gregorianos](../../../docs/standard/base-types/how-to-display-dates-in-non-gregorian-calendars.md)
- [Ejemplo: Utilidad de rango de semanas del calendario](https://code.msdn.microsoft.com/NET-Framework-4-Calendar-3360a84a)
- [Clase de calendario](xref:System.Globalization.Calendar)
