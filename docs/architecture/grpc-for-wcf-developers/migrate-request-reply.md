---
title: Migrar un servicio de solicitud-respuesta de WCF a gRPC-gRPC para desarrolladores de WCF
description: Obtenga información sobre cómo migrar un servicio de solicitud-respuesta simple de WCF a gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 018aa94a15cdcb1e0f559afb7b3a88cd4f915398
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628558"
---
# <a name="migrate-a-wcf-request-reply-service-to-a-grpc-unary-rpc"></a>Migrar un servicio de solicitud-respuesta de WCF a una RPC unaria de gRPC

En esta sección se explica cómo migrar un servicio básico de solicitud-respuesta en WCF a un servicio RPC unario en ASP.NET Core gRPC. Estos servicios son los tipos de servicio más sencillos en Windows Communication Foundation (WCF) y gRPC, por lo que es un lugar excelente para comenzar. Después de migrar el servicio, aprenderá a generar una biblioteca de cliente desde el mismo `.proto` archivo para consumir el servicio desde una aplicación cliente de .NET.

## <a name="the-wcf-solution"></a>La solución WCF

La [solución PortfoliosSample](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) incluye un servicio de cartera de solicitud-respuesta simple para descargar una sola cartera o todas las carteras de un comerciante determinado. El servicio se define en la interfaz `IPortfolioService` con un atributo de `ServiceContract`:

```csharp
[ServiceContract]
public interface IPortfolioService
{
    [OperationContract]
    Task<Portfolio> Get(Guid traderId, int portfolioId);

    [OperationContract]
    Task<List<Portfolio>> GetAll(Guid traderId);
}
```

El modelo `Portfolio` es una clase C# simple marcada con [DataContract](xref:System.Runtime.Serialization.DataContractAttribute) e incluye una lista de objetos `PortfolioItem`. Estos modelos se definen en el proyecto de `TraderSys.PortfolioData` junto con una clase de repositorio que representa una abstracción de acceso a datos.

```csharp
[DataContract]
public class Portfolio
{
    [DataMember]
    public int Id { get; set; }

    [DataMember]
    public Guid TraderId { get; set; }

    [DataMember]
    public List<PortfolioItem> Items { get; set; }
}

[DataContract]
public class PortfolioItem
{
    [DataMember]
    public int Id { get; set; }

    [DataMember]
    public int ShareId { get; set; }

    [DataMember]
    public int Holding { get; set; }

    [DataMember]
    public decimal Cost { get; set; }
}
```

La implementación de `ServiceContract` usa una clase de repositorio proporcionada a través de la inserción de dependencias que devuelve instancias de los tipos de `DataContract`:

```csharp
public class PortfolioService : IPortfolioService
{
    private readonly IPortfolioRepository _repository;

    public PortfolioService(IPortfolioRepository repository)
    {
        _repository = repository;
    }

    public async Task<Portfolio> Get(Guid traderId, int portfolioId)
    {
        return await _repository.GetAsync(traderId, portfolioId);
    }

    public async Task<List<Portfolio>> GetAll(Guid traderId)
    {
        return await _repository.GetAllAsync(traderId);
    }
}
```

## <a name="the-portfoliosproto-file"></a>El archivo portfolios. proto

Si ha seguido las instrucciones de la sección anterior, debe tener un proyecto de gRPC con un archivo `portfolios.proto` que tenga el siguiente aspecto:

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

El primer paso es migrar las clases de `DataContract` a sus equivalentes de protobuf.

## <a name="convert-the-datacontract-classes-to-grpc-messages"></a>Convertir las clases DataContract en mensajes gRPC

La clase `PortfolioItem` se convertirá primero en un mensaje protobuf, porque la clase `Portfolio` depende de ella. La clase es simple y tres de las propiedades se asignan directamente a los tipos de datos gRPC. La propiedad `Cost`, que representa el precio pagado por los recursos compartidos en compra, es un campo `decimal`. gRPC solo admite `float` o `double` para números reales, que no son adecuados para la moneda. Dado que los precios de los recursos compartidos varían en un mínimo de un cien, el costo puede expresarse como un `int32` de céntimos.

> [!NOTE]
> Recuerde usar camelCase para los nombres de campo en el archivo de `.proto`. El C# generador de código los convertirá a PascalCase por usted y los usuarios de otros idiomas le agradecerán que respete sus diferentes estándares de codificación.

