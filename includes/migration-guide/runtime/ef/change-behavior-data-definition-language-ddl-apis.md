### <a name="change-in-behavior-in-data-definition-language-ddl-apis"></a>Cambio de comportamiento en las API de lenguaje de definición de datos (DDL)

|   |   |
|---|---|
|Detalles|El comportamiento de las API de DDL cuando se especifica AttachDBFilename ha cambiado tal y como se describe a continuación:<ul><li>Las cadenas de conexión no necesitan especificar un valor Initial Catalog. Anteriormente, se necesitaban los valores AttachDBFilename e Initial Catalog.</li><li>Si se especifican los valores AttachDBFilename e Initial Catalog, y existe el archivo MDF indicado, el método ObjectContext.DatabaseExists devuelve true. Anteriormente, pasaba a ser false.</li><li>Si se especifican los valores AttachDBFilename e Initial Catalog, y existe el archivo MDF indicado, al llamar al método ObjectContext.DeleteDatabase se eliminan los archivos.</li><li>Si se llama al método ObjectContext.DeleteDatabase cuando la cadena de conexión especifica un valor de AttachDBFilename con un archivo MDF que no exista y un valor Initial Catalog que tampoco exista, el método inicia una excepción InvalidOperationException. Anteriormente, iniciaba una excepción SqlException.</li></ul>|
|Sugerencia|Estos cambios facilitan la creación de herramientas y aplicaciones que utilizan las API de DDL. Estos cambios pueden afectar a la compatibilidad de las aplicaciones en los escenarios siguientes:<ul><li>El usuario escribe código que ejecuta un comando DROP DATABASE directamente en lugar de llamar al método ObjectContext.DeleteDatabase si ObjectContext.DatabaseExists pasa a ser true. Esto interrumpe el código existente si la base de datos no está asociada pero el archivo MDF existe.</li><li>El usuario escribe código que espera que el método ObjectContext.DeleteDatabase inicie una excepción SqlException en lugar de InvalidOperationException cuando el valor Initial Catalog y el archivo MDF no existan.</li></ul>|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

