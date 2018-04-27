### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a>ServiceBase no propaga las excepciones OnStart

|   |   |
|---|---|
|Detalles|En .NET Framework 4.7 y versiones anteriores, las excepciones que se inician en el inicio del servicio no se propagan al autor de la llamada de <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>. A partir de las aplicaciones destinadas a .NET Framework 4.7.1, el entorno de ejecución propaga las excepciones a <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> para los servicios que no se pueden iniciar.|
|Sugerencia|Durante el inicio del servicio, si hay una excepción, se propaga. Esto debería ayudar a diagnosticar casos en los que no se pueden iniciar los servicios. Si no quiere este comportamiento, puede excluirlo si agrega el elemento <AppContextSwitchOverrides> siguiente a la sección <runtime> del archivo de configuración de la aplicación:<pre><code class="language-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true&quot; /&gt;&#13;&#10;</code></pre>Si la aplicación está destinada a una versión anterior a 4.7.1 pero quiere tener este comportamiento, agregue el elemento <AppContextSwitchOverrides> siguiente a la sección <runtime> del archivo de configuración de la aplicación:<pre><code class="language-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false&quot; /&gt;&#13;&#10;</code></pre>|
|Ámbito|Secundaria|
|Versión|4.7.1|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType></li><li><xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType></li></ul>|

