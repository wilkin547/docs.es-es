---
title: "C&#243;mo: Mostrar informaci&#243;n localizada de fecha y hora a usuarios web | Microsoft Docs"
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
  - "mostrar datos de fecha y hora"
  - "dar formato [.NET Framework], fechas"
  - "dar formato [.NET Framework], datos localizados"
  - "localización [.NET Framework], presentaciones de fecha y hora"
  - "presentaciones de fecha localizadas [.NET Framework]"
  - "analizar cadenas [.NET Framework], cadenas de fecha y hora"
ms.assetid: 377fe93c-32be-421a-a30a-be639a46ede8
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Mostrar informaci&#243;n localizada de fecha y hora a usuarios web
Dado que una página web puede mostrarse en cualquier parte del mundo, las operaciones de análisis y formato que se realizan sobre los valores de fecha y hora no deben basarse en un formato predeterminado \(que suele ser el formato de la referencia cultural local del servidor web\) al interactuar con el usuario.  En lugar de ello, los formularios web que controlan cadenas de fecha y hora escritas por el usuario deben analizar estas cadenas usando la referencia cultural preferida del usuario.  De igual forma, los datos de fecha y hora deben mostrarse al usuario en un formato que se ajuste a su referencia cultural.  En este tema se explica cómo hacerlo.  
  
### Para analizar cadenas de fecha y hora escritas por el usuario  
  
1.  Determine si la matriz de cadenas devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName> contiene elementos.  Si no es así, continúe en el paso 6.  
  
2.  Si la matriz de cadenas devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A> contiene elementos, recupere el primer elemento.  El primer elemento indica el idioma y la región predeterminados o preferidos por el usuario.  
  
3.  Cree una instancia de un objeto <xref:System.Globalization.CultureInfo> que represente la referencia cultural preferida del usuario; para ello, llame al constructor <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName>.  
  
4.  Llame al método `TryParse` o `Parse` del tipo <xref:System.DateTime> o <xref:System.DateTimeOffset> para intentar realizar la conversión.  Utilice una sobrecarga del método `TryParse` o `Parse` con un parámetro `provider` y pásele cualquiera de los elementos siguientes:  
  
    -   El objeto <xref:System.Globalization.CultureInfo> creado en el paso 3.  
  
    -   El objeto <xref:System.Globalization.DateTimeFormatInfo> devuelto por la propiedad <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> del objeto <xref:System.Globalization.CultureInfo> que se creó en el paso 3.  
  
5.  Si la conversión no se realiza correctamente, repita los pasos 2 al 4 en cada elemento restante de la matriz de cadenas devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A>.  
  
6.  Si la conversión sigue produciendo errores o si la matriz de cadenas devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A> está vacía, analice la cadena usando la referencia cultural de todos los idiomas devuelta por la propiedad <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.  
  
### Para analizar la fecha y hora locales de la solicitud del usuario  
  
1.  Agregue un control <xref:System.Web.UI.WebControls.HiddenField> a un formulario web.  
  
2.  Cree una función JavaScript que controle el evento `onClick` de un botón `Submit`; para ello, especifique la fecha y hora actuales y el desfase de la zona horaria local con respecto a la hora universal coordinada \(hora UTC\) en la propiedad <xref:System.Web.UI.WebControls.HiddenField.Value%2A>.  Use un delimitador \(por ejemplo, un punto y coma\) para separar los dos componentes de la cadena.  
  
3.  Use el evento <xref:System.Web.UI.Control.PreRender> del formulario web para insertar la función en el flujo de salida HTML; para ello, pase el texto del script al método <xref:System.Web.UI.ClientScriptManager.RegisterClientScriptBlock%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=fullName>.  
  
4.  Asocie el controlador de eventos con el evento `onClick` del botón `Submit`; para ello, especifique el nombre de la función JavaScript en el atributo `OnClientClick` del botón `Submit`.  
  
5.  Cree un controlador para el evento <xref:System.Web.UI.WebControls.Button.Click> del botón `Submit`.  
  
6.  En el controlador de eventos, determine si la matriz de cadenas devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName> contiene elementos.  Si no es así, continúe en el paso 14.  
  
7.  Si la matriz de cadenas devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A> contiene elementos, recupere el primer elemento.  El primer elemento indica el idioma y la región predeterminados o preferidos por el usuario.  
  