```protobuf
message PortfolioItem {
    int32 id = 1;
    int32 share_id = 2;
    int32 holding = 3;
    int32 cost_cents = 4;
}
```

La clase `Portfolio` es un poco más complicada. En el código WCF, el desarrollador usaba un `Guid` para la propiedad `TraderId` y contiene un `List<PortfolioItem>`. En protobuf, que no tiene un tipo de `UUID` de primera clase, debe utilizar un `string` para el campo de `traderId` y analizarlo en su propio código. Para la lista de elementos, utilice la palabra clave `repeated` en el campo.

```protobuf
message Portfolio {
    int32 id = 1;
    string trader_id = 2;
    repeated PortfolioItem items = 3;
}
```

Ahora que tiene los mensajes de datos, puede declarar los extremos de RPC del servicio.

## <a name="convert-servicecontract-to-a-grpc-service"></a>Convertir ServiceContract en un servicio gRPC

El método `Get` de WCF toma dos parámetros: `Guid traderId` y `int portfolioId`. los métodos de servicio de gRPC solo pueden tomar un único parámetro, por lo que debe crear un mensaje que contenga los dos valores. Es habitual asignar un nombre a estos objetos de solicitud con el mismo nombre que el método seguido del sufijo `Request`. De nuevo, `string` se usa para el campo `traderId` en lugar de `Guid`.

El servicio podría devolver solo un mensaje de `Portfolio` directamente, pero de nuevo, esto podría afectar a la compatibilidad con versiones anteriores en el futuro. Es recomendable definir mensajes de `Request` y `Response` independientes para cada método de un servicio, incluso si muchos de ellos son los mismos en este momento. Por lo tanto, declare un mensaje de `GetResponse` con un solo campo de `Portfolio`.

En este ejemplo se muestra la declaración del método de servicio gRPC con el mensaje `GetRequest`:

```protobuf
message GetRequest {
    string trader_id = 1;
    int32 portfolio_id = 2;
}

message GetResponse {
    Portfolio portfolio = 1;
}

service Portfolios {
    rpc Get(GetRequest) returns (GetResponse);
}
```

El método `GetAll` de WCF solo toma un parámetro, `traderId`, por lo que podría parecer que podría especificar `string` como el tipo de parámetro. Pero gRPC requiere un tipo de mensaje definido. Este requisito ayuda a exigir la práctica del uso de mensajes personalizados para todas las entradas y salidas, para mantener la compatibilidad con versiones anteriores.

El método WCF también devuelve un `List<Portfolio>`, pero por la misma razón no permite tipos de parámetros simples, gRPC no permitirá `repeated Portfolio` como un tipo de valor devuelto. En su lugar, cree un tipo de `GetAllResponse` para encapsular la lista.

> [!WARNING]
> Es posible que se sienta tentado a crear un mensaje de `PortfolioList` o algo similar y usarlo en varios métodos de servicio, pero debe resistir esta tentación. No es posible saber cómo evolucionan los distintos métodos de un servicio, por lo que debe mantener sus mensajes específicos y separados de forma limpia.

```protobuf
message GetAllRequest {
    string trader_id = 1;
}

message PortfolioList {
    repeated Portfolio portfolios = 1;
}

service Portfolios {
    rpc Get(GetRequest) returns (Portfolio);
    rpc GetAll(GetAllRequest) returns (GetAllResponse);
}
```

Si guarda el proyecto con estos cambios, el destino de compilación gRPC se ejecutará en segundo plano y generará todos los tipos de mensaje protobuf y una clase base que puede heredar para implementar el servicio.

Abra la clase `Services/GreeterService.cs` y elimine el código de ejemplo. Ahora puede Agregar la implementación del servicio de cartera. La clase base generada estará en el espacio de nombres `Protos` y se genera como una clase anidada. gRPC crea una clase estática con el mismo nombre que el servicio en el archivo `.proto` y una clase base con el sufijo `Base` dentro de esa clase estática, por lo que se `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`el identificador completo para el tipo base.

```csharp
namespace TraderSys.Portfolios.Services
{
    public class PortfolioService : Protos.Portfolios.PortfoliosBase
    {
    }
}
```

