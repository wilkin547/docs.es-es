### <a name="adonet-now-attempts-to-automatically-reconnect-broken-sql-connections"></a>ADO.NET ahora intenta volver a conectar automáticamente las conexiones SQL interrumpidas

|   |   |
|---|---|
|Detalles|A partir de la versión 4.5.1, .NET Framework intentará volver a conectar automáticamente las conexiones SQL interrumpidas. Aunque por lo general esto hará que las aplicaciones sean más confiables, hay casos extremos en los que la aplicación tiene que saber que se perdió la conexión para poder realizar alguna acción al volverse a conectar.|
|Sugerencia|Si por motivos de compatibilidad no quiere esta característica, se puede deshabilitar estableciendo la propiedad <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=name> de una cadena de conexión (o <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=name>) en 0.|
|Ámbito|Borde|
|Versión|4.5.1|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Data.IDbConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Configuration.ConnectionStringSettings.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnectionStringBuilder.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnectionStringBuilder.%23ctor?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnectionStringBuilder.%23ctor(System.Boolean)?displayProperty=nameWithType></li></ul>|

