### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a>Se puede producir un error en las deserialización de los objetos MailMessage serializados en .NET Framework 4.5

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.5, los objetos <xref:System.Web.Mail.MailMessage> pueden incluir caracteres que no sean ASCII. En .NET Framework 4, solo se admiten caracteres ASCII. Los objetos <xref:System.Web.Mail.MailMessage> que contienen caracteres que no son ASCII y que están serializados en .NET Framework 4.5 o una versión posterior no se pueden deserializar en .NET Framework 4.|
|Sugerencia|Asegúrese de que el código proporciona control de excepciones al deserializar un objeto <xref:System.Web.Mail.MailMessage>.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Web.Mail.MailMessage?displayProperty=nameWithType></li></ul>|

