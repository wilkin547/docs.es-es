---
title: Procedimiento para mostrar información localizada de fecha y hora a usuarios web
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- formatting [.NET Framework], dates
- parsing strings [.NET Framework], date and time strings
- localization [.NET Framework], date and time displays
- formatting [.NET Framework], localized data
- displaying date and time data
- localized date displays [.NET Framework]
ms.assetid: 377fe93c-32be-421a-a30a-be639a46ede8
dev_langs:
- csharp
- vb
ms.openlocfilehash: 51142a168aba4408e6ce550a032960c4df6c3ae7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138742"
---
# <a name="how-to-display-localized-date-and-time-information-to-web-users"></a>Procedimiento para mostrar información localizada de fecha y hora a usuarios web
Dado que una página web puede mostrarse en cualquier lugar del mundo, las operaciones que analizarán y darán formato a valores de fecha y hora no deben basarse en un formato predeterminado (que suele ser el formato de referencia cultural local del servidor web) al interactuar con el usuario. En su lugar, los formularios Web Forms que controlan las entradas del usuario de cadenas de fecha y hora deben analizar estas cadenas usando la referencia cultural preferida del usuario. De forma similar, los datos de fecha y hora deben mostrarse al usuario en un formato que se ajuste a la referencia cultural del usuario. En este tema se explica cómo hacerlo.  
  
## <a name="to-parse-date-and-time-strings-input-by-the-user"></a>Para analizar las entradas del usuario de cadenas de fecha y hora  
  
1. Determine si la matriz de cadena devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> se rellena. Si no es así, vaya al paso 6.  
  
2. Si la matriz de cadena devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A> se rellena, recupere el primer elemento. El primer elemento indica la región y el idioma preferidos o predeterminados del usuario.  
  
3. Cree una instancia de un objeto <xref:System.Globalization.CultureInfo> que representa la referencia cultural preferida del usuario con una llamada al constructor <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType>.  
  
4. Llame al método `TryParse` o `Parse` del tipo <xref:System.DateTime> o <xref:System.DateTimeOffset> para intentar la conversión. Use una sobrecarga del método `TryParse` o `Parse` con un parámetro `provider` y pásela con lo siguiente:  
  
    - El objeto <xref:System.Globalization.CultureInfo> creado en el paso 3.  
  
    - El objeto <xref:System.Globalization.DateTimeFormatInfo> devuelto por la propiedad <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> del objeto <xref:System.Globalization.CultureInfo> creado en el paso 3.  
  
5. Si se produce un error en la conversión, repita los pasos 2 a 4 para cada elemento restante de la matriz de cadena devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A>.  
  
6. Si todavía existen errores de conversión o si la matriz de cadena devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A> está vacía, analice la cadena con la referencia cultural invariable devuelta por la propiedad <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.  
  
## <a name="to-parse-the-local-date-and-time-of-the-users-request"></a>Para analizar la fecha y hora locales de la solicitud del usuario  
  
1. Agregue un control <xref:System.Web.UI.WebControls.HiddenField> al formulario web.  
  
2. Cree una función de JavaScript que controle el evento `onClick` de un botón `Submit` escribiendo la fecha y hora actuales y la diferencia horaria de la zona horaria local con respecto a la hora universal coordinada (UTC) para la propiedad <xref:System.Web.UI.WebControls.HiddenField.Value%2A>. Use un delimitador (por ejemplo, un punto y coma) para separar los dos componentes de la cadena.  
  
3. Use el evento <xref:System.Web.UI.Control.PreRender> del formulario web para insertar la función en el flujo de salida HTML pasando el texto del script al método <xref:System.Web.UI.ClientScriptManager.RegisterClientScriptBlock%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType>.  
  
4. Conecte el controlador de eventos al evento `onClick` del botón `Submit` proporcionando el nombre de la función JavaScript al atributo `OnClientClick` del botón `Submit`.  
  
5. Cree un controlador para el evento <xref:System.Web.UI.WebControls.Button.Click> del botón `Submit`.  
  
6. En el controlador de eventos, determine si la matriz de cadena devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> se rellena. Si no es así, vaya al paso 14.  
  
