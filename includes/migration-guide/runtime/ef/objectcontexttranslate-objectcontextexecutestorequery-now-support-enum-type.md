### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a>Los métodos ObjectContext.Translate y ObjectContext.ExecuteStoreQuery ahora admiten el tipo enum

|   |   |
|---|---|
|Detalles|En .NET Framework 4.0, el parámetro genérico <code>T</code> de los métodos <code>ObjectContext.Translate</code> y <code>ObjectContext.ExecuteStoreQuery</code> no podía ser un tipo enum. Ahora se admite este escenario.|
|Sugerencia|Si se llamaba a un elemento Translate o ExecuteStoreQuery en un tipo enum en .NET Framework 4.0, devolvía "0". Si este era el comportamiento deseado, las llamadas deberían reemplazarse por una constante 0 (o su tipo enum equivalente).|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|

