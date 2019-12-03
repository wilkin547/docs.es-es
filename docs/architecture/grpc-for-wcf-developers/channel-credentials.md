---
title: 'Credenciales de canal: gRPC para desarrolladores de WCF'
description: Cómo implementar y usar las credenciales del canal de gRPC en ASP.NET Core 3,0.
ms.date: 09/02/2019
ms.openlocfilehash: 133de2c732e72844f249f11bfe22b5980b828b89
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711492"
---
# <a name="channel-credentials"></a><span data-ttu-id="cf51e-103">Credenciales de canal</span><span class="sxs-lookup"><span data-stu-id="cf51e-103">Channel credentials</span></span>

<span data-ttu-id="cf51e-104">Como implica el nombre, las credenciales del canal se adjuntan al canal gRPC subyacente.</span><span class="sxs-lookup"><span data-stu-id="cf51e-104">As the name implies, channel credentials are attached to the underlying gRPC channel.</span></span> <span data-ttu-id="cf51e-105">La forma estándar de credenciales de canal utiliza la autenticación de certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="cf51e-105">The standard form of channel credentials uses client certificate authentication.</span></span> <span data-ttu-id="cf51e-106">En este proceso, el cliente proporciona un certificado TLS cuando se realiza la conexión y, a continuación, el servidor lo comprueba antes de permitir que se realicen las llamadas.</span><span class="sxs-lookup"><span data-stu-id="cf51e-106">In this process, the client provides a TLS certificate when it's making the connection, and then the server verifies this before allowing any calls to be made.</span></span>

<span data-ttu-id="cf51e-107">Puede combinar las credenciales del canal con las credenciales de llamada para proporcionar una seguridad completa para un servicio de gRPC.</span><span class="sxs-lookup"><span data-stu-id="cf51e-107">You can combine channel credentials with call credentials to provide comprehensive security for a gRPC service.</span></span> <span data-ttu-id="cf51e-108">Las credenciales del canal demuestran que la aplicación cliente puede tener acceso al servicio y las credenciales de llamada proporcionan información sobre la persona que utiliza la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="cf51e-108">The channel credentials prove that the client application is allowed to access the service, and the call credentials provide information about the person who is using the client application.</span></span>

<span data-ttu-id="cf51e-109">La autenticación de certificados de cliente funciona para gRPC de la misma manera que en ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="cf51e-109">Client certificate authentication works for gRPC the same way it works for ASP.NET Core.</span></span> <span data-ttu-id="cf51e-110">Para obtener más información, consulte [configurar la autenticación de certificados en ASP.net Core](/aspnet/core/security/authentication/certauth).</span><span class="sxs-lookup"><span data-stu-id="cf51e-110">For more information, see [Configure certificate authentication in ASP.NET Core](/aspnet/core/security/authentication/certauth).</span></span>

<span data-ttu-id="cf51e-111">Para fines de desarrollo, puede usar un certificado autofirmado, pero para producción debe usar un certificado HTTPS adecuado firmado por una entidad de confianza.</span><span class="sxs-lookup"><span data-stu-id="cf51e-111">For development purposes you can use a self-signed certificate, but for production you should use a proper HTTPS certificate signed by a trusted authority.</span></span>

## <a name="add-certificate-authentication-to-the-server"></a><span data-ttu-id="cf51e-112">Agregar autenticación de certificado al servidor</span><span class="sxs-lookup"><span data-stu-id="cf51e-112">Add certificate authentication to the server</span></span>

<span data-ttu-id="cf51e-113">Configure la autenticación de certificados en el nivel de host (por ejemplo, en el servidor de Kestrel) y en la canalización ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="cf51e-113">Configure certificate authentication both at the host level (for example, on the Kestrel server), and in the ASP.NET Core pipeline.</span></span>

### <a name="configure-certificate-validation-on-kestrel"></a><span data-ttu-id="cf51e-114">Configurar la validación de certificados en Kestrel</span><span class="sxs-lookup"><span data-stu-id="cf51e-114">Configure certificate validation on Kestrel</span></span>

<span data-ttu-id="cf51e-115">Puede configurar Kestrel (el servidor HTTP ASP.NET Core) para requerir un certificado de cliente y, opcionalmente, realizar alguna validación del certificado proporcionado antes de aceptar las conexiones entrantes.</span><span class="sxs-lookup"><span data-stu-id="cf51e-115">You can configure Kestrel (the ASP.NET Core HTTP server) to require a client certificate, and optionally to carry out some validation of the supplied certificate, before accepting incoming connections.</span></span> <span data-ttu-id="cf51e-116">Esto se hace en el método `CreateWebHostBuilder` de la clase `Program`, en lugar de en `Startup`.</span><span class="sxs-lookup"><span data-stu-id="cf51e-116">You do this in the `CreateWebHostBuilder` method of the `Program` class, rather than in `Startup`.</span></span>

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

<span data-ttu-id="cf51e-117">El valor `ClientCertificateMode.RequireCertificate` hace que Kestrel rechace inmediatamente cualquier solicitud de conexión que no proporcione un certificado de cliente, pero esta configuración por sí misma no validará un certificado proporcionado.</span><span class="sxs-lookup"><span data-stu-id="cf51e-117">The `ClientCertificateMode.RequireCertificate` setting causes Kestrel to immediately reject any connection request that doesn't provide a client certificate, but this setting by itself won't validate a certificate that is provided.</span></span> <span data-ttu-id="cf51e-118">Agregue la `ClientCertificateValidation` devolución de llamada para permitir que Kestrel valide el certificado de cliente en el momento en que se realiza la conexión, antes de que se active la canalización de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="cf51e-118">Add the `ClientCertificateValidation` callback to enable Kestrel to validate the client certificate at the point the connection is made, before the ASP.NET Core pipeline is engaged.</span></span> <span data-ttu-id="cf51e-119">(En este caso, la devolución de llamada garantiza que fue emitida por la misma *entidad de certificación* que el certificado de servidor).</span><span class="sxs-lookup"><span data-stu-id="cf51e-119">(In this case, the callback ensures that it was issued by the same *Certificate Authority* as the server certificate.)</span></span> 

