### <a name="deserialization-of-objects-across-appdomains-can-fail"></a>Se puede producir un error en la deserialización de objetos entre dominios de aplicación

|   |   |
|---|---|
|Detalles|En algunos casos, cuando una aplicación usa dos o más dominios de aplicación con distintas bases de aplicación, un intento de deserializar objetos en el contexto de llamada lógico entre dominios de aplicación produce una excepción.|
|Sugerencia|Vea [Mitigación: Deserialización de objetos en distintos dominios de aplicación](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md).|
|Ámbito|Borde|
|Versión|4.5.1|
|Tipo|Tiempo de ejecución|

