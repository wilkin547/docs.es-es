---
title: Directrices para migrar a WIF 4.5 una aplicación compilada con WIF 3.5
ms.date: 03/30/2017
ms.assetid: 7a32fe6e-5f68-4693-9371-19411fa8063c
author: BrucePerlerMS
ms.openlocfilehash: ad8ff2b6daaaf48975b86c637435b31fa1869e1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940574"
---
# <a name="guidelines-for-migrating-an-application-built-using-wif-35-to-wif-45"></a>Directrices para migrar a WIF 4.5 una aplicación compilada con WIF 3.5

## <a name="applies-to"></a>Se aplica a

- Microsoft® Windows® Identity Foundation (WIF) 3.5 y 4.5.

## <a name="overview"></a>Información general

Windows Identity Foundation (WIF) se publicó originalmente en el período de tiempo de .NET 3.5 SP1. Esa versión de WIF se denomina WIF 3.5. Se publicó como SDK y runtime independiente, lo que significa que cada equipo en el que se ejecutaba una aplicación habilitada para WIF debía tener el runtime de WIF instalado y los desarrolladores debían descargar e instalar el SDK de WIF para obtener las plantillas de Visual Studio y las herramientas que permitían el desarrollo de aplicaciones habilitadas para WIF. A partir de .NET 4.5, WIF se ha integrado por completo en .NET Framework. Ya no es necesario un runtime independiente y las herramientas de WIF se pueden instalar en Visual Studio 2012 mediante el Administrador de extensiones de Visual Studio. Esta versión de WIF se denomina WIF 4.5.

La integración de WIF en .NET requería varios cambios en la superficie de la API de WIF. WIF 4.5 incluye espacios de nombres nuevos, algunos cambios en los elementos de configuración y nuevas herramientas para Visual Studio. En este tema se proporcionan instrucciones que le pueden servir de ayuda para migrar aplicaciones compiladas con WIF 3.5 a WIF 4.5. Puede haber escenarios en los que necesite ejecutar aplicaciones heredadas compiladas con WIF 3.5 en equipos que ejecutan Windows 8 o Windows Server 2012. En este tema también se proporcionan instrucciones sobre cómo habilitar WIF 3.5 para estos sistemas operativos.

## <a name="changes-required-for-wif-45"></a>Cambios necesarios para WIF 4.5

En esta sección se describen los cambios necesarios para migrar una aplicación de WIF 3.5 a WIF 4.5.

### <a name="assembly-and-namespace-changes"></a>Cambios de ensamblado y espacio de nombres

