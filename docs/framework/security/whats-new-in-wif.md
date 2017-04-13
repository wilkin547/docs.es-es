---
title: "Novedades de Windows Identity Foundation 4.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3b381f04-593b-471f-bd33-0362be1aade5
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# Novedades de Windows Identity Foundation 4.5
La primera versión de Windows Identity Foundation \(WIF\) se suministró como una descarga independiente y se conoce como WIF 3.5 porque se introdujo en el período de tiempo de .NET 3.5 SP1.  A partir de .NET 4.5, WIF forma parte de .NET Framework.  Tener las clases de WIF disponibles directamente en la propia plataforma permite una integración mucho más profunda de la identidad basada en notificaciones en la plataforma .NET, lo que facilita el uso de notificaciones.  Las aplicaciones escritas para WIF 3.5 se tendrán que modificar para aprovechar el nuevo modelo; para obtener información, vea [Directrices para migrar a WIF 4.5 una aplicación compilada con WIF 3.5](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md).  
  
 A continuación, encontrará algunos aspectos destacados de los cambios principales.  
  
## WIF ahora forma parte de .NET Framework  
 Las clases de WIF se extienden ahora por varios ensamblados, siendo los principales `mscorlib`, `System.IdentityModel`, `System.IdentityModel.Services` y `System.ServiceModel`.  De igual manera, las clases de WIF se extienden por varios espacios de nombres: <xref:System.Security.Claims?displayProperty=fullName>, varios espacios de nombres [System.IdentityModel](http://go.microsoft.com/fwlink/?LinkId=272004) y <xref:System.ServiceModel.Security?displayProperty=fullName>.  El espacio de nombres <xref:System.Security.Claims?displayProperty=fullName> contiene las nuevas clases <xref:System.Security.Claims.ClaimsPrincipal> y <xref:System.Security.Claims.ClaimsIdentity> \(véase a continuación\).  Todas las entidades de seguridad de .NET se derivan ahora de <xref:System.Security.Claims.ClaimsPrincipal>.  Para obtener información más detallada acerca de los espacios de nombres de WIF y los tipos de clases que contienen, vea [Referencia de API de WIF](../../../docs/framework/security/wif-api-reference.md).  Para obtener información acerca de la asignación de espacios de nombres entre WIF 3.5 y WIF 4.5, vea [Asignación de espacio de nombres entre WIF 3.5 y WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md).  
  
## Nuevo modelo de notificaciones y objeto de entidad de seguridad  
 Las notificaciones forman parte del núcleo de .NET Framework 4.5. Toda las clases de notificación base \(<xref:System.Security.Claims.Claim>, <xref:System.Security.Claims.ClaimsIdentity>, <xref:System.Security.Claims.ClaimsPrincipal>, <xref:System.Security.Claims.ClaimTypes> y <xref:System.Security.Claims.ClaimValueTypes>\) se encuentran directamente en `mscorlib` en el espacio de nombres <xref:System.Security.Claims?displayProperty=fullName>.  Ya no es necesario utilizar interfaces para conectar notificaciones en el sistema de identidad de .NET: <xref:System.Security.Principal.WindowsPrincipal>, <xref:System.Security.Principal.GenericPrincipal> y <xref:System.Web.Security.RolePrincipal> heredan ahora de <xref:System.Security.Claims.ClaimsPrincipal>; y <xref:System.Security.Principal.WindowsIdentity>, <xref:System.Security.Principal.GenericIdentity> y <xref:System.Web.Security.FormsIdentity> heredan ahora de <xref:System.Security.Claims.ClaimsIdentity>.  En resumen, cada clase de entidad de seguridad servirá ahora notificaciones.  De esta manera, se han eliminado las interfaces y las clases de integración de WIF 3.5 \(`WindowsClaimsIdentity`, `WindowsClaimsPrincipal`, `IClaimsPrincipal`, `IClaimsIdentity`\).  Además, la clase <xref:System.Security.Claims.ClaimsIdentity> expone ahora métodos que facilitan la consulta de la colección de notificaciones de identidad.  
  
## Cambios en la experiencia de Visual Studio de WIF 4.5  
  
-   La funcionalidad de Visual Studio **Agregar referencia de servicio STS…** \(utilidad cmdline FedUtil\) ya no existe; en su lugar, puede utilizar la nueva extensión de Visual Studio **Identity and Access Tool for Visual Studio 2012**.  Esto le permite federarse con un STS existente o utilizar LocalSTS para probar sus soluciones.  Tras instalar la extensión, puede hacer clic con el botón secundario en el proyecto y buscar **Identity and Access** en el menú contextual.  
  
-   Las plantillas de ASP.NET y STS que ya no se proporcionan como notificaciones se pueden utilizar directamente en las plantillas de proyecto existentes para ASP.Net, sitios web y WCF.  
  
-   Los controles del espacio de nombres de `Microsoft.IdentityModel.Web.Controls` \(`SignInControl`, `FederatedPassiveSignInControl` y `FederatedPassiveSignInStatus`\) no se transmiten a WIF 4.5.  
  
## Cambios en la API de WIF 4.5  
  
-   En general, las clases relacionadas con notificaciones se encuentran en el espacio de nombres <xref:System.Security.Claims?displayProperty=fullName>; las clases relacionadas con WCF \(contratos de servicio, canales, generadores de canales y hosts de servicio que se usan para escenarios de WS\-Trust\) se encuentran en <xref:System.ServiceModel.Security?displayProperty=fullName>; y el resto de las clases de WIF se extienden por diversos espacios de nombres [System.IdentityModel](http://go.microsoft.com/fwlink/?LinkId=272004) \(entre estas se incluyen, por ejemplo, las clases que representan artefactos de WS\-\* y SAML, controladores de tokens y clases relacionadas, y clases utilizadas en escenarios de WS\-Federation\).  Para obtener más información, vea [Asignación de espacio de nombres entre WIF 3.5 y WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md) y [Referencia de API de WIF](../../../docs/framework/security/wif-api-reference.md).  
  
-   La clave del equipo se ha habilitado para usarla en cookies de sesión para escenarios de granjas de servidores web.  Para obtener más información, vea [WIF y granjas de servidores web](../../../docs/framework/security/wif-and-web-farms.md).  
  
-   Ahora WIF se configura mediante declaración bajo los elementos [\<system.identityModel\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) y [\<system.identityModel.services\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md).  Para obtener más información sobre la configuración de WIF, vea [Referencia de configuración de WIF](../../../docs/framework/security/wif-configuration-reference.md).  
  
## Otros cambios o características de .NET destacables producidos por la integración de WIF en .NET  
  
-   La posibilidad de realizar la autorización basada en notificaciones \(CBAC\) forma ahora parte integral de .NET Framework.  Puede configurar un objeto <xref:System.Security.Claims.ClaimsAuthorizationManager> y, después, utilizar las clases <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> y <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> para realizar comprobaciones de acceso imperativas y declarativas en el código.  CBAC proporciona mayor flexibilidad y granularidad que las comprobaciones de acceso basadas en roles \(RBAC\) tradicionales.  También permite una mayor separación de la directiva de autorización de la lógica de negocios porque la lógica de negocios puede basar la comprobación de acceso en una notificación concreta o conjunto de notificaciones y la directiva de autorización para dichas notificaciones se puede configurar mediante declaración bajo el elemento [\<claimsAuthorizationManager\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md).  
  
## Cambios de WCF como resultado de la integración de WIF:  
  
-   El modelo de identidad basado en notificaciones de WCF se reemplaza por WIF.  Esto significa que se deben quitar las clases de los espacios de nombres <xref:System.IdentityModel.Claims?displayProperty=fullName>, <xref:System.IdentityModel.Policy?displayProperty=fullName> y <xref:System.IdentityModel.Selectors?displayProperty=fullName> y que se deben usar las clases de WIF.  
  
-   WIF se habilita ahora en un servicio WCF especificando el atributo `useIdentityConfiguration` en el elemento `<system.serviceModel>`\/`<behaviors>`\/`<serviceBehaviors>`\/`<serviceCredentials>` como en el siguiente código XML:  
  
    ```xml  
    <serviceCredentials useIdentityConfiguration="true">  
        <!--Certificate added by Identity And Access VS Package.  Subject='CN=localhost', Issuer='CN=localhost'. Make sure you have this certificate installed. The Identity and Access tool does not install this certificate.-->  
        <serviceCertificate findValue="CN=localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName" />  
    </serviceCredentials>  
    ```  
  
     Cuando se utiliza **Identity and Access Tool for Visual Studio 2012** \(vea la sección anterior **Cambios en la experiencia de Visual Studio**\), la herramienta agrega un elemento `<serviceCredentials>` con el atributo `useIdentityConfiguration` establecido en el archivo de configuración para el usuario.  También agrega un elemento [\<system.identityModel\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) correspondiente que contiene las opciones de configuración de WIF y agrega un enlace y otros valores necesarios para externalizar la autenticación al STS elegido.  
  
## Vea también  
 [Directrices para migrar a WIF 4.5 una aplicación compilada con WIF 3.5](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md)   
 [Asignación de espacio de nombres entre WIF 3.5 y WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)   
 [Referencia de API de WIF](../../../docs/framework/security/wif-api-reference.md)   
 [Referencia de configuración de WIF](../../../docs/framework/security/wif-configuration-reference.md)