### <a name="deadlock-may-result-when-using-reentrant-services"></a>El uso de servicios reentrantes puede producir un interbloqueo

|   |   |
|---|---|
|Detalles|Se puede producir un interbloqueo en un servicio reentrante, lo que restringe las instancias del servicio a un subproceso de ejecución a la vez. Los servicios propensos a sufrir este problema tendrán el atributo <xref:System.ServiceModel.ServiceBehaviorAttribute> siguiente en su código:<pre><code class="language-csharp">[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]&#13;&#10;</code></pre>|
|Sugerencia|Para solucionar este problema, puede seguir estos pasos:<ul><li>Establezca el modo de simultaneidad del servicio en <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> o &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt;. Por ejemplo:</li></ul><pre><code class="language-csharp">[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single)]&#13;&#10;</code></pre><ul><li>Instale la actualización más reciente de .NET Framework 4.6.2 o actualice a una versión posterior de .NET Framework. Esto deshabilita el flujo de <xref:System.Threading.ExecutionContext> en <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>. Este comportamiento se puede configurar; equivale a agregar la configuración de aplicación siguiente al archivo de configuración:</li></ul><pre><code class="language-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&#13;&#10;The value of &#39;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&#39; should never be set to &#39;false&#39; for Rentrant services.&#13;&#10;</code></pre>|
|Ámbito|Secundaria|
|Versión|4.6.2|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType></li></ul>|