### <a name="add-aspnet-core-certificate-authentication"></a><span data-ttu-id="cf51e-120">Agregar ASP.NET Core autenticación de certificados</span><span class="sxs-lookup"><span data-stu-id="cf51e-120">Add ASP.NET Core certificate authentication</span></span>

<span data-ttu-id="cf51e-121">El paquete de NuGet [Microsoft. AspNetCore. Authentication. Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) proporciona autenticación de certificado.</span><span class="sxs-lookup"><span data-stu-id="cf51e-121">The [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet package provides certificate authentication.</span></span>

<span data-ttu-id="cf51e-122">Agregue el servicio de autenticación de certificados en el método `ConfigureServices` y agregue autenticación y autorización a la canalización de ASP.NET Core en el método `Configure`.</span><span class="sxs-lookup"><span data-stu-id="cf51e-122">Add the certificate authentication service in the `ConfigureServices` method, and add authentication and authorization to the ASP.NET Core pipeline in the `Configure` method.</span></span>

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

## <a name="provide-channel-credentials-in-the-client-application"></a><span data-ttu-id="cf51e-123">Proporcionar credenciales de canal en la aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="cf51e-123">Provide channel credentials in the client application</span></span>

<span data-ttu-id="cf51e-124">Con el paquete de `Grpc.Net.Client`, se configuran los certificados en una instancia <xref:System.Net.Http.HttpClient> que se proporciona al `GrpcChannel` que se usa para la conexión.</span><span class="sxs-lookup"><span data-stu-id="cf51e-124">With the `Grpc.Net.Client` package, you configure certificates on an <xref:System.Net.Http.HttpClient> instance that is provided to the `GrpcChannel` used for the connection.</span></span>

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

## <a name="combine-channelcredentials-and-callcredentials"></a><span data-ttu-id="cf51e-125">Combinación de ChannelCredentials y CallCredentials</span><span class="sxs-lookup"><span data-stu-id="cf51e-125">Combine ChannelCredentials and CallCredentials</span></span>

<span data-ttu-id="cf51e-126">Puede configurar el servidor para que use la autenticación de certificados y de tokens.</span><span class="sxs-lookup"><span data-stu-id="cf51e-126">You can configure your server to use both certificate and token authentication.</span></span> <span data-ttu-id="cf51e-127">Para ello, aplique los cambios de certificado al servidor de Kestrel y use el middleware portador de JWT en ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="cf51e-127">Do this by applying the certificate changes to the Kestrel server, and using the JWT bearer middleware in ASP.NET Core.</span></span>

<span data-ttu-id="cf51e-128">Para proporcionar `ChannelCredentials` y `CallCredentials` en el cliente, use el método `ChannelCredentials.Create` para aplicar las credenciales de llamada.</span><span class="sxs-lookup"><span data-stu-id="cf51e-128">To provide both `ChannelCredentials` and `CallCredentials` on the client, use the `ChannelCredentials.Create` method to apply the call credentials.</span></span> <span data-ttu-id="cf51e-129">Todavía es necesario aplicar la autenticación de certificado mediante la instancia de <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="cf51e-129">You still need to apply certificate authentication by using the <xref:System.Net.Http.HttpClient> instance.</span></span> <span data-ttu-id="cf51e-130">Si se pasan argumentos al constructor `SslCredentials`, el código de cliente interno produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="cf51e-130">If you pass any arguments to the `SslCredentials` constructor, the internal client code throws an exception.</span></span> <span data-ttu-id="cf51e-131">El parámetro `SslCredentials` solo se incluye en el método `Create` del paquete de `Grpc.Net.Client` para mantener la compatibilidad con el paquete de `Grpc.Core`.</span><span class="sxs-lookup"><span data-stu-id="cf51e-131">The `SslCredentials` parameter is only included in the `Grpc.Net.Client` package's `Create` method to maintain compatibility with the `Grpc.Core` package.</span></span>

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
> <span data-ttu-id="cf51e-132">Puede usar el método `ChannelCredentials.Create` para un cliente sin autenticación de certificado.</span><span class="sxs-lookup"><span data-stu-id="cf51e-132">You can use the `ChannelCredentials.Create` method for a client without certificate authentication.</span></span> <span data-ttu-id="cf51e-133">Esta es una forma útil de pasar credenciales de token con cada llamada realizada en el canal.</span><span class="sxs-lookup"><span data-stu-id="cf51e-133">This is a useful way to pass token credentials with every call made on the channel.</span></span>

<span data-ttu-id="cf51e-134">En GitHub se ha agregado una versión de la [aplicación FullStockTicker de ejemplo gRPC con autenticación de certificado](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) .</span><span class="sxs-lookup"><span data-stu-id="cf51e-134">A version of the [FullStockTicker sample gRPC application with certificate authentication added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="cf51e-135">[Anterior](call-credentials.md)
>[Siguiente](encryption.md)</span><span class="sxs-lookup"><span data-stu-id="cf51e-135">[Previous](call-credentials.md)
[Next](encryption.md)</span></span>
