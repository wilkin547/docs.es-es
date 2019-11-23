---
title: Llamada a Credentials-gRPC para desarrolladores de WCF
description: Cómo implementar y usar credenciales de llamada de gRPC en ASP.NET Core 3,0.
ms.date: 09/02/2019
ms.openlocfilehash: 2588fe3590a63ea6071b85ff29b3685efbfa25db
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967998"
---
# <a name="call-credentials"></a>Credenciales de llamada

Las credenciales de llamada se basan en algún tipo de token que se pasa en los metadatos con cada solicitud.

## <a name="ws-federation"></a>WS-Federation

ASP.NET Core admite WS-Federation mediante el paquete NuGet [WsFederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) . WS-Federation es la alternativa disponible más cercana a la autenticación de Windows, que no se admite a través de HTTP/2. Los usuarios se autentican mediante Servicios de federación de Active Directory (AD FS) (ADFS), que proporciona un token que se puede usar para autenticarse con ASP.NET Core.

Para obtener más información sobre cómo empezar a usar este método de autenticación, consulte el artículo [autenticación de usuarios con WS-Federation en ASP.net Core](https://docs.microsoft.com/aspnet/core/security/authentication/ws-federation?view=aspnetcore-3.0) .

## <a name="jwt-bearer-tokens"></a>Tokens de portador JWT

El estándar [JSON Web Token](https://jwt.io) proporciona una manera de codificar información sobre un usuario y sus notificaciones en una cadena codificada, así como firmar ese token de tal forma que el consumidor pueda comprobar la integridad del token mediante la criptografía de clave pública. Puede usar varios servicios, como IdentityServer4, para autenticar a los usuarios y generar tokens OpenID Connect (OIDC) para usarlos con las API de gRPC y HTTP.

ASP.NET Core 3,0 puede administrar tokens web JSON mediante el paquete de portador JWT. La configuración es exactamente la misma para una aplicación gRPC como una aplicación de MVC ASP.NET Core.

Este capítulo se centrará en los tokens de portador JWT, ya que son más fáciles de desarrollar con respecto a WS-Federation.

## <a name="adding-authentication-and-authorization-to-the-server"></a>Agregar autenticación y autorización al servidor

El paquete de portador de JWT no se incluye en ASP.NET Core 3,0 de forma predeterminada. Instale el paquete NuGet [Microsoft. AspNetCore. Authentication. JwtBearer](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) en la aplicación.

Agregue el servicio de autenticación en la clase de inicio y configure el controlador de portador JWT.

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();

    var signingKey = ObtainSigningKeySomehow();

    services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
        .AddJwtBearer(options =>
        {
            options.TokenValidationParameters =
                new TokenValidationParameters
                {
                    ValidateAudience = false,
                    ValidateIssuer = false,
                    ValidateActor = false,
                    ValidateLifetime = true,
                    IssuerSigningKey = signingKey
                };
        });

}
```

La propiedad `IssuerSigningKey` requiere una implementación de `Microsoft.IdentityModels.Tokens.SecurityKey` con los datos criptográficos necesarios para validar los tokens firmados. Este token se debe almacenar de forma segura en un *servidor de secretos* como Azure KeyVault.

A continuación, agregue el servicio de autorización, que controla el acceso al sistema.

```csharp
    services.AddAuthorization(options =>
    {
        options.AddPolicy(JwtBearerDefaults.AuthenticationScheme, policy =>
        {
            policy.AddAuthenticationSchemes(JwtBearerDefaults.AuthenticationScheme);
            policy.RequireClaim(ClaimTypes.Name);
        });
    });

```

> [!TIP]
> La autenticación y la autorización son dos pasos independientes. La autenticación se utiliza para determinar la identidad del usuario. La autorización decide si ese usuario puede tener acceso a distintas partes del sistema.

Ahora, agregue el middleware de autenticación y autorización a la canalización de ASP.NET Core en el método `Configure`.

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseRouting();

    // Authenticate, then Authorize
    app.UseAuthentication();
    app.UseAuthorization();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapGrpcService<PortfolioService>();
    });
}
```

Por último, aplique el atributo `[Authorize]` a los servicios o métodos que se van a proteger y use la propiedad `User` de la `HttpContext` subyacente para comprobar los permisos.

```csharp
[Authorize]
public override async Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!TryValidateUser(request.TraderId, context.GetHttpContext().User))
    {
        throw new RpcException(new Status(StatusCode.PermissionDenied, "Denied."));
    }

    var portfolio = await _repository.GetAsync(traderId, request.PortfolioId);

    return new GetResponse
    {
        Portfolio = Portfolio.FromRepositoryModel(portfolio)
    };
}
```

## <a name="providing-call-credentials-in-the-client-application"></a>Proporcionar credenciales de llamada en la aplicación cliente

Una vez que haya obtenido un token de JWT de un servidor de identidades, puede usarlo para autenticar llamadas de gRPC desde el cliente agregándolas como encabezado de metadatos en la llamada, como se indica a continuación:

```csharp
public async Task ShowPortfolioAsync(int portfolioId)
{
    var headers = new Grpc.Core.Metadata
    {
        { "Authorization", $"Bearer {_userToken}" }
    };
    var request = new GetRequest
    {
        TraderId = _userId,
        PortfolioId = portfolioId
    };
    var response = await _portfoliosClient.GetAsync(request, headers);

    // Display portfolio
}
```

Ahora, ha protegido el servicio gRPC mediante tokens de portador JWT como credenciales de llamada. En GitHub se muestra una versión de la [aplicación gRPC de ejemplo portfolios con autenticación y autorización agregada](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) .

>[!div class="step-by-step"]
>[Anterior](security.md)
>[Siguiente](channel-credentials.md)
