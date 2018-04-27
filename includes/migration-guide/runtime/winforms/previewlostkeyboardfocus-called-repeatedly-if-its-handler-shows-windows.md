### <a name="previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>Se llama repetidas veces a PreviewLostKeyboardFocus si su controlador muestra un cuadro de mensaje de Windows Forms

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.5, si se llama a <code>System.Windows.Forms.MessageBox.Show</code> desde un controlador de <xref:System.Windows.UIElement.PreviewLostKeyboardFocus>, se volverá a activar el controlador al cerrar el cuadro de mensaje, lo que podría generar un bucle infinito de cuadros de mensaje.|
|Sugerencia|Hay dos opciones para solucionar este problema:<ol><li>Se puede evitar llamando a <code>System.Windows.MessageBox.Show</code> en lugar de a <code>System.Windows.Forms.MessageBox.Show</code>.</li><li>Se puede evitar mostrando el cuadro de mensaje desde un controlador de eventos <xref:System.Windows.UIElement.LostKeyboardFocus> (en contraposición a un controlador de eventos <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=name>).</li></ol>|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType></li></ul>|

