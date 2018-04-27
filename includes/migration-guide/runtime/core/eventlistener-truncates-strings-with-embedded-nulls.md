### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a>EventListener trunca las cadenas con valores NULL insertados

|   |   |
|---|---|
|Detalles|<xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> trunca las cadenas con valores NULL incrustados. Los caracteres NULL no son compatibles con la clase <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name>. El cambio solo afecta a las aplicaciones que usan <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> para leer datos <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> en proceso y que utilizan caracteres NULL como delimitadores.|
|Sugerencia|Se deben actualizar los datos de <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name>, si es posible, para que no usen valores NULL insertados.|
|Ámbito|Borde|
|Versión|4.5.1|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Diagnostics.Tracing.EventListener.%23ctor?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType></li></ul>|

