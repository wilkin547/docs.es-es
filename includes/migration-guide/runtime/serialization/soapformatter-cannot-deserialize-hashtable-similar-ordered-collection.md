### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a>SoapFormatter no puede deserializar elementos Hashtable ni otros objetos de colecciones ordenados similares

|   |   |
|---|---|
|Detalles|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> no garantiza que los objetos serializados en una versión de .NET Framework se deserialicen correctamente en otra versión. En concreto, en algunas colecciones ordenadas (como <xref:System.Collections.Hashtable?displayProperty=name>) se agregaron miembros entre las versiones 4.0 y 4.5, de modo que los objetos de estos tipos no se pueden deserializar con .NET 4.0 si se serializaron con .NET 4.5. Si los datos se serializaron y deserializaron con la misma versión de .NET Framework, no ocurrirá ningún problema.|
|Sugerencia|La serialización de <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> se debe reemplazar por la de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> o <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> para que sea resistente a los cambios de .NET Framework.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType></li></ul>|

