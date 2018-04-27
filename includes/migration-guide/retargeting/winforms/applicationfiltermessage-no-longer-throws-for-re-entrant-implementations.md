### <a name="applicationfiltermessage-no-longer-throws-for-re-entrant-implementations-of-imessagefilterprefiltermessage"></a>Ya no se inicia Application.FilterMessage para las implementaciones reentrantes de IMessageFilter.PreFilterMessage

|   |   |
|---|---|
|Detalles|Antes de .NET Framework 4.6.1, la llamada a <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> con <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)> que llamaba a <xref:System.Windows.Forms.Application.AddMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=name> o <xref:System.Windows.Forms.Application.RemoveMessageFilter(System.Windows.Forms.IMessageFilter)?displayProperty=name> (a la vez que llamaba a <xref:System.Windows.Forms.Application.DoEvents>) iniciaba una excepción <xref:System.IndexOutOfRangeException?displayProperty=name>. A partir de las aplicaciones destinadas a .NET Framework 4.6.1, esta excepción ya no se inicia y se pueden usar los filtros reentrantes como se describe anteriormente.|
|Sugerencia|Tenga en cuenta que <xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)> ya no se iniciará para el comportamiento de <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage(System.Windows.Forms.Message@)> reentrantes descrito anteriormente. Esto solo afecta a las aplicaciones destinadas a .NET Framework 4.6.1. Es posible desactivar este cambio en las aplicaciones destinadas a .NET Framework 4.6.1 (o activarlo en las que tengan como destino versiones anteriores de .NET Framework) mediante el modificador de compatibilidad [DontSupportReentrantFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md#mitigation).|
|Ámbito|Borde|
|Versión|4.6.1|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message@)?displayProperty=nameWithType></li></ul>|

