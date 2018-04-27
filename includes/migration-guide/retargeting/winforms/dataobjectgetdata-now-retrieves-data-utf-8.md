### <a name="dataobjectgetdata-now-retrieves-data-as-utf-8"></a>DataObject.GetData ahora recupera los datos como UTF-8

|   |   |
|---|---|
|Detalles|Para las aplicaciones que tienen como destino .NET Framework 4 o que se ejecutan en .NET Framework 4.5.1 o versiones anteriores, <code>DataObject.GetData</code> recupera los datos con formato HTML como una cadena ASCII. Como resultado, los caracteres que no son ASCII (los caracteres cuyos códigos ASCII son mayores que 0x7F) se representan mediante dos caracteres aleatorios. Para las aplicaciones que tienen como destino .NET Framework 4.5 o una versión posterior y se ejecutan en .NET Framework 4.5.2, <code>DataObject.GetData</code> recupera los datos con formato HTML como UTF-8, que representa correctamente los caracteres mayores que 0x7F.|
|Sugerencia|Si implementó una solución alternativa para el problema de codificación mediante cadenas con formato HTML (por ejemplo, mediante la codificación explícita de la cadena HTML recuperada del Portapapeles y su transferencia a <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=name>) y va a redestinar la aplicación de la versión 4 a la versión 4.5, esa solución alternativa se debe eliminar. Si por algún motivo se necesita el comportamiento anterior, la aplicación se puede destinar a .NET Framework 4.0 para obtenerlo.|
|Ámbito|Borde|
|Versión|4.5.2|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Windows.DataObject.GetData(System.String)?displayProperty=nameWithType></li><li><xref:System.Windows.DataObject.GetData(System.Type)?displayProperty=nameWithType></li><li><xref:System.Windows.DataObject.GetData(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|

