### <a name="ef-no-longer-throws-for-queryviews-with-specific-characteristics"></a>EF ya no inicia excepciones para elementos QueryView con características específicas

|   |   |
|---|---|
|Detalles|Entity Framework ya no inicia una excepción <xref:System.StackOverflowException?displayProperty=name> cuando una aplicación ejecuta una consulta que usa QueryView con una propiedad de navegación 0..1 que intenta incluir las entidades relacionadas como parte de la consulta. Por ejemplo, mediante una llamada a <code>.Include(e =&gt; e.RelatedNavProp)</code>.|
|Sugerencia|Este cambio solo afecta al código que usa QueryViews con relaciones 1-0..1 cuando se ejecutan consultas que realizan llamadas a .Include. Mejora la fiabilidad y debe ser transparente para casi todas las aplicaciones. Pero puede deshabilitarlo si causa un comportamiento inesperado; para ello, agregue la entrada siguiente a la sección <code>&lt;appSettings&gt;</code> del archivo de configuración de la aplicación:<pre><code class="language-xml">&lt;add key=&quot;EntityFramework_SimplifyUserSpecifiedViews&quot; value=&quot;false&quot; /&gt;&#13;&#10;</code></pre>|
|Ámbito|Borde|
|Versión|4.5.2|
|Tipo|Tiempo de ejecución|

