### <a name="foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a>La variable de iterador Foreach ahora tiene como ámbito la iteración, por lo que la semántica de captura de clausura es diferente (en C#5)

|   |   |
|---|---|
|Detalles|A partir de C#5 (Visual Studio 2012), las variables de iterador <code>foreach</code> tienen como ámbito la iteración. Esto puede provocar interrupciones si el código dependía anteriormente de que las variables no se incluyeran en la clausura de <code>foreach</code>. El síntoma de este cambio es que una variable de iterador que se pasa a un delegado se trata como el valor que tiene en el momento de creación del delegado, en lugar de como el valor que tiene en el momento de invocarlo.|
|Sugerencia|Lo ideal sería actualizar el código para que espere el nuevo comportamiento del compilador. Si es necesario usar la semántica anterior, es posible reemplazar la variable de iterador por una variable independiente colocada de forma explícita fuera del ámbito del bucle.|
|Ámbito|Major|
|Versión|4.5|
|Tipo|Redestinación|

