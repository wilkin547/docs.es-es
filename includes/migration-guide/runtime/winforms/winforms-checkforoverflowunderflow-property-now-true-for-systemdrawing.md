### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>La propiedad CheckForOverflowUnderflow de WinForm ahora es true para System.Drawing

|   |   |
|---|---|
|Detalles|La propiedad CheckForOverflowUnderflow para el ensamblado System.Drawing.dll se establece en true.|
|Sugerencia|Anteriormente, cuando se producían desbordamientos, el resultado se truncaba de manera silenciosa. Ahora se inicia una excepción <xref:System.OverflowException?displayProperty=name>.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

