### <a name="glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-45"></a>GlyphRun.ComputeInkBoundingBox() y FormattedText.Extent devuelven otros valores a partir de .NET Framework 4.5

|   |   |
|---|---|
|Detalles|Se efectuaron mejoras en los elementos <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> y <xref:System.Windows.Media.FormattedText.Extent> en .NET Framework 4.5 para solucionar problemas por los que los rectángulos eran demasiado pequeños para los glifos incluidos en algunos casos en .NET Framework 4.0. Como resultado de ello, algunos rectángulos de selección son más grandes a partir de .NET Framework 4.5, por lo que hay ligeras diferencias en el diseño de la IU.|
|Sugerencia|Tenga en cuenta que los rectángulos de selección de algunos glifos ahora son de mayor tamaño. Por lo general, estos cambios mejorarán la presentación y las pruebas de acierto de los rectángulos, pero si se quiere revertir al comportamiento anterior (previo a la versión 4.5 de .NET Framework), puede añadirse la siguiente entrada al archivo app.config:<pre><code class="language-xml">&lt;appsettings&gt;&#13;&#10;&lt;add key=&quot;IncludeAllInkInBoundingBox&quot; value=&quot;false&quot;&gt;&#13;&#10;&lt;/appsettings&gt;&#13;&#10;</code></pre>|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=nameWithType></li><li><xref:System.Windows.Media.FormattedText.Extent?displayProperty=nameWithType></li></ul>|