En WIF 3.5, todas las clases de WIF se incluían en el ensamblado `Microsoft.IdentityModel` (microsoft.identitymicrosoft.identitymodel.dll). En WIF 4.5, las clases de WIF se han dividido entre los siguientes ensamblados: `mscorlib` (mscorlib.dll), `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll) y `System.ServiceModel` (System.ServiceModel.dll).

Todas las clases de WIF 3.5 se incluían en uno de los espacios de nombres `Microsoft.IdentityModel`; por ejemplo, `Microsoft.IdentityModel`, `Microsoft.IdentityModel.Tokens`, `Microsoft.IdentityModel.Web`, etc. En WIF 4.5, las clases de WIF ahora se extienden por los espacios de nombres [System.IdentityModel](https://go.microsoft.com/fwlink/?LinkId=272004), el espacio de nombres <xref:System.Security.Claims?displayProperty=nameWithType> y el espacio de nombres <xref:System.ServiceModel.Security?displayProperty=nameWithType>. Además de esta reorganización, algunas clases de WIF 3.5 se han quitado en WIF 4.5.

En la tabla siguiente se muestran algunos de los espacios de nombres de WIF 4.5 más importantes y el tipo de clases que contienen. Para obtener información detallada sobre la asignación de espacios de nombres entre WIF 3.5 y WIF 4.5 y los espacios de nombres y las clases que se han quitado en WIF 4.5, vea [Asignación de espacio de nombres entre WIF 3.5 y WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md).

|Espacio de nombres de WIF 4.5|Descripción|
|-----------------------|-----------------|
|<xref:System.IdentityModel?displayProperty=nameWithType>|Contiene clases que representan las transformaciones de cookies, los servicios de token de seguridad y los lectores de diccionario XML especializados. Contiene clases de los siguientes espacios de nombres de WIF 3.5: `Microsoft.IdentityModel`, `Microsoft.IdentityModel.SecurityTokenService` y `Microsoft.IdentityModel.Threading`.|
|<xref:System.Security.Claims?displayProperty=nameWithType>|Contiene clases que representan notificaciones, identidades basadas en notificaciones, entidades de seguridad basadas en notificaciones y otros artefactos del modelo de identidad basado en notificaciones. Contiene clases del espacio de nombres `Microsoft.IdentityModel.Claims`.|
|<xref:System.IdentityModel.Tokens?displayProperty=nameWithType>|Contiene clases que representan tokens de seguridad, controladores de tokens de seguridad y otros artefactos de tokens de seguridad. Contiene clases de los siguientes espacios de nombres de WIF 3.5: `Microsoft.IdentityModel.Tokens`, `Microsoft.IdentityModel.Tokens.Saml11` y `Microsoft.IdentityModel.Tokens.Saml2`.|
|<xref:System.IdentityModel.Services?displayProperty=nameWithType>|Contiene clases que se usan en escenarios pasivos (WS-Federation). Contiene clases del espacio de nombres `Microsoft.IdentityModel.Web`.|
|<xref:System.ServiceModel.Security?displayProperty=nameWithType>|Las clases que representan contratos WCF, canales, hosts de servicio y otros artefactos que se usan en escenarios activos (WS-Trust) se encuentran ahora en este espacio de nombres. En WIF 3.5, estas clases estaban en el espacio de nombres `Microsoft.IdentityModel.Protocols.WSTrust`.|

> [!IMPORTANT]
> Los siguientes espacios de nombres `System.IdentityModel` contienen clases que implementan el modelo de identidad basado en notificaciones de WCF: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType> y <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>. El modelo de identidad basado en notificaciones de WCF se reemplaza por WIF. No debe utilizar clases en estos tres espacios de nombres cuando compile soluciones basadas en WIF.

### <a name="changes-due-to-net-integration"></a>Cambios originados por la integración de .NET

WIF se integra ahora en .NET Framework. La mayoría de las clases de identidad y entidad de seguridad de .NET derivan ahora de <xref:System.Security.Claims.ClaimsIdentity?displayProperty=nameWithType> y <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=nameWithType>. Esto da lugar a los siguientes cambios en WIF 4.5:

- Las clases de WIF que representan notificaciones, identidades y entidades de seguridad se encuentran ahora en el espacio de nombres <xref:System.Security.Claims?displayProperty=nameWithType>.

    > [!IMPORTANT]
    > El espacio de nombres <xref:System.IdentityModel.Claims?displayProperty=nameWithType> contiene clases que representan artefactos en el modelo de identidad basado en notificaciones de WCF. Muchas de estas clases tienen los mismos nombres que las clases de WIF; por ejemplo, `Claims`. No utilice estas clases al compilar soluciones basadas en WIF.

- Las clases de identidad y entidad de seguridad de .NET derivan ahora directamente de <xref:System.Security.Claims.ClaimsIdentity?displayProperty=nameWithType> y <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=nameWithType>, que representan identidades y entidades de seguridad basadas en notificaciones. Por esta razón, ya no se necesitan las interfaces de WIF 3.5 `IClaimsIdentity` y `IClaimsPrincipal` y no están disponibles en WIF 4.5.

- Dado que las clases de identidad y entidad de seguridad de .NET, como <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType> y <xref:System.Security.Principal.WindowsPrincipal?displayProperty=nameWithType> se derivan ahora de <xref:System.Security.Claims.ClaimsIdentity> y <xref:System.Security.Claims.ClaimsPrincipal>, tienen la funcionalidad de notificaciones integrada. Por este motivo, las clases de identidad y entidad de seguridad específicas de notificaciones, como `WindowsClaimsIdentity` y `WindowsClaimsPrincipal`, que estaban presentes en WIF 3.5 ya no se necesitan y no existen en WIF 4.5.

### <a name="other-changes-to-wif-functionality"></a>Otros cambios en la funcionalidad de WIF

Además de los cambios en el espacio de nombres y los cambios originados por la integración con .NET, se producen los siguientes cambios generales en la funcionalidad de WIF en WIF 4.5.

- Se quita la clase `Microsoft.IdentityModel.ExceptionMapper`, que proporcionaba la funcionalidad que le permitía asignar excepciones a los errores de SOAP específicos.

- La superficie de la excepción se ha reducido de manera considerable.

- Se han eliminado muchas de las clases que definían las constantes específicas de WS-* o protocolo; por ejemplo, la clase `Microsoft.IdentityModel.WSAddressing10Constants`, que definía constantes relacionadas con WS-Addressing 1.0.

- Se han quitado las notificaciones del servicio de token de Windows (c2wts) y sus clases asociadas del espacio de nombres `Microsoft.IdentityModel.WindowsTokenService`.

### <a name="wif-configuration-changes"></a>Cambios de configuración de WIF

Muchos de los cambios del archivo de configuración se han producido por las actualizaciones del espacio de nombres en WIF 4.5. Por ejemplo, considere la siguiente entrada de WIF 3.5 de la sección `<httpModules>` para agregar el Administrador de autenticaciones de WS-Federation a una aplicación:

```xml
<add name="WSFederationAuthenticationModule" type="Microsoft.IdentityModel.Web.WSFederationAuthenticationModule, Microsoft.IdentityModel, Version=3.5.0.0, Culture=neutral, PublicKeyToken=abcd … 5678" />
```

Esta entrada se ha actualizado en WIF 4.5 para incluir los nuevos espacios de nombres y la versión de ensamblado:

```xml
<add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=abcd … 5678"/>
```

En la lista siguiente se muestran los cambios principales en el archivo de configuración de WIF 4.5.

- La sección `<microsoft.identityModel>` es ahora la sección [\<system.identityModel>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md).

- El elemento `<service>` es ahora el elemento [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md).

- Se ha agregado una nueva sección, [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md), para especificar valores que controlan el comportamiento en escenarios pasivos (WS-Federation).

- El elemento [\<federationConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) y sus elementos secundarios se han movido del elemento `<service>` de WIF 3.5 al nuevo elemento `<system.identityModel.services>`.

- Se han restringido varios elementos que se podían especificar en el nivel de servicio directamente bajo el elemento `<service>` en WIF 3.5 a su especificación bajo el elemento [\<securityTokenHandlerConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md). (Todavía se pueden especificar bajo el elemento [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) en WIF 4.5 para facilitar la compatibilidad con versiones anteriores).

Para obtener una lista completa de los elementos de configuración de WIF 4.5, vea [Esquema de configuración de WIF](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/index.md).

### <a name="visual-studio-tooling-changes"></a>Cambios en las herramientas de Visual Studio

El SDK de WIF 3.5 ofrecía una utilidad de federación independiente, FedUtil.exe (FedUtil), que podía utilizar para externalizar la administración de identidades en aplicaciones habilitadas para WIF a un servicio de token de seguridad (STS). Esta herramienta agregaba valores de WIF al archivo de configuración de la aplicación para que la aplicación obtuviera los tokens de seguridad de uno o más STS, y aparecía en Visual Studio mediante el botón **Agregar referencia de servicio STS**. FedUtil no se distribuye con WIF 4.5. En su lugar, WIF 4.5 admite una nueva extensión de Visual Studio denominada Identity and Access Tool for Visual Studio 2012 que puede utilizar para modificar el archivo de configuración de la aplicación con los valores de WIF necesarios para externalizar la administración de identidades a un STS. Identity and Access Tool también implementa un STS denominado STS local que puede usar para probar las aplicaciones habilitadas para WIF. En muchos casos, esta característica obvia la necesidad de compilar STS personalizados que, a menudo, son necesarios en WIF 3.5 para probar soluciones en desarrollo. Por este motivo, las plantillas de STS ya no se admiten en Visual Studio 2012. Sin embargo, las clases que admiten el desarrollo de STS siguen estando disponibles en WIF 4.5.

Puede instalar la herramienta identidad y acceso desde el Administrador de actualizaciones en Visual Studio y las extensiones o puede descargarlo desde la página siguiente en la Galería de código: [Identity and Access Tool para Visual Studio 2012 en la Galería de código](https://go.microsoft.com/fwlink/?LinkID=245849). Los cambios de las herramientas de Visual Studio se resumen en la siguiente lista:

- Se ha quitado la funcionalidad Agregar referencia de servicio de STS. Se ha sustituido por la extensión Identity and Access Tool.

- Se han quitado las plantillas STS de Visual Studio. Puede utilizar el STS local disponible a través de la extensión Identity and Access Tool para probar soluciones de identidad desarrolladas con WIF. La configuración del STS local se puede modificar para personalizar las notificaciones que sirve.

- La utilidad de federación independiente (FedUtil) no está disponible en WIF 4.5. Puede utilizar la extensión Identity and Access Tool para modificar los archivos de configuración y externalizar la administración de identidades a un STS.

Para obtener más información sobre la herramienta de identidad y acceso, vea [Herramienta de identidad y acceso para Visual Studio 2012](../../../docs/framework/security/identity-and-access-tool-for-vs.md).

<a name="BKMK_ToolingChanges"></a>

### <a name="passive-ws-federation-scenarios"></a>Escenarios pasivos (WS-Federation):

- Las clases que admiten escenarios pasivos se han movido al espacio de nombres <xref:System.IdentityModel.Services?displayProperty=nameWithType>. En WIF 3.5, estas clases estaban en el espacio de nombres `Microsoft.IdentityModel.Web`.

- Las clases del espacio de nombres `Microsoft.IdentityModel.Web.Configuration` se han movido a <xref:System.IdentityModel.Services.Configuration?displayProperty=nameWithType>. Estas clases representan objetos específicos de la configuración en escenarios pasivos.

- Ya no se admite `FederatedPassiveSignInControl`; se han quitado todas las clases del espacio de nombres `Microsoft.IdentityModel.Web.Controls` de WIF 4.5.

- La funcionalidad de cierre de sesión del módulo de autenticación de WS-Federation (<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>) es distinta de la de WIF 3.5. Para obtener más información sobre cómo funciona el cierre de sesión en WIF 4.5, vea el tema de la clase <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>.

### <a name="active-wcfws-trust-scenarios"></a>Escenarios activos (WCF/WS-Trust):

- El espacio de nombres `Microsoft.IdentityModel.Protocols.WSTrust` se ha dividido principalmente en dos espacios de nombres en WIF 4.5. Las clases que representan artefactos específicos del protocolo WS-Trust se encuentran ahora en <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType>. Esto incluye clases como <xref:System.IdentityModel.Protocols.WSTrust.RequestSecurityToken>. Las clases que representan contratos de servicio, canales, hosts de servicio y otros artefactos que intervienen en el uso de WS-Trust en aplicaciones de WCF se han movido a <xref:System.ServiceModel.Security?displayProperty=nameWithType>; por ejemplo, la interfaz <xref:System.ServiceModel.Security.IWSTrust13AsyncContract>.

- La configuración de una aplicación de WCF para usar WIF se ha simplificado en gran medida. Anteriormente, `Microsoft.IdentityModel.Configuration.ConfigureServiceHostBehaviorExtensionElement` se tenía que agregar como extensión de comportamiento y esta funcionalidad se utilizaba para acuñar WIF en el comportamiento del servicio especificando un elemento `<federatedServiceHostConfiguration>`. WIF 4.5 se ha integrado más estrechamente con WCF. WIF se habilita ahora en un servicio WCF especificando el atributo `useIdentityConfiguration` en el elemento `<system.serviceModel>`/`<behaviors>`/`<serviceBehaviors>`/`<serviceCredentials>`, como en el siguiente código XML:

    ```xml
    <serviceCredentials useIdentityConfiguration="true">
        <!--Certificate added by Identity And Access VS Package.  Subject='CN=localhost', Issuer='CN=localhost'. Make sure you have this certificate installed. The Identity and Access tool does not install this certificate.-->
        <serviceCertificate findValue="CN=localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName" />
    </serviceCredentials>
    ```

- En WIF 4.5, el certificado de servicio que utiliza un servicio activo (WCF) se debe especificar en el host de servicio. En la configuración, puede hacerlo a través del elemento `<system.serviceModel>`/`<behaviors>`/`<serviceBehaviors>`/`<serviceCredentials>`/`<serviceCertificate>`, como se muestra en el ejemplo anterior. En WIF 3.5 el certificado de servicio se podía especificar a través del elemento secundario `<serviceCertificate>` del elemento `<service>` de WIF. Esta funcionalidad no existe en WIF 4.5; especifique en su lugar el elemento `<serviceCertificate>` bajo el elemento `<serviceCredentials>`.

- Las clases utilizadas para acuñar WIF 3.5 en WCF ya no existen. Esto incluye las siguientes clases en el espacio de nombres `Microsoft.IdentityModel.Tokens`: `FederatedSecurityTokenManager`, `FederatedServiceCredentials` y `IdentityModelServiceAuthorizationManager`, así como la clase `Microsoft.IdentityModel.Configuration.ConfigureServiceHostBehaviorExtensionElement`.

## <a name="enabling-wif-35-in-windows-8"></a>Habilitar WIF 3.5 en Windows 8

Dado que WIF 4.5 forma parte de .NET 4.5, se habilita automáticamente en los equipos que ejecutan Windows 8 y Windows Server 2012, y las aplicaciones que se compilan con WIF 4.5 se ejecutarán en Windows 8 o Windows Server 2012 de forma predeterminada. Sin embargo, puede que sea necesario ejecutar aplicaciones compiladas con WIF 3.5 en un equipo que ejecute Windows 8 o Windows Server 2012. En este caso, tiene que habilitar WIF 3.5 en el equipo de destino. En un equipo que ejecute Windows 8, puede hacerlo mediante la herramienta Administración y mantenimiento de imágenes de implementación (DISM). En un equipo que ejecute Windows Server 2012, puede utilizar la herramienta DISM o usar el cmdlet `Add-WindowsFeature` de Windows PowerShell. En ambos casos, los comandos adecuados se pueden invocar en la línea de comandos o desde dentro del entorno de Windows PowerShell.

Los comandos siguientes muestran cómo utilizar la herramienta DISM desde la línea de comandos o desde dentro del entorno de Windows PowerShell. De forma predeterminada, el módulo de PowerShell de DISM se incluye en Windows 8 y Windows Server 2012 y no necesita importarse. Para obtener más información sobre cómo usar DISM con Windows PowerShell, vea [Usar DISM en Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=254419).

Para habilitar WIF 3.5 mediante DISM:

```console
dism /online /enable-feature:windows-identity-foundation
```

Para deshabilitar WIF 3.5 mediante DISM:

```console
dism /online /disable-feature:windows-identity-foundation
```

Para comprobar qué características están habilitadas o deshabilitadas mediante DISM:

```console
dism /online /get-features
```

Como alternativa, en los equipos que ejecutan Windows Server 2012, puede habilitar WIF 3.5 mediante el cmdlet `Add-WindowsFeature` de Windows PowerShell. Para hacerlo desde la línea de comandos, puede escribir el siguiente comando:

```console
powershell "add-windowsfeature windows-identity-foundation"
```

 Desde el entorno de Windows PowerShell, puede escribir el comando directamente:

```powershell
Add-WindowsFeature windows-identity-foundation
```

> [!NOTE]
> Dado que muchas de las clases de WIF 3.5 y WIF 4.5 comparten los mismos nombres, cuando utilice WIF 3.5 y WIF 4.5 al mismo tiempo, asegúrese de usar nombres de clases completos o alias de espacio de nombres para distinguir entre las clases de WIF 3.5 y WIF 4.5.

## <a name="see-also"></a>Vea también

- [Esquema de configuración de WIF](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/index.md)
- [Asignación de espacio de nombres entre WIF 3.5 y WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)
- [Novedades de Windows Identity Foundation 4.5](../../../docs/framework/security/whats-new-in-wif.md)
- [Identity and Access Tool para Visual Studio 2012](../../../docs/framework/security/identity-and-access-tool-for-vs.md)
