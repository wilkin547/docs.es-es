### <a name="systemuriiswellformeduristring-method-returns-false-for-relative-uris-with-a-colon-char-in-first-segment"></a>El método System.Uri.IsWellFormedUriString devuelve false para los identificadores URI relativos con un carácter de dos puntos en el primer segmento

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.5, <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> tratará los identificadores URI relativos con un <code>:</code> en el primer segmento como mal formados. Se trata de un cambio con respecto al comportamiento de <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=name> en .NET Framework 4.0 que se realizó para cumplir con RFC3986.|
|Sugerencia|Este cambio (como muchos otros cambios de URI) solo afecta a las aplicaciones destinadas a .NET Framework 4.5 (o una versión posterior). Para seguir usando el comportamiento anterior, cambie el destino de la aplicación a .NET Framework 4.0. Como alternativa, examine el URI antes de llamar a <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=name> en busca de caracteres <code>:</code> que se puedan quitar con fines de validación, si quiere el comportamiento anterior.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=nameWithType></li></ul>|

