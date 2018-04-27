### <a name="xmlschemaexception-now-sets-line-positions-properly"></a>XmlSchemaException ahora establece correctamente las posiciones de las líneas

|   |   |
|---|---|
|Detalles|Si el valor de <xref:System.Xml.Linq.LoadOptions.SetLineInfo> se pasa al método Load y se produce un error de validación, las propiedades <xref:System.Xml.Schema.XmlSchemaException.LineNumber> y <xref:System.Xml.Schema.XmlSchemaException.LinePosition> contendrán ahora la información de línea.|
|Sugerencia|Se debe actualizar el código de control de excepciones que suponga que <xref:System.Xml.Schema.XmlSchemaException.LineNumber> y <xref:System.Xml.Schema.XmlSchemaException.LinePosition> no se van a establecer, ya que ahora estas propiedades se establecerán correctamente al usar SetLineInfo durante la carga de XML.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|

