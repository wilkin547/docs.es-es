---
title: Soporte de almacenamiento en memoria caché para servicios web HTTP de WCF
ms.date: 03/30/2017
ms.assetid: 7f8078e0-00d9-415c-b8ba-c1b6d5c31799
ms.openlocfilehash: 63c83cc1af9a3ccfdbdd79f8d0480e6c29eaf2f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185426"
---
# <a name="caching-support-for-wcf-web-http-services"></a>Soporte de almacenamiento en memoria caché para servicios web HTTP de WCF

[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]le permite usar el mecanismo de almacenamiento en caché declarativo ya disponible en ASP.NET en los servicios HTTP Web WCF. Esto le permite almacenar en memoria caché las respuestas de las operaciones de servicio Web HTTP de WCF. Cuando un usuario envía un protocolo HTTP GET al servicio que está configurado para almacenarlo en memoria caché, ASP.NET devuelve la respuesta almacenada en memoria caché y no se llama al método de servicio. Cuando la memoria caché expira, la próxima vez que un usuario envía un protocolo HTTP GET, se llama al método de servicio y la respuesta se vuelve a almacenar en memoria caché. Para obtener más información sobre el almacenamiento en caché ASP.NET, consulte Información general sobre almacenamiento en [caché ASP.NET.](https://docs.microsoft.com/previous-versions/aspnet/ms178597(v=vs.100))  
  
## <a name="basic-web-http-service-caching"></a>Almacenamiento en memoria caché básico del servicio Web HTTP  

  Para habilitar el almacenamiento en caché del servicio HTTP WEB, primero <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute.RequirementsMode%2A> debe <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>habilitar ASP.NET compatibilidad aplicando la <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> configuración de servicio a o .  
  
 .NET Framework 4 presenta un <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> nuevo atributo llamado que le permite especificar un nombre de perfil de caché. Este atributo se aplica a una operación del servicio. El siguiente ejemplo aplica <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> a un servicio para habilitar la compatibilidad de ASP.NET y configura la operación `GetCustomer` para almacenar en memoria caché. El atributo <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> especifica un perfil de memoria caché que contiene la configuración de memoria caché que se va a utilizar.  
  
```csharp
[ServiceContract]
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]
public class Service
{
    [WebGet(UriTemplate = "{id}")]
    [AspNetCacheProfile("CacheFor60Seconds")]
    public Customer GetCustomer(string id)
    {
        // ...
    }
}
```  
  
Active también ASP.NET modo de compatibilidad en el archivo Web.config como se muestra en el ejemplo siguiente.  
  
```xml
<system.serviceModel>
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
</system.serviceModel>
```
  
> [!WARNING]
> Si no se activa el modo de compatibilidad de ASP.NET y se utiliza <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, se produce una excepción.  
  
 El nombre de perfil de memoria caché especificado por <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> identifica un perfil de memoria caché agregado al archivo de configuración Web.config. El perfil de caché se `outputCacheSetting` define con en un <> elemento como se muestra en el siguiente ejemplo de configuración.  
  
```xml
<!-- ...  -->
<system.web>  
   <caching>  
      <outputCacheSettings>  
         <outputCacheProfiles>  
            <add name="CacheFor60Seconds" duration="60" varyByParam="none" sqlDependency="MyTestDatabase:MyTable"/>  
         </outputCacheProfiles>  
      </outputCacheSettings>  
   </caching>  
   <!-- ... -->  
</system.web>  
```  
  
 Éste es el mismo elemento de configuración que está disponible para las aplicaciones ASP.NET. Para obtener más información acerca <xref:System.Web.Configuration.OutputCacheProfile>de ASP.NET perfiles de caché, consulte . Para los servicios Web HTTP, los atributos más importantes del perfil de la memoria caché son: `cacheDuration` y `varyByParam`. Se necesitan ambos atributos. `cacheDuration` establece la cantidad de tiempo que una respuesta se debe almacenar en memoria caché en segundos. `varyByParam` permite especificar un parámetro de cadena de consulta que se usa para almacenar en memoria caché las respuestas. Todas las solicitudes realizadas con valores de parámetro de cadena de consulta diferentes se almacenan en memoria caché por separado. Por ejemplo, una vez que `http://MyServer/MyHttpService/MyOperation?param=10`se realiza una solicitud inicial, todas las solicitudes posteriores realizadas con el mismo URI se devolverán la respuesta almacenada en caché (siempre que no haya transcurrido la duración de la memoria caché). Las respuestas para una solicitud similar que es igual pero tiene un valor diferente para el parámetro de cadena de consulta de parámetros se almacenan en la memoria caché por separado. Si no desea este comportamiento de almacenamiento en caché por separado, establezca `varyByParam` en "none".  
  
## <a name="sql-cache-dependency"></a>Dependencia de memoria caché de SQL  

  Las respuestas del servicio Web HTTP también pueden estar almacenadas en memoria caché con una dependencia de memoria caché de SQL. Si el servicio Web HTTP de WCF depende de los datos almacenados en una base de datos SQL, puede que desee almacenar en memoria caché la respuesta del servicio e invalidar la respuesta almacenada en memoria caché cuando se produzcan cambios en los datos de tabla de base de datos SQL. Este comportamiento se configura completamente en el archivo Web.config. En primer lugar, defina `connectionStrings` una cadena de conexión en el <> elemento.  
  
```xml
<connectionStrings>
  <add name="connectString"
       connectionString="Data Source=MyService;Initial Catalog=MyTestDatabase;Integrated Security=True"
       providerName="System.Data.SqlClient" />
</connectionStrings>
```  
  
 A continuación, debe habilitar la `caching` dependencia de `system.web` caché SQL dentro de un elemento> <dentro del elemento> de <, como se muestra en el siguiente ejemplo de configuración.  
  
```xml  
<system.web>
  <caching>
    <sqlCacheDependency enabled="true" pollTime="1000">
      <databases>
        <add name="MyTestDatabase" connectionStringName="connectString" />
      </databases>
    </sqlCacheDependency>
    <!-- ... -->
  </caching>
  <!-- ... -->
</system.web>
```  
  
 Aquí, la dependencia de memoria caché de SQL está habilitada y se establece un tiempo de sondeo de 1.000 milisegundos. Cada vez que el tiempo de sondeo transcurre, se comprueba la tabla de la base de datos para detectar actualizaciones. Si se detectan cambios, se quita el contenido de la memoria caché y la próxima vez que se invoque la operación del servicio, se almacenará en memoria caché una nueva respuesta. Dentro del `sqlCacheDependency` <> elemento agregue las bases `databases` de datos y haga referencia a las cadenas de conexión dentro del <> elemento como se muestra en el ejemplo siguiente.  
  
```xml  
<system.web>
  <caching>
    <sqlCacheDependency enabled="true" pollTime="1000">
      <databases>
        <add name="MyTestDatabase" connectionStringName="connectString" />
      </databases>  
    </sqlCacheDependency>  
    <!-- ... -->  
  </caching>  
  <!-- ... -->  
</system.web>  
```  
  
 A continuación, debe configurar la `caching` configuración de la caché de salida dentro del elemento <> como se muestra en el ejemplo siguiente.  
  
```xml
<system.web>
  <caching>  
    <!-- ...  -->
    <outputCacheSettings>
      <outputCacheProfiles>
        <add name="CacheFor60Seconds" duration="60" varyByParam="none" sqlDependency="MyTestDatabase:MyTable" />
      </outputCacheProfiles>
    </outputCacheSettings>
  </caching>
  <!-- ... -->
</system.web>
```  
  
 Aquí la duración de la memoria `varyByParam` caché se establece `sqlDependency` en 60 segundos, se establece en none y se establece en una lista delimitada por punto y coma de pares de nombre/tabla de base de datos separados por dos puntos. Cuando los datos de `MyTable` se cambian, se elimina la respuesta almacenada en memoria caché para la operación del servicio y, cuando se invoca la operación, la nueva respuesta se genera (llamando a la operación del servicio), se almacena en memoria caché y se devuelve al cliente.  
  
> [!IMPORTANT]
> Para ASP.NET tener acceso a una base de datos SQL, debe usar [la ASP.NET herramienta](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms229862(v=vs.90))de registro de SQL Server . Además, debe permitir el acceso de la cuenta de usuario correspondiente tanto a la base de datos como a la tabla. Para obtener más información, vea [Acceso a SQL Server desde una aplicación web](https://docs.microsoft.com/previous-versions/aspnet/ht43wsex(v=vs.100)).  
  
## <a name="conditional-http-get-based-caching"></a>Almacenamiento en memoria caché basado en HTTP GET condicional  

  En escenarios WEB HTTP, los servicios suelen utilizar un HTTP GET condicional para implementar el almacenamiento en caché HTTP inteligente como se describe en la [especificación HTTP.](https://www.w3.org/Protocols/rfc2616/rfc2616.html) Para ello, el servicio debe establecer el valor del encabezado ETag en la respuesta HTTP. También debe comprobar el encabezado If-None-Match en la solicitud HTTP para ver si alguno de los ETag especificados coincide con el ETag actual.  
  
 Para las solicitudes GET y HEAD, <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> toma un valor de ETag y lo comprueba con respecto al encabezado If-None-Match de la solicitud. Si el encabezado está presente y <xref:System.ServiceModel.Web.WebFaultException> hay una coincidencia, se produce un código de estado HTTP 304 (No modificado) y se agrega un encabezado ETag a la respuesta con el ETag coincidente.  
  
 Una sobrecarga del método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> toma la última fecha modificada y la compara con el encabezado If-Modified-Since de la solicitud. Si el encabezado está presente y el recurso no se ha modificado desde entonces, se produce <xref:System.ServiceModel.Web.WebFaultException> con un código de estado HTTP 304 (No modificado).  
  
 Para las solicitudes PUT, POST y DELETE, <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> toma el valor de ETag actual de un recurso. Si el valor actual de ETag es null, el método comprueba que el encabezado If-None- Match tiene un valor de "*".  Si el valor de ETag actual no es un valor predeterminado, el método comprueba el valor de ETag actual con respecto al encabezado If-Match de la solicitud. En cualquier caso, el método produce <xref:System.ServiceModel.Web.WebFaultException> con un código de estado HTTP 412 (Error de condición previa) si el encabezado esperado no se encuentra en la solicitud o si su valor no satisface la comprobación condicional y establece el encabezado de ETag de la respuesta al valor de ETag actual.  
  
 Tanto los métodos `CheckConditional` como el método <xref:System.ServiceModel.Web.OutgoingWebResponseContext.SetETag%2A> garantizan que el valor de ETag definido en el encabezado de respuesta es un ETag válido según la especificación de HTTP. Esto incluye la delimitación del valor de ETag con comillas dobles si aún no están presentes y el escape correspondiente de cualquier carácter interno de comillas dobles. No se admite la comparación de ETag débil.  
  
 En el siguiente ejemplo, se muestra cómo utilizar estos métodos.  
  
```csharp
[WebGet(UriTemplate = "{id}"), Description("Returns the specified customer from customers collection. Returns NotFound if there is no such customer. Supports conditional GET.")]
public Customer GetCustomer(string id)
{
    lock (writeLock)
    {
        // return NotFound if there is no item with the specified id.
        object itemEtag = customerEtags[id];
        if (itemEtag == null)
        {
            throw new WebFaultException(HttpStatusCode.NotFound);
        }
  
        // return NotModified if the client did a conditional GET and the customer item has not changed
        // since when the client last retrieved it
        WebOperationContext.Current.IncomingRequest.CheckConditionalRetrieve((long)itemEtag);
        Customer result = this.customers[id] as Customer;

        // set the customer etag before returning the result
        WebOperationContext.Current.OutgoingResponse.SetETag((long)itemEtag);
        return result;
    }
}
```  
  
## <a name="security-considerations"></a>Consideraciones sobre la seguridad  
 Las solicitudes que requieren autorización no deberían tener sus respuestas almacenadas en memoria caché, porque la autorización no se realiza cuando la respuesta se sirve desde la memoria caché.  Si se almacena en memoria caché tales respuestas, se introduce una vulnerabilidad de seguridad grave.  Normalmente, las solicitudes que requieren autorización proporcionan los datos específicos del usuario y, por consiguiente, el almacenamiento en caché del lado servidor no es beneficioso.  En tales situaciones, será más apropiado usar el almacenamiento en caché del lado cliente o, simplemente, no usar el almacenamiento en memoria caché.
