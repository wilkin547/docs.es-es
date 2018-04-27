### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a>Ya no se puede establecer EnableViewStateMac en false

|   |   |
|---|---|
|Detalles|ASP.NET ya no permite a los desarrolladores especificar <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> o <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>. El código de autenticación de mensajes (MAC) de estado de vista ahora es obligatorio para todas las solicitudes con estado de vista integrado. Solo afecta a las aplicaciones en las que la propiedad EnableViewStateMac esté establecida específicamente en <code>false</code>.|
|Sugerencia|Se debe suponer que EnableViewStateMac se establece en true y se debe resolver cualquier error de MAC resultante (como se explica en [esta guía](https://support.microsoft.com/kb/2915218), que contiene varias resoluciones en función de la causa específica de los errores de MAC).|
|Ámbito|Major|
|Versión|4.5.2|
|Tipo|Tiempo de ejecución|

