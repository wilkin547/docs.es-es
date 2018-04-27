### <a name="wpf-printing-stack-update"></a>Actualización de la pila de impresión de WPF

|   |   |
|---|---|
|Detalles|Las API de impresión de WPF en las que se usa <xref:System.Printing.PrintQueue?displayProperty=name> ahora llaman a la API Print Document Package de Windows en lugar de la API XPS Print, que está en desuso. El cambio se realizó con la facilidad en mente; ni los usuarios ni los desarrolladores deberían percibir cambios en el comportamiento o el uso de la API. La nueva pila de impresión está habilitada de forma predeterminada cuando se ejecuta en Windows 10 Creators Update. La pila de impresión antigua seguirá funcionando como antes en las versiones anteriores de Windows.|
|Sugerencia|Para usar la pila antigua en Windows 10 Creators Update, establezca el valor <code>UseXpsOMPrinting</code> REG_DWORD de la clave del Registro <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> en <code>1</code>.|
|Ámbito|Borde|
|Versión|4.7|
|Tipo|Tiempo de ejecución|