7. Si la matriz de cadena devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A> se rellena, recupere el primer elemento. El primer elemento indica la región y el idioma preferidos o predeterminados del usuario.  
  
8. Cree una instancia de un objeto <xref:System.Globalization.CultureInfo> que representa la referencia cultural preferida del usuario con una llamada al constructor <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType>.  
  
9. Pase la cadena asignada a la propiedad <xref:System.Web.UI.WebControls.HiddenField.Value%2A> al método <xref:System.String.Split%2A> para almacenar la representación de cadena de la fecha y hora locales del usuario y la representación de cadena de la diferencia de la zona horaria local del usuario en elementos de matriz independientes.  
  
10. Llame a los métodos <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> o <xref:System.DateTime.TryParse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%2CSystem.DateTime%40%29?displayProperty=nameWithType> para convertir la fecha y hora de la solicitud del usuario en un valor <xref:System.DateTime>. Use una sobrecarga del método con un parámetro `provider` y pásela con lo siguiente:  
  
    - El objeto <xref:System.Globalization.CultureInfo> creado en el paso 8.  
  
    - El objeto <xref:System.Globalization.DateTimeFormatInfo> devuelto por la propiedad <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> del objeto <xref:System.Globalization.CultureInfo> creado en el paso 8.  
  
11. Si se produce un error en la operación de análisis en el paso 10, vaya al paso 13. De lo contrario, llame al método <xref:System.UInt32.Parse%28System.String%29?displayProperty=nameWithType> para convertir la representación de cadena de la diferencia de la zona horaria del usuario en un entero.  
  
12. Cree una instancia de un objeto <xref:System.DateTimeOffset> que representa la zona horaria local del usuario con una llamada al constructor <xref:System.DateTimeOffset.%23ctor%28System.DateTime%2CSystem.TimeSpan%29?displayProperty=nameWithType>.  
  
13. Si se produce un error en la conversión en el paso 10, repita los pasos 7 a 12 para cada elemento restante de la matriz de cadena devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A>.  
  
