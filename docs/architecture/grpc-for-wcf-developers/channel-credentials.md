---
title: 'Credenciales de canal: gRPC para desarrolladores de WCF'
description: Cómo implementar y usar las credenciales del canal de gRPC en ASP.NET Core 3,0.
ms.date: 12/15/2020
ms.openlocfilehash: 3663bbf061156db957241e2a32dbb9c64562ade2
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938642"
---
# <a name="channel-credentials"></a>Credenciales de canal

Como implica el nombre, las credenciales del canal se adjuntan al canal gRPC subyacente. La forma estándar de credenciales de canal utiliza la autenticación de certificado de cliente. En este proceso, el cliente proporciona un certificado TLS cuando está realizando la conexión y, a continuación, el servidor comprueba este certificado antes de permitir que se realicen llamadas.

Puede combinar las credenciales del canal con las credenciales de llamada para proporcionar una seguridad completa para un servicio de gRPC. Las credenciales del canal demuestran que la aplicación cliente puede tener acceso al servicio y las credenciales de llamada proporcionan información sobre la persona que utiliza la aplicación cliente.

La autenticación de certificados de cliente funciona para gRPC de la misma manera que en ASP.NET Core. Para obtener más información, consulte [configurar la autenticación de certificados en ASP.net Core](/aspnet/core/security/authentication/certauth).

Para fines de desarrollo, puede usar un certificado autofirmado, pero para producción debe usar un certificado HTTPS adecuado firmado por una entidad de confianza.

## <a name="add-certificate-authentication-to-the-server"></a>Agregar autenticación de certificado al servidor

Configure la autenticación de certificados en el nivel de host (por ejemplo, en el servidor de Kestrel) y en la canalización ASP.NET Core.

### <a name="configure-certificate-validation-on-kestrel"></a>Configurar la validación de certificados en Kestrel

Puede configurar Kestrel (el servidor HTTP ASP.NET Core) para requerir un certificado de cliente y, opcionalmente, realizar alguna validación del certificado proporcionado antes de aceptar las conexiones entrantes. Esta configuración se especifica en el `CreateWebHostBuilder` método de la `Program` clase, en lugar de en `Startup` .

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

La `ClientCertificateMode.RequireCertificate` configuración hace que Kestrel rechace inmediatamente cualquier solicitud de conexión que no proporcione un certificado de cliente, pero esta configuración por sí misma no validará un certificado proporcionado. Agregue la `ClientCertificateValidation` devolución de llamada para habilitar Kestrel con el fin de validar el certificado de cliente en el momento en que se realiza la conexión, antes de que se active la canalización de ASP.net Core. (En este caso, la devolución de llamada garantiza que fue emitida por la misma *entidad de certificación* que el certificado de servidor).

### <a name="add-aspnet-core-certificate-authentication"></a>Agregar ASP.NET Core autenticación de certificados

El paquete de NuGet [Microsoft. AspNetCore. Authentication. Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) proporciona autenticación de certificado.

Agregue el servicio de autenticación de certificados en el `ConfigureServices` método y agregue autenticación y autorización a la canalización de ASP.net Core en el `Configure` método.

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

## <a name="provide-channel-credentials-in-the-client-application"></a>Proporcionar credenciales de canal en la aplicación cliente

Con el `Grpc.Net.Client` paquete, los certificados se configuran en una <xref:System.Net.Http.HttpClient> instancia de que se proporciona al `GrpcChannel` utilizado para la conexión.

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

## <a name="combine-channelcredentials-and-callcredentials"></a>Combinación de ChannelCredentials y CallCredentials

Puede configurar el servidor para que use la autenticación de certificados y de tokens. Para ello, aplique los cambios de certificado en el servidor de Kestrel y use el middleware portador de JWT en ASP.NET Core.

Para proporcionar `ChannelCredentials` y `CallCredentials` en el cliente, use el `ChannelCredentials.Create` método para aplicar las credenciales de llamada. Todavía es necesario aplicar la autenticación de certificado mediante la <xref:System.Net.Http.HttpClient> instancia de. Si se pasan argumentos al `SslCredentials` constructor, el código de cliente interno produce una excepción. El `SslCredentials` parámetro solo se incluye en el `Grpc.Net.Client` método del paquete `Create` para mantener la compatibilidad con el `Grpc.Core` paquete.

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
> Puede usar el `ChannelCredentials.Create` método para un cliente sin autenticación de certificado. Esta es una forma útil de pasar credenciales de token con cada llamada realizada en el canal.

En GitHub se ha agregado una versión de la [aplicación FullStockTicker de ejemplo gRPC con autenticación de certificado](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) .

>[!div class="step-by-step"]
>[Anterior](call-credentials.md)
>[Siguiente](encryption.md)
