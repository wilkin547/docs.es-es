---
title: Información general sobre el módulo de autenticación WSFederation
ms.date: 03/30/2017
ms.assetid: 02c4d5e8-f0a7-49ee-9cf5-3647578510ad
author: BrucePerlerMS
ms.openlocfilehash: c64bbfc868268fea77d2d17317bfea43aa413b3f
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2019
ms.locfileid: "63808263"
---
# <a name="wsfederation-authentication-module-overview"></a>Información general sobre el módulo de autenticación WSFederation
Windows Identity Foundation (WIF) es compatible con la autenticación federada en aplicaciones ASP.NET a través del Módulo de autenticación de WS-Federation (WS-FAM). Este tema le ayudará a comprender cómo funciona la autenticación federada y cómo se utiliza.  
  
### <a name="overview-of-federated-authentication"></a>Información general sobre la autenticación federada  
 La autenticación federada permite al servicio de token de seguridad (STS) de un dominio de confianza proporcionar información de autenticación a un STS de otro dominio de confianza cuando hay una relación de confianza entre los dos dominios. En la siguiente ilustración se muestra un ejemplo de esto:  
  
 ![Diagrama que muestra el escenario de autenticación federada.](./media/wsfederation-authentication-module-overview/federated-authentication.gif)  
  
1. Un cliente del dominio de confianza Fabrikam envía una solicitud a una aplicación de usuario de confianza (RP) del dominio de confianza Contoso.  
  
2. El RP redirige al cliente a un STS del dominio de confianza Contoso. Este STS no conoce al cliente.  
  
3. El STS de Contoso redirige al cliente a un STS del dominio de confianza Fabrikam, con el que el dominio de confianza Contoso tiene una relación de confianza.  
  
4. El STS de Fabrikam comprueba la identidad del cliente y emite un token de seguridad para el STS de Contoso.  
  
5. El STS de Contoso utiliza el token de Fabrikam para crear su propio token que pueda utilizar el RP y lo envía al RP.  
  
6. El RP extrae las notificaciones del cliente del token de seguridad y toma una decisión de autorización.  
  
### <a name="using-the-federated-authentication-module-with-aspnet"></a>Usar el módulo de autenticación federada con ASP.NET  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WS-FAM) es un módulo HTTP que le permite agregar la autenticación federada a una aplicación de [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]. La autenticación federada permite al STS controlar la lógica de autenticación y permite al usuario centrarse en la escritura de la lógica de negocios.  
  
 Configure WS-FAM para especificar el STS al que deben redirigirse las solicitudes no autenticadas. WIF le permite autenticar a un usuario de dos maneras:  
  
1. Redirección pasiva: Cuando un usuario no autenticado intenta tener acceso a un recurso protegido, y desea simplemente redirigirlas al STS sin necesidad de una página de inicio de sesión, es el enfoque correcto. El STS comprueba la identidad del usuario y emite un token de seguridad que contiene las notificaciones adecuadas para dicho usuario. Esta opción requiere que se agregue el WS-FAM a la canalización de módulos HTTP. Puede utilizar la herramienta denominada Identity and Access Tool de Visual Studio 2012 para modificar el archivo de configuración de la aplicación de modo que use WS-FAM y se federe con un STS. Para más información, vea [Identity and Access Tool for Visual Studio 2012 (Herramienta de identidad y acceso para Visual Studio 2012)](../../../docs/framework/security/identity-and-access-tool-for-vs.md).  
  
2. Puede llamar al método <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SignIn%2A?displayProperty=nameWithType> o al método <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectToIdentityProvider%2A> desde el código subyacente para utilizar una página de inicio de sesión en su aplicación de RP.  
  
 En la redirección pasiva, toda la comunicación se lleva a cabo a través de la respuesta/redirección desde el cliente (normalmente, un explorador). Puede agregar el WS-FAM a la canalización HTTP de la aplicación, donde está a la espera de solicitudes de usuario no autenticadas y redirige a los usuarios al STS especificado.  
  
 El WS-FAM también genera varios eventos que le permiten personalizar su funcionalidad en una aplicación de [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].  
  
