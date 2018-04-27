### <a name="il-ret-not-allowed-in-a-try-region"></a>No se permite ret de IL en una región try

|   |   |
|---|---|
|Detalles|A diferencia del compilador Just-In-Time JIT64, RyuJIT (que se usa en .NET 4.6) no admite una instrucción ret de nivel de integridad en una región try. Devolver desde una región try no permite la especificación de ECMA-335 y ningún compilador administrado conocido genera tal IL. Sin embargo, el compilador JIT64 ejecutará dicho IL si se genera mediante la emisión de reflexión.|
|Sugerencia|Si una aplicación genera un IL que incluye un código de operación de ret en una región try, la aplicación puede tener como destino .NET 4.5 para usar el JIT antiguo y evitar esta interrupción. Como alternativa, se puede actualizar el IL generado para que devuelva después de la región try.|
|Ámbito|Borde|
|Versión|4.6|
|Tipo|Redestinación|

