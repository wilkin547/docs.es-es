### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a>No se puede intentar una conexión TCP/IP a una base de datos de SQL Server que se resuelve en `localhost`

|   |   |
|---|---|
|Detalles|En .NET Framework 4.6 y 4.6.1, el intento de una conexión TCP/IP a una base de datos de SQL Server que se resuelve en <code>localhost</code> produce el error &quot;Error relacionado con la red o específico de la instancia mientras se establecía una conexión con el servidor SQL Server. No se encontró el servidor o éste no estaba accesible. Compruebe que el nombre de la instancia es correcto y que SQL Server está configurado para admitir conexiones remotas. (proveedor: interfaces de red de SQL, error: 26 - Error al buscar el servidor o instancia especificado)&quot;|
|Sugerencia|Este problema se ha resuelto y se ha restaurado el comportamiento anterior, en .NET Framework 4.6.2. Para conectarse a una base de datos de SQL Server que se resuelve en <code>localhost</code>, actualice a .NET Framework 4.6.2.|
|Ámbito|Secundaria|
|Versión|4.6|
|Tipo|Tiempo de ejecución|

