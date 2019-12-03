---
title: Llamada a Credentials-gRPC para desarrolladores de WCF
description: Cómo implementar y usar credenciales de llamada de gRPC en ASP.NET Core 3,0.
ms.date: 09/02/2019
ms.openlocfilehash: 01f21f58ed4235f45509c948c84653cd99d35618
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711538"
---
# <a name="call-credentials"></a><span data-ttu-id="4dd22-103">Credenciales de llamada</span><span class="sxs-lookup"><span data-stu-id="4dd22-103">Call credentials</span></span>

<span data-ttu-id="4dd22-104">Las credenciales de llamada se basan en un token que se pasa en los metadatos con cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="4dd22-104">Call credentials are all based on a token passed in metadata with each request.</span></span>

## <a name="ws-federation"></a><span data-ttu-id="4dd22-105">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="4dd22-105">WS-Federation</span></span>

<span data-ttu-id="4dd22-106">ASP.NET Core admite WS-Federation mediante el paquete NuGet [WsFederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) .</span><span class="sxs-lookup"><span data-stu-id="4dd22-106">ASP.NET Core supports WS-Federation using the [WsFederation](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.WsFederation) NuGet package.</span></span> <span data-ttu-id="4dd22-107">WS-Federation es la alternativa disponible más cercana a la autenticación de Windows, que no se admite a través de HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="4dd22-107">WS-Federation is the closest available alternative to Windows Authentication, which isn't supported over HTTP/2.</span></span> <span data-ttu-id="4dd22-108">Los usuarios se autentican mediante Servicios de federación de Active Directory (AD FS) (AD FS), que proporciona un token que se puede usar para autenticarse con ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="4dd22-108">Users are authenticated by using Active Directory Federation Services (AD FS), which provides a token that can be used to authenticate with ASP.NET Core.</span></span>

<span data-ttu-id="4dd22-109">Para obtener más información sobre cómo empezar a usar este método de autenticación, consulte [autenticación de usuarios con WS-Federation en ASP.net Core](/aspnet/core/security/authentication/ws-federation).</span><span class="sxs-lookup"><span data-stu-id="4dd22-109">For more information on how to get started with this authentication method, see [Authenticate users with WS-Federation in ASP.NET Core](/aspnet/core/security/authentication/ws-federation).</span></span>

## <a name="jwt-bearer-tokens"></a><span data-ttu-id="4dd22-110">Tokens de portador JWT</span><span class="sxs-lookup"><span data-stu-id="4dd22-110">JWT Bearer tokens</span></span>