### <a name="how-the-ws-fam-works"></a>Cómo funciona el WS-FAM  
 El WS-FAM se implementa en la clase <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>. Normalmente, agrega el WS-FAM a la canalización HTTP de la aplicación RP de [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]. Cuando un usuario no autenticado intenta acceder a un recurso protegido, el RP devuelve una respuesta HTTP "401 Autorización denegada". El WS-FAM intercepta esta respuesta en lugar de permitir al cliente recibirla y, a continuación, redirige al usuario al STS especificado. El STS emite un token de seguridad, que el WS-FAM intercepta de nuevo. El WS-FAM utiliza el token para crear una instancia de <xref:System.Security.Claims.ClaimsPrincipal> para el usuario autenticado, lo que permite a los mecanismos de autorización de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] normales funcionar.  
  
 Dado que el HTTP no tiene estado, necesitamos una manera de evitar repetir todo este proceso completo cada vez que el usuario trata de tener acceso a otro recurso protegido. Aquí es donde entra en juego el <xref:System.IdentityModel.Services.SessionAuthenticationModule>. Cuando el STS emite un token de seguridad para el usuario, <xref:System.IdentityModel.Services.SessionAuthenticationModule> también crea un token de seguridad de la sesión para el usuario y lo coloca en una cookie. En solicitudes posteriores, <xref:System.IdentityModel.Services.SessionAuthenticationModule> intercepta esta cookie y la utiliza para reconstruir la <xref:System.Security.Claims.ClaimsPrincipal> del usuario.  
  
 En el siguiente diagrama se muestra el flujo general de información en el caso de redirección pasiva. La solicitud se redirige de manera automática a través del STS para establecer credenciales sin una página de inicio de sesión:  
  
 ![Diagrama que muestra inicie sesión con redirección pasiva.](./media/wsfederation-authentication-module-overview/sign-in-using-passive-redirect.gif)  
  
 En el diagrama siguiente se muestra con mayor detalle lo que sucede cuando el usuario se ha autenticado en el STS y el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> procesa sus tokens de seguridad:  
  
 ![Control de tiempo de procesamiento de tokens con redirección pasiva](../../../docs/framework/security/media/signinusingpassiveredirect-tokenprocessing.gif "SignInUsingPassiveRedirect_TokenProcessing")  
  
 En el siguiente diagrama se muestra con mayor detalle lo que sucede cuando se han serializado los tokens de seguridad del usuario en cookies y el <xref:System.IdentityModel.Services.SessionAuthenticationModule> los intercepta:  
  
 ![Diagrama de control de tiempo de SAM que muestra el inicio de sesión con controles](../../../docs/framework/security/media/signinusingconrols-sam.gif "SignInUsingConrols_SAM")  
  
### <a name="events"></a>Eventos  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>, <xref:System.IdentityModel.Services.SessionAuthenticationModule>, y su clase primaria, <xref:System.IdentityModel.Services.HttpModuleBase>, generan eventos en las diferentes fases de procesamiento de una solicitud HTTP. Puede controlar estos eventos en el archivo `global.asax` de la aplicación [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].  
  
- La infraestructura de ASP.NET invoca el método <xref:System.IdentityModel.Services.HttpModuleBase.Init%2A> del módulo para inicializarlo.  
  
- Se genera el evento <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated?displayProperty=nameWithType> cuando la infraestructura de ASP.NET invoca el método <xref:System.IdentityModel.Services.HttpModuleBase.Init%2A> por primera vez en uno de los módulos de la aplicación derivados de <xref:System.IdentityModel.Services.HttpModuleBase>. Este método obtiene acceso a la propiedad <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> estática, que hace que se cargue la configuración del archivo Web.config. Este evento solo se genera la primera vez que se accede a esta propiedad. Al objeto <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> que se inicializa desde la configuración se puede acceder mediante la propiedad <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> de un controlador de eventos. Puede utilizar este evento para modificar la configuración antes de que se aplique a cualquier módulo. Puede agregar un controlador para este evento en el método Application_Start:  
  
    ```  
    void Application_Start(object sender, EventArgs e)  
    {  
        FederatedAuthentication.FederationConfigurationCreated += new EventHandler<FederationConfigurationCreatedEventArgs>(FederatedAuthentication_FederationConfigurationCreated);  
    }  
    ```  
  
     Cada módulo invalida los métodos abstractos <xref:System.IdentityModel.Services.HttpModuleBase.InitializeModule%2A?displayProperty=nameWithType> y <xref:System.IdentityModel.Services.HttpModuleBase.InitializePropertiesFromConfiguration%2A?displayProperty=nameWithType>. El primero de estos métodos agrega controladores para los eventos de canalización de ASP.NET que son del interés del módulo. En la mayoría de los casos, la implementación predeterminada del módulo será suficiente. El segundo de estos métodos inicializa las propiedades del módulo desde su propiedad <xref:System.IdentityModel.Services.HttpModuleBase.FederationConfiguration%2A?displayProperty=nameWithType>. (Esta es una copia de la configuración que se cargó anteriormente). Puede que necesite invalidar este segundo método si desea admitir la inicialización de nuevas propiedades desde la configuración en clases derivadas de <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> o <xref:System.IdentityModel.Services.SessionAuthenticationModule>. En casos como este, también necesitaría derivar desde los objetos de configuración adecuados para admitir las propiedades de configuración agregadas; por ejemplo, desde <xref:System.IdentityModel.Configuration.IdentityConfiguration>, <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> o <xref:System.IdentityModel.Services.Configuration.FederationConfiguration>.  
  
- El WS-FAM genera el evento <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SecurityTokenReceived> cuando intercepta un token de seguridad que el STS ha emitido.  
  
- El WS-FAM genera el evento <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SecurityTokenValidated> después de validar el token.  
  
- El <xref:System.IdentityModel.Services.SessionAuthenticationModule> genera el evento <xref:System.IdentityModel.Services.SessionAuthenticationModule.SessionSecurityTokenCreated> cuando crea un token de seguridad de la sesión para el usuario.  
  
