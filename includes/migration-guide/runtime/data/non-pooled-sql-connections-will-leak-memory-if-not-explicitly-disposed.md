### <a name="non-pooled-sql-connections-will-leak-memory-if-not-explicitly-disposed"></a>Las conexiones de SQL no agrupadas producirán una pérdida de memoria si no se eliminan de forma explícita

|   |   |
|---|---|
|Detalles|En .NET Framework 4.5, las conexiones de SQL no agrupadas que no se expongan de forma explícita (mediante Dispose, Close o using) producirán una pérdida de memoria.|
|Sugerencia|Este problema se ha corregido en la actualización de servicio de .NET Framework 4.5. Para corregir este problema, actualice .NET Framework 4.5 o actualice a la versión 4.5.1 o posterior de .NET Framework. Como alternativa, se puede evitar este problema mediante el uso de <xref:System.Data.SqlClient.SqlConnection?displayProperty=name> en un patrón "using" (procedimiento recomendado) o mediante una llamada explícita a Dispose o Close cuando ya no se necesita la conexión.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String%2CSystem.Data.SqlClient.SqlCredential)?displayProperty=nameWithType></li></ul>|

