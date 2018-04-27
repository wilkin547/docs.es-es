### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a>HttpUtility.JavaScriptStringEncode aplica un carácter de escape a la Y comercial

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name> incluye un carácter de escape antes del carácter de Y comercial (&amp;).|
|Sugerencia|Si la aplicación depende del comportamiento anterior de este método, puede agregar un ajuste aspnet:JavaScriptDoNotEncodeAmpersand al [elemento appSettings de ASP.NET](https://msdn.microsoft.com/library/hh975440.aspx) en el archivo de configuración.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|

