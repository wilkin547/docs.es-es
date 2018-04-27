### <a name="signedxmlgetpublickey-returns-rsacng-on-net462-or-lightup-without-retargeting-change"></a>SignedXml.GetPublicKey devuelve RSACng en net462 (o Lightup) sin cambios de redestinación

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.6.2, se ha cambiado (sin peculiaridades) el tipo concreto del objeto devuelto por el método <xref:System.Security.Cryptography.Xml.SignedXml.GetPublicKey%2A?displayProperty=nameWithType> de una implementación de CryptoServiceProvider a una implementación de Cng. Esto se debe a que la implementación ha pasado de usar <code>certificate.PublicKey.Key</code> a usar la <code>certificate.GetAnyPublicKey</code> interna que reenvía a <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=nameWithType>.|
|Sugerencia|A partir de las aplicaciones que se ejecutan en .NET Framework 4.7.1, se puede usar la implementación de CryptoServiceProvider que se usa de forma predeterminada en .NET Framework 4.6.1 y versiones anteriores mediante la adición del conmutador siguiente a la sección [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:<pre><code class="language-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.Xml.SignedXmlUseLegacyCertificatePrivateKey=true&quot; /&gt;&#13;&#10;</code></pre>|
|Ámbito|Borde|
|Versión|4.6.2|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Security.Cryptography.Xml.SignedXml.CheckSignatureReturningKey(System.Security.Cryptography.AsymmetricAlgorithm@)?displayProperty=nameWithType></li></ul>|

