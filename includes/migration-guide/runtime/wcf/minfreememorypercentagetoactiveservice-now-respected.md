### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a>Ahora se respeta MinFreeMemoryPercentageToActiveService

|   |   |
|---|---|
|Detalles|Este ajuste establece la memoria mínima que debe estar disponible en el servidor para que se pueda activar un servicio WCF. Está diseñado para evitar las excepciones <xref:System.OutOfMemoryException?displayProperty=name>. En .NET Framework 4.5, este ajuste no tenía ningún efecto. En .NET Framework 4.5.1, este ajuste se respeta.|
|Sugerencia|Se produce una excepción si la memoria libre disponible en el servidor web es menor que el porcentaje definido por la opción de configuración. Algunos servicios WCF que se iniciaban y ejecutaban correctamente en un entorno de memoria restringida ahora pueden producir errores.|
|Ámbito|Secundaria|
|Versión|4.5.1|
|Tipo|Tiempo de ejecución|

