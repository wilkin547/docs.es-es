### <a name="stack-traces-obtained-when-using-portable-pdbs-now-include-source-file-and-line-information-if-requested"></a>Los seguimientos de la pila obtenidos al usar archivos PDB portátiles ahora incluyen información del archivo y la línea de origen si se solicita

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.7.2, los seguimientos de la pila obtenidos al usar archivos PDB portátiles incluyen información del archivo y la línea de origen cuando se solicita. En las versiones anteriores a .NET Framework 4.7.2, la información del archivo y la línea de origen no estaba disponible al usar archivos PDB portátiles incluso si se solicitaba de forma explícita.|
|Sugerencia|Para las aplicaciones que tienen como destino .NET Framework 4.7.2, se puede rechazar la información del archivo y la línea de origen cuando se usan archivos PDB portátiles si no es adecuada mediante la adición de lo siguiente a la sección <code>&lt;runtime&gt;</code> del archivo <code>app.config</code>:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Para las aplicaciones que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en .NET Framework 4.7.2 o versiones posteriores, se puede incluir la información del archivo y la línea de origen cuando se usan archivos PDB portátiles si se agrega lo siguiente a la sección <code>&lt;runtime&gt;</code> del archivo <code>app.config</code>:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Diagnostics.IgnorePortablePDBsInStackTraces=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ámbito|Borde|
|Versión|4.7.2|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Diagnostics.StackTrace.%23ctor(System.Boolean)?displayProperty=nameWithType></li><li>`System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Boolean)`<li><xref:System.Diagnostics.StackTrace.%23ctor(System.Exception,System.Int32,System.Boolean)?displayProperty=nameWithType></li></ul>|

