### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a>ClickOnce admite SHA-256 en aplicaciones destinadas a la versión 4.0

|   |   |
|---|---|
|Detalles|Anteriormente, una aplicación ClickOnce con un certificado firmado con SHA-256 requería la presencia de .NET 4.5 o una versión posterior, incluso si la aplicación se destinaba a la versión 4.0. Ahora, las aplicaciones ClickOnce destinadas a la versión 4.0 se pueden ejecutar en 4.0, incluso si están firmadas con SHA-256.|
|Sugerencia|Este cambio elimina esa dependencia y permite usar certificados de SHA-256 para firmar las aplicaciones ClickOnce que tienen como destino .NET Framework 4 y versiones anteriores.|
|Ámbito|Secundaria|
|Versión|4.6|
|Tipo|Redestinación|

