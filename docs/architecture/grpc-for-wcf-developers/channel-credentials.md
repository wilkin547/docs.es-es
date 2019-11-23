---
title: 'Credenciales de canal: gRPC para desarrolladores de WCF'
description: Cómo implementar y usar las credenciales del canal de gRPC en ASP.NET Core 3,0.
ms.date: 09/02/2019
ms.openlocfilehash: b424db49337a2dc6e3d0245d36349e3f408cdf6c
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967961"
---
# <a name="channel-credentials"></a><span data-ttu-id="f02b8-103">Credenciales de canal</span><span class="sxs-lookup"><span data-stu-id="f02b8-103">Channel credentials</span></span>

<span data-ttu-id="f02b8-104">Como implica el nombre, las credenciales del canal se adjuntan al canal gRPC subyacente.</span><span class="sxs-lookup"><span data-stu-id="f02b8-104">As the name implies, channel credentials are attached to the underlying gRPC channel.</span></span> <span data-ttu-id="f02b8-105">La forma estándar de credenciales de canal utiliza la autenticación de certificados de cliente, en la que el cliente proporciona un certificado TLS cuando se realiza la conexión, que el servidor comprueba antes de permitir que se realicen llamadas.</span><span class="sxs-lookup"><span data-stu-id="f02b8-105">The standard form of channel credentials uses Client Certificate authentication, where the client provides a TLS certificate when it's making the connection, which is verified by the server before allowing any calls to be made.</span></span>

<span data-ttu-id="f02b8-106">Las credenciales del canal pueden combinarse con credenciales de llamada para proporcionar una seguridad completa para un servicio de gRPC.</span><span class="sxs-lookup"><span data-stu-id="f02b8-106">Channel credentials can be combined with call credentials to provide comprehensive security for a gRPC service.</span></span> <span data-ttu-id="f02b8-107">Las credenciales del canal demuestran que la aplicación cliente puede tener acceso al servicio y las credenciales de llamada proporcionan información sobre la persona que utiliza la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="f02b8-107">The channel credentials prove that the client application is allowed to access the service, and the call credentials provide information about the person using the client application.</span></span>

<span data-ttu-id="f02b8-108">La autenticación de certificados de cliente funciona para gRPC de la misma manera que en ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f02b8-108">Client certificate authentication works for gRPC the same way it works for ASP.NET Core.</span></span> <span data-ttu-id="f02b8-109">El proceso de configuración se resumirá aquí, pero hay más información disponible en el artículo [configuración de la autenticación de certificados en ASP.net Core](https://docs.microsoft.com/aspnet/core/security/authentication/certauth?view=aspnetcore-3.0) .</span><span class="sxs-lookup"><span data-stu-id="f02b8-109">The configuration process will be summarized here, but more information is available in the [Configure certificate authentication in ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/certauth?view=aspnetcore-3.0) article.</span></span>

<span data-ttu-id="f02b8-110">Para fines de desarrollo, puede usar un certificado autofirmado, pero para producción debe usar un certificado HTTPS adecuado firmado por una entidad de confianza.</span><span class="sxs-lookup"><span data-stu-id="f02b8-110">For development purposes you can use a self-signed certificate, but for production you should use a proper HTTPS certificate signed by a trusted authority.</span></span>

## <a name="adding-certificate-authentication-to-the-server"></a><span data-ttu-id="f02b8-111">Agregar autenticación de certificado al servidor</span><span class="sxs-lookup"><span data-stu-id="f02b8-111">Adding certificate authentication to the server</span></span>

<span data-ttu-id="f02b8-112">Debe configurar la autenticación de certificados en el nivel de host, por ejemplo, en el servidor de Kestrel y en la canalización de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f02b8-112">You need to configure certificate authentication both at the host level, for example on the Kestrel server, and in the ASP.NET Core pipeline.</span></span>

### <a name="configuring-certificate-validation-on-kestrel"></a><span data-ttu-id="f02b8-113">Configuración de la validación de certificados en Kestrel</span><span class="sxs-lookup"><span data-stu-id="f02b8-113">Configuring certificate validation on Kestrel</span></span>

