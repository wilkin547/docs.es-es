### <a name="resolveassemblyreference-task-now-warns-of-dependencies-with-the-wrong-architecture"></a>La tarea ResolveAssemblyReference ahora advierte sobre dependencias con la arquitectura incorrecta

|   |   |
|---|---|
|Detalles|La tarea emite una advertencia, MSB3270, que indica que una referencia o cualquiera de sus dependencias no coincide con la arquitectura de la aplicación. Por ejemplo, esto ocurre si una aplicación compilada con la opción <code>AnyCPU</code> incluye una referencia a x86. Este tipo de escenario podría producir un error de la aplicación en tiempo de ejecución (en este caso, si la aplicación se implementa como un proceso x64).|
|Sugerencia|Existen dos áreas de impacto:<ul><li>Una nueva compilación genera advertencias que no aparecieron al compilar la aplicación con una versión anterior de MSBuild. Sin embargo, dado que la advertencia identifica un posible origen de errores en el runtime, se debe investigar y solucionar.</li><li>Si las advertencias se tratan como errores, la aplicación no se compilará.</li></ul>|
|Ámbito|Secundaria|
|Versión|4.5.1|
|Tipo|Redestinación|

