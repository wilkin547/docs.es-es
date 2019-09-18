---
title: WIF y granjas de servidores web
ms.date: 03/30/2017
ms.assetid: fc3cd7fa-2b45-4614-a44f-8fa9b9d15284
author: BrucePerlerMS
ms.openlocfilehash: 32d2875ebe0a46b9f9b1856ed70a30114793e492
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71045252"
---
# <a name="wif-and-web-farms"></a><span data-ttu-id="3419d-102">WIF y granjas de servidores web</span><span class="sxs-lookup"><span data-stu-id="3419d-102">WIF and Web Farms</span></span>
<span data-ttu-id="3419d-103">Cuando se usa Windows Identity Foundation (WIF) para proteger los recursos de una aplicación de usuario de confianza (RP) implementada en una granja de servidores web, debe realizar determinados pasos para garantizar que WIF pueda procesar tokens de instancias de la aplicación de RP que se ejecutan en equipos diferentes de la granja de servidores.</span><span class="sxs-lookup"><span data-stu-id="3419d-103">When you use Windows Identity Foundation (WIF) to secure the resources of a relying party (RP) application that is deployed in a web farm, you must take specific steps to ensure that WIF can process tokens from instances of the RP application running on different computers in the farm.</span></span> <span data-ttu-id="3419d-104">Este proceso implica la validación de firmas de token de sesión, el cifrado y descifrado de tokens de sesión, el almacenamiento en caché de tokens de sesión y la detección de tokens de seguridad reproducidos.</span><span class="sxs-lookup"><span data-stu-id="3419d-104">This processing includes validating session token signatures, encrypting and decrypting session tokens, caching session tokens, and detecting replayed security tokens.</span></span>  
  
 <span data-ttu-id="3419d-105">En el caso típico, cuando se usa WIF para proteger los recursos de una aplicación de RP (tanto si el RP se está ejecutando en un único equipo como en una granja de servidores web), se establece una sesión con el cliente en función del token de seguridad obtenido del servicio de token de seguridad (STS).</span><span class="sxs-lookup"><span data-stu-id="3419d-105">In the typical case, when WIF is used to secure resources of an RP application – whether the RP is running on a single computer or in a web farm -- a session is established with the client based on the security token that was obtained from the security token service (STS).</span></span> <span data-ttu-id="3419d-106">Esto es así para evitar forzar al cliente a autenticarse en el STS para cada recurso de aplicación que se proteja mediante WIF.</span><span class="sxs-lookup"><span data-stu-id="3419d-106">This is to avoid forcing the client to have to authenticate at the STS for every application resource that is secured using WIF.</span></span> <span data-ttu-id="3419d-107">Para más información sobre cómo controla WIF las sesiones, vea [WIF Session Management (Administración de sesiones de WIF)](wif-session-management.md).</span><span class="sxs-lookup"><span data-stu-id="3419d-107">For more information about how WIF handles sessions, see [WIF Session Management](wif-session-management.md).</span></span>  
  
 <span data-ttu-id="3419d-108">Cuando se usa la configuración predeterminada, WIF hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3419d-108">When default settings are used, WIF does the following:</span></span>  
  
- <span data-ttu-id="3419d-109">Usa una instancia de la clase <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> para leer y escribir un token de sesión (una instancia de la clase <xref:System.IdentityModel.Tokens.SessionSecurityToken>) que contiene las notificaciones y demás información sobre el token de seguridad que se ha usado para la autenticación, así como información sobre la propia sesión.</span><span class="sxs-lookup"><span data-stu-id="3419d-109">It uses an instance of the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class to read and write a session token (an instance of the <xref:System.IdentityModel.Tokens.SessionSecurityToken> class) that carries the claims and other information about the security token that was used for authentication as well as information about the session itself.</span></span> <span data-ttu-id="3419d-110">El token de sesión se empaqueta y se almacena en una cookie de la sesión.</span><span class="sxs-lookup"><span data-stu-id="3419d-110">The session token is packaged and stored in a session cookie.</span></span> <span data-ttu-id="3419d-111">De forma predeterminada, <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> usa la clase <xref:System.IdentityModel.ProtectedDataCookieTransform>, que emplea la API de protección de datos (DPAPI), para proteger el token de sesión.</span><span class="sxs-lookup"><span data-stu-id="3419d-111">By default, <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> uses the <xref:System.IdentityModel.ProtectedDataCookieTransform> class, which uses the Data Protection API (DPAPI), to protect the session token.</span></span> <span data-ttu-id="3419d-112">DPAPI proporciona protección mediante las credenciales de usuario o equipo y almacena los datos clave en el perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="3419d-112">The DPAPI provides protection by using the user or machine credentials and stores the key data in the user profile.</span></span>  
  