<span data-ttu-id="f02b8-114">Puede configurar Kestrel (el servidor HTTP ASP.NET Core) para requerir un certificado de cliente y, opcionalmente, realizar alguna validación del certificado proporcionado antes de aceptar las conexiones entrantes.</span><span class="sxs-lookup"><span data-stu-id="f02b8-114">You can configure Kestrel (the ASP.NET Core HTTP server) to require a client certificate, and optionally to carry out some validation of the supplied certificate before accepting incoming connections.</span></span> <span data-ttu-id="f02b8-115">Esta configuración se realiza en el método `CreateWebHostBuilder` de la clase `Program`, en lugar de en `Startup`.</span><span class="sxs-lookup"><span data-stu-id="f02b8-115">This configuration is done in the `CreateWebHostBuilder` method of the `Program` class, rather than in `Startup`.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureWebHostDefaults(webBuilder =>
        {
            var serverCert = ObtainServerCertificate();
            webBuilder.UseStartup<Startup>()
                .ConfigureKestrel(kestrelServerOptions => {
                    kestrelServerOptions.ConfigureHttpsDefaults(opt =>
                    {
                        opt.ClientCertificateMode = ClientCertificateMode.RequireCertificate;

                        // Verify that client certificate was issued by same CA as server certificate
                        opt.ClientCertificateValidation = (certificate, chain, errors) =>
                            certificate.Issuer == serverCert.Issuer;
                    });
                });
        });

```

<span data-ttu-id="f02b8-116">El valor `ClientCertificateMode.RequireCertificate` hará que Kestrel rechace inmediatamente cualquier solicitud de conexión que no proporcione un certificado de cliente, pero no validará el certificado.</span><span class="sxs-lookup"><span data-stu-id="f02b8-116">The `ClientCertificateMode.RequireCertificate` setting will cause Kestrel to immediately reject any connection request that doesn't provide a client certificate, but it won't validate the certificate.</span></span> <span data-ttu-id="f02b8-117">La adición de la devolución de llamada `ClientCertificateValidation` permite a Kestrel validar el certificado de cliente (en este caso, asegurándose de que lo emitió la misma *entidad de certificación* como el certificado de servidor) en el momento en que se realiza la conexión, antes de que se conceda la canalización de ASP.net Core.</span><span class="sxs-lookup"><span data-stu-id="f02b8-117">Adding the `ClientCertificateValidation` callback enables Kestrel to validate the client certificate (in this case, ensuring that it was issued by the same *Certificate Authority* as the server certificate) at the point the connection is made, before the ASP.NET Core pipeline is engaged.</span></span>

### <a name="adding-aspnet-core-certificate-authentication"></a><span data-ttu-id="f02b8-118">Agregar ASP.NET Core la autenticación de certificados</span><span class="sxs-lookup"><span data-stu-id="f02b8-118">Adding ASP.NET Core certificate authentication</span></span>

<span data-ttu-id="f02b8-119">El paquete NuGet [Microsoft. AspNetCore. Authentication. Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) proporciona la autenticación de certificados.</span><span class="sxs-lookup"><span data-stu-id="f02b8-119">Certificate authentication is provided by the [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet package.</span></span>

<span data-ttu-id="f02b8-120">Agregue el servicio de autenticación de certificados en el método `ConfigureServices` y agregue autenticación y autorización a la canalización de ASP.NET Core en el método `Configure`.</span><span class="sxs-lookup"><span data-stu-id="f02b8-120">Add the certificate authentication service in the `ConfigureServices` method, and add authentication and authorization to the ASP.NET Core pipeline in the `Configure` method.</span></span>

```csharp
public class Startup
{
    private readonly bool _isDevelopment;

    public Startup(IWebHostEnvironment env)
    {
        _isDevelopment = env.IsDevelopment();
    }

    public void ConfigureServices(IServiceCollection services)
    {
        services.AddAuthentication(CertificateAuthenticationDefaults.AuthenticationScheme)
            .AddCertificate(options =>
            {
                if (_isDevelopment)
                {
                    // DO NOT DO THIS IN PRODUCTION!
                    options.RevocationMode = X509RevocationMode.NoCheck;
                }
            });
        services.AddAuthorization();
        services.AddGrpc();
    }

