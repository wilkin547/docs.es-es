### <a name="sqlbulkcopy-uses-destination-column-encoding-for-strings"></a>SqlBulkCopy usa la codificación de columna de destino para las cadenas

|   |   |
|---|---|
|Detalles|Al insertar datos en una columna, <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=name> utiliza la codificación de la columna de destino en lugar de la codificación predeterminada para los tipos <code>VARCHAR</code> y <code>CHAR</code>. Este cambio elimina la posibilidad de que se produzcan daños en los datos al usar la codificación predeterminada cuando la columna de destino no utiliza la codificación predeterminada. En raras ocasiones, una aplicación existente podría iniciar una excepción SqlException si el cambio de codificación genera datos que son demasiado grandes como para caber en la columna de destino.|
|Sugerencia|Espere que <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=name> ya no dañe los datos debido a diferencias de codificación. Si se copian cadenas cerca del límite de tamaño de la columna de destino, puede que sea necesario codificar previamente los datos (que se van a copiar para comprobar que caben en la columna de destino) o capturar las excepciones <xref:System.Data.SqlClient.SqlException?displayProperty=name>.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlBulkCopy.%23ctor(System.Data.SqlClient.SqlConnection)?displayProperty=nameWithType></li></ul>|

