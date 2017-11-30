---
title: "Cómo: Mostrar información localizada de fecha y hora a usuarios web"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- formatting [.NET Framework], dates
- parsing strings [.NET Framework], date and time strings
- localization [.NET Framework], date and time displays
- formatting [.NET Framework], localized data
- displaying date and time data
- localized date displays [.NET Framework]
ms.assetid: 377fe93c-32be-421a-a30a-be639a46ede8
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 21493e0e0c9e42cf5efc42d86c8f126fbae9b392
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-localized-date-and-time-information-to-web-users"></a>Cómo: Mostrar información localizada de fecha y hora a usuarios web
Dado que una página Web puede mostrarse en cualquier lugar del mundo, las operaciones que analizarán y dar formato a valores de fecha y hora no deben confiar en un formato predeterminado (que suele ser el formato de referencia cultural local del servidor Web) al interactuar con el usuario. En su lugar, formularios Web forms que controlen la fecha y hora de entrada de cadenas por el usuario deben analizar estas cadenas usando la referencia cultural preferida del usuario. De forma similar, los datos de fecha y hora deben mostrarse al usuario en un formato que se ajusta a la referencia cultural del usuario. En este tema se explica cómo hacerlo.  
  
### <a name="to-parse-date-and-time-strings-input-by-the-user"></a>Analizar la fecha y hora en cadenas de datos proporcionados por el usuario  
  
1.  Determinar si la matriz de cadena devueltos por la <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> propiedad se rellena. Si no es así, vaya al paso 6.  
  
2.  Si la matriz de cadenas devuelta por la <xref:System.Web.HttpRequest.UserLanguages%2A> propiedad se rellena, recupere el primer elemento. El primer elemento indica el usuario predeterminado o idioma preferido y región.  
  
3.  Crear una instancia de un <xref:System.Globalization.CultureInfo> objeto que representa al usuario preferido referencia cultural mediante una llamada a la <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> constructor.  
  
4.  Llamar a la `TryParse` o `Parse` método de la <xref:System.DateTime> o <xref:System.DateTimeOffset> tipo intentar la conversión. Use una sobrecarga de la `TryParse` o `Parse` método con un `provider` parámetro y pasar cualquiera de las siguientes acciones:  
  
    -   La <xref:System.Globalization.CultureInfo> objeto creado en el paso 3.  
  
    -   El <xref:System.Globalization.DateTimeFormatInfo> objeto devuelto por la <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> propiedad de la <xref:System.Globalization.CultureInfo> objeto creado en el paso 3.  
  
5.  Si se produce un error en la conversión, repita los pasos del 2 al 4 para cada elemento restante en la matriz de cadenas devueltos por la <xref:System.Web.HttpRequest.UserLanguages%2A> propiedad.  
  
6.  Si todavía se produce un error en la conversión o si la matriz de cadenas devuelta por la <xref:System.Web.HttpRequest.UserLanguages%2A> propiedad está vacía, analizar la cadena usando la referencia cultural, lo que es devuelto por la <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> propiedad.  
  
### <a name="to-parse-the-local-date-and-time-of-the-users-request"></a>Analizar la fecha y hora local de la solicitud del usuario  
  
1.  Agregar un <xref:System.Web.UI.WebControls.HiddenField> control a un formulario Web Forms.  
  
2.  Crear una función de JavaScript que controla la `onClick` eventos de un `Submit` botón escribiendo la fecha y hora actuales y desplazamiento de la zona horaria local de la hora Universal coordinada (UTC) para el <xref:System.Web.UI.WebControls.HiddenField.Value%2A> propiedad. Use un delimitador (por ejemplo, un punto y coma) para separar los dos componentes de la cadena.  
  
3.  Utilizar el formulario Web <xref:System.Web.UI.Control.PreRender> flujo de salida de evento para insertar la función en el código HTML, pasando el texto de la secuencia de comandos para la <xref:System.Web.UI.ClientScriptManager.RegisterClientScriptBlock%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType> método.  
  
4.  Conectar el controlador de eventos para el `Submit` del botón `onClick` eventos proporcionando el nombre de la función JavaScript a la `OnClientClick` atributo de la `Submit` botón.  
  
5.  Crear un controlador para el `Submit` del botón <xref:System.Web.UI.WebControls.Button.Click> eventos.  
  
