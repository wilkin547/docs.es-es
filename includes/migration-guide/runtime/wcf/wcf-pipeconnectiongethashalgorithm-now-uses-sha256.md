### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a>En PipeConnection.GetHashAlgorithm de WCF ahora se usa SHA256

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.7.1, Windows Communication Foundation usa un código hash SHA256 para generar nombres aleatorios para las canalizaciones con nombre. En .NET Framework 4.7 y versiones anteriores, usaba un hash SHA1.|
|Sugerencia|Si tiene problemas de compatibilidad con este cambio en .NET Framework 4.7.1 o una versión posterior, puede excluirlo mediante la adición de la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config:<pre><code class="language-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ámbito|Secundaria|
|Versión|4.7.1|
|Tipo|Tiempo de ejecución|

