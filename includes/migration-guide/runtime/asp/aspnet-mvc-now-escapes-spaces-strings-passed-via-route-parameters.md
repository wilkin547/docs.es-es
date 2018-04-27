### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a>ASP.NET MVC ahora aplica caracteres de escape a los espacios de las cadenas que se pasan a través de parámetros de ruta

|   |   |
|---|---|
|Detalles|Para cumplir con RFC 2396, ahora se aplican caracteres de escape a los espacios de las rutas de acceso al rellenar parámetros de acción desde una ruta. Por tanto, mientras que <code>/controller/action/some data</code> antes coincidía con la ruta <code>/controller/action/{data}</code> y proporcionaba <code>some data</code> como parámetro de datos, ahora proporciona <code>some%20data</code>.|
|Sugerencia|Debería actualizarse el código para no eliminar las secuencias de escape de los parámetros de las cadenas desde una ruta. Si se necesita el identificador URI original, se puede tener acceso a él con la API <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString.|
|Ámbito|Secundaria|
|Versión|4.5.2|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)?displayProperty=nameWithType></li></ul>|

