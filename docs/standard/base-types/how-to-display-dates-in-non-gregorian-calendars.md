---
title: Procedimiento para mostrar fechas en calendarios no gregorianos
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [.NET Framework], dates
- dates [.NET Framework], formatting
- calendars [.NET Framework], displaying dates
- displaying date and time data
ms.assetid: ed324eff-4aff-4a76-b6c0-04e6c0d8f5a9
ms.openlocfilehash: 8d02b74f63ec5b6260679ae4cea04791681ec238
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523926"
---
# <a name="how-to-display-dates-in-non-gregorian-calendars"></a>Procedimiento para mostrar fechas en calendarios no gregorianos
Los tipos <xref:System.DateTime> y <xref:System.DateTimeOffset> usan el calendario gregoriano como calendario predeterminado. Esto significa que al llamar al método `ToString` de un valor de fecha y hora se muestra la representación de cadena de esa fecha y hora en el calendario gregoriano, aunque se creara con otro calendario. Esto se muestra en el ejemplo siguiente, que usa dos maneras diferentes de crear un valor de fecha y hora con el calendario persa, pero muestra esos valores de fecha y hora en el calendario gregoriano cuando llama al método <xref:System.DateTime.ToString%2A>. En este ejemplo se reflejan dos técnicas usadas habitualmente, aunque incorrectas, para mostrar la fecha en un calendario determinado.  
  
 [!code-csharp[Formatting.HowTo.Calendar#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#1)]
 [!code-vb[Formatting.HowTo.Calendar#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#1)]  
  
 Se pueden usar dos técnicas distintas para mostrar la fecha en un calendario determinado. La primera exige que el calendario sea el predeterminado de una referencia cultural determinada. La segunda se puede usar con cualquier calendario.  
  
### <a name="to-display-the-date-for-a-cultures-default-calendar"></a>Para mostrar la fecha del calendario predeterminado de una referencia cultural  
  
1. Cree una instancia de un objeto de calendario derivado de la clase <xref:System.Globalization.Calendar> que representa al calendario que se va a usar.  
  
2. Cree una instancia de un objeto <xref:System.Globalization.CultureInfo> que representa la referencia cultural cuyo formato se va a usar para mostrar la fecha.  
  
3. Llame al método <xref:System.Array.Exists%2A?displayProperty=nameWithType> para determinar si el objeto de calendario es miembro de la matriz devuelta por la propiedad <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>. Esto indica que el calendario puede actuar como calendario predeterminado del objeto <xref:System.Globalization.CultureInfo>. Si no es miembro de la matriz, siga las instrucciones de la sección "Para mostrar la fecha en cualquier calendario".  
  
4. Asigne el objeto de calendario a la propiedad <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A> del objeto <xref:System.Globalization.DateTimeFormatInfo> devuelto por la propiedad <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>.  
  
    > [!NOTE]
    > La clase <xref:System.Globalization.CultureInfo> también tiene una propiedad <xref:System.Globalization.CultureInfo.Calendar%2A>. Pero es de solo lectura y constante; no cambia para reflejar el nuevo calendario predeterminado asignado a la propiedad <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType>.  
  
5. Llame al método <xref:System.DateTime.ToString%2A> o <xref:System.DateTime.ToString%2A> y pásele el objeto <xref:System.Globalization.CultureInfo> cuyo calendario predeterminado se modificó en el paso anterior.  
  
### <a name="to-display-the-date-in-any-calendar"></a>Para mostrar la fecha en cualquier calendario  
  
1. Cree una instancia de un objeto de calendario derivado de la clase <xref:System.Globalization.Calendar> que representa al calendario que se va a usar.  
  
2. Determine qué elementos de fecha y hora deben aparecer en la representación de cadena del valor de fecha y hora.  
  
3. Para cada elemento de fecha y hora que quiera mostrar, llame al método `Get` del objeto de calendario... . Están disponibles los siguientes métodos:  
  
    - <xref:System.Globalization.Calendar.GetYear%2A>, para mostrar el año en el calendario adecuado.  
  
    - <xref:System.Globalization.Calendar.GetMonth%2A>, para mostrar el mes en el calendario adecuado.  
  
    - <xref:System.Globalization.Calendar.GetDayOfMonth%2A>, para mostrar el número del día del mes en el calendario adecuado.  
  
    - <xref:System.Globalization.Calendar.GetHour%2A>, para mostrar la hora del día en el calendario adecuado.  
  
    - <xref:System.Globalization.Calendar.GetMinute%2A>, para mostrar los minutos de la hora en el calendario adecuado.  
  
    - <xref:System.Globalization.Calendar.GetSecond%2A>, para mostrar los segundos del minuto en el calendario adecuado.  
  
    - <xref:System.Globalization.Calendar.GetMilliseconds%2A>, para mostrar los milisegundos del segundo en el calendario adecuado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo se muestra una fecha con dos calendarios diferentes. Se muestra la fecha después de definir el calendario Hijri como calendario predeterminado de la referencia cultural ar-JO y se muestra la fecha con el calendario persa, que no se admite como calendario opcional de la referencia cultural fa-IR.  
  
 [!code-csharp[Formatting.HowTo.Calendar#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#2)]
 [!code-vb[Formatting.HowTo.Calendar#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#2)]  
  
 Cada objeto <xref:System.Globalization.CultureInfo> puede admitir uno o varios calendarios, que se indican mediante la propiedad <xref:System.Globalization.CultureInfo.OptionalCalendars%2A>. Uno de ellos se designa como calendario predeterminado de la referencia cultural y es devuelto por la propiedad de solo lectura <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType>. Otro de los calendarios opcionales se puede designar como valor predeterminado si se asigna un objeto <xref:System.Globalization.Calendar> que represente ese calendario a la propiedad <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType> devuelta por la propiedad <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>. Pero algunos calendarios, como el persa representado por la clase <xref:System.Globalization.PersianCalendar>, no actúan como calendarios opcionales de ninguna referencia cultural.  
  
 En el ejemplo se define una clase de utilidad de calendario reutilizable, `CalendarUtility`, para controlar muchos de los detalles de generación de la representación de cadena de una fecha mediante un calendario determinado. La clase `CalendarUtility` tiene los siguientes miembros:  
  
- Un constructor parametrizado cuyo único parámetro es un objeto <xref:System.Globalization.Calendar> en el que se va a representar una fecha. Se asigna a un campo privado de la clase.  
  
- `CalendarExists`, un método privado que devuelve un valor booleano que indica si el calendario representado por el objeto `CalendarUtility` es compatible con el objeto <xref:System.Globalization.CultureInfo> pasado al método como parámetro. El método encapsula una llamada al método <xref:System.Array.Exists%2A?displayProperty=nameWithType>, al que pasa la matriz <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>.  
  
- `HasSameName`, un método privado asignado al delegado <xref:System.Predicate%601> que se pasa como parámetro al método <xref:System.Array.Exists%2A?displayProperty=nameWithType>. Cada miembro de la matriz se pasa al método hasta que este devuelve `true`. El método determina si el nombre de un calendario opcional es igual que el calendario representado por el objeto `CalendarUtility`.  
  
- `DisplayDate`, un método público sobrecargado al que se pasan dos parámetros: un valor <xref:System.DateTime> o <xref:System.DateTimeOffset> para expresar en el calendario representado por el objeto `CalendarUtility`; y la referencia cultural cuyas reglas de formato se van a usar. Su comportamiento a la hora de devolver la representación de cadena de una fecha depende de si la referencia cultural cuyas reglas de formato se van a usar admite el calendario de destino.  
  
 Independientemente del calendario usado para crear un valor <xref:System.DateTime> o <xref:System.DateTimeOffset> en este ejemplo, ese valor normalmente se expresa como una fecha gregoriana. Esto se debe a que los tipos <xref:System.DateTime> y <xref:System.DateTimeOffset> no conservan ninguna información del calendario. Internamente, se representan como el número de tics transcurridos desde la medianoche del 1 de enero de 0001. La interpretación de ese número depende del calendario. En la mayoría de las referencias culturales, el calendario predeterminado es el gregoriano.
