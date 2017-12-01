---
title: "Cómo: Mostrar fechas en calendarios no gregorianos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [.NET Framework], dates
- dates [.NET Framework], formatting
- calendars [.NET Framework], displaying dates
- displaying date and time data
ms.assetid: ed324eff-4aff-4a76-b6c0-04e6c0d8f5a9
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a79860091e549dcf4eaa7090947f9506eceb6119
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-display-dates-in-non-gregorian-calendars"></a>Cómo: Mostrar fechas en calendarios no gregorianos
El <xref:System.DateTime> y <xref:System.DateTimeOffset> tipos utilizan el calendario gregoriano como su calendario predeterminado. Esto significa que al llamar al método `ToString` de un valor de fecha y hora se muestra la representación de cadena de esa fecha y hora en el calendario gregoriano, aunque se creara con otro calendario. Esto se muestra en el ejemplo siguiente, que se muestran dos maneras diferentes para crear un valor de fecha y hora con el calendario persa, pero muestra los valores de fecha y hora en el calendario gregoriano cuando llama a la <xref:System.DateTime.ToString%2A> método. En este ejemplo se reflejan dos técnicas usadas habitualmente, aunque incorrectas, para mostrar la fecha en un calendario determinado.  
  
 [!code-csharp[Formatting.HowTo.Calendar#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#1)]
 [!code-vb[Formatting.HowTo.Calendar#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#1)]  
  
 Se pueden usar dos técnicas distintas para mostrar la fecha en un calendario determinado. La primera exige que el calendario sea el predeterminado de una referencia cultural determinada. La segunda se puede usar con cualquier calendario.  
  
### <a name="to-display-the-date-for-a-cultures-default-calendar"></a>Para mostrar la fecha del calendario predeterminado de una referencia cultural  
  
1.  Crear una instancia de un objeto de calendario derivado de la <xref:System.Globalization.Calendar> clase que representa el calendario que se utilizará.  
  
2.  Crear una instancia de un <xref:System.Globalization.CultureInfo> objeto que representa la referencia cultural cuyo formato se usará para mostrar la fecha.  
  
3.  Llame a la <xref:System.Array.Exists%2A?displayProperty=nameWithType> método para determinar si el objeto de calendario es un miembro de la matriz devuelta por la <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType> propiedad. Esto indica que el calendario puede actuar como el calendario predeterminado para la <xref:System.Globalization.CultureInfo> objeto. Si no es miembro de la matriz, siga las instrucciones de la sección "Para mostrar la fecha en cualquier calendario".  
  
4.  Asigne el objeto de calendario a la <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A> propiedad de la <xref:System.Globalization.DateTimeFormatInfo> objeto devuelto por la <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> propiedad.  
  
    > [!NOTE]
    >  El <xref:System.Globalization.CultureInfo> clase también tiene un <xref:System.Globalization.CultureInfo.Calendar%2A> propiedad. Sin embargo, es de solo lectura y constante; no se cambia para reflejar el nuevo calendario predeterminado asignado a la <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType> propiedad.  
  
5.  Llamar a la <xref:System.DateTime.ToString%2A> o <xref:System.DateTime.ToString%2A> método y pasarle el <xref:System.Globalization.CultureInfo> objeto cuyo calendario predeterminado se modificó en el paso anterior.  
  
### <a name="to-display-the-date-in-any-calendar"></a>Para mostrar la fecha en cualquier calendario  
  
1.  Crear una instancia de un objeto de calendario derivado de la <xref:System.Globalization.Calendar> clase que representa el calendario que se utilizará.  
  
2.  Determine qué elementos de fecha y hora deben aparecer en la representación de cadena del valor de fecha y hora.  
  
3.  Para cada elemento de fecha y hora en que desea mostrar, llaman al objeto de calendario `Get`... . Están disponibles los siguientes métodos:  
  
    -   <xref:System.Globalization.Calendar.GetYear%2A>, para mostrar el año en el calendario adecuado.  
  
    -   <xref:System.Globalization.Calendar.GetMonth%2A>, para mostrar el mes en el calendario adecuado.  
  
    -   <xref:System.Globalization.Calendar.GetDayOfMonth%2A>, para mostrar el número del día del mes en el calendario adecuado.  
  
    -   <xref:System.Globalization.Calendar.GetHour%2A>, para mostrar la hora del día en el calendario adecuado.  
  
    -   <xref:System.Globalization.Calendar.GetMinute%2A>, para mostrar los minutos de la hora en el calendario adecuado.  
  
    -   <xref:System.Globalization.Calendar.GetSecond%2A>, para mostrar los segundos en el minuto en el calendario adecuado.  
  
    -   <xref:System.Globalization.Calendar.GetMilliseconds%2A>, para mostrar las milésimas de segundo en el segundo en el calendario adecuado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo se muestra una fecha con dos calendarios diferentes. Se muestra la fecha después de definir el calendario Hijri como calendario predeterminado de la referencia cultural ar-JO y se muestra la fecha con el calendario persa, que no se admite como calendario opcional de la referencia cultural fa-IR.  
  
 [!code-csharp[Formatting.HowTo.Calendar#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#2)]
 [!code-vb[Formatting.HowTo.Calendar#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#2)]  
  
 Cada <xref:System.Globalization.CultureInfo> objeto puede admitir uno o más calendarios, que se indican mediante el <xref:System.Globalization.CultureInfo.OptionalCalendars%2A> propiedad. Uno de ellos se designa como calendario predeterminado de la referencia cultural y se devuelve en solo lectura <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType> propiedad. Otro de los calendarios opcionales puede designarse como el valor predeterminado asignando un <xref:System.Globalization.Calendar> objeto que represente ese calendario a la <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType> propiedad devuelta por la <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> propiedad. Sin embargo, algunos calendarios, como el calendario persa representado por la <xref:System.Globalization.PersianCalendar> clase, no actúan como calendarios opcionales para cualquier referencia cultural.  
  
 En el ejemplo se define una clase de utilidad de calendario reutilizable, `CalendarUtility`, para controlar muchos de los detalles de generación de la representación de cadena de una fecha mediante un calendario determinado. La clase `CalendarUtility` tiene los siguientes miembros:  
  
-   Un constructor parametrizado cuyo único parámetro es un <xref:System.Globalization.Calendar> objeto en el que se puede representar una fecha. Se asigna a un campo privado de la clase.  
  
-   `CalendarExists`, un método privado que devuelve un valor booleano que indica si el calendario representado por el `CalendarUtility` objeto es compatible con la <xref:System.Globalization.CultureInfo> objeto que se pasa al método como parámetro. El método contiene una llamada a la <xref:System.Array.Exists%2A?displayProperty=nameWithType> método, al que pasa el <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType> matriz.  
  
-   `HasSameName`, un método privado asignado a la <xref:System.Predicate%601> delegado que se pasa como un parámetro a la <xref:System.Array.Exists%2A?displayProperty=nameWithType> método. Cada miembro de la matriz se pasa al método hasta que este devuelve `true`. El método determina si el nombre de un calendario opcional es igual que el calendario representado por el objeto `CalendarUtility`.  
  
-   `DisplayDate`, un método público sobrecargado que se pasa dos parámetros: ya sea un <xref:System.DateTime> o <xref:System.DateTimeOffset> valor para expresar en el calendario representado por la `CalendarUtility` objeto y la referencia cultural cuyas reglas de formato que se van a utilizar. Su comportamiento a la hora de devolver la representación de cadena de una fecha depende de si la referencia cultural cuyas reglas de formato se van a usar admite el calendario de destino.  
  
 Sin tener en cuenta el calendario utilizado para crear un <xref:System.DateTime> o <xref:System.DateTimeOffset> valor en este ejemplo, que el valor se expresa normalmente como una fecha del calendario gregoriano. Esto es porque el <xref:System.DateTime> y <xref:System.DateTimeOffset> tipos no conservan ninguna información del calendario. Internamente, se representan como el número de tics transcurridos desde la medianoche del 1 de enero de 0001. La interpretación de ese número depende del calendario. En la mayoría de las referencias culturales, el calendario predeterminado es el gregoriano.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Este ejemplo requiere una referencia a System.Core.dll.  
  
 Compile el código de la línea de comandos mediante csc.exe o vb.exe. Para compilar el código de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], póngalo en una plantilla de proyecto de aplicación de consola.  
  
## <a name="see-also"></a>Vea también  
 [Efectuar operaciones de formato](../../../docs/standard/base-types/performing-formatting-operations.md)
