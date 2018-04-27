### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>VB.NET ya no admite la calificación de espacios de nombres parciales para las API de System.Windows

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.5.2, los proyectos de VB.NET ya no pueden especificar API de System.Windows con espacios de nombres parciales. Por ejemplo, se producirá un error al hacer referencia a <code>Windows.Forms.DialogResult</code>. En su lugar, el código debe hacer referencia al nombre completo (<xref:System.Windows.Forms.DialogResult>) o importar el espacio de nombres específico y simplemente hacer referencia a <xref:System.Windows.Forms.DialogResult?displayProperty=name>.|
|Sugerencia|Debería actualizarse el código para hacer referencia a las API <code>System.Windows</code> con nombres simples (e importar el espacio de nombres correspondiente) o con nombres completos.|
|Ámbito|Secundaria|
|Versión|4.5.2|
|Tipo|Redestinación|

