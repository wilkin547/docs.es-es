---
title: 'Credenciales de canal: gRPC para desarrolladores de WCF'
description: Cómo implementar y usar las credenciales del canal de gRPC en ASP.NET Core 3,0.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 61141dc4143f36f9ac511c3369c3fde668c9d703
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841670"
---
# <a name="channel-credentials"></a>Credenciales de canal

Como implica el nombre, las credenciales del canal se adjuntan al canal gRPC subyacente. La forma estándar de credenciales de canal utiliza la autenticación de certificados de cliente, en la que el cliente proporciona un certificado TLS cuando se realiza la conexión, que el servidor comprueba antes de permitir que se realicen llamadas.

Las credenciales del canal pueden combinarse con credenciales de llamada para proporcionar una seguridad completa para un servicio de gRPC. Las credenciales del canal demuestran que la aplicación cliente puede tener acceso al servicio y las credenciales de llamada proporcionan información sobre la persona que utiliza la aplicación cliente.

La autenticación de certificados de cliente funciona para gRPC de la misma manera que en ASP.NET Core. El proceso de configuración se resumirá aquí, pero hay más información disponible en el artículo [configuración de la autenticación de certificados en ASP.net Core](https://docs.microsoft.com/aspnet/core/security/authentication/certauth?view=aspnetcore-3.0) .

Para fines de desarrollo, puede usar un certificado autofirmado, pero para producción debe usar un certificado HTTPS adecuado firmado por una entidad de confianza.

## <a name="adding-certificate-authentication-to-the-server"></a>Agregar autenticación de certificado al servidor

Debe configurar la autenticación de certificados en el nivel de host, por ejemplo, en el servidor de Kestrel y en la canalización de ASP.NET Core.

### <a name="configuring-certificate-validation-on-kestrel"></a>Configuración de la validación de certificados en Kestrel

Puede configurar Kestrel (el servidor HTTP ASP.NET Core) para requerir un certificado de cliente y, opcionalmente, realizar alguna validación del certificado proporcionado antes de aceptar las conexiones entrantes. Esta configuración se realiza en el método `CreateWebHostBuilder` de la clase `Program`, en lugar de en `Startup`.

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

El valor `ClientCertificateMode.RequireCertificate` hará que Kestrel rechace inmediatamente cualquier solicitud de conexión que no proporcione un certificado de cliente, pero no validará el certificado. La adición de la devolución de llamada `ClientCertificateValidation` permite a Kestrel validar el certificado de cliente (en este caso, asegurándose de que lo emitió la misma *entidad de certificación* como el certificado de servidor) en el momento en que se realiza la conexión, antes de que se conceda la canalización de ASP.net Core.

### <a name="adding-aspnet-core-certificate-authentication"></a>Agregar ASP.NET Core la autenticación de certificados

El paquete NuGet [Microsoft. AspNetCore. Authentication. Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) proporciona la autenticación de certificados.

Agregue el servicio de autenticación de certificados en el método `ConfigureServices` y agregue autenticación y autorización a la canalización de ASP.NET Core en el método `Configure`.

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

## <a name="providing-channel-credentials-in-the-client-application"></a>Proporcionar credenciales de canal en la aplicación cliente

Con el paquete de `Grpc.Net.Client`, los certificados se configuran en una instancia de <xref:System.Net.Http.HttpClient> que se proporciona al `GrpcChannel` que se usa para la conexión.

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

## <a name="combining-channelcredentials-and-callcredentials"></a>Combinación de ChannelCredentials y CallCredentials

Puede configurar el servidor para que use la autenticación de certificados y de tokens aplicando los cambios de certificado en el servidor de Kestrel y usando el middleware portador de JWT en ASP.NET Core.

Para proporcionar ChannelCredentials y CallCredentials en el cliente, use el método `ChannelCredentials.Create` para aplicar las credenciales de llamada. La autenticación de certificados todavía debe aplicarse mediante la <xref:System.Net.Http.HttpClient> instancia: si se pasan argumentos al constructor `SslCredentials`, el código de cliente interno produce una excepción. El parámetro `SslCredentials` solo se incluye en el método `Create` del paquete de `Grpc.Net.Client` para mantener la compatibilidad con el paquete de `Grpc.Core`.

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
> Puede usar el método `ChannelCredentials.Create` para un cliente sin autenticación de certificado, como una manera útil de pasar credenciales de token con cada llamada realizada en el canal.

En GitHub se ha agregado una versión de la [aplicación FullStockTicker de ejemplo gRPC con autenticación de certificado](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) .

>[!div class="step-by-step"]
>[Anterior](call-credentials.md)
>[Siguiente](encryption.md)
