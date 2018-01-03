---
title: WIF y granjas de servidores web
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc3cd7fa-2b45-4614-a44f-8fa9b9d15284
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 93c3e4251943afa383002043d9259184be82d929
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="wif-and-web-farms"></a>WIF y granjas de servidores web
Cuando se usa Windows Identity Foundation (WIF) para proteger los recursos de una aplicación de usuario de confianza (RP) implementada en una granja de servidores web, debe realizar determinados pasos para garantizar que WIF pueda procesar tokens de instancias de la aplicación de RP que se ejecutan en equipos diferentes de la granja de servidores. Este proceso implica la validación de firmas de token de sesión, el cifrado y descifrado de tokens de sesión, el almacenamiento en caché de tokens de sesión y la detección de tokens de seguridad reproducidos.  
  
 En el caso típico, cuando se usa WIF para proteger los recursos de una aplicación de RP (tanto si el RP se está ejecutando en un único equipo como en una granja de servidores web), se establece una sesión con el cliente en función del token de seguridad obtenido del servicio de token de seguridad (STS). Esto es así para evitar forzar al cliente a autenticarse en el STS para cada recurso de aplicación que se proteja mediante WIF. Para más información sobre cómo controla WIF las sesiones, vea [WIF Session Management (Administración de sesiones de WIF)](../../../docs/framework/security/wif-session-management.md).  
  
 Cuando se usa la configuración predeterminada, WIF hace lo siguiente:  
  
-   Usa una instancia de la clase <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> para leer y escribir un token de sesión (una instancia de la clase <xref:System.IdentityModel.Tokens.SessionSecurityToken>) que contiene las notificaciones y demás información sobre el token de seguridad que se ha usado para la autenticación, así como información sobre la propia sesión. El token de sesión se empaqueta y se almacena en una cookie de la sesión. De forma predeterminada, <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> usa la clase <xref:System.IdentityModel.ProtectedDataCookieTransform>, que emplea la API de protección de datos (DPAPI), para proteger el token de sesión. DPAPI proporciona protección mediante las credenciales de usuario o equipo y almacena los datos clave en el perfil de usuario.  
  
-   Usa una implementación en memoria predeterminada de la clase <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> para almacenar y procesar el token de sesión.  
  
 Esta configuración predeterminada funciona en escenarios en los que se implementa la aplicación de RP en un único equipo; pero si se implementa en una granja de servidores web, cada solicitud HTTP se puede enviar a otra instancia de la aplicación de RP que se ejecuta en un equipo diferente y ser procesada por ella. En este escenario, la configuración de WIF predeterminada que se ha descrito anteriormente no funciona, ya que la protección de token y el almacenamiento en caché de token dependen de un equipo concreto.  
  
 Para implementar una aplicación de RP en una granja de servidores web, debe asegurarse de que el procesamiento de tokens de sesión (así como de tokens reproducidos) no dependa de la aplicación que se ejecuta en un equipo específico. Una manera de hacerlo es implementar la aplicación de RP de modo que use la funcionalidad proporcionada por el elemento de configuración `<machineKey>` de ASP.NET y proporcione almacenamiento en caché distribuido para el procesamiento de tokens de sesión y tokens reproducidos. El elemento `<machineKey>` permite especificar las claves necesarias para validar, cifrar y descifrar los tokens de un archivo de configuración, lo que permite especificar las mismas claves en diferentes equipos de la granja de servidores web. WIF proporciona un controlador de token de sesión especializado, <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>, que protege los tokens con las claves especificadas en el elemento `<machineKey>`. Para implementar esta estrategia, siga estas instrucciones:  
  
-   Use el elemento `<machineKey>` de ASP.NET de la configuración para especificar de forma explícita las claves de firma y cifrado que se pueden usar en los equipos de la granja de servidores. El siguiente XML muestra la especificación del elemento `<machineKey>` bajo el elemento `<system.web>` de un archivo de configuración.  
  
    ```xml  
    <machineKey compatibilityMode="Framework45" decryptionKey="CC510D … 8925E6" validationKey="BEAC8 … 6A4B1DE" />  
    ```  
  