    public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
    {
        app.UseRouting();

        app.UseAuthentication();
        app.UseAuthorization();

        app.UseEndpoints(endpoints => { endpoints.MapGrpcService<GreeterService>(); });
    }
}
```

## <a name="providing-channel-credentials-in-the-client-application"></a><span data-ttu-id="f02b8-121">Proporcionar credenciales de canal en la aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="f02b8-121">Providing channel credentials in the client application</span></span>

<span data-ttu-id="f02b8-122">Con el paquete de `Grpc.Net.Client`, los certificados se configuran en una instancia de <xref:System.Net.Http.HttpClient> que se proporciona al `GrpcChannel` que se usa para la conexión.</span><span class="sxs-lookup"><span data-stu-id="f02b8-122">With the `Grpc.Net.Client` package, certificates are configured on an <xref:System.Net.Http.HttpClient> instance that is provided to the `GrpcChannel` used for the connection.</span></span>

```csharp
class Program
{
    static async Task Main(string[] args)
    {
        // Assume path to a client .pfx file and password are passed from command line
        // On Windows this would probably be a reference to the Certificate Store
        var cert = new X509Certificate2(args[0], args[1]);

        var handler = new HttpClientHandler();
        handler.ClientCertificates.Add(cert);
        var httpClient = new HttpClient(handler);

        var channel = GrpcChannel.ForAddress("https://localhost:5001/", new GrpcChannelOptions
        {
            HttpClient = httpClient
        });

        var grpc = new Greeter.GreeterClient(channel);
        var response = await grpc.SayHelloAsync(new HelloRequest { Name = "Bob" });
        System.Console.WriteLine(response.Message);
    }
}
```

## <a name="combining-channelcredentials-and-callcredentials"></a><span data-ttu-id="f02b8-123">Combinación de ChannelCredentials y CallCredentials</span><span class="sxs-lookup"><span data-stu-id="f02b8-123">Combining ChannelCredentials and CallCredentials</span></span>

<span data-ttu-id="f02b8-124">Puede configurar el servidor para que use la autenticación de certificados y de tokens aplicando los cambios de certificado en el servidor de Kestrel y usando el middleware portador de JWT en ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f02b8-124">You can configure your server to use both certificate and token authentication by applying the certificate changes to the Kestrel server and using the JWT bearer middleware in ASP.NET Core.</span></span>

<span data-ttu-id="f02b8-125">Para proporcionar ChannelCredentials y CallCredentials en el cliente, use el método `ChannelCredentials.Create` para aplicar las credenciales de llamada.</span><span class="sxs-lookup"><span data-stu-id="f02b8-125">To provide both ChannelCredentials and CallCredentials on the client, use the `ChannelCredentials.Create` method to apply the call credentials.</span></span> <span data-ttu-id="f02b8-126">La autenticación de certificados todavía debe aplicarse mediante la <xref:System.Net.Http.HttpClient> instancia: si se pasan argumentos al constructor `SslCredentials`, el código de cliente interno produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="f02b8-126">Certificate authentication still needs to be applied using the <xref:System.Net.Http.HttpClient> instance: if you pass any arguments to the `SslCredentials` constructor, the internal client code throws an exception.</span></span> <span data-ttu-id="f02b8-127">El parámetro `SslCredentials` solo se incluye en el método `Create` del paquete de `Grpc.Net.Client` para mantener la compatibilidad con el paquete de `Grpc.Core`.</span><span class="sxs-lookup"><span data-stu-id="f02b8-127">The `SslCredentials` parameter is only included in the `Grpc.Net.Client` package's `Create` method to maintain compatibility with the `Grpc.Core` package.</span></span>

```csharp
var handler = new HttpClientHandler();
handler.ClientCertificates.Add(cert);

var httpClient = new HttpClient(handler);

var callCredentials = CallCredentials.FromInterceptor(((context, metadata) =>
    {
        metadata.Add("Authorization", $"Bearer {_token}");
    }));

var channelCredentials = ChannelCredentials.Create(new SslCredentials(), callCredentials);

var channel = GrpcChannel.ForAddress("https://localhost:5001/", new GrpcChannelOptions
{
    HttpClient = httpClient,
    Credentials = channelCredentials
});

var grpc = new Portfolios.PortfoliosClient(channel);
```

> [!TIP]
> <span data-ttu-id="f02b8-128">Puede usar el método `ChannelCredentials.Create` para un cliente sin autenticación de certificado, como una manera útil de pasar credenciales de token con cada llamada realizada en el canal.</span><span class="sxs-lookup"><span data-stu-id="f02b8-128">You can use the `ChannelCredentials.Create` method for a client without certificate authentication, as a useful way to pass token credentials with every call made on the channel.</span></span>

<span data-ttu-id="f02b8-129">En GitHub se ha agregado una versión de la [aplicación FullStockTicker de ejemplo gRPC con autenticación de certificado](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) .</span><span class="sxs-lookup"><span data-stu-id="f02b8-129">A version of the [FullStockTicker sample gRPC application with certificate authentication added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f02b8-130">[Anterior](call-credentials.md)
>[Siguiente](encryption.md)</span><span class="sxs-lookup"><span data-stu-id="f02b8-130">[Previous](call-credentials.md)
[Next](encryption.md)</span></span>
