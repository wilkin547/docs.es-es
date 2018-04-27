### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a>Los catálogos de MEF implementan IEnumerable y, por tanto, ya no se pueden usar para crear un serializador

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.5, los catálogos de MEF implementan IEnumerable y, por tanto, ya no se pueden usar para crear un serializador (un objeto <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name>). Al intentar serializar un catálogo de MEF se inicia una excepción.|
|Sugerencia|Ya no se puede usar MEF para crear un serializador.|
|Ámbito|Major|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

