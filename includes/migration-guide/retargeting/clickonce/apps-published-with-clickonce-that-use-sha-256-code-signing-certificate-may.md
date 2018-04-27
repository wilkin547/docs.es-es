### <a name="apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a>Puede producirse un error en las aplicaciones publicadas con ClickOnce que usan un certificado de firma de código SHA-256 en Windows 2003

|   |   |
|---|---|
|Detalles|El archivo ejecutable está firmado con SHA-256. Antes se firmaba con SHA1, independientemente de si el certificado de firma de código era SHA-1 o SHA-256. Esto se aplica a lo siguiente:<ul><li>Todas las aplicaciones compiladas con Visual Studio 2012 o versiones posteriores.</li><li>Aplicaciones compiladas con Visual Studio 2010 o versiones anteriores en sistemas con .NET Framework 4.5.</li></ul>Además, si está presente .NET Framework 4.5 o versiones posteriores, el manifiesto de ClickOnce también está firmado con SHA-256 para certificados SHA-256, independientemente de la versión de .NET Framework con la que se compiló.|
|Sugerencia|El cambio al firmar el ejecutable ClickOnce solo afecta a los sistemas Windows Server 2003; requieren que se instale KB 938397. El cambio al firmar el manifiesto con SHA-256, incluso cuando una aplicación tiene como destino .NET Framework 4.0 o versiones anteriores, introduce una dependencia de tiempo de ejecución en .NET Framework 4.5 o una versión posterior.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Redestinación|

