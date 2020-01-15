---
title: Soporte de almacenamiento en memoria caché para servicios web HTTP de WCF
ms.date: 03/30/2017
ms.assetid: 7f8078e0-00d9-415c-b8ba-c1b6d5c31799
ms.openlocfilehash: 5964c58ce28f67815774741815bba0fcbe3b2de7
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964232"
---
# <a name="caching-support-for-wcf-web-http-services"></a><span data-ttu-id="893f5-102">Soporte de almacenamiento en memoria caché para servicios web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="893f5-102">Caching Support for WCF Web HTTP Services</span></span>

[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="893f5-103">le permite usar el mecanismo de almacenamiento en caché declarativo que ya está disponible en ASP.NET en los servicios Web HTTP de WCF.</span><span class="sxs-lookup"><span data-stu-id="893f5-103">enables you to use the declarative caching mechanism already available in ASP.NET in your WCF Web HTTP services.</span></span> <span data-ttu-id="893f5-104">Esto le permite almacenar en memoria caché las respuestas de las operaciones de servicio Web HTTP de WCF.</span><span class="sxs-lookup"><span data-stu-id="893f5-104">This allows you to cache responses from your WCF Web HTTP service operations.</span></span> <span data-ttu-id="893f5-105">Cuando un usuario envía un protocolo HTTP GET al servicio que está configurado para almacenarlo en memoria caché, ASP.NET devuelve la respuesta almacenada en memoria caché y no se llama al método de servicio.</span><span class="sxs-lookup"><span data-stu-id="893f5-105">When a user sends an HTTP GET to your service that is configured for caching, ASP.NET sends back the cached response and the service method is not called.</span></span> <span data-ttu-id="893f5-106">Cuando la memoria caché expira, la próxima vez que un usuario envía un protocolo HTTP GET, se llama al método de servicio y la respuesta se vuelve a almacenar en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="893f5-106">When the cache expires, the next time a user sends an HTTP GET, your service method is called and the response is once again cached.</span></span> <span data-ttu-id="893f5-107">Para obtener más información sobre el almacenamiento en caché de ASP.NET, consulte [información general sobre Caching de ASP.net](https://docs.microsoft.com/previous-versions/aspnet/ms178597(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="893f5-107">For more information about ASP.NET caching, see [ASP.NET Caching Overview](https://docs.microsoft.com/previous-versions/aspnet/ms178597(v=vs.100)).</span></span>  
  
## <a name="basic-web-http-service-caching"></a><span data-ttu-id="893f5-108">Almacenamiento en memoria caché básico del servicio Web HTTP</span><span class="sxs-lookup"><span data-stu-id="893f5-108">Basic Web HTTP Service Caching</span></span>  
 <span data-ttu-id="893f5-109">Para habilitar el almacenamiento en memoria caché del servicio WEB HTTP, debe habilitar primero la compatibilidad de ASP.NET aplicando <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> al servicio, definiendo <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute.RequirementsMode%2A> como <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> o <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>.</span><span class="sxs-lookup"><span data-stu-id="893f5-109">To enable WEB HTTP service caching you must first enable ASP.NET compatibility by applying the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> to the service setting <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute.RequirementsMode%2A> to <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> or <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>.</span></span>  
  
 <span data-ttu-id="893f5-110">.NET Framework 4 introduce un nuevo atributo denominado <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> que le permite especificar un nombre de Perfil de caché.</span><span class="sxs-lookup"><span data-stu-id="893f5-110">.NET Framework 4 introduces a new attribute called <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> that allows you to specify a cache profile name.</span></span> <span data-ttu-id="893f5-111">Este atributo se aplica a una operación del servicio.</span><span class="sxs-lookup"><span data-stu-id="893f5-111">This attribute is applied to a service operation.</span></span> <span data-ttu-id="893f5-112">El siguiente ejemplo aplica <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> a un servicio para habilitar la compatibilidad de ASP.NET y configura la operación `GetCustomer` para almacenar en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="893f5-112">The following example applies the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> to a service to enable ASP.NET compatibility and configures the `GetCustomer` operation for caching.</span></span> <span data-ttu-id="893f5-113">El atributo <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> especifica un perfil de memoria caché que contiene la configuración de memoria caché que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="893f5-113">The <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> attribute specifies a cache profile that contains the cache settings to be used.</span></span>  
  
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
  
 <span data-ttu-id="893f5-114">También debe activar el modo de compatibilidad de ASP.NET en el archivo Web.config, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="893f5-114">You must also turn on ASP.NET compatibility mode in the Web.config file as shown in the following example.</span></span>  
  
```xml
<system.serviceModel>
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
</system.serviceModel>
```
  
> [!WARNING]
> <span data-ttu-id="893f5-115">Si no se activa el modo de compatibilidad de ASP.NET y se utiliza <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="893f5-115">If ASP.NET compatibility mode is not turned on and the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> is used an exception is thrown.</span></span>  
  
 <span data-ttu-id="893f5-116">El nombre de perfil de memoria caché especificado por <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> identifica un perfil de memoria caché agregado al archivo de configuración Web.config.</span><span class="sxs-lookup"><span data-stu-id="893f5-116">The cache profile name specified by the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> identifies a cache profile that is added to your Web.config configuration file.</span></span> <span data-ttu-id="893f5-117">El perfil de caché se define con en un <`outputCacheSetting`elemento > como se muestra en el siguiente ejemplo de configuración.</span><span class="sxs-lookup"><span data-stu-id="893f5-117">The cache profile is defined with in a <`outputCacheSetting`> element as shown in the following configuration example.</span></span>  
  
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
  
 <span data-ttu-id="893f5-118">Éste es el mismo elemento de configuración que está disponible para las aplicaciones ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="893f5-118">This is the same configuration element that is available to ASP.NET applications.</span></span> <span data-ttu-id="893f5-119">Para obtener más información sobre los perfiles de caché de ASP.NET, consulte <xref:System.Web.Configuration.OutputCacheProfile>.</span><span class="sxs-lookup"><span data-stu-id="893f5-119">For more information about ASP.NET cache profiles, see <xref:System.Web.Configuration.OutputCacheProfile>.</span></span> <span data-ttu-id="893f5-120">Para los servicios Web HTTP, los atributos más importantes del perfil de la memoria caché son: `cacheDuration` y `varyByParam`.</span><span class="sxs-lookup"><span data-stu-id="893f5-120">For Web HTTP services, the most important attributes in the cache profile are: `cacheDuration` and `varyByParam`.</span></span> <span data-ttu-id="893f5-121">Se necesitan ambos atributos.</span><span class="sxs-lookup"><span data-stu-id="893f5-121">Both of these attributes are required.</span></span> <span data-ttu-id="893f5-122">`cacheDuration` establece la cantidad de tiempo que una respuesta se debe almacenar en memoria caché en segundos.</span><span class="sxs-lookup"><span data-stu-id="893f5-122">`cacheDuration` sets the amount of time a response should be cached in seconds.</span></span> <span data-ttu-id="893f5-123">`varyByParam` permite especificar un parámetro de cadena de consulta que se usa para almacenar en memoria caché las respuestas.</span><span class="sxs-lookup"><span data-stu-id="893f5-123">`varyByParam` allows you to specify a query string parameter that is used to cache responses.</span></span> <span data-ttu-id="893f5-124">Todas las solicitudes realizadas con valores de parámetro de cadena de consulta diferentes se almacenan en memoria caché por separado.</span><span class="sxs-lookup"><span data-stu-id="893f5-124">All requests made with different query string parameter values are cached separately.</span></span> <span data-ttu-id="893f5-125">Por ejemplo, una vez que se realiza una solicitud inicial a `http://MyServer/MyHttpService/MyOperation?param=10`, todas las solicitudes posteriores realizadas con el mismo URI se devolverían la respuesta almacenada en caché (siempre que no haya transcurrido la duración de la caché).</span><span class="sxs-lookup"><span data-stu-id="893f5-125">For example, once an initial request is made to `http://MyServer/MyHttpService/MyOperation?param=10`, all subsequent requests made with the same URI would be returned the cached response (so long as the cache duration has not elapsed).</span></span> <span data-ttu-id="893f5-126">Las respuestas para una solicitud similar que es igual pero tiene un valor diferente para el parámetro de cadena de consulta de parámetros se almacenan en la memoria caché por separado.</span><span class="sxs-lookup"><span data-stu-id="893f5-126">Responses for a similar request that is the same but has a different value for the parameter query string parameter are cached separately.</span></span> <span data-ttu-id="893f5-127">Si no desea este comportamiento de almacenamiento en caché por separado, establezca `varyByParam` en "none".</span><span class="sxs-lookup"><span data-stu-id="893f5-127">If you do not want this separate caching behavior, set `varyByParam` to "none".</span></span>  
  
## <a name="sql-cache-dependency"></a><span data-ttu-id="893f5-128">Dependencia de memoria caché de SQL</span><span class="sxs-lookup"><span data-stu-id="893f5-128">SQL Cache Dependency</span></span>  
 <span data-ttu-id="893f5-129">Las respuestas del servicio Web HTTP también pueden estar almacenadas en memoria caché con una dependencia de memoria caché de SQL.</span><span class="sxs-lookup"><span data-stu-id="893f5-129">Web HTTP service responses can also be cached with a SQL cache dependency.</span></span> <span data-ttu-id="893f5-130">Si el servicio Web HTTP de WCF depende de los datos almacenados en una base de datos SQL, puede que desee almacenar en memoria caché la respuesta del servicio e invalidar la respuesta almacenada en memoria caché cuando se produzcan cambios en los datos de tabla de base de datos SQL.</span><span class="sxs-lookup"><span data-stu-id="893f5-130">If your WCF Web HTTP service depends on data stored in a SQL database, you may want to cache the service's response and invalidate the cached response when data in the SQL database table changes.</span></span> <span data-ttu-id="893f5-131">Este comportamiento se configura completamente en el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="893f5-131">This behavior is configured completely within the Web.config file.</span></span> <span data-ttu-id="893f5-132">Primero debe definir una cadena de conexión en el <`connectionStrings`elemento >.</span><span class="sxs-lookup"><span data-stu-id="893f5-132">You must first define a connection string in the <`connectionStrings`> element.</span></span>  
  
```xml
<connectionStrings>
  <add name="connectString"
       connectionString="Data Source=MyService;Initial Catalog=MyTestDatabase;Integrated Security=True"
       providerName="System.Data.SqlClient" />
</connectionStrings>
```  
  
 <span data-ttu-id="893f5-133">A continuación, debe habilitar la dependencia de caché de SQL dentro de una <`caching`elemento > en el elemento <`system.web`> como se muestra en el siguiente ejemplo de configuración.</span><span class="sxs-lookup"><span data-stu-id="893f5-133">Then you must enable SQL cache dependency within a <`caching`> element within the <`system.web`> element as shown in the following config example.</span></span>  
  
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
  
 <span data-ttu-id="893f5-134">Aquí, la dependencia de memoria caché de SQL está habilitada y se establece un tiempo de sondeo de 1.000 milisegundos.</span><span class="sxs-lookup"><span data-stu-id="893f5-134">Here SQL cache dependency is enabled and a polling time of 1000 milliseconds is set.</span></span> <span data-ttu-id="893f5-135">Cada vez que el tiempo de sondeo transcurre, se comprueba la tabla de la base de datos para detectar actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="893f5-135">Each time the polling time elapses the database table is checked for updates.</span></span> <span data-ttu-id="893f5-136">Si se detectan cambios, se quita el contenido de la memoria caché y la próxima vez que se invoque la operación del servicio, se almacenará en memoria caché una nueva respuesta.</span><span class="sxs-lookup"><span data-stu-id="893f5-136">If changes are detected the contents of the cache are removed and the next time the service operation is invoked a new response is cached.</span></span> <span data-ttu-id="893f5-137">Dentro de la <`sqlCacheDependency`elemento > Agregue las bases de datos y haga referencia a las cadenas de conexión en el <`databases`elemento >, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="893f5-137">Within the <`sqlCacheDependency`> element add the databases and reference the connection strings within the <`databases`> element as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="893f5-138">A continuación, debe configurar los valores de la caché de resultados en el <`caching`elemento > como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="893f5-138">Next you must configure the output cache settings within the <`caching`> element as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="893f5-139">Aquí, la duración del almacenamiento en memoria caché está establecida en 60 segundos, `varyByParam` no está establecido en ninguno y `sqlDependency` está establecido en una lista delimitada por punto y coma con pares de nombre de base de datos/tabla separados por dos puntos.</span><span class="sxs-lookup"><span data-stu-id="893f5-139">Here the cache duration is set to 60 seconds, `varyByParam` is set to none and `sqlDependency` is set to a semicolon delimited list of database name/table pairs separated by colons.</span></span> <span data-ttu-id="893f5-140">Cuando los datos de `MyTable` se cambian, se elimina la respuesta almacenada en memoria caché para la operación del servicio y, cuando se invoca la operación, la nueva respuesta se genera (llamando a la operación del servicio), se almacena en memoria caché y se devuelve al cliente.</span><span class="sxs-lookup"><span data-stu-id="893f5-140">When data in `MyTable` is changed the cached response for the service operation is removed and when the operation is invoked a new response is generated (by calling the service operation), cached, and returned to the client.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="893f5-141">Para que ASP.NET tenga acceso a una base de datos SQL, debe usar la [herramienta de registro de ASP.NET SQL Server](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms229862(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="893f5-141">For ASP.NET to access a SQL database, you must use the [ASP.NET SQL Server Registration Tool](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms229862(v=vs.90)).</span></span> <span data-ttu-id="893f5-142">Además, debe permitir el acceso de la cuenta de usuario correspondiente tanto a la base de datos como a la tabla.</span><span class="sxs-lookup"><span data-stu-id="893f5-142">In addition you must allow the appropriate user account access to the database and table.</span></span> <span data-ttu-id="893f5-143">Para obtener más información, consulte [acceso a SQL Server desde una aplicación web](https://docs.microsoft.com/previous-versions/aspnet/ht43wsex(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="893f5-143">For more information, see [Accessing SQL Server from a Web Application](https://docs.microsoft.com/previous-versions/aspnet/ht43wsex(v=vs.100)).</span></span>  
  
## <a name="conditional-http-get-based-caching"></a><span data-ttu-id="893f5-144">Almacenamiento en memoria caché basado en HTTP GET condicional</span><span class="sxs-lookup"><span data-stu-id="893f5-144">Conditional HTTP GET Based Caching</span></span>  
 <span data-ttu-id="893f5-145">En escenarios HTTP Web, los servicios suelen usar una instrucción HTTP GET condicional para implementar el almacenamiento en caché de HTTP inteligente, como se describe en la [especificación http](https://www.w3.org/Protocols/rfc2616/rfc2616.html).</span><span class="sxs-lookup"><span data-stu-id="893f5-145">In Web HTTP scenarios a conditional HTTP GET is often used by services to implement intelligent HTTP caching as described in the [HTTP Specification](https://www.w3.org/Protocols/rfc2616/rfc2616.html).</span></span> <span data-ttu-id="893f5-146">Para ello, el servicio debe establecer el valor del encabezado ETag en la respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="893f5-146">To do this the service must set the value of the ETag header in the HTTP response.</span></span> <span data-ttu-id="893f5-147">También debe comprobar el encabezado If-None-Match en la solicitud HTTP para ver si alguno de los ETag especificados coincide con el ETag actual.</span><span class="sxs-lookup"><span data-stu-id="893f5-147">It also must check the If-None-Match header in the HTTP request to see whether any of the ETag specified matches the current ETag.</span></span>  
  
 <span data-ttu-id="893f5-148">Para las solicitudes GET y HEAD, <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> toma un valor de ETag y lo comprueba con respecto al encabezado If-None-Match de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="893f5-148">For GET and HEAD requests, <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> takes an ETag value and checks it against the If-None-Match header of the request.</span></span> <span data-ttu-id="893f5-149">Si el encabezado está presente y hay una coincidencia, se produce <xref:System.ServiceModel.Web.WebFaultException> con un código de estado HTTP 304 (No modificado) y se añade un encabezado de ETag a la respuesta con el ETag coincidente.</span><span class="sxs-lookup"><span data-stu-id="893f5-149">If the header is present and there is a match, a <xref:System.ServiceModel.Web.WebFaultException> with a HTTP status code 304 (Not Modified) is thrown and an ETag header is added to the response with the matching ETag.</span></span>  
  
 <span data-ttu-id="893f5-150">Una sobrecarga del método <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> toma la última fecha modificada y la compara con el encabezado If-Modified-Since de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="893f5-150">One overload of the <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> method takes a last modified date and checks it against the If-Modified-Since header of the request.</span></span> <span data-ttu-id="893f5-151">Si el encabezado está presente y el recurso no se ha modificado desde entonces, se produce <xref:System.ServiceModel.Web.WebFaultException> con un código de estado HTTP 304 (No modificado).</span><span class="sxs-lookup"><span data-stu-id="893f5-151">If the header is present and the resource has not been modified since, a <xref:System.ServiceModel.Web.WebFaultException> with an HTTP status code 304 (Not Modified) is thrown.</span></span>  
  
 <span data-ttu-id="893f5-152">Para las solicitudes PUT, POST y DELETE, <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> toma el valor de ETag actual de un recurso.</span><span class="sxs-lookup"><span data-stu-id="893f5-152">For PUT, POST, and DELETE requests, <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> takes the current ETag value of a resource.</span></span> <span data-ttu-id="893f5-153">Si el valor ETag actual es null, el método comprueba que el encabezado if-None-Match tiene un valor de "\*".</span><span class="sxs-lookup"><span data-stu-id="893f5-153">If the current ETag value is null, the method checks that the If-None- Match header has a value of "\*".</span></span>  <span data-ttu-id="893f5-154">Si el valor de ETag actual no es un valor predeterminado, el método comprueba el valor de ETag actual con respecto al encabezado If-Match de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="893f5-154">If the current ETag value is not a default value, then the method checks the current ETag value against the If- Match header of the request.</span></span> <span data-ttu-id="893f5-155">En cualquier caso, el método produce <xref:System.ServiceModel.Web.WebFaultException> con un código de estado HTTP 412 (Error de condición previa) si el encabezado esperado no se encuentra en la solicitud o si su valor no satisface la comprobación condicional y establece el encabezado de ETag de la respuesta al valor de ETag actual.</span><span class="sxs-lookup"><span data-stu-id="893f5-155">In either case, the method throws a <xref:System.ServiceModel.Web.WebFaultException> with an HTTP status code 412 (Precondition Failed) if the expected header is not present in the request or its value does not satisfy the conditional check and sets the ETag header of the response to the current ETag value.</span></span>  
  
 <span data-ttu-id="893f5-156">Tanto los métodos `CheckConditional` como el método <xref:System.ServiceModel.Web.OutgoingWebResponseContext.SetETag%2A> garantizan que el valor de ETag definido en el encabezado de respuesta es un ETag válido según la especificación de HTTP.</span><span class="sxs-lookup"><span data-stu-id="893f5-156">Both the `CheckConditional` methods and the <xref:System.ServiceModel.Web.OutgoingWebResponseContext.SetETag%2A> method ensures that the ETag value set on the response header is a valid ETag according to the HTTP specification.</span></span> <span data-ttu-id="893f5-157">Esto incluye la delimitación del valor de ETag con comillas dobles si aún no están presentes y el escape correspondiente de cualquier carácter interno de comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="893f5-157">This includes surrounding the ETag value in double quotes if they are not already present and properly escaping any internal double quote characters.</span></span> <span data-ttu-id="893f5-158">No se admite la comparación de ETag débil.</span><span class="sxs-lookup"><span data-stu-id="893f5-158">Weak ETag comparison is not supported.</span></span>  
  
 <span data-ttu-id="893f5-159">En el siguiente ejemplo, se muestra cómo utilizar estos métodos.</span><span class="sxs-lookup"><span data-stu-id="893f5-159">The following example shows how to use these methods.</span></span>  
  
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
  
## <a name="security-considerations"></a><span data-ttu-id="893f5-160">Consideraciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="893f5-160">Security Considerations</span></span>  
 <span data-ttu-id="893f5-161">Las solicitudes que requieren autorización no deberían tener sus respuestas almacenadas en memoria caché, porque la autorización no se realiza cuando la respuesta se sirve desde la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="893f5-161">Requests that require authorization should not have their responses cached, because the authorization is not performed when the response is served from the cache.</span></span>  <span data-ttu-id="893f5-162">Si se almacena en memoria caché tales respuestas, se introduce una vulnerabilidad de seguridad grave.</span><span class="sxs-lookup"><span data-stu-id="893f5-162">Caching such responses would introduce a serious security vulnerability.</span></span>  <span data-ttu-id="893f5-163">Normalmente, las solicitudes que requieren autorización proporcionan los datos específicos del usuario y, por consiguiente, el almacenamiento en caché del lado servidor no es beneficioso.</span><span class="sxs-lookup"><span data-stu-id="893f5-163">Usually, requests that require authorization provide user-specific data and therefore server-side caching is not even beneficial.</span></span>  <span data-ttu-id="893f5-164">En tales situaciones, será más apropiado usar el almacenamiento en caché del lado cliente o, simplemente, no usar el almacenamiento en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="893f5-164">In such situations, client-side caching or simply not caching at all will be more appropriate.</span></span>