- <span data-ttu-id="3419d-113">Usa una implementación en memoria predeterminada de la clase <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> para almacenar y procesar el token de sesión.</span><span class="sxs-lookup"><span data-stu-id="3419d-113">It uses a default, in-memory implementation of the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class to store and process the session token.</span></span>  
  
 <span data-ttu-id="3419d-114">Esta configuración predeterminada funciona en escenarios en los que se implementa la aplicación de RP en un único equipo; pero si se implementa en una granja de servidores web, cada solicitud HTTP se puede enviar a otra instancia de la aplicación de RP que se ejecuta en un equipo diferente y ser procesada por ella.</span><span class="sxs-lookup"><span data-stu-id="3419d-114">These default settings work in scenarios in which the RP application is deployed on a single computer; however, when deployed in a web farm, each HTTP request may be sent to and processed by a different instance of the RP application running on a different computer.</span></span> <span data-ttu-id="3419d-115">En este escenario, la configuración de WIF predeterminada que se ha descrito anteriormente no funciona, ya que la protección de token y el almacenamiento en caché de token dependen de un equipo concreto.</span><span class="sxs-lookup"><span data-stu-id="3419d-115">In this scenario, the default WIF settings described above will not work because both token protection and token caching are dependent on a specific computer.</span></span>  
  
 <span data-ttu-id="3419d-116">Para implementar una aplicación de RP en una granja de servidores web, debe asegurarse de que el procesamiento de tokens de sesión (así como de tokens reproducidos) no dependa de la aplicación que se ejecuta en un equipo específico.</span><span class="sxs-lookup"><span data-stu-id="3419d-116">To deploy an RP application in a web farm, you must ensure that the processing of session tokens (as well as of replayed tokens) is not dependent on the application running on a specific computer.</span></span> <span data-ttu-id="3419d-117">Una manera de hacerlo es implementar la aplicación de RP de modo que use la funcionalidad proporcionada por el elemento de configuración `<machineKey>` de ASP.NET y proporcione almacenamiento en caché distribuido para el procesamiento de tokens de sesión y tokens reproducidos.</span><span class="sxs-lookup"><span data-stu-id="3419d-117">One way to do this is to implement your RP application so that it uses the functionality provided by the ASP.NET `<machineKey>` configuration element and provides distributed caching for processing session tokens and replayed tokens.</span></span> <span data-ttu-id="3419d-118">El elemento `<machineKey>` permite especificar las claves necesarias para validar, cifrar y descifrar los tokens de un archivo de configuración, lo que permite especificar las mismas claves en diferentes equipos de la granja de servidores web.</span><span class="sxs-lookup"><span data-stu-id="3419d-118">The `<machineKey>` element allows you to specify the keys needed to validate, encrypt, and decrypt tokens in a configuration file, which enables you to specify the same keys on different computers in the web farm.</span></span> <span data-ttu-id="3419d-119">WIF proporciona un controlador de token de sesión especializado, <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>, que protege los tokens con las claves especificadas en el elemento `<machineKey>`.</span><span class="sxs-lookup"><span data-stu-id="3419d-119">WIF provides a specialized session token handler, the <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>, that protects tokens by using the keys specified in the `<machineKey>` element.</span></span> <span data-ttu-id="3419d-120">Para implementar esta estrategia, siga estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="3419d-120">To implement this strategy, you can follow these guidelines:</span></span>  
  
