### <a name="signedxml-and-encryptedxml-breaking-changes"></a>Cambios importantes en SignedXml y EncryptedXml

|   |   |
|---|---|
|Detalles|En .NET Framework 4.6.2, las revisiones de seguridad de <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=name> y <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=name> generan otros comportamientos en tiempo de ejecución. Por ejemplo,<ul><li>Si un documento tiene varios elementos con el mismo atributo <code>id</code> y una firma está destinada a uno de esos elementos como la raíz de la firma, el documento ahora se considerará no válido.</li><li>Los documentos con algoritmos de transformación de XPath no canónicos en las referencias ahora se consideran no válidos.</li><li>Los documentos con algoritmos de transformación de XSLT no canónicos en las referencias ahora se consideran no válidos.</li><li>Los programas que usen firmas separadas de recurso externo no podrán hacerlo.</li></ul>|
|Sugerencia|Es posible que los desarrolladores quieran revisar el uso de <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> y <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform>, así como los tipos derivados de <xref:System.Security.Cryptography.Xml.Transform>, ya que es posible que un receptor de documentos no pueda procesarlo.|
|Ámbito|Secundaria|
|Versión|4.6.2|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Security.Cryptography.Xml.Transform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform?displayProperty=nameWithType></li></ul>|