- El <xref:System.IdentityModel.Services.SessionAuthenticationModule> genera el evento <xref:System.IdentityModel.Services.SessionAuthenticationModule.SessionSecurityTokenReceived> cuando intercepta las solicitudes posteriores con la cookie que contiene el token de seguridad de la sesión.  
  
- Antes de que el WS-FAM redirija al usuario al emisor, genera el evento <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider>. La solicitud de inicio de sesión de WS-Federation está disponible mediante la propiedad <xref:System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs.SignInRequestMessage%2A> de los <xref:System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs> pasados en el evento. Puede elegir modificar la solicitud antes de enviarlos al emisor.  
  
- El WS-FAM genera el evento <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SignedIn> cuando la cookie se escribe correctamente y el usuario ha iniciado sesión.  
  
- El WS-FAM genera el evento <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SigningOut> una vez por sesión cuando se cierra la sesión para cada usuario. No se genera si la sesión se cierra en el lado del cliente (por ejemplo, eliminando la cookie de la sesión). En un entorno de SSO, el IP-STS también puede solicitar a cada RP que cierre sesión. Esto también generará este evento, con <xref:System.IdentityModel.Services.SigningOutEventArgs.IsIPInitiated%2A> establecido en `true`.  
  
> [!NOTE]
>  No debe utilizar la propiedad <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> durante ningún evento generado por <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> o <xref:System.IdentityModel.Services.SessionAuthenticationModule>. Esto se debe a que <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> se establece después del proceso de autenticación, mientras que los eventos se generan durante el proceso de autenticación.  
  
### <a name="configuration-of-federated-authentication"></a>Configuración de la autenticación federada  
 WS-FAM y SAM se configuran mediante el elemento [\<federationConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md). El elemento secundario [\<wsFederation>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md) configura los valores predeterminados de las propiedades de WS-FAM, como la propiedad <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.Issuer%2A> y la propiedad <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.Realm%2A>. (Estos valores se pueden cambiar en cada solicitud proporcionando controladores para algunos de los eventos de WS-FAM. Por ejemplo, <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider>). El controlador de cookies que usa SAM se configura mediante el elemento secundario [\<cookieHandler>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md). WIF proporciona un controlador de cookies predeterminado implementado en la clase <xref:System.IdentityModel.Services.ChunkedCookieHandler> cuyo tamaño de fragmento se puede establecer mediante el elemento [\<chunkedCookieHandler>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md). El elemento `<federationConfiguration>` hace referencia a un <xref:System.IdentityModel.Configuration.IdentityConfiguration>, que proporciona la configuración para otros componentes de WIF utilizados en la aplicación, como <xref:System.Security.Claims.ClaimsAuthenticationManager> y <xref:System.Security.Claims.ClaimsAuthorizationManager>. Se puede hacer referencia de manera explícita a la configuración de identidad al especificar un elemento [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) con nombre en el atributo `identityConfigurationName` del elemento `<federationConfiguration>`. Si no se hace referencia a la configuración de identidad de manera explícita, se usará la configuración de identidad predeterminada.  
  
 El código XML siguiente muestra una configuración de una aplicación de usuario de confianza (RP) de ASP.NET. Las secciones de configuración <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> y <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> se agregan bajo el elemento `<configSections>`. SAM y WS-FAM se agregan a los módulos HTTP bajo el elemento `<system.webServer>`/`<modules>`. Por último, los componentes de WIF se configuran bajo los elementos `<system.identityModel>`/`<identityConfiguration>` y `<system.identityModel.services>`/`<federationConfiguration>`. Esta configuración especifica el controlador de cookies fragmentado, ya que es el controlador de cookies predeterminado y no hay un tipo de controlador de cookies especificado en el elemento `<cookieHandler>`.  
  
> [!WARNING]
>  En el ejemplo siguiente, el atributo `requireHttps` del elemento `<wsFederation>` y el atributo `requireSsl` del elemento `<cookieHandler>` son `false`. Esto presenta una amenaza de seguridad potencial. En producción, ambos valores se deben establecer en `true`.  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  ...  
  
  <system.webServer>  
    <modules>  
      <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
    </modules>  
  </system.webServer>  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost:50969/" />  
      </audienceUris>  
      <certificateValidation certificateValidationMode="None" />  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
        <trustedIssuers>  
          <add thumbprint="9B74CB2F320F7AAFC156E1252270B1DC01EF40D0" name="LocalSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
    </identityConfiguration>  
  </system.identityModel>  
  <system.identityModel.services>  
    <federationConfiguration>  
      <wsFederation passiveRedirectEnabled="true" issuer="http://localhost:15839/wsFederationSTS/Issue" realm="http://localhost:50969/" reply="http://localhost:50969/" requireHttps="false" />  
      <cookieHandler requireSsl="false" />  
    </federationConfiguration>  
  </system.identityModel.services>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- [\<federationConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)