8.  Cree una instancia de un objeto <xref:System.Globalization.CultureInfo> que represente la referencia cultural preferida del usuario; para ello, llame al constructor <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName>.  
  
9. Pase la cadena asignada a la propiedad <xref:System.Web.UI.WebControls.HiddenField.Value%2A> al método <xref:System.String.Split%2A> para almacenar la representación de cadena de la fecha y hora locales del usuario y la representación de cadena del desfase de la zona horaria local del usuario en diferentes elementos de la matriz.  
  
10. Llame al método <xref:System.DateTime.Parse%2A?displayProperty=fullName> o <xref:System.DateTime.TryParse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%2CSystem.DateTime%40%29?displayProperty=fullName> para convertir la fecha y hora de la solicitud del usuario en un valor <xref:System.DateTime>.  Utilice una sobrecarga del método con un parámetro `provider` y pásele cualquiera de los objetos siguientes:  
  
    -   El objeto <xref:System.Globalization.CultureInfo> creado en el paso 8.  
  
    -   El objeto <xref:System.Globalization.DateTimeFormatInfo> devuelto por la propiedad <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> del objeto <xref:System.Globalization.CultureInfo> que se creó en el paso 8.  
  
11. Si la operación de análisis produce un error en el paso 10, vaya al paso 13.  De lo contrario, llame al método <xref:System.UInt32.Parse%28System.String%29?displayProperty=fullName> para convertir la representación de cadena del desfase de zona horaria del usuario en un entero.  
  
12. Cree una instancia de <xref:System.DateTimeOffset> que represente la hora local del usuario llamando al constructor <xref:System.DateTimeOffset.%23ctor%28System.DateTime%2CSystem.TimeSpan%29?displayProperty=fullName>.  
  
13. Si la conversión del paso 10 no se realiza correctamente, repita los pasos del 7 al 12 en cada elemento restante de la matriz de cadenas devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A>.  
  
14. Si la conversión sigue produciendo errores o si la matriz de cadenas devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A> está vacía, analice la cadena usando la referencia cultural de todos los idiomas devuelta por la propiedad <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.  A continuación, repita los pasos del 7 al 12.  
  
 El resultado es un objeto <xref:System.DateTimeOffset> que representa la hora local del usuario de su página web.  Puede determinar a continuación la hora UTC equivalente llamando al método <xref:System.DateTimeOffset.ToUniversalTime%2A>.  También puede determinar la fecha y hora equivalentes del servidor web llamando al método <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=fullName> y pasando un valor <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName> como zona horaria a la que debe convertirse la hora.  
  