La clase base declara métodos `virtual` para `Get` y `GetAll` que se pueden invalidar para implementar el servicio. Los métodos son `virtual` en lugar de `abstract` para que, si no los implemente, el servicio pueda devolver un código de estado de gRPC explícito `Unimplemented`, de forma muy similar a C# como podría iniciar una `NotImplementedException` en código normal.

La firma para todos los métodos de servicio unario gRPC en ASP.NET Core es coherente. Hay dos parámetros: el primero es el tipo de mensaje declarado en el archivo `.proto` y el segundo es un `ServerCallContext` que funciona de forma similar a la `HttpContext` de ASP.NET Core. De hecho, hay un método de extensión denominado `GetHttpContext` en la clase `ServerCallContext` que se puede usar para obtener el `HttpContext`subyacente, aunque no es necesario usarlo a menudo. Echemos un vistazo a `ServerCallContext` más adelante en este capítulo y también en el capítulo en el que se describe la autenticación.

El tipo de valor devuelto del método es un `Task<T>`, donde `T` es el tipo de mensaje de respuesta. Todos los métodos de servicio de gRPC son asíncronos.

## <a name="migrate-the-portfoliodata-library-to-net-core"></a>Migración de la biblioteca de PortfolioData a .NET Core

En este momento, el proyecto necesita el repositorio y los modelos de cartera incluidos en la biblioteca de clases de `TraderSys.PortfolioData` en la solución WCF. La forma más fácil de llevarlos a cabo es crear una nueva biblioteca de clases mediante el cuadro de diálogo **nuevo proyecto** de Visual Studio con la plantilla biblioteca de clases (.net Standard) o desde la línea de comandos mediante el CLI de .net Core, ejecutando estos comandos desde el directorio que contiene el archivo `TraderSys.sln`:

```dotnetcli
dotnet new classlib -o src/TraderSys.PortfolioData
dotnet sln add src/TraderSys.PortfolioData
```

Una vez creada la biblioteca y agregada a la solución, elimine el archivo de `Class1.cs` generado y copie los archivos de la biblioteca de la solución WCF en la carpeta de la nueva biblioteca de clases, manteniendo la estructura de carpetas:

```
Models
  Portfolio.cs
  PortfolioItem.cs
IPortfolioRepository.cs
PortfolioRepository.cs
```

Los proyectos de .NET de estilo SDK incluyen automáticamente los archivos `.cs` en su propio directorio, por lo que no es necesario agregarlos explícitamente al proyecto. El único paso que queda es quitar los atributos `DataContract` y `DataMember` de las clases `Portfolio` y `PortfolioItem` para que sean clases antiguas C# sin formato:

```csharp
public class Portfolio
{
    public int Id { get; set; }
    public Guid TraderId { get; set; }
    public List<PortfolioItem> Items { get; set; }
}

public class PortfolioItem
{
    public int Id { get; set; }
    public int ShareId { get; set; }
    public int Holding { get; set; }
    public decimal Cost { get; set; }
}
```

## <a name="use-aspnet-core-dependency-injection"></a>Usar la inserción de dependencias ASP.NET Core

Ahora puede Agregar una referencia a esta biblioteca al proyecto de aplicación gRPC y consumir la clase `PortfolioRepository` mediante la inserción de dependencias en la implementación del servicio gRPC. En la aplicación WCF, el contenedor de IoC Autofac proporcionó la inserción de dependencias. ASP.NET Core tiene incrustada la inserción de dependencias. Puede registrar el repositorio en el método `ConfigureServices` de la clase `Startup`:

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        // Register the repository class as a scoped service (instance per request)
        services.AddScoped<IPortfolioRepository, PortfolioRepository>();

        services.AddGrpc();
    }

    // ...
}
```

La implementación de `IPortfolioRepository` ahora se puede especificar como un parámetro de constructor en la clase `PortfolioService`, como se indica a continuación:

```csharp
public class PortfolioService : Protos.Portfolios.PortfoliosBase
{
    private readonly IPortfolioRepository _repository;