-   Configure la aplicación para que use <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> al agregarlo a la colección de controladores de tokens. Si hay un controlador de este tipo, primero debe quitar <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> (o cualquier controlador derivado de la clase <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>) de la colección de controladores de tokens. <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> usa la clase <xref:System.IdentityModel.Services.MachineKeyTransform>, que protege los datos de la cookie de la sesión con el material criptográfico especificado en el elemento `<machineKey>`. El siguiente XML muestra cómo agregar <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> a una colección de controladores de tokens.  
  
    ```xml  
    <securityTokenHandlers>  
      <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
      <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </securityTokenHandlers>  
    ```  
  
-   Derive de <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> e implemente el almacenamiento en caché distribuido, es decir, una memoria caché que sea accesible desde todos los equipos de la granja de servidores en la que se puede ejecutar el RP. Configure el RP para que use la memoria caché distribuida al especificar el elemento [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) del archivo de configuración. Puede invalidar el método <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A?displayProperty=nameWithType> de la clase derivada para implementar elementos secundarios del elemento `<sessionSecurityTokenCache>` si fueran necesarios.  
  
    ```xml  
    <caches>  
      <sessionSecurityTokenCache type="MyCacheLibrary.MySharedSessionSecurityTokenCache, MyCacheLibrary">  
        <!—optional child configuration elements, if implemented by the derived class -->  
      </sessionSecurityTokenCache>  
    </caches>  
    ```  
  
     Una manera de implementar el almacenamiento en caché distribuido es proporcionar un front-end de WCF para la memoria caché personalizada. Para más información sobre la implementación de un servicio de almacenamiento en caché de WCF, vea [Servicio de almacenamiento en caché de WCF](#BKMK_TheWCFCachingService). Para más información sobre la implementación de un cliente WCF que la aplicación de RP pueda usar para llamar al servicio de almacenamiento en caché, vea [Cliente de almacenamiento en caché de WCF](#BKMK_TheWCFClient).  
  
-   Si la aplicación detecta tokens reproducidos, debe seguir una estrategia similar de almacenamiento en caché distribuido para la memoria caché de reproducción de tokens al derivar de <xref:System.IdentityModel.Tokens.TokenReplayCache> y apuntar al servicio de almacenamiento en caché de reproducción de tokens del elemento de configuración [\<tokenReplayCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md).  
  
> [!IMPORTANT]
>  Todo el XML y el código de ejemplo de este tema proceden del ejemplo [ClaimsAwareWebFarm](http://go.microsoft.com/fwlink/?LinkID=248408) (http://go.microsoft.com/fwlink/?LinkID=248408).  
  
> [!IMPORTANT]
>  Los ejemplos de este tema se proporcionan tal cual y no están diseñados para usarse en código de producción sin modificación.  
  
<a name="BKMK_TheWCFCachingService"></a>   
## <a name="the-wcf-caching-service"></a>Servicio de almacenamiento en caché de WCF  
 La siguiente interfaz define el contrato entre el servicio de almacenamiento en caché de WCF y el cliente WCF usado por la aplicación de usuario de confianza para comunicarse con él. Básicamente expone los métodos de la clase <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> como operaciones de servicio.  
  
```  
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
  
 En el siguiente código se muestra la implementación del servicio de almacenamiento en caché de WCF. En este ejemplo se usa la memoria caché del token de sesión en memoria predeterminada implementada por WIF. También se podría implementar una memoria caché duradera respaldada por una base de datos. `ISessionSecurityTokenCacheService` define la interfaz mostrada arriba. En este ejemplo no se muestran todos los métodos necesarios para implementar la interfaz en aras de la brevedad.  
  
```  
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
## <a name="the-wcf-caching-client"></a>Cliente de almacenamiento en caché de WCF  
 En esta sección se muestra la implementación de una clase que deriva de <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> y que delega llamadas al servicio de almacenamiento en caché. La aplicación de RP se configura de modo que use esta clase en el elemento [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) como en el siguiente XML.  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
 Las clase invalida el método <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A> para obtener el punto de conexión de servicio del elemento secundario `<cacheServiceAddress>` personalizado del elemento `<sessionSecurityTokenCache>`. Usa este punto de conexión para inicializar un canal `ISessionSecurityTokenCacheService` a través del que se puede comunicar con el servicio.  En este ejemplo no se muestran todos los métodos necesarios para implementar la clase <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> en aras de la brevedad.  
  
```  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>  
 <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>  
 [Administración de sesiones de WIF](../../../docs/framework/security/wif-session-management.md)