<span data-ttu-id="4dd22-111">El estándar [JSON Web Token](https://jwt.io) (JWT) proporciona una manera de codificar información sobre un usuario y sus notificaciones en una cadena codificada.</span><span class="sxs-lookup"><span data-stu-id="4dd22-111">The [JSON Web Token](https://jwt.io) (JWT) standard provides a way to encode information about a user and their claims in an encoded string.</span></span> <span data-ttu-id="4dd22-112">También proporciona una manera de firmar el token, de modo que el consumidor pueda comprobar la integridad del token mediante el uso de la criptografía de clave pública.</span><span class="sxs-lookup"><span data-stu-id="4dd22-112">It also provides a way to sign that token, so that the consumer can verify the integrity of the token by using public key cryptography.</span></span> <span data-ttu-id="4dd22-113">Puede usar varios servicios, como IdentityServer4, para autenticar a los usuarios y generar tokens OpenID Connect (OIDC) para usarlos con las API de gRPC y HTTP.</span><span class="sxs-lookup"><span data-stu-id="4dd22-113">You can use various services, such as IdentityServer4, to authenticate users and generate OpenID Connect (OIDC) tokens to use with gRPC and HTTP APIs.</span></span>

<span data-ttu-id="4dd22-114">ASP.NET Core 3,0 puede administrar JWT mediante el paquete de portador JWT.</span><span class="sxs-lookup"><span data-stu-id="4dd22-114">ASP.NET Core 3.0 can handle JWTs by using the JWT Bearer package.</span></span> <span data-ttu-id="4dd22-115">La configuración es exactamente la misma para una aplicación de gRPC que para una aplicación de MVC ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="4dd22-115">The configuration is exactly the same for a gRPC application as it is for an ASP.NET Core MVC application.</span></span> <span data-ttu-id="4dd22-116">Aquí nos centraremos en los tokens de portador de JWT, ya que son más fáciles de desarrollar con respecto a WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="4dd22-116">Here, we'll focus on JWT Bearer tokens, because they're easier to develop with than WS-Federation.</span></span>

## <a name="add-authentication-and-authorization-to-the-server"></a><span data-ttu-id="4dd22-117">Agregar autenticación y autorización al servidor</span><span class="sxs-lookup"><span data-stu-id="4dd22-117">Add authentication and authorization to the server</span></span>

<span data-ttu-id="4dd22-118">El paquete de portador de JWT no se incluye en ASP.NET Core 3,0 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4dd22-118">The JWT Bearer package isn't included in ASP.NET Core 3.0 by default.</span></span> <span data-ttu-id="4dd22-119">Instale el paquete NuGet [Microsoft. AspNetCore. Authentication. JwtBearer](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4dd22-119">Install the [Microsoft.AspNetCore.Authentication.JwtBearer](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.JwtBearer) NuGet package in your app.</span></span>

<span data-ttu-id="4dd22-120">Agregue el servicio de autenticación en la clase startup y configure el controlador de portador JWT:</span><span class="sxs-lookup"><span data-stu-id="4dd22-120">Add the Authentication service in the Startup class, and configure the JWT Bearer handler:</span></span>

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

<span data-ttu-id="4dd22-121">La propiedad `IssuerSigningKey` requiere una implementación de `Microsoft.IdentityModels.Tokens.SecurityKey` con los datos criptográficos necesarios para validar los tokens firmados.</span><span class="sxs-lookup"><span data-stu-id="4dd22-121">The `IssuerSigningKey` property requires an implementation of `Microsoft.IdentityModels.Tokens.SecurityKey` with the cryptographic data necessary to validate the signed tokens.</span></span> <span data-ttu-id="4dd22-122">Almacene este token de forma segura en un *servidor de secretos*, como Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="4dd22-122">Store this token securely in a *secrets server*, like Azure Key Vault.</span></span>

<span data-ttu-id="4dd22-123">A continuación, agregue el servicio de autorización, que controla el acceso al sistema:</span><span class="sxs-lookup"><span data-stu-id="4dd22-123">Next, add the Authorization service, which controls access to the system:</span></span>

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
> <span data-ttu-id="4dd22-124">La autenticación y la autorización son dos pasos independientes.</span><span class="sxs-lookup"><span data-stu-id="4dd22-124">Authentication and authorization are two separate steps.</span></span> <span data-ttu-id="4dd22-125">Use la autenticación de para determinar la identidad del usuario.</span><span class="sxs-lookup"><span data-stu-id="4dd22-125">You use authentication to determine the user's identity.</span></span> <span data-ttu-id="4dd22-126">La autorización se usa para decidir si el usuario puede tener acceso a las distintas partes del sistema.</span><span class="sxs-lookup"><span data-stu-id="4dd22-126">You use authorization to decide whether that user is allowed to access various parts of the system.</span></span>

<span data-ttu-id="4dd22-127">Ahora, agregue el middleware de autenticación y autorización a la canalización de ASP.NET Core en el método `Configure`:</span><span class="sxs-lookup"><span data-stu-id="4dd22-127">Now add the authentication and authorization middleware to the ASP.NET Core pipeline in the `Configure` method:</span></span>

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

<span data-ttu-id="4dd22-128">Por último, aplique el atributo `[Authorize]` a los servicios o métodos que se van a proteger y use la propiedad `User` de la `HttpContext` subyacente para comprobar los permisos.</span><span class="sxs-lookup"><span data-stu-id="4dd22-128">Finally, apply the `[Authorize]` attribute to any services or methods to be secured, and use the `User` property from the underlying `HttpContext` to verify permissions.</span></span>

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

## <a name="provide-call-credentials-in-the-client-application"></a><span data-ttu-id="4dd22-129">Proporcionar credenciales de llamada en la aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="4dd22-129">Provide call credentials in the client application</span></span>

<span data-ttu-id="4dd22-130">Después de obtener un token de JWT de un servidor de identidades, puede usarlo para autenticar llamadas de gRPC desde el cliente agregándolas como un encabezado de metadatos en la llamada, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="4dd22-130">After you've obtained a JWT token from an identity server, you can use it to authenticate gRPC calls from the client by adding it as a metadata header on the call, as follows:</span></span>

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

<span data-ttu-id="4dd22-131">Ahora ha protegido el servicio gRPC mediante tokens de portador JWT como credenciales de llamada.</span><span class="sxs-lookup"><span data-stu-id="4dd22-131">Now you've secured your gRPC service by using JWT bearer tokens as call credentials.</span></span> <span data-ttu-id="4dd22-132">En GitHub se muestra una versión de la [aplicación gRPC de ejemplo portfolios con autenticación y autorización agregada](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) .</span><span class="sxs-lookup"><span data-stu-id="4dd22-132">A version of the [portfolios sample gRPC application with authentication and authorization added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/grpc/TraderSysAuth) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4dd22-133">[Anterior](security.md)
>[Siguiente](channel-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="4dd22-133">[Previous](security.md)
[Next](channel-credentials.md)</span></span>
