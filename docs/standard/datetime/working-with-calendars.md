---
title: "Trabajar con calendarios | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "calendarios, aplicaciones globales"
  - "referencia cultural, calendarios"
  - "aplicaciones globales, calendarios"
  - "globalización [.NET Framework], calendarios"
  - "aplicaciones internacionales [.NET Framework], calendarios"
  - "aplicaciones de uso internacional, calendarios"
ms.assetid: 0c1534e5-979b-4c8a-a588-1c24301aefb3
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# Trabajar con calendarios
Aunque un valor de fecha y hora representa un momento en el tiempo, su representación de cadena tiene en cuenta la referencia cultural y depende tanto de las convenciones empleadas para mostrar los valores de fecha y hora por una referencia cultural específica como del calendario usado por esa referencia cultural.  En este tema se explora la compatibilidad con calendarios de .NET Framework y se explica el uso de clases de calendario al trabajar con valores de fecha.  
  
## Calendarios de .NET Framework  
 Todos los calendarios de .NET Framework se derivan de la clase <xref:System.Globalization.Calendar?displayProperty=fullName>, que proporciona la aplicación de calendario base.  Una de las clases que hereda de la clase <xref:System.Globalization.Calendar> es <xref:System.Globalization.EastAsianLunisolarCalendar>, que es la clase base para todos los calendarios lunisolares.  .NET Framework incluye las siguientes implementaciones de calendario:  
  
-   <xref:System.Globalization.ChineseLunisolarCalendar>, que representa el calendario lunisolar chino.  
  
-   <xref:System.Globalization.GregorianCalendar>, que representa el calendario gregoriano.  Este calendario se divide a su vez en subtipos \(como el árabe y el francés de Oriente Medio\) definidos por la enumeración <xref:System.Globalization.GregorianCalendarTypes?displayProperty=fullName>.  La propiedad <xref:System.Globalization.GregorianCalendar.CalendarType%2A?displayProperty=fullName> especifica el subtipo del calendario Gregoriano.  
  
-   <xref:System.Globalization.HebrewCalendar>, que representa el calendario hebreo.  
  
-   <xref:System.Globalization.HijriCalendar>, que representa el calendario Hijri.  
  
-   <xref:System.Globalization.JapaneseCalendar>, que representa el calendario japonés.  
  
-   <xref:System.Globalization.JapaneseLunisolarCalendar>, que representa el calendario lunisolar japonés.  
  
-   <xref:System.Globalization.JulianCalendar>, que representa el calendario juliano.  
  
-   <xref:System.Globalization.KoreanCalendar>, que representa el calendario coreano.  
  
-   <xref:System.Globalization.KoreanLunisolarCalendar>, que representa el calendario lunisolar coreano.  
  
-   <xref:System.Globalization.PersianCalendar>, que representa el calendario persa.  
  
-   <xref:System.Globalization.TaiwanCalendar>, que representa el calendario taiwanés.  
  
-   <xref:System.Globalization.TaiwanLunisolarCalendar>, que representa el calendario lunisolar taiwanés.  
  
-   <xref:System.Globalization.ThaiBuddhistCalendar>, que representa el calendario budista tailandés.  
  
-   <xref:System.Globalization.UmAlQuraCalendar>, que representa el calendario Um\-Al\-Qura.  
  
 Un calendario se puede usar de dos maneras:  
  
-   Como el calendario empleado por una referencia cultural específica.  Cada objeto <xref:System.Globalization.CultureInfo> tiene un calendario actual, que es el calendario que el objeto está usando actualmente.  Las representaciones de cadena de todos los valores de fecha y hora reflejan automáticamente la referencia cultural actual y su calendario actual.  Normalmente, el calendario actual es el calendario predeterminado de la referencia cultural.  Los objetos <xref:System.Globalization.CultureInfo> tienen también calendarios opcionales, que incluyen los calendarios adicionales que esa referencia cultural puede usar.  
  
