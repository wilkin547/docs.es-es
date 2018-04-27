### <a name="icontobitmap-successfully-converts-icons-with-png-frames-into-bitmap-objects"></a>Icon.ToBitmap convierte correctamente los iconos con marcos PNG en objetos de mapa de bits

|   |   |
|---|---|
|Detalles|A partir de las aplicaciones destinadas a .NET Framework 4.6, el método <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> convierte correctamente los iconos con marcos PNG en objetos de mapa de bits. En las aplicaciones destinadas a .NET Framework 4.5.2 y versiones anteriores, el método <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> inicia una excepción <xref:System.ArgumentOutOfRangeException> si el objeto Icon tiene marcos PNG. Este cambio afecta a las aplicaciones recompiladas para tener como destino .NET Framework 4.6 y que implementan un control especial para la excepción <xref:System.ArgumentOutOfRangeException> que se inicia cuando un objeto Icon tiene marcos PNG. Cuando se ejecuta en .NET Framework 4.6, la conversión es correcta, ya no se genera un <xref:System.ArgumentOutOfRangeException> y, por tanto, ya no se invoca el controlador de excepciones.|
|Sugerencia|Si no quiere este comportamiento, puede conservar el comportamiento anterior agregando el elemento siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config:<pre><code class="language-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true&quot; /&gt;&#13;&#10;</code></pre>Si el archivo app.config ya contiene el elemento <code>AppContextSwitchOverrides</code>, el valor nuevo se debe combinar con el atributo value de esta forma:<pre><code class="language-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true;&lt;previous key&gt;=&lt;previous value&gt;&quot; /&gt;&#13;&#10;</code></pre>|
|Ámbito|Secundaria|
|Versión|4.6|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Drawing.Icon.ToBitmap?displayProperty=nameWithType></li></ul>|

