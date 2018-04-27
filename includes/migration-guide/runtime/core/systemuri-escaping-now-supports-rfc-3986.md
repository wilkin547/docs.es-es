### <a name="systemuri-escaping-now-supports-rfc-3986"></a>La aplicación de secuencias de escape de System.Uri ahora es compatible con RFC 3986

|   |   |
|---|---|
|Detalles|La aplicación de secuencias de escape a los identificadores URI se ha modificado en .NET 4.5 para hacerlo compatible con [RFC 3986](http://tools.ietf.org/html/rfc3986). Cambios concretos:<ul><li>El método <xref:System.Uri.EscapeDataString(System.String)?displayProperty=name> incluye los caracteres reservados entre caracteres de escape de con arreglo a RFC 3986.</li><li>El método <xref:System.Uri.EscapeUriString(System.String)?displayProperty=name> no incluye entre caracteres de escape los caracteres reservados.</li><li>El método <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=name> no inicia una excepción si encuentra una secuencia de escape no válida.</li><li>Los caracteres de escape no reservados no se incluyen en una secuencia de escape.</li></ul>|
|Sugerencia|<ul><li>Actualice las aplicaciones para que no se basen en el inicio de <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=name> en caso de tratarse de secuencias de escape no válidas. Ahora, este tipo de secuencias deben detectarse directamente.</li><li>De igual modo, cabe esperar que los identificadores URI y las cadenas de datos con secuencias de escape y sin ellas varíen entre .NET 4.0 y .NET 4.5, y no deben compararse directamente entre distintas versiones de .NET. En lugar de ello, deben analizarse y normalizarse en una única versión de .NET antes de efectuar cualquier comparación.</li></ul>|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType></li></ul>|

