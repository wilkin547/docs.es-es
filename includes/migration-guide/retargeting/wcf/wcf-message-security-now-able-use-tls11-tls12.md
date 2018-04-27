### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a>La seguridad de los mensajes de WCF ahora puede usar TLS1.1 y TLS1.2

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.7, los clientes pueden configurar TLS1.1 o TLS1.2 en la seguridad de los mensajes de WCF además de SSL3.0 y TLS1.0 a través de ajustes de configuración de la aplicación.|
|Sugerencia|En .NET Framework 4.7, la compatibilidad con TLS1.1 y TLS1.2 en la seguridad de los mensajes de WCF está deshabilitada de forma predeterminada. Se puede habilitar si se agrega la línea siguiente a la sección <code>&lt;runtime&gt;</code> del archivo app.config o web.config:<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ámbito|Borde|
|Versión|4.7|
|Tipo|Redestinación|