- <span data-ttu-id="3419d-121">Use el elemento `<machineKey>` de ASP.NET de la configuración para especificar de forma explícita las claves de firma y cifrado que se pueden usar en los equipos de la granja de servidores.</span><span class="sxs-lookup"><span data-stu-id="3419d-121">Use the ASP.NET `<machineKey>` element in configuration to explicitly specify signing and encryption keys that can be used across computers in the farm.</span></span> <span data-ttu-id="3419d-122">El siguiente XML muestra la especificación del elemento `<machineKey>` bajo el elemento `<system.web>` de un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3419d-122">The following XML shows the specification of the `<machineKey>` element under the `<system.web>` element in a configuration file.</span></span>  
  
    ```xml  
    <machineKey compatibilityMode="Framework45" decryptionKey="CC510D … 8925E6" validationKey="BEAC8 … 6A4B1DE" />  
    ```  
  
- <span data-ttu-id="3419d-123">Configure la aplicación para que use <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> al agregarlo a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="3419d-123">Configure the application to use the <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> by adding it to the token handler collection.</span></span> <span data-ttu-id="3419d-124">Si hay un controlador de este tipo, primero debe quitar <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> (o cualquier controlador derivado de la clase <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>) de la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="3419d-124">You must first remove the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> (or any handler derived from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class) from the token handler collection if such a handler is present.</span></span> <span data-ttu-id="3419d-125"><xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> usa la clase <xref:System.IdentityModel.Services.MachineKeyTransform>, que protege los datos de la cookie de la sesión con el material criptográfico especificado en el elemento `<machineKey>`.</span><span class="sxs-lookup"><span data-stu-id="3419d-125">The <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> uses the <xref:System.IdentityModel.Services.MachineKeyTransform> class, which protects the session cookie data by using the cryptographic material specified in the `<machineKey>` element.</span></span> <span data-ttu-id="3419d-126">El siguiente XML muestra cómo agregar <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> a una colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="3419d-126">The following XML shows how to add the <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> to a token handler collection.</span></span>  
  
    ```xml  
    <securityTokenHandlers>  
      <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
      <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </securityTokenHandlers>  
    ```  
  
