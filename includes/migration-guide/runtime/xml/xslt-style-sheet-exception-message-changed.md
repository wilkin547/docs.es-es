### <a name="xslt-style-sheet-exception-message-changed"></a>Cambio del mensaje de excepción de la hoja de estilos XSLT

|   |   |
|---|---|
|Detalles|En .NET Framework 4.5, el texto del mensaje de error cuando un archivo XSLT es demasiado complejo es &quot;The style sheet is too complex&quot; (La hoja de estilos es demasiado compleja). En versiones anteriores, el mensaje de error era &quot;Error de compilación de XSLT&quot;. El código de aplicación que se base en el texto del mensaje de error ya no funcionará. Sin embargo, los tipos de excepción siguen siendo iguales, por lo que este cambio no debería tener ningún impacto real.|
|Sugerencia|Actualice cualquier código de aplicación en función del mensaje de la excepción de esta condición de error para que espere el mensaje nuevo, o bien (e incluso mejor), actualice el código para que solo dependa del tipo de excepción (<xref:System.Xml.Xsl.XsltException?displayProperty=name>), que no ha cambiado.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Type)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Reflection.MethodInfo,System.Byte[],System.Type[])?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li></ul>|

