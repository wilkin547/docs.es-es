### <a name="improved-accessibility-for-some-net-sdk-tools"></a>Mejor accesibilidad para algunas herramientas del SDK de .NET

|   |   |
|---|---|
|Detalles|En el SDK de .NET Framework 4.7.1, se han mejorado las herramientas svcconfigedit.exe y svctraceviewer.exe mediante la corrección de varios problemas de accesibilidad. La mayoría eran problemas menores como un nombre sin definir o determinados patrones de automatización de la interfaz de usuario que no se implementaban correctamente. Aunque muchos usuarios no eran conscientes de estos valores incorrectos, los clientes que usan tecnologías de asistencia como lectores de pantalla encontrarán estas herramientas del SDK más accesibles. De hecho, estas correcciones cambian algunos comportamientos anteriores, como el orden del foco del teclado. Para obtener todas las correcciones de accesibilidad en estas herramientas, puede agregar lo siguiente al archivo app.config:<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ámbito|Borde|
|Versión|4.7.1|
|Tipo|Redestinación|