6.  En el controlador de eventos, determine si la matriz de cadena devueltos por la <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> propiedad se rellena. Si no es así, vaya al paso 14.  
  
7.  Si la matriz de cadenas devuelta por la <xref:System.Web.HttpRequest.UserLanguages%2A> propiedad se rellena, recupere el primer elemento. El primer elemento indica el usuario predeterminado o idioma preferido y región.  
  
8.  Crear una instancia de un <xref:System.Globalization.CultureInfo> objeto que representa al usuario preferido referencia cultural mediante una llamada a la <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> constructor.  
  
9. Pase la cadena asignada a la <xref:System.Web.UI.WebControls.HiddenField.Value%2A> propiedad a la <xref:System.String.Split%2A> método utilizado para almacenar la representación de cadena de fecha local del usuario y la hora y la representación de cadena de ajuste de zona horaria local del usuario en elementos de matriz independiente.  
  
10. Llamar a la <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> o <xref:System.DateTime.TryParse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%2CSystem.DateTime%40%29?displayProperty=nameWithType> método para convertir la fecha y hora de la solicitud del usuario a un <xref:System.DateTime> valor. Use una sobrecarga del método con un `provider` parámetro y pasar cualquiera de las siguientes acciones:  
  
    -   La <xref:System.Globalization.CultureInfo> objeto creado en el paso 8.  
  
    -   El <xref:System.Globalization.DateTimeFormatInfo> objeto devuelto por la <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> propiedad de la <xref:System.Globalization.CultureInfo> objeto creado en el paso 8.  
  
11. Si se produce un error en la operación de análisis en el paso 10, vaya al paso 13. De lo contrario, llame a la <xref:System.UInt32.Parse%28System.String%29?displayProperty=nameWithType> método para convertir la representación de cadena de ajuste de zona horaria del usuario en un entero.  
  
12. Crear una instancia de un <xref:System.DateTimeOffset> que representa la hora local del usuario mediante una llamada a la <xref:System.DateTimeOffset.%23ctor%28System.DateTime%2CSystem.TimeSpan%29?displayProperty=nameWithType> constructor.  
  
13. Si se produce un error en la conversión en el paso 10, repita los pasos del 7 al 12 para cada elemento restante en la matriz de cadenas devueltas por la <xref:System.Web.HttpRequest.UserLanguages%2A> propiedad.  
  
