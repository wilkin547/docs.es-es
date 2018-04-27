### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a>Los métodos MachineKey.Encode y MachineKey.Decode ahora están obsoletos

|   |   |
|---|---|
|Detalles|Estos métodos están obsoletos. La compilación del código que llama a estos métodos genera una advertencia del compilador.|
|Sugerencia|Las alternativas recomendadas son <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> y <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>. Como alternativa, se pueden suprimir las advertencias de compilación o usar un compilador anterior para evitarlas. Las API siguen siendo compatibles.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li><li><xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li></ul>|

