---
title: Credenciales de canal - gRPC para desarrolladores de WCF
description: Cómo implementar y utilizar credenciales de canal gRPC en ASP.NET Core 3.0.
ms.date: 09/02/2019
ms.openlocfilehash: 9ebe0aecb517e4cc2fe280632c4ecb593da9871c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148210"
---
# <a name="channel-credentials"></a><span data-ttu-id="69a66-103">Credenciales de canal</span><span class="sxs-lookup"><span data-stu-id="69a66-103">Channel credentials</span></span>

<span data-ttu-id="69a66-104">Como su nombre indica, las credenciales de canal se asocian al canal gRPC subyacente.</span><span class="sxs-lookup"><span data-stu-id="69a66-104">As the name implies, channel credentials are attached to the underlying gRPC channel.</span></span> <span data-ttu-id="69a66-105">La forma estándar de credenciales de canal utiliza la autenticación de certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="69a66-105">The standard form of channel credentials uses client certificate authentication.</span></span> <span data-ttu-id="69a66-106">En este proceso, el cliente proporciona un certificado TLS cuando realiza la conexión y, a continuación, el servidor comprueba esto antes de permitir que se realicen llamadas.</span><span class="sxs-lookup"><span data-stu-id="69a66-106">In this process, the client provides a TLS certificate when it's making the connection, and then the server verifies this before allowing any calls to be made.</span></span>

<span data-ttu-id="69a66-107">Puede combinar las credenciales de canal con las credenciales de llamada para proporcionar una seguridad completa para un servicio gRPC.</span><span class="sxs-lookup"><span data-stu-id="69a66-107">You can combine channel credentials with call credentials to provide comprehensive security for a gRPC service.</span></span> <span data-ttu-id="69a66-108">Las credenciales de canal prueban que la aplicación cliente tiene permiso para tener acceso al servicio y las credenciales de llamada proporcionan información sobre la persona que usa la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="69a66-108">The channel credentials prove that the client application is allowed to access the service, and the call credentials provide information about the person who is using the client application.</span></span>

<span data-ttu-id="69a66-109">La autenticación de certificado de cliente funciona para gRPC de la misma manera que para ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="69a66-109">Client certificate authentication works for gRPC the same way it works for ASP.NET Core.</span></span> <span data-ttu-id="69a66-110">Para obtener más información, consulte Configurar la autenticación de [certificados en ASP.NET Core](/aspnet/core/security/authentication/certauth).</span><span class="sxs-lookup"><span data-stu-id="69a66-110">For more information, see [Configure certificate authentication in ASP.NET Core](/aspnet/core/security/authentication/certauth).</span></span>

<span data-ttu-id="69a66-111">Para fines de desarrollo, puede usar un certificado autofirmado, pero para la producción debe usar un certificado HTTPS adecuado firmado por una autoridad de confianza.</span><span class="sxs-lookup"><span data-stu-id="69a66-111">For development purposes you can use a self-signed certificate, but for production you should use a proper HTTPS certificate signed by a trusted authority.</span></span>

## <a name="add-certificate-authentication-to-the-server"></a><span data-ttu-id="69a66-112">Agregar autenticación de certificado al servidor</span><span class="sxs-lookup"><span data-stu-id="69a66-112">Add certificate authentication to the server</span></span>

<span data-ttu-id="69a66-113">Configure la autenticación de certificados tanto en el nivel de host (por ejemplo, en el servidor de Kestrel) como en la canalización ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="69a66-113">Configure certificate authentication both at the host level (for example, on the Kestrel server), and in the ASP.NET Core pipeline.</span></span>

### <a name="configure-certificate-validation-on-kestrel"></a><span data-ttu-id="69a66-114">Configurar la validación de certificados en Kestrel</span><span class="sxs-lookup"><span data-stu-id="69a66-114">Configure certificate validation on Kestrel</span></span>

<span data-ttu-id="69a66-115">Puede configurar Kestrel (el servidor HTTP ASP.NET Core) para que requiera un certificado de cliente y, opcionalmente, para llevar a cabo alguna validación del certificado proporcionado antes de aceptar conexiones entrantes.</span><span class="sxs-lookup"><span data-stu-id="69a66-115">You can configure Kestrel (the ASP.NET Core HTTP server) to require a client certificate, and optionally to carry out some validation of the supplied certificate, before accepting incoming connections.</span></span> <span data-ttu-id="69a66-116">Esto se hace `CreateWebHostBuilder` en `Program` el método de `Startup`la clase, en lugar de en .</span><span class="sxs-lookup"><span data-stu-id="69a66-116">You do this in the `CreateWebHostBuilder` method of the `Program` class, rather than in `Startup`.</span></span>

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

<span data-ttu-id="69a66-117">La `ClientCertificateMode.RequireCertificate` configuración hace que Kestrel rechace inmediatamente cualquier solicitud de conexión que no proporcione un certificado de cliente, pero esta configuración por sí misma no validará un certificado que se proporciona.</span><span class="sxs-lookup"><span data-stu-id="69a66-117">The `ClientCertificateMode.RequireCertificate` setting causes Kestrel to immediately reject any connection request that doesn't provide a client certificate, but this setting by itself won't validate a certificate that is provided.</span></span> <span data-ttu-id="69a66-118">Agregue `ClientCertificateValidation` la devolución de llamada para permitir que Kestrel valide el certificado de cliente en el punto en que se realiza la conexión, antes de que se active la canalización de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="69a66-118">Add the `ClientCertificateValidation` callback to enable Kestrel to validate the client certificate at the point the connection is made, before the ASP.NET Core pipeline is engaged.</span></span> <span data-ttu-id="69a66-119">(En este caso, la devolución de llamada se asegura de que fue emitida por la misma entidad de *certificación* que el certificado de servidor.)</span><span class="sxs-lookup"><span data-stu-id="69a66-119">(In this case, the callback ensures that it was issued by the same *Certificate Authority* as the server certificate.)</span></span>

