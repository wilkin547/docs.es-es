### <a name="certificate-eku-oid-validation"></a>Validación de OID de EKU de certificado

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.6, las clases <xref:System.Net.Security.SslStream> o <xref:System.Net.ServicePointManager> realizan la validación de identificador de objetos (OID) de uso mejorado de clave (EKU). Una extensión de uso mejorado de clave (EKU) es una colección de identificadores de objetos (OID) que indica las aplicaciones que usan la clave. En la validación de OID de EKU se usan devoluciones de llamada de certificado remoto para asegurarse de que el certificado remoto tiene los OID correctos para el propósito previsto.|
|Sugerencia|Si no quiere este cambio, puede deshabilitar la validación de OID de EKU del certificado mediante la adición del modificador siguiente a [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) a la [`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Net.DontCheckCertificateEKUs=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre> <blockquote> [!IMPORTANT] Este valor solamente se proporciona por motivos de compatibilidad con versiones anteriores. Pero no se recomienda su uso.</blockquote> |
|Ámbito|Secundaria|
|Versión|4.6|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Net.Security.SslStream?displayProperty=nameWithType></li><li><xref:System.Net.ServicePointManager?displayProperty=nameWithType></li><li><xref:System.Net.Http.HttpClient?displayProperty=nameWithType></li><li><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType></li><li><xref:System.Net.HttpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.FtpWebRequest?displayProperty=nameWithType></li></ul>|

