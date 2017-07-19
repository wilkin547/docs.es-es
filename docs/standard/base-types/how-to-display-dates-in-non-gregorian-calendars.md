---
title: "C&#243;mo: Mostrar fechas en calendarios no gregorianos | Microsoft Docs"
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
  - "formato [.NET Framework], fechas"
  - "fechas [.NET Framework], formato"
  - "calendarios [.NET Framework], mostrar fechas"
  - "mostrar datos de fecha y hora"
ms.assetid: ed324eff-4aff-4a76-b6c0-04e6c0d8f5a9
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Mostrar fechas en calendarios no gregorianos
Los tipos <xref:System.DateTime> y <xref:System.DateTimeOffset> utilizan el calendario gregoriano como calendario predeterminado.  Esto significa que al llamar al método `ToString` del valor de fecha y hora, se muestra la representación de cadena de esa fecha y hora en el calendario gregoriano, aunque esa fecha y hora se crearan con otro calendario.  Esto se ilustra en el ejemplo siguiente, en el que se utilizan dos maneras diferentes de crear un valor de fecha y hora con el calendario persa, aunque se siguen mostrando esos valores de fecha y hora en el calendario gregoriano cuando se llama al método <xref:System.DateTime.ToString%2A>.  En este ejemplo se reflejan dos técnicas que se utilizan habitualmente, aunque son incorrectas, para mostrar la fecha en un calendario determinado.  
  
 [!code-csharp[Formatting.HowTo.Calendar#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#1)]
 [!code-vb[Formatting.HowTo.Calendar#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#1)]  
  
 Se pueden utilizar dos técnicas distintas para mostrar la fecha en un calendario determinado.  La primera requiere que el calendario sea el calendario predeterminado de una determinada referencia cultural.  La segunda se puede utilizar con cualquier calendario.  
  
### Para mostrar la fecha en el calendario predeterminado de una referencia cultural  
  
1.  Cree instancias de un objeto de calendario derivado de la clase <xref:System.Globalization.Calendar> que representa el calendario que se va a utilizar.  
  
2.  Cree instancias de un objeto <xref:System.Globalization.CultureInfo> que represente la referencia cultural cuyo formato se utilizará para mostrar la fecha.  
  
3.  Llame al método <xref:System.Array.Exists%2A?displayProperty=fullName> para determinar si el objeto de calendario es un miembro de la matriz devuelta por la propiedad <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=fullName>.  Esto indica que el calendario puede actuar como calendario predeterminado del objeto <xref:System.Globalization.CultureInfo>.  Si no es miembro de la matriz, siga las instrucciones que aparecen en la sección "Para mostrar la fecha en cualquier calendario".  
  
4.  Asigne el objeto de calendario a la propiedad <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A> del objeto <xref:System.Globalization.DateTimeFormatInfo> devuelto por la propiedad <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=fullName>.  
  
    > [!NOTE]
    >  La clase <xref:System.Globalization.CultureInfo> tiene también una propiedad <xref:System.Globalization.CultureInfo.Calendar%2A>.  Sin embargo, es una propiedad de sólo lectura y constante, no cambia para reflejar el nuevo calendario predeterminado asignado a la propiedad <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=fullName>.  
  
5.  Llame al método <xref:System.DateTime.ToString%2A> o <xref:System.DateTime.ToString%2A> y pásele el objeto <xref:System.Globalization.CultureInfo> cuyo calendario predeterminado se modificó en el paso anterior.  
  
### Para mostrar la fecha en cualquier calendario  
  
1.  Cree instancias de un objeto de calendario derivado de la clase <xref:System.Globalization.Calendar> que representa el calendario que se va a utilizar.  
  
2.  Determine qué elementos de fecha y hora deben aparecer en la representación de cadena del valor de fecha y hora.  
  
3.  Para cada elemento de fecha y hora que desee mostrar, llame al método del objeto `Get`.  Los métodos siguientes están disponibles:  
  
    -   <xref:System.Globalization.Calendar.GetYear%2A>, para mostrar el año en el calendario adecuado.  
  
    -   <xref:System.Globalization.Calendar.GetMonth%2A>, para mostrar el mes en el calendario adecuado.  
  
    -   <xref:System.Globalization.Calendar.GetDayOfMonth%2A>, para mostrar el número del día del mes en el calendario adecuado.  
  
    -   <xref:System.Globalization.Calendar.GetHour%2A>, para mostrar la hora del día del mes en el calendario adecuado.  
  
    -   <xref:System.Globalization.Calendar.GetMinute%2A>, para mostrar los minutos de la hora en el calendario adecuado.  
  
    -   <xref:System.Globalization.Calendar.GetSecond%2A>, para mostrar los segundos del minuto en el calendario adecuado.  
  
    -   <xref:System.Globalization.Calendar.GetMilliseconds%2A>, para mostrar los milisegundos del segundo en el calendario adecuado.  
  
## Ejemplo  
 En el ejemplo se muestra una fecha utilizando dos calendarios diferentes.  Se muestra la fecha después de definir el calendario hijri como calendario predeterminado para la referencia cultural ar\-JO y se muestra la fecha con el calendario Persa, que no se admite como calendario opcional en la referencia cultural fa\-IR.  
  
 [!code-csharp[Formatting.HowTo.Calendar#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#2)]
 [!code-vb[Formatting.HowTo.Calendar#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#2)]  
  
 Cada objeto <xref:System.Globalization.CultureInfo> puede admitir uno o varios calendarios, que se especifican mediante la propiedad <xref:System.Globalization.CultureInfo.OptionalCalendars%2A>.  Uno de estos calendarios se establece como calendario predeterminado de la referencia cultural y es devuelto por la propiedad de sólo lectura <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=fullName>.  Otro de los calendarios opcionales se puede establecer como valor predeterminado asignando un objeto <xref:System.Globalization.Calendar> que represente ese calendario a la propiedad <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=fullName> devuelta por la propiedad <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=fullName>.  Sin embargo, algunos calendarios, como el calendario persa representado por la clase <xref:System.Globalization.PersianCalendar>, no actúan como calendarios opcionales de cualquier referencia cultural.  
  
 En el ejemplo se define una clase de utilidad de calendario reutilizable, `CalendarUtility`, para administrar muchos de los detalles de la generación de la representación de cadena de una fecha mediante un calendario determinado.  La clase `CalendarUtility` tiene los siguientes miembros:  
  
-   Un constructor parametrizado cuyo único parámetro es un objeto <xref:System.Globalization.Calendar> en el que se va a representar una fecha.  Éste se asigna a un campo privado de la clase.  
  
-   `CalendarExists`, un método privado que devuelve un valor booleano que indica si el calendario representado por el objeto `CalendarUtility` es compatible con el objeto <xref:System.Globalization.CultureInfo> que se pasa al método como parámetro.  El método contiene una llamada al método <xref:System.Array.Exists%2A?displayProperty=fullName>, al que pasa la matriz <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=fullName>.  
  
-   `HasSameName`, un método privado asignado al delegado <xref:System.Predicate%601> que se pasa como parámetro al método <xref:System.Array.Exists%2A?displayProperty=fullName>.  Los miembros de la matriz se pasan al método hasta que devuelve `true`.  El método determina si el nombre de un calendario opcional es igual que el calendario representado por el objeto `CalendarUtility`.  
  
-   `DisplayDate`, un método público sobrecargado al que se pasan dos parámetros: el valor <xref:System.DateTime> o <xref:System.DateTimeOffset> que se va a expresar en el calendario representado por el objeto `CalendarUtility` y la referencia cultural cuyas reglas de formato se van a utilizar.  Su comportamiento a la hora de devolver la representación de cadena de una fecha depende de si el calendario de destino es compatible con la referencia cultural cuyas reglas de formato se van a utilizar.  
  
 Independientemente del calendario que se utilice para crear un valor <xref:System.DateTime> o <xref:System.DateTimeOffset> en este ejemplo, ese valor normalmente se expresa como una fecha gregoriana.  Esto se debe a que los tipos <xref:System.DateTime> y <xref:System.DateTimeOffset> no conservan ninguna información del calendario.  Internamente, se representan como el número de pasos transcurridos desde la medianoche del 1 de enero de 0001.  La interpretación de ese número depende del calendario.  En la mayoría de las referencias culturales, el calendario predeterminado es el calendario gregoriano.  
  
## Compilar el código  
 Este ejemplo requiere una referencia a System.Core.dll.  
  
 Compile el código de la línea de comandos mediante csc.exe o vb.exe.  Para compilar el código de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], póngalo en una plantilla de proyecto de aplicación de consola.  
  
## Vea también  
 [Efectuar operaciones de formato](../../../docs/standard/base-types/performing-formatting-operations.md)