### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>X509Certificate2.ToString(Boolean) ahora no se inicia cuando .NET no puede controlar el certificado

|   |   |
|---|---|
|Detalles|En .NET Framework 4.5.2 y versiones anteriores, este método iniciaba una excepción si se pasaba <code>true</code> para el parámetro detallado y había certificados instalados no admitidos por .NET Framework. Ahora, el método se realizará correctamente y devolverá una cadena válida que omite las partes inaccesibles del certificado.|
|Sugerencia|Cualquier código que dependa de <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> se debe actualizar para esperar que la cadena devuelta pueda excluir algunos datos del certificado (como la clave pública, la clave privada y las extensiones) en algunos casos en los que anteriormente se habría iniciado la API.|
|Ámbito|Borde|
|Versión|4.6|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|