## Ejemplo  
 El ejemplo siguiente incluye código fuente HTML y el código de un formulario web de ASP.NET que solicita al usuario que escriba un valor de fecha y hora.  También hay un script de cliente que escribe información sobre la fecha y hora local de la solicitud del usuario y el desfase de la zona horaria del usuario con respecto a la hora UTC en un campo oculto.  Esta información se analiza a continuación en el servidor, que devuelve una página web en la que se muestran los datos especificados por el usuario.  También muestra la fecha y hora de la solicitud del usuario utilizando la hora local del usuario, la hora del servidor y la hora UTC.  
  
 [!code-csharp[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/cs/GetDateInfo.aspx#1)]
 [!code-vb[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/vb/GetDateInfo.aspx#1)]  
  
 El script de cliente llama al método `toLocaleString` de JavaScript.  Esto genera una cadena que se ajusta a las convenciones de formato de la configuración regional del usuario, por lo que es más probable que se analice correctamente en el servidor.  
  
 La propiedad <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName> se rellena a partir de los nombres de la referencia cultural incluidos en los encabezados `Accept-Language` de una solicitud HTTP.  Sin embargo, no todos los exploradores incluyen encabezados `Accept-Language` en sus solicitudes y además los usuarios pueden suprimir los encabezados por completo.  Por ello, es importante tener una referencia cultural de reserva al analizar los datos proporcionados por el usuario.  Normalmente, la referencia cultural de reserva es la referencia cultural de todos los idiomas devuelta por la propiedad <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.  Los usuarios también pueden proporcionar a Internet Explorer nombres de la referencia cultural escribiéndolos en un cuadro de texto, de modo que es posible que los nombres de la referencia cultural no sean válidos.  Por todo esto, es importante utilizar el control de excepciones al crear instancias de un objeto <xref:System.Globalization.CultureInfo>.  
  
 Cuando se recupera de una solicitud HTTP enviada por Internet Explorer, la matriz <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName> se rellena en orden de preferencia del usuario.  El primer elemento de la matriz contiene el nombre de la referencia cultural o región primaria del usuario.  Si la matriz contiene algún otro elemento, Internet Explorer le asigna arbitrariamente un especificador de calidad, que está delimitado del nombre de la referencia cultural mediante un punto y coma.  Por ejemplo, una entrada para la referencia cultural fr\-FR podría tener la forma `fr-FR;q=0.7`.  
  
 En el ejemplo, se llama al constructor <xref:System.Globalization.CultureInfo.%23ctor%2A> con el parámetro `useUserOverride` establecido en `false` para crear un nuevo objeto <xref:System.Globalization.CultureInfo>.  De este modo, tiene la seguridad de que si el nombre de la referencia cultural es el nombre de la referencia cultural predeterminada del servidor, el nuevo objeto <xref:System.Globalization.CultureInfo> creado por el constructor de clase contiene la configuración predeterminada de una referencia cultural y no refleja las configuraciones invalidadas con la aplicación **Configuración regional y de idioma** del servidor.  Es poco probable que los valores de una configuración invalidada en el servidor permanezcan en el sistema del usuario o se reflejen en los datos proporcionados por el usuario.  
  
 Dado que en este ejemplo se analizan dos representaciones de cadena de una fecha y hora \(un valor proporcionado por el usuario y otro valor almacenado en el campo oculto\), se definen los objetos <xref:System.Globalization.CultureInfo> que a priori podrían ser necesarios.  En el ejemplo se crea una matriz de objetos <xref:System.Globalization.CultureInfo> con un elemento más que el número de elementos devuelto por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName>.  A continuación, se crean instancias de un objeto <xref:System.Globalization.CultureInfo> para cada cadena de idioma o región y también se crean instancias de un objeto <xref:System.Globalization.CultureInfo> que representa <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.  
  
 Su código puede llamar al método <xref:System.DateTime.Parse%2A> o <xref:System.DateTime.TryParse%2A> para convertir la representación de cadena del usuario de una fecha y hora en un valor <xref:System.DateTime>.  Puede ser necesario llamar varias veces a un método de análisis en una única operación de análisis.  Como consecuencia, el método <xref:System.DateTime.TryParse%2A> resulta más conveniente porque devuelve `false` si se producen errores en una operación de análisis.  Por el contrario, mantener un control sobre las excepciones repetidas que puede iniciar el método <xref:System.DateTime.Parse%2A> puede ser una tarea excesivamente costosa cuando se trata de una aplicación web.  
  
## Compilar el código  
 Para compilar el código, cree una página web de [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] sin código subyacente.  A continuación, copie el ejemplo en la página web de modo que reemplace todo el código existente.  La página web de [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] debe contener los controles siguientes:  
  
-   Un control <xref:System.Web.UI.WebControls.Label>, al que no se hace referencia en código.  Establezca la propiedad <xref:System.Web.UI.WebControls.TextBox.Text%2A> en "Escriba un número:".  
  
-   Un control <xref:System.Web.UI.WebControls.TextBox> denominado `DateString`.  
  
-   Un control <xref:System.Web.UI.WebControls.Button> denominado `OKButton`.  Establezca la propiedad <xref:System.Web.UI.WebControls.Button.Text%2A> en "Aceptar".  
  
-   Un control <xref:System.Web.UI.WebControls.HiddenField> denominado `DateInfo`.  
  
## Seguridad de .NET Framework  
 Para evitar que un usuario inserte el script en la secuencia HTML, los datos proporcionados por el usuario nunca deberían devolverse directamente en la respuesta del servidor.  En su lugar, deberían codificarse con el método <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=fullName>.  
  
## Vea también  
 [Efectuar operaciones de formato](../../../docs/standard/base-types/performing-formatting-operations.md)   
 [Cadenas con formato de fecha y hora estándar](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)   
 [Cadenas con formato de fecha y hora personalizado](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)   
 [Analizar cadenas de fecha y hora](../../../docs/standard/base-types/parsing-datetime.md)