- <span data-ttu-id="3419d-127">Derive de <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> e implemente el almacenamiento en caché distribuido, es decir, una memoria caché que sea accesible desde todos los equipos de la granja de servidores en la que se puede ejecutar el RP.</span><span class="sxs-lookup"><span data-stu-id="3419d-127">Derive from <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> and implement distributed caching, that is, a cache that is accessible from all computers in the farm on which the RP might run.</span></span> <span data-ttu-id="3419d-128">Configure el RP para que use la memoria caché distribuida al especificar el elemento [\<sessionSecurityTokenCache>](../configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3419d-128">Configure the RP to use your distributed cache by specifying the [\<sessionSecurityTokenCache>](../configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) element in the configuration file.</span></span> <span data-ttu-id="3419d-129">Puede invalidar el método <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A?displayProperty=nameWithType> de la clase derivada para implementar elementos secundarios del elemento `<sessionSecurityTokenCache>` si fueran necesarios.</span><span class="sxs-lookup"><span data-stu-id="3419d-129">You can override the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A?displayProperty=nameWithType> method in your derived class to implement child elements of the `<sessionSecurityTokenCache>` element if they are required.</span></span>  
  
    ```xml  
    <caches>  
      <sessionSecurityTokenCache type="MyCacheLibrary.MySharedSessionSecurityTokenCache, MyCacheLibrary">  
        <!--optional child configuration elements, if implemented by the derived class -->  
      </sessionSecurityTokenCache>  
    </caches>  
    ```  
  
     <span data-ttu-id="3419d-130">Una manera de implementar el almacenamiento en caché distribuido es proporcionar un front-end de WCF para la memoria caché personalizada.</span><span class="sxs-lookup"><span data-stu-id="3419d-130">One way to implement distributed caching is to provide a WCF front end for your custom cache.</span></span> <span data-ttu-id="3419d-131">Para más información sobre la implementación de un servicio de almacenamiento en caché de WCF, vea [Servicio de almacenamiento en caché de WCF](#BKMK_TheWCFCachingService).</span><span class="sxs-lookup"><span data-stu-id="3419d-131">For more information about implementing a WCF caching service, see [The WCF Caching Service](#BKMK_TheWCFCachingService).</span></span> <span data-ttu-id="3419d-132">Para más información sobre la implementación de un cliente WCF que la aplicación de RP pueda usar para llamar al servicio de almacenamiento en caché, vea [Cliente de almacenamiento en caché de WCF](#BKMK_TheWCFClient).</span><span class="sxs-lookup"><span data-stu-id="3419d-132">For more information about implementing a WCF client that the RP application can use to call the caching service, see [The WCF Caching Client](#BKMK_TheWCFClient).</span></span>  
  
- <span data-ttu-id="3419d-133">Si la aplicación detecta tokens reproducidos, debe seguir una estrategia similar de almacenamiento en caché distribuido para la memoria caché de reproducción de tokens al derivar de <xref:System.IdentityModel.Tokens.TokenReplayCache> y apuntar al servicio de almacenamiento en caché de reproducción de tokens del elemento de configuración [\<tokenReplayCache>](../configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md).</span><span class="sxs-lookup"><span data-stu-id="3419d-133">If your application detects replayed tokens you must follow a similar distributed caching strategy for the token replay cache by deriving from <xref:System.IdentityModel.Tokens.TokenReplayCache> and pointing to your token replay caching service in the [\<tokenReplayCache>](../configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) configuration element.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3419d-134">Todo el código y XML de ejemplo de este tema se toma del ejemplo [ClaimsAwareWebFarm](https://go.microsoft.com/fwlink/?LinkID=248408) .</span><span class="sxs-lookup"><span data-stu-id="3419d-134">All of the example XML and code in this topic is taken from the [ClaimsAwareWebFarm](https://go.microsoft.com/fwlink/?LinkID=248408) sample.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3419d-135">Los ejemplos de este tema se proporcionan tal cual y no están diseñados para usarse en código de producción sin modificación.</span><span class="sxs-lookup"><span data-stu-id="3419d-135">The examples in this topic are provided as-is and are not intended to be used in production code without modification.</span></span>  
  
<a name="BKMK_TheWCFCachingService"></a>   
## <a name="the-wcf-caching-service"></a><span data-ttu-id="3419d-136">Servicio de almacenamiento en caché de WCF</span><span class="sxs-lookup"><span data-stu-id="3419d-136">The WCF Caching Service</span></span>  
 <span data-ttu-id="3419d-137">La siguiente interfaz define el contrato entre el servicio de almacenamiento en caché de WCF y el cliente WCF usado por la aplicación de usuario de confianza para comunicarse con él.</span><span class="sxs-lookup"><span data-stu-id="3419d-137">The following interface defines the contract between the WCF caching service and the WCF client used by the relying party application to communicate with it.</span></span> <span data-ttu-id="3419d-138">Básicamente expone los métodos de la clase <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> como operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="3419d-138">It essentially exposes the methods of the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class as service operations.</span></span>  
  
```csharp
[ServiceContract()]  
public interface ISessionSecurityTokenCacheService  
{  
    [OperationContract]  
    void AddOrUpdate(string endpointId, string contextId, string keyGeneration, SessionSecurityToken value, DateTime expiryTime);  
  
    [OperationContract]  
    IEnumerable<SessionSecurityToken> GetAll(string endpointId, string contextId);  
  
    [OperationContract]  
    SessionSecurityToken Get(string endpointId, string contextId, string keyGeneration);  
  
    [OperationContract(Name = "RemoveAll")]  
    void RemoveAll(string endpointId, string contextId);  
  
    [OperationContract(Name = "RemoveAllByEndpointId")]  
    void RemoveAll(string endpointId);  
  
    [OperationContract]  
    void Remove(string endpointId, string contextId, string keyGeneration);  
}  
```  
  
 <span data-ttu-id="3419d-139">En el siguiente código se muestra la implementación del servicio de almacenamiento en caché de WCF.</span><span class="sxs-lookup"><span data-stu-id="3419d-139">The following code shows the implementation of the WCF caching service.</span></span> <span data-ttu-id="3419d-140">En este ejemplo se usa la memoria caché del token de sesión en memoria predeterminada implementada por WIF.</span><span class="sxs-lookup"><span data-stu-id="3419d-140">In this example, the default, in-memory session token cache implemented by WIF is used.</span></span> <span data-ttu-id="3419d-141">También se podría implementar una memoria caché duradera respaldada por una base de datos.</span><span class="sxs-lookup"><span data-stu-id="3419d-141">Alternatively, you could implement a durable cache backed by a database.</span></span> <span data-ttu-id="3419d-142">`ISessionSecurityTokenCacheService` define la interfaz mostrada arriba.</span><span class="sxs-lookup"><span data-stu-id="3419d-142">`ISessionSecurityTokenCacheService` defines the interface shown above.</span></span> <span data-ttu-id="3419d-143">En este ejemplo no se muestran todos los métodos necesarios para implementar la interfaz en aras de la brevedad.</span><span class="sxs-lookup"><span data-stu-id="3419d-143">In this example, not all of the methods required to implement the interface are shown for brevity.</span></span>  
  
```csharp
using System;  
using System.Collections.Generic;  
using System.IdentityModel.Configuration;  
using System.IdentityModel.Tokens;  
using System.ServiceModel;  
using System.Xml;  
  
namespace WcfSessionSecurityTokenCacheService  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    public class SessionSecurityTokenCacheService : ISessionSecurityTokenCacheService  
    {  
        SessionSecurityTokenCache internalCache;  
  
        // sets the internal cache used by the service to the default WIF in-memory cache.  
        public SessionSecurityTokenCacheService()  
        {  
            internalCache = new IdentityModelCaches().SessionSecurityTokenCache;  
        }  
  
        ...  
  
        public SessionSecurityToken Get(string endpointId, string contextId, string keyGeneration)  
        {  
            // Delegates to the default, in-memory MruSessionSecurityTokenCache used by WIF  
            SessionSecurityToken token = internalCache.Get(new SessionSecurityTokenCacheKey(endpointId, GetContextId(contextId), GetKeyGeneration(keyGeneration)));  
            return token;  
        }  
  
        ...  
  
        private static UniqueId GetContextId(string contextIdString)  
        {  
            return contextIdString == null ? null : new UniqueId(contextIdString);  
        }  
  
        private static UniqueId GetKeyGeneration(string keyGenerationString)  
        {  
            return keyGenerationString == null ? null : new UniqueId(keyGenerationString);  
        }  
    }  
}  
```  
  
<a name="BKMK_TheWCFClient"></a>   
## <a name="the-wcf-caching-client"></a><span data-ttu-id="3419d-144">Cliente de almacenamiento en caché de WCF</span><span class="sxs-lookup"><span data-stu-id="3419d-144">The WCF Caching Client</span></span>  
 <span data-ttu-id="3419d-145">En esta sección se muestra la implementación de una clase que deriva de <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> y que delega llamadas al servicio de almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="3419d-145">This section shows the implementation of a class that derives from <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> and that delegates calls to the caching service.</span></span> <span data-ttu-id="3419d-146">La aplicación de RP se configura de modo que use esta clase en el elemento [\<sessionSecurityTokenCache>](../configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) como en el siguiente XML.</span><span class="sxs-lookup"><span data-stu-id="3419d-146">You configure the RP application to use this class through the [\<sessionSecurityTokenCache>](../configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) element as in the following XML</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
 <span data-ttu-id="3419d-147">Las clase invalida el método <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A> para obtener el punto de conexión de servicio del elemento secundario `<cacheServiceAddress>` personalizado del elemento `<sessionSecurityTokenCache>`.</span><span class="sxs-lookup"><span data-stu-id="3419d-147">The class overrides the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A> method to get the service endpoint from the custom `<cacheServiceAddress>` child element of the `<sessionSecurityTokenCache>` element.</span></span> <span data-ttu-id="3419d-148">Usa este punto de conexión para inicializar un canal `ISessionSecurityTokenCacheService` a través del que se puede comunicar con el servicio.</span><span class="sxs-lookup"><span data-stu-id="3419d-148">It uses this endpoint to initialize an `ISessionSecurityTokenCacheService` channel over which it can communicate with the service.</span></span>  <span data-ttu-id="3419d-149">En este ejemplo no se muestran todos los métodos necesarios para implementar la clase <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> en aras de la brevedad.</span><span class="sxs-lookup"><span data-stu-id="3419d-149">In this example, not all of the methods required to implement the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class are shown for brevity.</span></span>  
  
```csharp
using System;  
using System.Configuration;  
using System.IdentityModel.Configuration;  
using System.IdentityModel.Tokens;  
using System.ServiceModel;  
using System.Xml;  
  
namespace CacheLibrary  
{  
    /// <summary>  
    /// This class acts as a proxy to the WcfSessionSecurityTokenCacheService.  
    /// </summary>  
    public class SharedSessionSecurityTokenCache : SessionSecurityTokenCache, ICustomIdentityConfiguration  
    {  
        private ISessionSecurityTokenCacheService WcfSessionSecurityTokenCacheServiceClient;  
  
        internal SharedSessionSecurityTokenCache()  
        {  
        }  
  
        /// <summary>  
        /// Creates a client channel to call the service host.  
        /// </summary>  
        protected void Initialize(string cacheServiceAddress)  
        {  
            if (this.WcfSessionSecurityTokenCacheServiceClient != null)  
            {  
                return;  
            }  
  
            ChannelFactory<ISessionSecurityTokenCacheService> cf = new ChannelFactory<ISessionSecurityTokenCacheService>(  
                new WS2007HttpBinding(SecurityMode.None),  
                new EndpointAddress(cacheServiceAddress));  
            this.WcfSessionSecurityTokenCacheServiceClient = cf.CreateChannel();  
        }  
  
        #region SessionSecurityTokenCache Members  
        // Delegates the following operations to the centralized session security token cache service in the web farm.  
  
        ...  
  
        public override SessionSecurityToken Get(SessionSecurityTokenCacheKey key)  
        {  
            return this.WcfSessionSecurityTokenCacheServiceClient.Get(key.EndpointId, GetContextIdString(key), GetKeyGenerationString(key));  
        }  
  
        ...  
  
        #endregion  
  
        #region ICustomIdentityConfiguration Members  
        // Called from configuration infrastructure to load custom elements  
        public void LoadCustomConfiguration(XmlNodeList nodeList)  
        {  
            // Retrieve the endpoint address of the centralized session security token cache service running in the web farm  
            if (nodeList.Count == 0)  
            {  
                throw new ConfigurationException("No child config element found under <sessionSecurityTokenCache>.");  
            }  
  
            XmlElement cacheServiceAddressElement = nodeList.Item(0) as XmlElement;  
            if (cacheServiceAddressElement.LocalName != "cacheServiceAddress")  
            {  
                throw new ConfigurationException("First child config element under <sessionSecurityTokenCache> is expected to be <cacheServiceAddress>.");  
            }  
  
            string cacheServiceAddress = null;  
            if (cacheServiceAddressElement.Attributes["url"] != null)  
            {  
                cacheServiceAddress = cacheServiceAddressElement.Attributes["url"].Value;  
            }  
            else  
            {  
                throw new ConfigurationException("<cacheServiceAddress> is expected to contain a 'url' attribute.");  
            }  
  
            // Initialize the proxy to the WebFarmSessionSecurityTokenCacheService  
            this.Initialize(cacheServiceAddress);  
        }  
        #endregion  
  
        private static string GetKeyGenerationString(SessionSecurityTokenCacheKey key)  
        {  
            return key.KeyGeneration == null ? null : key.KeyGeneration.ToString();  
        }  
  
        private static string GetContextIdString(SessionSecurityTokenCacheKey key)  
        {  
            return GetContextIdString(key.ContextId);  
        }  
  
        private static string GetContextIdString(UniqueId contextId)  
        {  
            return contextId == null ? null : contextId.ToString();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="3419d-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="3419d-150">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
- <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>
- <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>
- [<span data-ttu-id="3419d-151">Administración de sesiones de WIF</span><span class="sxs-lookup"><span data-stu-id="3419d-151">WIF Session Management</span></span>](wif-session-management.md)
