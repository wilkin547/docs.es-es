---
title: IdentityServer para aplicaciones nativas en la nube
description: Diseño de aplicaciones .NET nativas en la nube para Azure | IdentityServer
ms.date: 06/30/2019
ms.openlocfilehash: 536a4cbdbdaee47f3a5a0d9f93b2736270d9ea7a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83394878"
---
# <a name="identityserver-for-cloud-native-applications"></a>IdentityServer para aplicaciones nativas para la nube

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

IdentityServer es un servidor de autenticación de código abierto que implementa los estándares OpenID Connect (OIDC) y OAuth 2,0 para ASP.NET Core. Está diseñado para proporcionar una manera común de autenticar las solicitudes en todas las aplicaciones, tanto si son puntos de conexión Web, nativos, móviles o de API. IdentityServer se puede usar para implementar el inicio de sesión único (SSO) para varias aplicaciones y tipos de aplicaciones. Se puede usar para autenticar a los usuarios reales mediante formularios de inicio de sesión e interfaces de usuario similares, así como la autenticación basada en servicio que normalmente implica la emisión, comprobación y renovación de tokens sin ninguna interfaz de usuario. IdentityServer está diseñado para ser una solución personalizable. Normalmente, cada instancia está personalizada para adaptarse a las necesidades de una organización o un conjunto de aplicaciones.

## <a name="common-web-app-scenarios"></a>Escenarios comunes de aplicaciones Web

Normalmente, las aplicaciones deben admitir algunos o todos los escenarios siguientes:

- Usuarios humanos que acceden a aplicaciones web con un explorador.
- Usuarios humanos que acceden a las API Web de back-end desde aplicaciones basadas en explorador.
- Usuarios humanos de clientes móviles o nativos que acceden a las API Web de back-end.
- Otras aplicaciones que acceden a las API Web de back-end (sin una interfaz de usuario o usuario activa).
- Cualquier aplicación puede necesitar interactuar con otras API Web, usando su propia identidad o delegando la identidad del usuario.

![Escenarios y tipos de aplicación](./media/application-types.png)

**Figura 8-1**. Tipos y escenarios de aplicaciones.

En cada uno de estos escenarios, la funcionalidad expuesta debe protegerse contra el uso no autorizado. Como mínimo, normalmente esto requiere la autenticación del usuario o la entidad de seguridad que realiza una solicitud para un recurso. Esta autenticación puede usar uno de varios protocolos comunes, como SAML2p, WS-FED o OpenID Connect. La comunicación con las API normalmente usa el protocolo OAuth2 y su compatibilidad con los tokens de seguridad. La separación de estas cuestiones críticas de seguridad transversales y sus detalles de implementación de las propias aplicaciones garantiza la coherencia y mejora la seguridad y el mantenimiento. El outsourcing de estos problemas con un producto dedicado, como IdentityServer, ayuda a la necesidad de que cada aplicación resuelva estos problemas por sí mismo.

