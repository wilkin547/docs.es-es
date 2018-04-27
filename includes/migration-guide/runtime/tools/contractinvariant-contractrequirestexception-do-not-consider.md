### <a name="contractinvariant-or-contractrequirestexception-do-not-consider-stringisnullorempty-to-be-pure"></a>Contract.Invariant o Contract.Requires<TException> no consideran que String.IsNullOrEmpty sea puro

|   |   |
|---|---|
|Detalles|Para las aplicaciones que tienen como destino .NET Framework 4.6.1, si el contrato invariable para <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> o el contrato de condición previa para <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> llama al método <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType>, el sistema de reescritura emite la advertencia del compilador CC1036: &quot;Se detectó llamada al método "System.String.IsNullOrWhiteSpace(System.String)" sin [Pure] en el método&quot;. Se trata de una advertencia del compilador en lugar de un error del compilador.|
|Sugerencia|Este comportamiento se solucionó en [Problema de GitHub #339](https://github.com/Microsoft/CodeContracts/issues/339). Para eliminar esta advertencia, puede descargar y compilar una versión actualizada del código fuente para la herramienta Contratos de código desde [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md). La información de descarga se encuentra en la parte inferior de la página.|
|Ámbito|Secundaria|
|Versión|4.6.1|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)?displayProperty=nameWithType></li></ul>|