    public PortfolioService(IPortfolioRepository repository)
    {
        _repository = repository;
    }
}
```

## <a name="implement-the-grpc-service"></a>Implementar el servicio gRPC

Ahora que ha declarado los mensajes y el servicio en el archivo `portfolios.proto`, tiene que implementar los métodos de servicio en la clase `PortfolioService` que hereda de la clase `Portfolios.PortfoliosBase` generada por gRPC. Los métodos se declaran como `virtual` en la clase base. Si no los invalida, devolverán un código de estado gRPC "no implementado" de forma predeterminada.

Empiece por implementar el método `Get`. La invalidación predeterminada es similar a la de este ejemplo:

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    return base.Get(request, context);
}
```

El primer problema es que `request.TraderId` es una cadena y el servicio requiere un `Guid`. Aunque el formato esperado para la cadena es `UUID`, el código tiene que tratar con la posibilidad de que un autor de llamada haya enviado un valor no válido y de responder adecuadamente. El servicio puede responder con errores iniciando una `RpcException` y usando el código de estado de `InvalidArgument` estándar para expresar el problema:

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    return base.Get(request, context);
}
```

Después de que haya un valor de `Guid` adecuado para `traderId`, puede usar el repositorio para recuperar la cartera y devolverla al cliente:

```csharp
    var response = new GetResponse
    {
        Portfolio = await _repository.GetAsync(request.TraderId, request.PortfolioId)
    };
```

### <a name="map-internal-models-to-grpc-messages"></a>Asignación de modelos internos a mensajes gRPC

El código anterior no funciona realmente porque el repositorio devuelve su propio modelo POCO `Portfolio`, pero gRPC necesita su propio mensaje de protobuf `Portfolio`. Al asignar Entity Framework tipos a tipos de transferencia de datos, la mejor solución es proporcionar una conversión entre ambos. Un buen lugar para colocar el código para esta conversión se encuentra en la clase generada por protobuf, que se declara como una clase `partial` para que se pueda extender:

```csharp
namespace TraderSys.Portfolios.Protos
{
    public partial class PortfolioItem
    {
        public static PortfolioItem FromRepositoryModel(PortfolioData.Models.PortfolioItem source)
        {
            if (source is null) return null;

            return new PortfolioItem
            {
                Id = source.Id,
                ShareId = source.ShareId,
                Holding = source.Holding,
                CostCents = (int)(source.Cost * 100)
            };
        }
    }

    public partial class Portfolio
    {
        public static Portfolio FromRepositoryModel(PortfolioData.Models.Portfolio source)
        {
            if (source is null) return null;

            var target = new Portfolio
            {
                Id = source.Id,
                TraderId = source.TraderId.ToString(),
            };

            target.Items.AddRange(source.Items.Select(PortfolioItem.FromRepositoryModel));

            return target;
        }
    }
}
```

> [!NOTE]
> Puede usar una biblioteca como [automapper](https://automapper.org/) para controlar esta conversión de las clases de modelo internas a tipos protobuf, siempre y cuando configure las conversiones de tipo de nivel inferior, como `string`/`Guid` o `decimal`/`double` y la asignación de lista.

Ahora que tiene el código de conversión en su lugar, puede completar la implementación del método `Get`:

```csharp
public override async Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    var portfolio = await _repository.GetAsync(traderId, request.PortfolioId);

    return new GetResponse
    {
        Portfolio = Portfolio.FromRepositoryModel(portfolio)
    };
}