IdentityServer proporciona middleware que se ejecuta dentro de una aplicación ASP.NET Core y agrega compatibilidad con OpenID Connect y OAuth2 (consulte las [Especificaciones admitidas](http://docs.identityserver.io/en/latest/intro/specs.html)). Las organizaciones crearían su propia aplicación ASP.NET Core con middleware IdentityServer para que actúe como STS para todos sus protocolos de seguridad basados en tokens. El middleware IdentityServer expone puntos de conexión para admitir la funcionalidad estándar, como:

- Autorizar (autenticar al usuario final)
- Token (solicitar un token mediante programación)
- Detección (metadatos sobre el servidor)
- Información de usuario (obtener información de usuario con un token de acceso válido)
- Autorización de dispositivo (se usa para iniciar la autorización de flujo de dispositivo)
- Introspección (validación de token)
- Revocación (revocación de tokens)
- Finalizar sesión (desencadenar el cierre de sesión único en todas las aplicaciones)

## <a name="getting-started"></a>Introducción

IdentityServer4 es de código abierto y está disponible para su uso. Puede agregarlo a las aplicaciones mediante sus paquetes de NuGet. El paquete principal es [IdentityServer4](https://www.nuget.org/packages/IdentityServer4/) que se ha descargado más de 4 millones veces. El paquete base no incluye ningún código de interfaz de usuario y solo admite en la configuración de memoria. Para usarlo con una base de datos, también querrá un proveedor de datos como [IdentityServer4. EntityFramework](https://www.nuget.org/packages/IdentityServer4.EntityFramework) que usa Entity Framework Core para almacenar la configuración y los datos operativos de IdentityServer. Para la interfaz de usuario, puede copiar archivos del repositorio de la interfaz de usuario de [Inicio rápido](https://github.com/IdentityServer/IdentityServer4.Quickstart.UI) en la aplicación ASP.net Core MVC para agregar compatibilidad para iniciar sesión y cerrar sesión con middleware IdentityServer.

## <a name="configuration"></a>Configuración

IdentityServer admite distintos tipos de protocolos y proveedores de autenticación social que se pueden configurar como parte de cada instalación personalizada. Esto se hace normalmente en la clase de la aplicación ASP.NET Core `Startup` en el `ConfigureServices` método. La configuración implica especificar los protocolos admitidos y las rutas de acceso a los servidores y extremos que se usarán. En la figura 8-2 se muestra una configuración de ejemplo tomada del proyecto de IU de inicio rápido de IdentityServer4:

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();

        // some details omitted
        services.AddIdentityServer();

          services.AddAuthentication()
            .AddGoogle("Google", options =>
            {
                options.SignInScheme = IdentityServerConstants.ExternalCookieAuthenticationScheme;

                options.ClientId = "<insert here>";
                options.ClientSecret = "<insert here>";
            })
            .AddOpenIdConnect("demoidsrv", "IdentityServer", options =>
            {
                options.SignInScheme = IdentityServerConstants.ExternalCookieAuthenticationScheme;
                options.SignOutScheme = IdentityServerConstants.SignoutScheme;

                options.Authority = "https://demo.identityserver.io/";
                options.ClientId = "implicit";
                options.ResponseType = "id_token";
                options.SaveTokens = true;
                options.CallbackPath = new PathString("/signin-idsrv");
                options.SignedOutCallbackPath = new PathString("/signout-callback-idsrv");
                options.RemoteSignOutPath = new PathString("/signout-idsrv");

                options.TokenValidationParameters = new TokenValidationParameters
                {
                    NameClaimType = "name",
                    RoleClaimType = "role"
                };
            });
    }
}
```

**Figura 8-2**. Configuración de IdentityServer.

IdentityServer también hospeda un sitio de demostración público que se puede usar para probar diversos protocolos y configuraciones. Se encuentra en [https://demo.identityserver.io/](https://demo.identityserver.io/) e incluye información sobre cómo configurar su comportamiento en función del que `client_id` se le proporciona.

## <a name="javascript-clients"></a>Clientes de JavaScript

Muchas aplicaciones nativas en la nube aprovechan las API del lado servidor y las aplicaciones de página única de cliente enriquecidas (Spa) en el front-end. IdentityServer envía un [cliente de JavaScript](http://docs.identityserver.io/en/latest/quickstarts/4_javascript_client.html) ( `oidc-client.js` ) a través de NPM que se puede Agregar a Spa para permitirles usar IdentityServer para el inicio de sesión, el cierre de sesión y la autenticación basada en tokens de las API Web.

## <a name="references"></a>Referencias

- [Documentación de IdentityServer](http://docs.identityserver.io/en/latest/)
- [Tipos de aplicación](https://docs.microsoft.com/azure/active-directory/develop/app-types)
- [Cliente OIDC de JavaScript](http://docs.identityserver.io/en/latest/quickstarts/4_javascript_client.html)

>[!div class="step-by-step"]
>[Anterior](azure-active-directory.md)
>[Siguiente](security.md)
