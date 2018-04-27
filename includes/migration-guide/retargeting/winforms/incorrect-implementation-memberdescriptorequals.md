### <a name="incorrect-implementation-of-memberdescriptorequals"></a>Implementación incorrecta de MemberDescriptor.Equals

|   |   |
|---|---|
|Detalles|En la implementación original del método &quot;Equals&quot; se comparaban dos propiedades de cadena diferentes de los objetos comparados: el nombre de la categoría con la cadena de descripción. La solución consiste en comparar la &quot;categoría&quot; del primer objeto con la &quot;categoría&quot; del segundo y &quot;descripción&quot; con &quot;descripción&quot;. El valor de configuración de MemberDescriptorEqualsReturnsFalseIfEquivalent se puede establecer en true para descartar el comportamiento nuevo si el destino es 4.6.2, o bien en false para habilitar esta corrección cuando la versión de la plataforma de destino es inferior a la 4.6.2.|
|Sugerencia|Si la aplicación depende de que MemberDescriptor.Equals a veces devuelva false cuando los descriptores son equivalentes, y el destino es la versión 4.6.2 de .NET Framework, tiene varias opciones:<ol><li>Realizar cambios de código para comparar manualmente los campos &quot;categoría&quot; y &quot;descripción&quot; además de ejecutar el método Equals.</li><li>Excluir este cambio mediante la adición del valor siguiente al archivo app.config:</li></ol><pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Si la aplicación está destinada a .NET Framework 4.6.1 o una versión anterior, y quiere deshabilitar este cambio, puede establecer el modificador de compatibilidad en false mediante la adición del valor siguiente al archivo app.config:<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ámbito|Borde|
|Versión|4.6.2|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType></li></ul>|

