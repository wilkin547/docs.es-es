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
# <a name="channel-credentials"></a>Credenciales de canal

Como su nombre indica, las credenciales de canal se asocian al canal gRPC subyacente. La forma estándar de credenciales de canal utiliza la autenticación de certificado de cliente. En este proceso, el cliente proporciona un certificado TLS cuando realiza la conexión y, a continuación, el servidor comprueba esto antes de permitir que se realicen llamadas.

Puede combinar las credenciales de canal con las credenciales de llamada para proporcionar una seguridad completa para un servicio gRPC. Las credenciales de canal prueban que la aplicación cliente tiene permiso para tener acceso al servicio y las credenciales de llamada proporcionan información sobre la persona que usa la aplicación cliente.

La autenticación de certificado de cliente funciona para gRPC de la misma manera que para ASP.NET Core. Para obtener más información, consulte Configurar la autenticación de [certificados en ASP.NET Core](/aspnet/core/security/authentication/certauth).

Para fines de desarrollo, puede usar un certificado autofirmado, pero para la producción debe usar un certificado HTTPS adecuado firmado por una autoridad de confianza.

## <a name="add-certificate-authentication-to-the-server"></a>Agregar autenticación de certificado al servidor

Configure la autenticación de certificados tanto en el nivel de host (por ejemplo, en el servidor de Kestrel) como en la canalización ASP.NET Core.

### <a name="configure-certificate-validation-on-kestrel"></a>Configurar la validación de certificados en Kestrel

Puede configurar Kestrel (el servidor HTTP ASP.NET Core) para que requiera un certificado de cliente y, opcionalmente, para llevar a cabo alguna validación del certificado proporcionado antes de aceptar conexiones entrantes. Esto se hace `CreateWebHostBuilder` en `Program` el método de `Startup`la clase, en lugar de en .

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

La `ClientCertificateMode.RequireCertificate` configuración hace que Kestrel rechace inmediatamente cualquier solicitud de conexión que no proporcione un certificado de cliente, pero esta configuración por sí misma no validará un certificado que se proporciona. Agregue `ClientCertificateValidation` la devolución de llamada para permitir que Kestrel valide el certificado de cliente en el punto en que se realiza la conexión, antes de que se active la canalización de ASP.NET Core. (En este caso, la devolución de llamada se asegura de que fue emitida por la misma entidad de *certificación* que el certificado de servidor.)

### <a name="add-aspnet-core-certificate-authentication"></a>Agregar autenticación de certificado ASP.NET Core

El paquete NuGet [Microsoft.AspNetCore.Authentication.Certificate](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Certificate) proporciona autenticación de certificado.

Agregue el servicio de `ConfigureServices` autenticación de certificados en el método y `Configure` agregue autenticación y autorización a la canalización de ASP.NET Core en el método.

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

Con `Grpc.Net.Client` el paquete, se <xref:System.Net.Http.HttpClient> configuran certificados en `GrpcChannel` una instancia que se proporciona al utilizado para la conexión.

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

## <a name="combine-channelcredentials-and-callcredentials"></a>Combinar ChannelCredentials y CallCredentials

Puede configurar el servidor para que use la autenticación de certificados y tokens. Para ello, aplique los cambios de certificado al servidor de Kestrel y utilice el middleware del portador de JWT en ASP.NET Core.

Para proporcionar `ChannelCredentials` `CallCredentials` ambos y en `ChannelCredentials.Create` el cliente, utilice el método para aplicar las credenciales de llamada. Todavía debe aplicar la autenticación <xref:System.Net.Http.HttpClient> de certificado mediante la instancia. Si pasa argumentos al `SslCredentials` constructor, el código de cliente interno produce una excepción. El `SslCredentials` parámetro solo se `Grpc.Net.Client` incluye `Create` en el método del `Grpc.Core` paquete para mantener la compatibilidad con el paquete.

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
> Puede utilizar `ChannelCredentials.Create` el método para un cliente sin autenticación de certificado. Esta es una forma útil de pasar credenciales de token con cada llamada realizada en el canal.

Una versión de la aplicación gRPC de [ejemplo FullStockTicker con autenticación](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTickerAuth/FullStockTicker) de certificado agregada se encuentra en GitHub.

>[!div class="step-by-step"]
>[Anterior](call-credentials.md)
>[Siguiente](encryption.md)