14. Si todavía existen errores de conversión o si la matriz de cadena devuelta por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A> está vacía, analice la cadena con la referencia cultural invariable devuelta por la propiedad <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Después, repita los pasos 7 a 12.  
  
 El resultado es un objeto <xref:System.DateTimeOffset> que representa la hora local del usuario de la página web. A continuación, puede determinar la hora UTC equivalente mediante una llamada al método <xref:System.DateTimeOffset.ToUniversalTime%2A>. También puede determinar la fecha y hora equivalentes en el servidor web mediante una llamada al método <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> y pasar un valor de <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> como la zona horaria para convertir la hora.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente contiene el código fuente HTML y el código de un formulario web de ASP.NET que pide al usuario que especifique un valor de fecha y hora. Un script del lado cliente también escribe información en la fecha y hora locales de la solicitud del usuario y la diferencia horaria de la zona horaria del usuario con respecto a UTC en un campo oculto. A continuación, el servidor analiza esta información, que devuelve una página web que muestra la entrada del usuario. También muestra la fecha y hora de la solicitud del usuario mediante la hora local del usuario, la hora en el servidor y la hora UTC.  
  
 [!code-aspx-csharp[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/cs/GetDateInfo.aspx#1)]
 [!code-aspx-vb[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/vb/GetDateInfo.aspx#1)]
  
 El script del lado cliente llama al método `toLocaleString` de JavaScript. Esto genera una cadena que sigue las convenciones de formato de la configuración regional del usuario, que es más probable que se analice correctamente en el servidor.  
  
 La propiedad <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> se rellena a partir de los nombres de referencia cultural contenidos en los encabezados `Accept-Language` incluidos en una solicitud HTTP. Sin embargo, no todos los exploradores incluyen encabezados `Accept-Language` en sus solicitudes, y los usuarios también pueden suprimir los encabezados por completo. Esto hace que sea importante tener una referencia cultural de reserva al analizar la entrada del usuario. Normalmente, la referencia cultural de reserva es la referencia cultural invariable devuelta por <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Los usuarios también pueden proporcionar a Internet Explorer nombres de referencia cultural que se escriben en un cuadro de texto, lo que plantea la posibilidad de que los nombres de referencia cultural no sean válidos. Esto hace que sea importante usar el control de excepciones al crear instancias de un objeto <xref:System.Globalization.CultureInfo>.  
  
 Cuando se recupera a partir de una solicitud HTTP enviada por Internet Explorer, la matriz <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> se rellena en función de las preferencias del usuario. El primer elemento de la matriz contiene el nombre de la región o referencia cultural principales del usuario. Si la matriz contiene elementos adicionales, Internet Explorer les asigna arbitrariamente un especificador de calidad, que está delimitado por un punto y coma desde el nombre de la referencia cultural. Por ejemplo, una entrada para la referencia cultural fr-FR podría tener el formato `fr-FR;q=0.7`.  
  
 El ejemplo llama al constructor <xref:System.Globalization.CultureInfo.%23ctor%2A> con su parámetro `useUserOverride` establecido en `false` para crear un objeto <xref:System.Globalization.CultureInfo>. Esto garantiza que, si el nombre de la referencia cultural es el nombre de la referencia cultural predeterminado en el servidor, el nuevo objeto <xref:System.Globalization.CultureInfo> creado por el constructor de clase contiene la configuración predeterminada de una referencia cultural y no refleja las configuraciones invalidadas al usar la aplicación **Configuración regional y de idioma** del servidor. Es poco probable que la configuración invalidada del servidor exista en el sistema del usuario o que se refleje en la entrada del usuario.  
  
 Dado que este ejemplo analiza dos representaciones de cadena de fecha y hora (un valor proporcionado por el usuario y el otro valor almacenado en el campo oculto), define los posibles objetos <xref:System.Globalization.CultureInfo> que podrían ser necesarios de antemano. Crea una matriz de objetos <xref:System.Globalization.CultureInfo> que es una unidad mayor que el número de elementos devueltos por la propiedad <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>. A continuación, crea una instancia de un objeto <xref:System.Globalization.CultureInfo> para cada cadena de idioma y región y también crea una instancia de un objeto <xref:System.Globalization.CultureInfo> que representa <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.  
  
 El código puede llamar al método <xref:System.DateTime.Parse%2A> o <xref:System.DateTime.TryParse%2A> para convertir la representación de cadena del usuario de una fecha y hora en un valor <xref:System.DateTime>. Puede que se necesiten llamadas repetidas a un método de análisis para una única operación de análisis. Como resultado, el método <xref:System.DateTime.TryParse%2A> es mejor, porque devuelve `false` si se produce algún error con la operación de análisis. En cambio, controlar las excepciones repetidas que el método <xref:System.DateTime.Parse%2A> puede ocasionar puede ser una propuesta muy costosa en una aplicación web.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para compilar el código, cree una página web de ASP.NET sin un código subyacente. A continuación, copie el ejemplo en la página web para que reemplace todo el código existente. La página web de ASP.NET debe contener los siguientes controles:  
  
- Un control <xref:System.Web.UI.WebControls.Label>, al que no se hace referencia en el código. Establezca su propiedad <xref:System.Web.UI.WebControls.TextBox.Text%2A> en "Enter a Number:".  
  
- Control <xref:System.Web.UI.WebControls.TextBox> denominado `DateString`.  
  
- Control <xref:System.Web.UI.WebControls.Button> denominado `OKButton`. Establezca la propiedad <xref:System.Web.UI.WebControls.Button.Text%2A> en "OK".  
  
- Control <xref:System.Web.UI.WebControls.HiddenField> denominado `DateInfo`.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Para evitar que un usuario inserte el script en la secuencia HTML, la entrada del usuario nunca debe devolverse directamente en la respuesta del servidor. En su lugar, debe codificarse con el método <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

- [Efectuar operaciones de formato](../../../docs/standard/base-types/performing-formatting-operations.md)
- [Standard Date and Time Format Strings](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)
- [Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)
- [Análisis de cadenas de fecha y hora](../../../docs/standard/base-types/parsing-datetime.md)