14. Si todavía se produce un error en la conversión o si la matriz de cadenas devuelta por la <xref:System.Web.HttpRequest.UserLanguages%2A> propiedad está vacía, analizar la cadena usando la referencia cultural, lo que es devuelto por la <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> propiedad. A continuación, repita los pasos del 7 al 12.  
  
 El resultado es un <xref:System.DateTimeOffset> objeto que representa la hora local del usuario de la página Web. A continuación, puede determinar la hora UTC equivalente mediante una llamada a la <xref:System.DateTimeOffset.ToUniversalTime%2A> método. También puede determinar la fecha y hora equivalente en el servidor Web mediante una llamada a la <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> método y se pasa un valor de <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> como la zona horaria para convertir el tiempo.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente contiene el código fuente HTML y el código de un formulario Web de ASP.NET que pide al usuario a un valor de fecha y hora de entrada. Un script del lado cliente también escribe información en la fecha local y la hora de la solicitud del usuario y el desplazamiento de zona horaria del usuario a la hora UTC en un campo oculto. Esta información, a continuación, se analiza el servidor, que devuelve una página Web que muestra la entrada del usuario. También muestra la fecha y hora de la solicitud del usuario mediante la hora local del usuario, la hora en el servidor y la hora UTC.  
  
 [!code-aspx-csharp[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/cs/GetDateInfo.aspx#1)]
 [!code-aspx-vb[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/vb/GetDateInfo.aspx#1)]
  
 El script de cliente llama a JavaScript `toLocaleString` método. Esto genera una cadena que sigue las convenciones de formato de la configuración regional del usuario, que es más probable que se analizó correctamente en el servidor.  
  
 El <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> propiedad se rellena a partir de los nombres de referencia cultural que se encuentran en `Accept-Language` encabezados incluidos en una solicitud HTTP. Sin embargo, no todos los exploradores incluyen `Accept-Language` encabezados en sus solicitudes y los usuarios también pueden suprimir los encabezados por completo. Esto hace que sea importante tener una referencia cultural de reserva al analizar proporcionados por el usuario. Normalmente, la referencia cultural de reserva es la referencia cultural invariable devuelta por <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Los usuarios también pueden proporcionar Internet Explorer con nombres de referencia cultural escribiéndolos en un cuadro de texto, que crea la posibilidad de que los nombres de referencia cultural pueden no ser válidos. Esto hace que sea importante para usar el control de excepciones al crear instancias de un <xref:System.Globalization.CultureInfo> objeto.  
  
 Cuando se recuperan de una solicitud HTTP enviada por Internet Explorer, la <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> matriz se rellena en orden de preferencia de usuario. El primer elemento de la matriz contiene el nombre de referencia cultural/región principal del usuario. Si la matriz contiene los elementos adicionales, Internet Explorer le asigna arbitrariamente un especificador de calidad, que está delimitado del nombre de referencia cultural de un punto y coma. Por ejemplo, una entrada para la referencia cultural fr-FR podría tener el formato `fr-FR;q=0.7`.  
  
 El ejemplo se llama el <xref:System.Globalization.CultureInfo.%23ctor%2A> constructor con su `useUserOverride` parámetro establecido en `false` para crear un nuevo <xref:System.Globalization.CultureInfo> objeto. Esto garantiza que, si el nombre de referencia cultural es el nombre de la referencia cultural predeterminada en el servidor, el nuevo <xref:System.Globalization.CultureInfo> objeto creado por el constructor de clase contiene la configuración predeterminada de una referencia cultural y no refleja las configuraciones invalidadas con el servidor  **Regional y de idioma** aplicación. Los valores de una configuración invalidada en el servidor son poco probable que exista en el sistema del usuario o para que se refleje en la entrada del usuario.  
  
 Dado que este ejemplo analizan dos representaciones de cadena de una fecha y hora (un valor proporcionado por el usuario, otro valor almacenado en el campo oculto), define los posibles <xref:System.Globalization.CultureInfo> objetos que podrían ser necesarios de antemano. Crea una matriz de <xref:System.Globalization.CultureInfo> objetos que es una unidad mayor que el número de elementos devueltos por la <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> propiedad. A continuación, crea una instancia de un <xref:System.Globalization.CultureInfo> objeto para cada cadena de idioma y región y también crea una instancia de un <xref:System.Globalization.CultureInfo> objeto que representa <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.  
  
 El código puede llamar a la <xref:System.DateTime.Parse%2A> o <xref:System.DateTime.TryParse%2A> método para convertir la representación de cadena del usuario de una fecha y hora a la que un <xref:System.DateTime> valor. Las llamadas repetidas a un método de análisis pueden resultar necesarias para una única operación de análisis. Como resultado, el <xref:System.DateTime.TryParse%2A> métodos es mejor porque devuelve `false` si se produce un error en una operación de análisis. En cambio, controlar las excepciones repetidas que pueden producir el <xref:System.DateTime.Parse%2A> método puede ser una propuesta muy costosa en una aplicación Web.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para compilar el código, cree un [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] página Web sin un código subyacente. A continuación, copie el ejemplo en la página Web para que lo reemplace todo el código existente. La [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] página Web debe contener los siguientes controles:  
  
-   Un <xref:System.Web.UI.WebControls.Label> control, que no se hace referencia en el código. Establecer su <xref:System.Web.UI.WebControls.TextBox.Text%2A> propiedad en "Escriba un número:".  
  
-   Un control <xref:System.Web.UI.WebControls.TextBox> llamado `DateString`.  
  
-   Un control <xref:System.Web.UI.WebControls.Button> llamado `OKButton`. Establecer su <xref:System.Web.UI.WebControls.Button.Text%2A> propiedad en "Aceptar".  
  
-   Control <xref:System.Web.UI.WebControls.HiddenField> denominado `DateInfo`.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Para evitar que un usuario inserte el script en el flujo HTML, los proporcionados por el usuario nunca deben devolverse directamente en la respuesta del servidor. En su lugar, debe codificarse utilizando el <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType> método.  
  
## <a name="see-also"></a>Vea también  
 [Efectuar operaciones de formato](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [Standard Date and Time Format Strings](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)  
 [Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)  
 [Análisis de cadenas de fecha y hora](../../../docs/standard/base-types/parsing-datetime.md)