### <a name="add-aspnet-core-certificate-authentication"></a><span data-ttu-id="69a66-120">Agregar autenticación de certificado ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="69a66-120">Add ASP.NET Core certificate authentication</span></span>

<span data-ttu-id="69a66-121">El paquete NuGet [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) proporciona autenticación de certificado.</span><span class="sxs-lookup"><span data-stu-id="69a66-121">The [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) NuGet package provides certificate authentication.</span></span>

<span data-ttu-id="69a66-122">Agregue el servicio de `ConfigureServices` autenticación de certificados en el método y `Configure` agregue autenticación y autorización a la canalización de ASP.NET Core en el método.</span><span class="sxs-lookup"><span data-stu-id="69a66-122">Add the certificate authentication service in the `ConfigureServices` method, and add authentication and authorization to the ASP.NET Core pipeline in the `Configure` method.</span></span>

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

## <a name="provide-channel-credentials-in-the-client-application"></a><span data-ttu-id="69a66-123">Proporcionar credenciales de canal en la aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="69a66-123">Provide channel credentials in the client application</span></span>

<span data-ttu-id="69a66-124">Con `Grpc.Net.Client` el paquete, se <xref:System.Net.Http.HttpClient> configuran certificados en `GrpcChannel` una instancia que se proporciona al utilizado para la conexión.</span><span class="sxs-lookup"><span data-stu-id="69a66-124">With the `Grpc.Net.Client` package, you configure certificates on an <xref:System.Net.Http.HttpClient> instance that is provided to the `GrpcChannel` used for the connection.</span></span>

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

## <a name="combine-channelcredentials-and-callcredentials"></a><span data-ttu-id="69a66-125">Combinar ChannelCredentials y CallCredentials</span><span class="sxs-lookup"><span data-stu-id="69a66-125">Combine ChannelCredentials and CallCredentials</span></span>

<span data-ttu-id="69a66-126">Puede configurar el servidor para que use la autenticación de certificados y tokens.</span><span class="sxs-lookup"><span data-stu-id="69a66-126">You can configure your server to use both certificate and token authentication.</span></span> <span data-ttu-id="69a66-127">Para ello, aplique los cambios de certificado al servidor de Kestrel y utilice el middleware del portador de JWT en ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="69a66-127">Do this by applying the certificate changes to the Kestrel server, and using the JWT bearer middleware in ASP.NET Core.</span></span>

<span data-ttu-id="69a66-128">Para proporcionar `ChannelCredentials` `CallCredentials` ambos y en `ChannelCredentials.Create` el cliente, utilice el método para aplicar las credenciales de llamada.</span><span class="sxs-lookup"><span data-stu-id="69a66-128">To provide both `ChannelCredentials` and `CallCredentials` on the client, use the `ChannelCredentials.Create` method to apply the call credentials.</span></span> <span data-ttu-id="69a66-129">Todavía debe aplicar la autenticación <xref:System.Net.Http.HttpClient> de certificado mediante la instancia.</span><span class="sxs-lookup"><span data-stu-id="69a66-129">You still need to apply certificate authentication by using the <xref:System.Net.Http.HttpClient> instance.</span></span> <span data-ttu-id="69a66-130">Si pasa argumentos al `SslCredentials` constructor, el código de cliente interno produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="69a66-130">If you pass any arguments to the `SslCredentials` constructor, the internal client code throws an exception.</span></span> <span data-ttu-id="69a66-131">El `SslCredentials` parámetro solo se `Grpc.Net.Client` incluye `Create` en el método del `Grpc.Core` paquete para mantener la compatibilidad con el paquete.</span><span class="sxs-lookup"><span data-stu-id="69a66-131">The `SslCredentials` parameter is only included in the `Grpc.Net.Client` package's `Create` method to maintain compatibility with the `Grpc.Core` package.</span></span>

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
> <span data-ttu-id="69a66-132">Puede utilizar `ChannelCredentials.Create` el método para un cliente sin autenticación de certificado.</span><span class="sxs-lookup"><span data-stu-id="69a66-132">You can use the `ChannelCredentials.Create` method for a client without certificate authentication.</span></span> <span data-ttu-id="69a66-133">Esta es una forma útil de pasar credenciales de token con cada llamada realizada en el canal.</span><span class="sxs-lookup"><span data-stu-id="69a66-133">This is a useful way to pass token credentials with every call made on the channel.</span></span>

<span data-ttu-id="69a66-134">Una versión de la aplicación gRPC de [ejemplo FullStockTicker con autenticación](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) de certificado agregada se encuentra en GitHub.</span><span class="sxs-lookup"><span data-stu-id="69a66-134">A version of the [FullStockTicker sample gRPC application with certificate authentication added](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) is on GitHub.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="69a66-135">[Anterior](call-credentials.md)
>[Siguiente](encryption.md)</span><span class="sxs-lookup"><span data-stu-id="69a66-135">[Previous](call-credentials.md)
[Next](encryption.md)</span></span>
