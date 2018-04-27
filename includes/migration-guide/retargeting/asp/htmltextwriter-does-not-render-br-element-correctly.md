### <a name="htmltextwriter-does-not-render-br-element-correctly"></a>HtmlTextWriter no representa el elemento `<br/>` de forma correcta

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.6, al llamar a <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> y <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> con un elemento <code>&lt;BR /&gt;</code> solo insertará correctamente un <code>&lt;BR /&gt;</code> (en lugar de dos).|
|Sugerencia|Si alguna aplicación dependía de la etiqueta <code>&lt;BR /&gt;</code> adicional, debería llamarse a <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> una segunda vez. Tenga en cuenta que este cambio de comportamiento solo afecta a las aplicaciones que tengan como destino .NET Framework 4.6 o una versión posterior, por lo que otra opción es seleccionar como destino una versión anterior de .NET Framework para conseguir el comportamiento anterior.|
|Ámbito|Borde|
|Versión|4.6|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType></li></ul>|

