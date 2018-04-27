### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a>TextBox.Text de WPF se puede desincronizar con el enlace de datos

|   |   |
|---|---|
|Detalles|En algunos casos, la propiedad <xref:System.Windows.Controls.TextBox.Text> refleja un valor anterior al valor de propiedad de enlace de datos si la propiedad se modifica durante una operación de escritura de enlace de datos.|
|Sugerencia|Esto no debería tener ningún impacto negativo. Sin embargo, puede restaurar el comportamiento anterior estableciendo la propiedad <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> en <code>false</code>.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType></li></ul>|