-   Como calendario independiente de una referencia cultural concreta.  En este caso, los métodos de <xref:System.Globalization.Calendar> se emplean para expresar las fechas como valores que reflejen el calendario.  
  
 Tenga en cuenta que seis clases de calendario \(<xref:System.Globalization.ChineseLunisolarCalendar>, <xref:System.Globalization.JapaneseLunisolarCalendar>, <xref:System.Globalization.JulianCalendar>, <xref:System.Globalization.KoreanLunisolarCalendar>, <xref:System.Globalization.PersianCalendar> y <xref:System.Globalization.TaiwanLunisolarCalendar>\) solo se pueden usar como calendarios independientes.  Ninguna referencia cultural los usa como calendario predeterminado ni como calendario opcional.  
  
## Calendarios y referencias culturales  
 Cada referencia cultural tiene un calendario predeterminado, que está definido por la propiedad <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=fullName>.  La propiedad <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=fullName> devuelve una matriz de objetos <xref:System.Globalization.Calendar> que especifica todos los calendarios admitidos por una referencia cultural determinada, incluido el calendario predeterminado de esa referencia cultural.  
  
 En el ejemplo siguiente se muestra cómo usar las propiedades <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=fullName>.  Crea objetos `CultureInfo` para las referencias culturales de tailandés \(Tailandia\) y japonés \(Japón\), y muestra sus calendarios predeterminados y opcionales.  Tenga en cuenta que, en ambos casos, el calendario predeterminado de la referencia cultural también se incluye en la colección <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=fullName>.  
  
 [!code-csharp[Conceptual.Calendars#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/calendarinfo1.cs#1)]
 [!code-vb[Conceptual.Calendars#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/calendarinfo1.vb#1)]  
  
 El calendario en uso actualmente por un objeto <xref:System.Globalization.CultureInfo> determinado está definido por la propiedad <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=fullName> de la referencia cultural.  La propiedad <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=fullName> devuelve el objeto <xref:System.Globalization.DateTimeFormatInfo> de la referencia cultural.  Cuando se crea una referencia cultural, su valor predeterminado es igual que el valor de la propiedad <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=fullName>.  Sin embargo, puede cambiar el calendario actual de la referencia cultural a cualquier calendario contenido en la matriz devuelta por la propiedad <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=fullName>.  Si intenta establecer el calendario actual en un calendario que no está incluido en el valor de propiedad <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=fullName>, se produce <xref:System.ArgumentException>.  
  
 En el ejemplo siguiente se cambia el calendario usado por la referencia cultural Árabe \(Arabia Saudí\).  Primero, se crean instancias de un valor <xref:System.DateTime> y se muestra usando la referencia cultural actual que, en este caso, es inglés \(Estados Unidos\), y el calendario de la referencia cultural actual \(que en este caso es el calendario gregoriano\).  A continuación, cambia la referencia cultural actual a Árabe \(Arabia Saudí\) y muestra la fecha usando su calendario predeterminado Um\-Al\-Qura.  Después, llama al método `CalendarExists` para determinar si la referencia cultural Árabe \(Arabia Saudí\) admite el calendario Hijri.  Puesto que se admite el calendario, cambia el calendario actual a Hijri y vuelve a mostrar la fecha.  Tenga en cuenta que en cada caso la fecha se muestra usando el calendario actual de la referencia cultural actual.  
  
 [!code-csharp[Conceptual.Calendars#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/changecalendar2.cs#2)]
 [!code-vb[Conceptual.Calendars#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/changecalendar2.vb#2)]  
  
## Fechas y calendarios  
 Salvo los constructores que incluyen un parámetro de tipo <xref:System.Globalization.Calendar> y permiten que los elementos de una fecha \(es decir, el mes, el día y el año\) reflejen los valores de un calendario designado, los valores <xref:System.DateTime> y <xref:System.DateTimeOffset> siempre se basan en el calendario gregoriano.  Esto significa, por ejemplo, que la propiedad <xref:System.DateTime.Year%2A?displayProperty=fullName> devuelve el año en el calendario gregoriano y la propiedad <xref:System.DateTime.Day%2A?displayProperty=fullName> devuelve el día del mes en el calendario gregoriano.  
  
> [!IMPORTANT]
>  Es importante recordar que existe una diferencia entre un valor de fecha y su representación de cadena.  El primero se basa en el calendario gregoriano, mientras que la última se basa en el calendario actual de una referencia cultural concreta.  
  
 En el ejemplo siguiente se muestra esta diferencia entre las propiedades de <xref:System.DateTime> y sus métodos <xref:System.Globalization.Calendar> correspondientes.  En el ejemplo, la referencia cultural actual es Árabe \(Egipto\) y el calendario actual es Um\-Al\-Qura.  Un valor <xref:System.DateTime> se establece en el decimoquinto día del séptimo mes de 2011.  Está claro que esto se interpreta como una fecha gregoriana, ya que el método <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=fullName> devuelve estos mismos valores cuando se usan las convenciones de la referencia cultural para todos los idiomas.  La representación de cadena de la fecha a la que se aplica formato con las convenciones de la referencia cultural actual es 14\/08\/32, que es la fecha equivalente en el calendario Um\-Al\-Qura.  Después, se usan miembros de `DateTime` y `Calendar` para devolver el día, el mes y el año del valor <xref:System.DateTime>.  En cada caso, los valores devueltos por los miembros de <xref:System.DateTime> reflejan los valores en el calendario gregoriano, mientras que los valores devueltos por los miembros de <xref:System.Globalization.UmAlQuraCalendar> reflejan los valores en el calendario Uum\-al\-Qura.  
  
 [!code-csharp[Conceptual.Calendars#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/datesandcalendars2.cs#3)]
 [!code-vb[Conceptual.Calendars#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/datesandcalendars2.vb#3)]  
  
### Crear instancias de fechas basadas en un calendario  
 Puesto que los valores <xref:System.DateTime> y <xref:System.DateTimeOffset> se basan en el calendario gregoriano, debe llamar a un constructor sobrecargado que incluya un parámetro de tipo <xref:System.Globalization.Calendar> para crear instancias de un valor de fecha si desea usar los valores de día, mes o año de otro calendario.  También puede llamar a una de las sobrecargas del método <xref:System.Globalization.Calendar.ToDateTime%2A?displayProperty=fullName> de un calendario específico para crear instancias de un objeto <xref:System.DateTime> basándose en los valores de un calendario determinado.  
  
 En el ejemplo siguiente se crean instancias de un valor <xref:System.DateTime> pasando un objeto <xref:System.Globalization.HebrewCalendar> a un constructor <xref:System.DateTime> y se crean instancias de un segundo valor <xref:System.DateTime> llamando al método <xref:System.Globalization.HebrewCalendar.ToDateTime%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>.  Como los dos valores se crean con valores idénticos del calendario hebreo, la llamada al método <xref:System.DateTime.Equals%2A?displayProperty=fullName> muestra que los dos valores <xref:System.DateTime> son iguales.  
  
 [!code-csharp[Conceptual.Calendars#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatehcdate1.cs#4)]
 [!code-vb[Conceptual.Calendars#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatehcdate1.vb#4)]  
  
### Representar fechas en el calendario actual  
 Los métodos de formato de fecha y hora siempre usan el calendario actual al convertir fechas en cadenas.  Esto significa que la representación de cadena del año, el mes y el día del mes refleja el calendario actual, y no refleja necesariamente el calendario gregoriano.  
  
 En el ejemplo siguiente se muestra cómo afecta el calendario actual a la representación de cadena de una fecha.  Cambia la referencia cultural actual a Chino \(tradicional, Taiwán\) y crea instancias de un valor de fecha.  Después muestra el calendario actual y la fecha, cambia el calendario actual a <xref:System.Globalization.TaiwanCalendar> y vuelve a mostrar la fecha y el calendario actual.  La primera vez que se muestra la fecha, se representa como una fecha del calendario gregoriano.  La segunda vez que se muestra, se representa como una fecha del calendario taiwanés.  
  
 [!code-csharp[Conceptual.Calendars#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/currentcalendar1.cs#5)]
 [!code-vb[Conceptual.Calendars#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/currentcalendar1.vb#5)]  
  
### Representar fechas en un calendario que no es el actual  
 Para representar una fecha mediante un calendario que no es el calendario actual de una referencia cultural determinada, debe llamar a métodos de ese objeto <xref:System.Globalization.Calendar>.  Por ejemplo, los métodos <xref:System.Globalization.Calendar.GetYear%2A?displayProperty=fullName>, <xref:System.Globalization.Calendar.GetMonth%2A?displayProperty=fullName> y <xref:System.Globalization.Calendar.GetDayOfMonth%2A?displayProperty=fullName> convierten el año, el mes y el día a los valores que reflejan un calendario determinado.  
  
> [!WARNING]
>  Puesto que algunos calendarios no son calendarios opcionales de ninguna referencia cultural, para representar fechas en estos calendarios siempre es necesario llamar a métodos de calendario.  Esto es cierto para todos los calendarios que se derivan de las clases <xref:System.Globalization.EastAsianLunisolarCalendar>, <xref:System.Globalization.JulianCalendar> y <xref:System.Globalization.PersianCalendar>.  
  
 En el ejemplo siguiente se usa un objeto <xref:System.Globalization.JulianCalendar> para crear instancias de una fecha, el 9 de enero de 1905, en el calendario juliano.  Cuando esta fecha se muestra usando el calendario predeterminado \(gregoriano\), se representa como el 22 de enero de 1905.  Las llamadas a métodos individuales de <xref:System.Globalization.JulianCalendar> permiten representar la fecha en el calendario juliano.  
  
 [!code-csharp[Conceptual.Calendars#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/noncurrentcalendar1.cs#6)]
 [!code-vb[Conceptual.Calendars#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/noncurrentcalendar1.vb#6)]  
  
### Calendarios e intervalos de fechas  
 La fecha más temprana admitida por un calendario se indica mediante la propiedad <xref:System.Globalization.Calendar.MinSupportedDateTime%2A?displayProperty=fullName> de dicho calendario.  Para la clase <xref:System.Globalization.GregorianCalendar>, esa fecha es el 1 de enero del año 1 de la era cristiana. La mayoría del resto de calendarios de .NET Framework admiten una fecha posterior.  Al intentar trabajar con un valor de fecha y hora anterior a la fecha compatible más temprana de un calendario, se produce una excepción <xref:System.ArgumentOutOfRangeException>.  
  
 Sin embargo, hay una excepción importante.  El valor \(sin inicializar\) predeterminado de un objeto <xref:System.DateTime> y un objeto <xref:System.DateTimeOffset> es igual al valor <xref:System.Globalization.GregorianCalendar.MinSupportedDateTime%2A?displayProperty=fullName>.  Si se intenta dar formato a esta fecha en un calendario que no admite el 1 de enero del año 1 de la era cristiana y no se proporciona un especificador de formato, el método de formato usa el especificador de formato "s" \(patrón de fecha y hora que se puede ordenar\) en lugar del especificador de formato "G" \(patrón de fecha y hora general\).  Como resultado, la operación de formato no produce una excepción <xref:System.ArgumentOutOfRangeException>.  En su lugar, devuelve la fecha no compatible.  Esto se ilustra en el ejemplo siguiente, que muestra el valor de <xref:System.DateTime.MinValue?displayProperty=fullName> cuando la referencia cultural actual se establece en japonés \(Japón\) con el calendario japonés y en árabe \(Egipto\) con el calendario Um\-Al\-Qura.  También establece la referencia cultural actual en inglés \(Estados Unidos\) y llama al método <xref:System.DateTime.ToString%28System.IFormatProvider%29?displayProperty=fullName> con cada uno de estos objetos <xref:System.Globalization.CultureInfo>.  En cada caso, la fecha se muestra mediante el patrón de fecha y hora que se puede ordenar.  
  
 [!code-csharp[Conceptual.Calendars#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/minsupporteddatetime1.cs#11)]
 [!code-vb[Conceptual.Calendars#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/minsupporteddatetime1.vb#11)]  
  
## Trabajar con eras  
 Los calendarios suelen dividir las fechas en eras.  Sin embargo, las clases <xref:System.Globalization.Calendar> de .NET Framework no admiten todas las eras definidas por un calendario y la mayoría de las clases de <xref:System.Globalization.Calendar> solo admiten una era.  Únicamente las clases <xref:System.Globalization.JapaneseCalendar> y <xref:System.Globalization.JapaneseLunisolarCalendar> admiten varias eras.  
  
### Eras y nombres de era  
 En .NET Framework, los enteros que representa las eras admitidas por una implementación de calendario determinada se almacenan en orden inverso en la matriz de <xref:System.Globalization.Calendar.Eras%2A?displayProperty=fullName>.  La era actual está en el índice cero y para las clases <xref:System.Globalization.Calendar> que admiten varias eras, cada índice sucesivo refleja la era anterior.  La propiedad estática <xref:System.Globalization.Calendar.CurrentEra?displayProperty=fullName> define el índice de la era actual en la matriz de <xref:System.Globalization.Calendar.Eras%2A?displayProperty=fullName>; es una constante cuyo valor es siempre cero.  Las clases individuales de <xref:System.Globalization.Calendar> también incluyen campos estáticos que devuelven el valor de la era actual.  Se muestran en la tabla siguiente.  
  
|Clase de calendario|Campo de era actual|  
|-------------------------|-------------------------|  
|<xref:System.Globalization.ChineseLunisolarCalendar>|<xref:System.Globalization.ChineseLunisolarCalendar.ChineseEra>|  
|<xref:System.Globalization.GregorianCalendar>|<xref:System.Globalization.GregorianCalendar.ADEra>|  
|<xref:System.Globalization.HebrewCalendar>|<xref:System.Globalization.HebrewCalendar.HebrewEra>|  
|<xref:System.Globalization.HijriCalendar>|<xref:System.Globalization.HijriCalendar.HijriEra>|  
|<xref:System.Globalization.JapaneseLunisolarCalendar>|<xref:System.Globalization.JapaneseLunisolarCalendar.JapaneseEra>|  
|<xref:System.Globalization.JulianCalendar>|<xref:System.Globalization.JulianCalendar.JulianEra>|  
|<xref:System.Globalization.KoreanCalendar>|<xref:System.Globalization.KoreanCalendar.KoreanEra>|  
|<xref:System.Globalization.KoreanLunisolarCalendar>|<xref:System.Globalization.KoreanLunisolarCalendar.GregorianEra>|  
|<xref:System.Globalization.PersianCalendar>|<xref:System.Globalization.PersianCalendar.PersianEra>|  
|<xref:System.Globalization.ThaiBuddhistCalendar>|<xref:System.Globalization.ThaiBuddhistCalendar.ThaiBuddhistEra>|  
|<xref:System.Globalization.UmAlQuraCalendar>|<xref:System.Globalization.UmAlQuraCalendar.UmAlQuraEra>|  
  
 El nombre correspondiente a un número de era determinado se puede recuperar pasando el número de era al método <xref:System.Globalization.DateTimeFormatInfo.GetEraName%2A?displayProperty=fullName> o <xref:System.Globalization.DateTimeFormatInfo.GetAbbreviatedEraName%2A?displayProperty=fullName>.  En el ejemplo siguiente se llama a estos métodos para recuperar información sobre la compatibilidad de eras de la clase <xref:System.Globalization.GregorianCalendar>.  
  
 [!code-csharp[Conceptual.Calendars#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatewithera1.cs#7)]
 [!code-vb[Conceptual.Calendars#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatewithera1.vb#7)]  
  
 Además, la cadena de formato de fecha y hora personalizado "g" incluye el nombre de era de un calendario en la representación de cadena de una fecha y hora.  Para obtener más información, vea [Cadenas con formato de fecha y hora personalizado](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).  
  
### Crear instancias de una fecha con una era  
 Para las dos clases de <xref:System.Globalization.Calendar> que admiten varias eras, una fecha que consta de un valor determinado de año, mes y día del mes puede ser ambigua. Por ejemplo, las cuatro eras de <xref:System.Globalization.JapaneseCalendar> tienen los años numerados entre 1 y 15.  Normalmente, si no se especifica ninguna era, los métodos de fecha y hora y de calendario suponen que los valores pertenecen a la era actual.  Para especificar explícitamente la era al crear una instancia de una fecha para una clase <xref:System.Globalization.Calendar> que admite varias eras, se puede llamar al método <xref:System.Globalization.Calendar.ToDateTime%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>.  Este método le permite especificar explícitamente una era junto con el año del calendario, mes, día, hora, minuto, segundo y milisegundo.  
  
 En el ejemplo siguiente se usa el método <xref:System.Globalization.Calendar.ToDateTime%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName> para crear instancias de la misma fecha, el primer mes del primer día del segundo año, en cada era admitida por la clase <xref:System.Globalization.JapaneseCalendar>.  Después, se muestra la fecha en los calendarios gregoriano y japonés.  También se llama a un constructor de <xref:System.DateTime> para mostrar que los métodos que crean valores de fecha sin especificar una era crean fechas de la era actual.  
  
 [!code-csharp[Conceptual.Calendars#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/instantiatewithera1.cs#7)]
 [!code-vb[Conceptual.Calendars#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/instantiatewithera1.vb#7)]  
  
### Representar fechas en calendarios con eras  
 Si un objeto <xref:System.Globalization.Calendar> admite eras y es el calendario actual de un objeto <xref:System.Globalization.CultureInfo>, la era se incluye en la representación de cadena de un valor de fecha y hora para los modelos de fecha y hora completa, fecha larga y fecha corta.  En el ejemplo siguiente se muestran estos modelos de fecha cuando la referencia cultural actual es Japonés \(Japón\) y el calendario actual es el calendario japonés.  
  
 [!code-csharp[Conceptual.Calendars#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings1.cs#8)]
 [!code-vb[Conceptual.Calendars#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings1.vb#8)]  
  
> [!WARNING]
>  La clase <xref:System.Globalization.JapaneseCalendar> es la única clase de calendario de .NET Framework que admite fechas en más de una era y que puede ser el calendario actual de un objeto <xref:System.Globalization.CultureInfo>; en concreto, de un objeto <xref:System.Globalization.CultureInfo> que represente la referencia cultural Japonés \(Japón\).  
  
 Para todos los demás calendarios, el especificador de formato personalizado "g" incluye la era en la cadena de resultado.  En el ejemplo siguiente se usa la cadena de formato personalizada "MM\-dd\-yyyy g" para incluir la era en la cadena de resultado cuando el calendario actual es el calendario gregoriano.  
  
 [!code-csharp[Conceptual.Calendars#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings2.cs#9)]
 [!code-vb[Conceptual.Calendars#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings2.vb#9)]  
  
 En aquellos casos donde la representación de cadena de una fecha se expresa en un calendario que no es el actual, la clase <xref:System.Globalization.Calendar> incluye un método <xref:System.Globalization.Calendar.GetEra%2A?displayProperty=fullName> que se puede usar junto con los métodos <xref:System.Globalization.Calendar.GetYear%2A?displayProperty=fullName>, <xref:System.Globalization.Calendar.GetMonth%2A?displayProperty=fullName> y <xref:System.Globalization.Calendar.GetDayOfMonth%2A?displayProperty=fullName> para indicar de forma inequívoca una fecha y la era a la que pertenece.  En el ejemplo siguiente se usa la clase <xref:System.Globalization.JapaneseLunisolarCalendar> para proporcionar una ilustración.  Sin embargo, tenga en cuenta que para incluir un nombre descriptivo o una abreviatura en lugar de un entero para la era en la cadena de resultado hay que crear una instancia de un objeto <xref:System.Globalization.DateTimeFormatInfo> y convertir <xref:System.Globalization.JapaneseCalendar> en su calendario actual. \(El calendario <xref:System.Globalization.JapaneseLunisolarCalendar> no puede ser el calendario actual de ninguna referencia cultural, pero en este caso los dos calendarios comparten las mismas eras.\)  
  
 [!code-csharp[Conceptual.Calendars#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.calendars/cs/formatstrings3.cs#10)]
 [!code-vb[Conceptual.Calendars#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.calendars/vb/formatstrings3.vb#10)]  
  
## Vea también  
 [Cómo: Mostrar fechas en calendarios no gregorianos](../../../docs/standard/base-types/how-to-display-dates-in-non-gregorian-calendars.md)   
 [Ejemplo: Utilidad de intervalo de semanas del calendario](http://code.msdn.microsoft.com/NET-Framework-4-Calendar-3360a84a)