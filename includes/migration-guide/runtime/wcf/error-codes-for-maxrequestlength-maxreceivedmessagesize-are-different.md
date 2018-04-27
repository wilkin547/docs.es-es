### <a name="error-codes-for-maxrequestlength-or-maxreceivedmessagesize-are-different"></a>Los códigos de error para maxRequestLength o maxReceivedMessageSize son diferentes

|   |   |
|---|---|
|Detalles|Los mensajes de servicios web de WCF hospedados en Internet Information Services (IIS) o Servidor de desarrollo de ASP.NET que superan maxRequestLength (en ASP.NET) o maxReceivedMessageSize (en WCF) tienen otro código de error. El código de estado HTTP ha cambiado de 400 (Solicitud incorrecta) a 413 (Entidad de solicitud demasiado grande), y los mensajes que superan el valor maxRequestLength o maxReceivedMessageSize inician una excepción <xref:System.ServiceModel.ProtocolException?displayProperty=name>. Esto incluye los casos en los que el modo de transferencia es Streamed.|
|Sugerencia|Este cambio facilita la depuración en casos donde la longitud del mensaje supera los límites permitidos por ASP.NET o WCF. Debe modificar cualquier código que realice el procesamiento en función de un código de estado HTTP 400.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

