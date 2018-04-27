### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a>Los cuadros de texto de WPF tienen como valor predeterminado un límite de 100 para la fase de reversión

|   |   |
|---|---|
|Detalles|En .NET Framework 4.5, el límite para la fase de reversión de un cuadro de texto de WPF es de 100 (a diferencia de .NET Framework 4.0, donde no existía ningún límite).|
|Sugerencia|Si el límite de 100 para la fase de reversión es demasiado bajo, se puede establecer de forma explícita con <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit>.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|

