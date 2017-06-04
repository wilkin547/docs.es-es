---
title: "WIF y granjas de servidores web | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc3cd7fa-2b45-4614-a44f-8fa9b9d15284
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# WIF y granjas de servidores web
Cuando utilice Foundation de identidad de Windows \(WIF\) para proteger los recursos de una aplicación de terceros \(RP\) confía que se implementa en un conjunto de servidores web, debe seguir unos pasos específicos para asegurarse de que WIF pueda procesar símbolos \(tokens\) de instancias de la aplicación de punto de reunión que se ejecutan en diferentes equipos de la granja.  Este procesamiento incluye la validación de firmas de token de sesión, cifrar y descifrar los símbolos de sesión, almacenamiento en caché de símbolos de sesión y detectar reproducen los tokens de seguridad.  
  
 En el caso típico, cuando WIF se utiliza para proteger los recursos de una aplicación de punto de reunión: si el punto de reunión se está ejecutando en un único equipo o en un conjunto de servidores web, se establece una sesión con el cliente basado en el símbolo \(token\) de seguridad que se obtuvo desde el servicio de tokens de seguridad \(STS\).  Esto es evitar exigir que el cliente que tienen que autenticarse en el STS para cada recurso de aplicación que se protege con WIF.  Para obtener más información acerca de cómo WIF controla las sesiones, consulte [Administración de sesiones de WIF](../../../docs/framework/security/wif-session-management.md).  
  
 Cuando se utiliza la configuración predeterminada, WIF hace lo siguiente:  
  
-   Se utiliza una instancia de la <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> clase para leer y escribir un símbolo \(token\) de sesión \(una instancia de la <xref:System.IdentityModel.Tokens.SessionSecurityToken> clase\) que lleva a las reclamaciones y otra información sobre el símbolo \(token\) de seguridad que se utilizó para la autenticación, así como información acerca de la sesión.  El símbolo \(token\) de sesión se empaqueta y se almacena en una cookie de sesión.  De forma predeterminada, <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> utiliza el <xref:System.IdentityModel.ProtectedDataCookieTransform> \(clase\), que utiliza la API de protección de datos \(DPAPI\), para proteger el símbolo \(token\) de sesión.  La DPAPI proporciona protección mediante el uso de las credenciales de usuario o equipo y almacena los datos de clave en el perfil de usuario.  
  
-   Utiliza un valor predeterminado, la aplicación de en memoria de la <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> clase para almacenar y procesar el símbolo \(token\) de sesión.  
  
 Esta configuración predeterminada funciona en escenarios en los que se implementa la aplicación de punto de reunión en un único equipo; Sin embargo, cuando se implementa en un conjunto de servidores web, cada solicitud HTTP puede enviar a y procesarse por una instancia diferente de la aplicación de punto de reunión que se ejecuta en un equipo diferente.  En este escenario, la configuración de WIF predeterminado descrita anteriormente no funcionará porque el símbolo \(token\) protección y almacenamiento en caché de símbolo \(token\) son dependientes en un equipo específico.  
  
 Para implementar una aplicación de punto de reunión en un conjunto de servidores web, debe asegurarse de que el procesamiento de símbolos de sesión \(así como de tokens reproducidos\) no es dependiente de la aplicación que se ejecuta en un equipo específico.  Una forma de hacerlo consiste en implementar la aplicación de punto de reunión para que utilice la funcionalidad proporcionada por la aplicación ASP.NET `<machineKey>` elemento de configuración y proporciona almacenamiento en caché distribuido para el procesamiento de símbolos de sesión y reproducen símbolos \(tokens\).  El `<machineKey>` elemento permite especificar las claves necesarias para validar, cifrar y descifrar los símbolos \(tokens\) en un archivo de configuración, lo que permite especificar las mismas claves en diferentes ordenadores en el conjunto de servidores web.  WIF proporciona un controlador de token de sesión especializado, la <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>, que protege los símbolos \(tokens\) mediante el uso de las claves especificadas en el `<machineKey>` elemento.  En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
-   Atributo  Descripción  
  
    ```xml  
    <machineKey compatibilityMode="Framework45" decryptionKey="CC510D … 8925E6" validationKey="BEAC8 … 6A4B1DE" />  
    ```  
  
-   type  Debe quitar primero la <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> \(o derivado de cualquier controlador de la <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> clase\) de la colección de controladores de símbolo \(token\) si este tipo de controlador está presente.  El <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> utiliza el <xref:System.IdentityModel.Services.MachineKeyTransform> \(clase\), que protege los datos de la cookie de sesión mediante el uso del material criptográfico especificado en el `<machineKey>` elemento.  Elemento  
  
    ```xml  
    <securityTokenHandlers>  
      <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
      <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </securityTokenHandlers>  
    ```  
  
-   Descripción  Configurar el punto de reunión para utilizar la caché distribuida mediante la especificación de la [\<sessionSecurityTokenCache\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) elemento en el archivo de configuración.  Se puede reemplazar el <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A?displayProperty=fullName> método en una clase derivada para implementar los elementos secundarios de la `<sessionSecurityTokenCache>` elemento si son necesarios.  
  
    ```xml  
    <caches>  
      <sessionSecurityTokenCache type="MyCacheLibrary.MySharedSessionSecurityTokenCache, MyCacheLibrary">  
        <!—optional child configuration elements, if implemented by the derived class -->  
      </sessionSecurityTokenCache>  
    </caches>  
    ```  
  
     Una manera de implementar el almacenamiento en caché distribuido es proporcionar un front\-end WCF para su caché personalizada.  Para obtener más información acerca de cómo implementar un servicio de caché de WCF, consulte [El servicio de almacenamiento en caché de WCF](#BKMK_TheWCFCachingService).  Elemento  
  
-   Descripción  
  
> [!IMPORTANT]
>  ¿Todos los XML de ejemplo y el código de este tema procede de la [ClaimsAwareWebFarm](http://go.microsoft.com/fwlink/?LinkID=248408) \(¿http:\/\/go.microsoft.com\/fwlink\/?LinkID\=248408\) muestra.  
  
> [!IMPORTANT]
>  Los ejemplos de este tema se proporcionan como\-es y no está pensado para utilizarlo en el código de producción sin ninguna modificación.  
  
<a name="BKMK_TheWCFCachingService"></a>   
## El servicio de almacenamiento en caché de WCF  
 La siguiente interfaz define el contrato entre el servicio de almacenamiento en caché de WCF y el cliente WCF utilizado por la aplicación de parte de usuario de confianza para comunicarse con él.  Expone básicamente los métodos de la <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> clase como operaciones de servicio.  
  
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
  
 El código siguiente muestra la implementación de la WCF servicio de caché.  En este ejemplo, el valor predeterminado, se utiliza la caché de símbolo \(token\) de sesión en memoria implementada por WIF.  Como alternativa, podría implementar una caché duradera respaldada por una base de datos.  `ISessionSecurityTokenCacheService`define la interfaz que se muestra arriba.  En este ejemplo, no todos los métodos necesarios para implementar la interfaz se muestran para mayor brevedad.  
  
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
## El cliente de almacenamiento en caché de WCF  
 En esta sección se muestra la implementación de una clase que deriva de <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> y que los delegados se llama al servicio de almacenamiento en caché.  Configurar la aplicación de punto de reunión para utilizar esta clase a través de la [\<sessionSecurityTokenCache\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) elemento como en el siguiente código XML  
  
```  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  None  Elemento  
  
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
  
## Vea también  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>   
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>   
 <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>   
 [Administración de sesiones de WIF](../../../docs/framework/security/wif-session-management.md)