```

La implementación del método `GetAll` es similar. Tenga en cuenta que los campos de `repeated` en los mensajes protobuf se generan como propiedades `readonly` de tipo `RepeatedField<T>`, por lo que tiene que agregar elementos a ellos mediante el método `AddRange`, como en este ejemplo:

```csharp
public override async Task<GetAllResponse> GetAll(GetAllRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    var portfolios = await _repository.GetAllAsync(traderId);

    var response = new GetAllResponse();
    response.Portfolios.AddRange(portfolios.Select(Portfolio.FromRepositoryModel));

    return response;
}
```

Después de migrar correctamente el servicio de solicitud-respuesta de WCF a gRPC, echemos un vistazo a la creación de un cliente para él desde el archivo de `.proto`.

## <a name="generate-client-code"></a>Generar código de cliente

Cree una biblioteca de clases de .NET Standard en la misma solución que contenga el cliente. Este es principalmente un ejemplo de la creación de código de cliente, pero podría empaquetar dicha biblioteca mediante el uso de NuGet y distribuirlo en un repositorio interno para que otros equipos de .NET lo consuman. Continúe y agregue una nueva biblioteca de clases .NET Standard denominada `TraderSys.Portfolios.Client` a la solución y elimine el archivo `Class1.cs`.

> [!CAUTION]
> El paquete NuGet de [GRPC .net. Client](https://www.nuget.org/packages/Grpc.Net.Client) requiere .net Core 3,0 (u otro tiempo de ejecución compatible con .net Standard 2,1). Las versiones anteriores de .NET Framework y .NET Core son compatibles con el paquete NuGet [GRPC. Core](https://www.nuget.org/packages/Grpc.Core) .

En Visual Studio 2019, puede Agregar referencias a los servicios de gRPC de una manera similar a como se haría con la adición de referencias de servicio a proyectos de WCF en versiones anteriores de Visual Studio. Las referencias de servicio y los servicios conectados se administran ahora en la misma interfaz de usuario. Para acceder a la interfaz de usuario, haga clic con el botón secundario en el nodo **dependencias** del proyecto `TraderSys.Portfolios.Client` en explorador de soluciones y seleccione **Agregar servicio conectado**. En la ventana de herramientas que aparece, seleccione la sección **referencias de servicio** y, a continuación, seleccione **Agregar nueva referencia de servicio de gRPC**:

![Servicios conectados interfaz de usuario en Visual Studio 2019](media/migrate-request-reply/add-connected-service.png)

Busque el archivo de `portfolios.proto` en el proyecto `TraderSys.Portfolios`, deje **cliente** en **Seleccione el tipo de clase que se va a generar**y, a continuación, seleccione **Aceptar**:

![Cuadro de diálogo Agregar nueva referencia de servicio de gRPC en Visual Studio 2019](media/migrate-request-reply/add-new-grpc-service-reference.png)

> [!TIP]
> Tenga en cuenta que este cuadro de diálogo también proporciona un campo de dirección URL. Si su organización mantiene un directorio accesible desde web de `.proto` archivos, puede crear clientes simplemente estableciendo esta dirección URL.

Cuando se usa la característica **Agregar servicio conectado** de Visual Studio, el archivo de `portfolios.proto` se agrega al proyecto de biblioteca de clases como un *archivo vinculado* , en lugar de copiarse, por lo que los cambios en el archivo del proyecto de servicio se aplicarán automáticamente en el proyecto de cliente. El elemento `<Protobuf>` del archivo `csproj` tiene el siguiente aspecto:

```xml
<Protobuf Include="..\TraderSys.Portfolios\Protos\portfolios.proto" GrpcServices="Client">
  <Link>Protos\portfolios.proto</Link>
</Protobuf>
```

> [!TIP]
> Si no usa Visual Studio o prefiere trabajar desde la línea de comandos, puede usar la herramienta global `dotnet-grpc` para administrar las referencias de protobuf en un proyecto de gRPC de .NET. Para obtener más información, consulte la [documentación de`dotnet-grpc`](/aspnet/core/grpc/dotnet-grpc).

### <a name="use-the-portfolios-service-from-a-client-application"></a>Usar el servicio de carteras desde una aplicación cliente

El código siguiente es un breve ejemplo de cómo usar el cliente generado en una aplicación de consola. Al final de este capítulo, se describe con más detalle la exploración del código de cliente de gRPC.

```csharp
public class Program
{
    public async Task Main(string[] args)
    {
        GetResponse response;

        using (var channel = GrpcChannel.ForAddress("https://localhost:5001"))
        {
            var client = new Protos.Portfolios.PortfoliosClient(channel);

            response = await client.GetAsync(new GetRequest
            {
                TraderId = args[0],
                PortfolioId = int.Parse(args[1])
            });
        }

        foreach (var item in response.Portfolio.Items)
        {
            Console.WriteLine($"Holding {item.Holding} of Share ID {item.ShareId}.");
        }
    }
}
```

Ahora ha migrado una aplicación WCF básica a un ASP.NET Core servicio gRPC y ha creado un cliente para consumir el servicio desde una aplicación .NET. En la siguiente sección se tratarán los servicios dúplex más implicados.

>[!div class="step-by-step"]
>[Anterior](create-project.md)
>[Siguiente](migrate-duplex-services.md)
