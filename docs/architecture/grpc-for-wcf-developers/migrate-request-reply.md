---
title: Migrar un servicio de solicitud-respuesta de WCF a gRPC-gRPC para desarrolladores de WCF
description: Obtenga información sobre cómo migrar un servicio de solicitud-respuesta simple de WCF a gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 29a7bc77bc3a4becd767fc7a50adff5b746f54bc
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "97512702"
---
# <a name="migrate-a-wcf-request-reply-service-to-a-grpc-unary-rpc"></a><span data-ttu-id="ce1ae-103">Migrar un servicio de solicitud-respuesta de WCF a una RPC unaria de gRPC</span><span class="sxs-lookup"><span data-stu-id="ce1ae-103">Migrate a WCF request-reply service to a gRPC unary RPC</span></span>

<span data-ttu-id="ce1ae-104">En esta sección se explica cómo migrar un servicio básico de solicitud-respuesta en WCF a un servicio RPC unario en ASP.NET Core gRPC.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-104">This section covers how to migrate a basic request-reply service in WCF to a unary RPC service in ASP.NET Core gRPC.</span></span> <span data-ttu-id="ce1ae-105">Estos servicios son los tipos de servicio más sencillos en Windows Communication Foundation (WCF) y gRPC, por lo que es un lugar excelente para comenzar.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-105">These services are the simplest service types in both Windows Communication Foundation (WCF) and gRPC, so it's an excellent place to start.</span></span> <span data-ttu-id="ce1ae-106">Después de migrar el servicio, aprenderá a generar una biblioteca de cliente desde el mismo `.proto` archivo para consumir el servicio desde una aplicación cliente de .net.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-106">After migrating the service, you'll learn how to generate a client library from the same `.proto` file to consume the service from a .NET client application.</span></span>

## <a name="the-wcf-solution"></a><span data-ttu-id="ce1ae-107">La solución WCF</span><span class="sxs-lookup"><span data-stu-id="ce1ae-107">The WCF solution</span></span>

<span data-ttu-id="ce1ae-108">La [solución PortfoliosSample](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) incluye un servicio de cartera de solicitud-respuesta simple para descargar una sola cartera o todas las carteras de un comerciante determinado.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-108">The [PortfoliosSample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) includes a simple request-reply Portfolio service to download either a single portfolio or all portfolios for a given trader.</span></span> <span data-ttu-id="ce1ae-109">El servicio se define en la interfaz `IPortfolioService` con un `ServiceContract` atributo:</span><span class="sxs-lookup"><span data-stu-id="ce1ae-109">The service is defined in the interface `IPortfolioService` with a `ServiceContract` attribute:</span></span>

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

<span data-ttu-id="ce1ae-110">El `Portfolio` modelo es una clase de C# simple marcada con [DataContract](xref:System.Runtime.Serialization.DataContractAttribute) e incluye una lista de `PortfolioItem` objetos.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-110">The `Portfolio` model is a simple C# class marked with [DataContract](xref:System.Runtime.Serialization.DataContractAttribute) and including a list of `PortfolioItem` objects.</span></span> <span data-ttu-id="ce1ae-111">Estos modelos se definen en el `TraderSys.PortfolioData` proyecto junto con una clase de repositorio que representa una abstracción de acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-111">These models are defined in the `TraderSys.PortfolioData` project along with a repository class that represents a data access abstraction.</span></span>

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

<span data-ttu-id="ce1ae-112">La `ServiceContract` implementación utiliza una clase de repositorio proporcionada a través de la inserción de dependencias que devuelve instancias de los `DataContract` tipos:</span><span class="sxs-lookup"><span data-stu-id="ce1ae-112">The `ServiceContract` implementation uses a repository class provided via dependency injection that returns instances of the `DataContract` types:</span></span>

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

## <a name="the-portfoliosproto-file"></a><span data-ttu-id="ce1ae-113">El archivo portfolios. proto</span><span class="sxs-lookup"><span data-stu-id="ce1ae-113">The portfolios.proto file</span></span>

<span data-ttu-id="ce1ae-114">Si ha seguido las instrucciones de la sección anterior, debe tener un proyecto gRPC con un `portfolios.proto` archivo similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="ce1ae-114">If you followed the instructions in the previous section, you should have a gRPC project with a `portfolios.proto` file that looks like this:</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

<span data-ttu-id="ce1ae-115">El primer paso es migrar las `DataContract` clases a sus equivalentes de protobuf.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-115">The first step is to migrate the `DataContract` classes to their Protobuf equivalents.</span></span>

## <a name="convert-the-datacontract-classes-to-grpc-messages"></a><span data-ttu-id="ce1ae-116">Convertir las clases DataContract en mensajes gRPC</span><span class="sxs-lookup"><span data-stu-id="ce1ae-116">Convert the DataContract classes to gRPC messages</span></span>

<span data-ttu-id="ce1ae-117">La `PortfolioItem` clase se convertirá en un mensaje protobuf en primer lugar, porque la `Portfolio` clase depende de él.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-117">The `PortfolioItem` class will be converted to a Protobuf message first, because the `Portfolio` class depends on it.</span></span> <span data-ttu-id="ce1ae-118">La clase es simple y tres de las propiedades se asignan directamente a los tipos de datos gRPC.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-118">The class is simple, and three of the properties map directly to gRPC data types.</span></span> <span data-ttu-id="ce1ae-119">La `Cost` propiedad, que representa el precio pagado por los recursos compartidos en compra, es un `decimal` campo.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-119">The `Cost` property, which represents the price paid for the shares at purchase, is a `decimal` field.</span></span> <span data-ttu-id="ce1ae-120">gRPC solo admite `float` o `double` para números reales, que no son adecuados para la moneda.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-120">gRPC supports only `float` or `double` for real numbers, which aren't suitable for currency.</span></span> <span data-ttu-id="ce1ae-121">Dado que los precios de los recursos compartidos varían en un mínimo de un ciento, el costo puede expresarse como un `int32` de céntimos.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-121">Because share prices vary by a minimum of one cent, the cost can be expressed as an `int32` of cents.</span></span>

> [!NOTE]
> <span data-ttu-id="ce1ae-122">Recuerde usar `snake_case` para los nombres de campo en el `.proto` archivo.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-122">Remember to use `snake_case` for field names in your `.proto` file.</span></span> <span data-ttu-id="ce1ae-123">El generador de código de C# los convertirá en `PascalCase` para usted y los usuarios de otros idiomas le agradecerán que respete sus diferentes estándares de codificación.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-123">The C# code generator will convert them to `PascalCase` for you, and users of other languages will thank you for respecting their different coding standards.</span></span>

```protobuf
message PortfolioItem {
    int32 id = 1;
    int32 share_id = 2;
    int32 holding = 3;
    int32 cost_cents = 4;
}
```

<span data-ttu-id="ce1ae-124">La `Portfolio` clase es un poco más complicada.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-124">The `Portfolio` class is a little more complicated.</span></span> <span data-ttu-id="ce1ae-125">En el código de WCF, el desarrollador usaba un `Guid` para la `TraderId` propiedad y contiene un `List<PortfolioItem>` .</span><span class="sxs-lookup"><span data-stu-id="ce1ae-125">In the WCF code, the developer used a `Guid` for the `TraderId` property, and contains a `List<PortfolioItem>`.</span></span> <span data-ttu-id="ce1ae-126">En protobuf, que no tiene un tipo de primera clase `UUID` , debe utilizar `string` para el `traderId` campo y analizarlo en su propio código.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-126">In Protobuf, which doesn't have a first-class `UUID` type, you should use a `string` for the `traderId` field and parse it in your own code.</span></span> <span data-ttu-id="ce1ae-127">Para la lista de elementos, use la `repeated` palabra clave en el campo.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-127">For the list of items, use the `repeated` keyword on the field.</span></span>

```protobuf
message Portfolio {
    int32 id = 1;
    string trader_id = 2;
    repeated PortfolioItem items = 3;
}
```

<span data-ttu-id="ce1ae-128">Ahora que tiene los mensajes de datos, puede declarar los extremos de RPC del servicio.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-128">Now that you have the data messages, you can declare the service RPC endpoints.</span></span>

## <a name="convert-servicecontract-to-a-grpc-service"></a><span data-ttu-id="ce1ae-129">Convertir ServiceContract en un servicio gRPC</span><span class="sxs-lookup"><span data-stu-id="ce1ae-129">Convert ServiceContract to a gRPC service</span></span>

<span data-ttu-id="ce1ae-130">El `Get` método WCF toma dos parámetros: `Guid traderId` y `int portfolioId` .</span><span class="sxs-lookup"><span data-stu-id="ce1ae-130">The WCF `Get` method takes two parameters: `Guid traderId` and `int portfolioId`.</span></span> <span data-ttu-id="ce1ae-131">los métodos de servicio de gRPC solo pueden tomar un único parámetro, por lo que debe crear un mensaje que contenga los dos valores.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-131">gRPC service methods can take only a single parameter, so you need to create a message to hold the two values.</span></span> <span data-ttu-id="ce1ae-132">Es habitual asignar un nombre a estos objetos de solicitud con el mismo nombre que el método seguido del sufijo `Request` .</span><span class="sxs-lookup"><span data-stu-id="ce1ae-132">It's common practice to name these request objects with the same name as the method followed by the suffix `Request`.</span></span> <span data-ttu-id="ce1ae-133">De nuevo, `string` se usa para el `traderId` campo en lugar de `Guid` .</span><span class="sxs-lookup"><span data-stu-id="ce1ae-133">Again, `string` is being used for the `traderId` field instead of `Guid`.</span></span>

<span data-ttu-id="ce1ae-134">El servicio podría devolver un `Portfolio` mensaje directamente, pero de nuevo, esto podría afectar a la compatibilidad con versiones anteriores en el futuro.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-134">The service could just return a `Portfolio` message directly, but again, this could affect backward compatibility in the future.</span></span> <span data-ttu-id="ce1ae-135">Es recomendable definir `Request` mensajes independientes y `Response` para cada método de un servicio, incluso si muchos de ellos son los mismos en este momento.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-135">It's a good practice to define separate `Request` and `Response` messages for every method in a service, even if many of them are the same right now.</span></span> <span data-ttu-id="ce1ae-136">Por lo tanto, declare un `GetResponse` mensaje con un solo `Portfolio` campo.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-136">So declare a `GetResponse` message with a single `Portfolio` field.</span></span>

<span data-ttu-id="ce1ae-137">En este ejemplo se muestra la declaración del método de servicio gRPC con el `GetRequest` mensaje:</span><span class="sxs-lookup"><span data-stu-id="ce1ae-137">This example shows the declaration of the gRPC service method with the `GetRequest` message:</span></span>

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

<span data-ttu-id="ce1ae-138">El `GetAll` método WCF solo toma un parámetro, `traderId` , por lo que podría parecer que podría especificar `string` como el tipo de parámetro.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-138">The WCF `GetAll` method takes only a single parameter, `traderId`, so it might seem that you could specify `string` as the parameter type.</span></span> <span data-ttu-id="ce1ae-139">Pero gRPC requiere un tipo de mensaje definido.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-139">But gRPC requires a defined message type.</span></span> <span data-ttu-id="ce1ae-140">Este requisito ayuda a exigir la práctica del uso de mensajes personalizados para todas las entradas y salidas, para mantener la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-140">This requirement helps to enforce the practice of using custom messages for all inputs and outputs, for future backward compatibility.</span></span>

<span data-ttu-id="ce1ae-141">El método WCF también devuelve `List<Portfolio>` , pero por la misma razón no permite tipos de parámetros simples, gRPC no permitirá `repeated Portfolio` como tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-141">The WCF method also returns a `List<Portfolio>`, but for the same reason it doesn't allow simple parameter types, gRPC won't allow `repeated Portfolio` as a return type.</span></span> <span data-ttu-id="ce1ae-142">En su lugar, cree un `GetAllResponse` tipo para encapsular la lista.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-142">Instead, create a `GetAllResponse` type to wrap the list.</span></span>

> [!WARNING]
> <span data-ttu-id="ce1ae-143">Es posible que se sienta tentado a crear un `PortfolioList` mensaje o algo similar y usarlo en varios métodos de servicio, pero debe resistir esta tentación.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-143">You might be tempted to create a `PortfolioList` message or something similar and use it across multiple service methods, but you should resist this temptation.</span></span> <span data-ttu-id="ce1ae-144">No es posible saber cómo evolucionan los distintos métodos de un servicio, por lo que debe mantener sus mensajes específicos y separados de forma limpia.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-144">It's impossible to know how the various methods on a service will evolve, so keep their messages specific and cleanly separated.</span></span>

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

<span data-ttu-id="ce1ae-145">Si guarda el proyecto con estos cambios, el destino de compilación gRPC se ejecutará en segundo plano y generará todos los tipos de mensaje protobuf y una clase base que puede heredar para implementar el servicio.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-145">If you save your project with these changes, the gRPC build target will run in the background and generate all the Protobuf message types and a base class that you can inherit to implement the service.</span></span>

<span data-ttu-id="ce1ae-146">Abra la `Services/GreeterService.cs` clase y elimine el código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-146">Open the `Services/GreeterService.cs` class and delete the example code.</span></span> <span data-ttu-id="ce1ae-147">Ahora puede Agregar la implementación del servicio de cartera.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-147">Now you can add the Portfolio service implementation.</span></span> <span data-ttu-id="ce1ae-148">La clase base generada estará en el `Protos` espacio de nombres y se generará como una clase anidada.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-148">The generated base class will be in the `Protos` namespace and is generated as a nested class.</span></span> <span data-ttu-id="ce1ae-149">gRPC crea una clase estática con el mismo nombre que el servicio en el `.proto` archivo y una clase base con el sufijo `Base` dentro de esa clase estática, por lo que el identificador completo del tipo base es `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase` .</span><span class="sxs-lookup"><span data-stu-id="ce1ae-149">gRPC creates a static class with the same name as the service in the `.proto` file and a base class with the suffix `Base` inside that static class, so the full identifier for the base type is `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`.</span></span>

```csharp
namespace TraderSys.Portfolios.Services
{
    public class PortfolioService : Protos.Portfolios.PortfoliosBase
    {
    }
}
```

<span data-ttu-id="ce1ae-150">La clase base declara `virtual` métodos para `Get` y `GetAll` que se pueden invalidar para implementar el servicio.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-150">The base class declares `virtual` methods for `Get` and `GetAll` that can be overridden to implement the service.</span></span> <span data-ttu-id="ce1ae-151">Los métodos son `virtual` en lugar de `abstract` para que, si no los implemente, el servicio pueda devolver un `Unimplemented` código de estado gRPC explícito, de forma muy similar a como podría producir un `NotImplementedException` en código C# normal.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-151">The methods are `virtual` rather than `abstract` so that if you don't implement them, the service can return an explicit gRPC `Unimplemented` status code, much like you might throw a `NotImplementedException` in regular C# code.</span></span>

<span data-ttu-id="ce1ae-152">La firma para todos los métodos de servicio unario gRPC en ASP.NET Core es coherente.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-152">The signature for all gRPC unary service methods in ASP.NET Core is consistent.</span></span> <span data-ttu-id="ce1ae-153">Hay dos parámetros: el primero es el tipo de mensaje declarado en el `.proto` archivo y el segundo es un `ServerCallContext` que funciona de forma similar a `HttpContext` desde ASP.net Core.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-153">There are two parameters: the first is the message type declared in the `.proto` file, and the second is a `ServerCallContext` that works similarly to the `HttpContext` from ASP.NET Core.</span></span> <span data-ttu-id="ce1ae-154">De hecho, hay un método de extensión denominado `GetHttpContext` en la `ServerCallContext` clase que se puede usar para obtener el subyacente `HttpContext` , aunque no es necesario usarlo a menudo.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-154">In fact, there's an extension method called `GetHttpContext` on the `ServerCallContext` class that you can use to get the underlying `HttpContext`, although you shouldn't need to use it often.</span></span> <span data-ttu-id="ce1ae-155">Veremos `ServerCallContext` más adelante en este capítulo y también en el capítulo en el que se describe la autenticación.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-155">We'll take a look at `ServerCallContext` later in this chapter, and also in the chapter that discusses authentication.</span></span>

<span data-ttu-id="ce1ae-156">El tipo de valor devuelto del método es `Task<T>` , donde `T` es el tipo de mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-156">The method's return type is a `Task<T>`, where `T` is the response message type.</span></span> <span data-ttu-id="ce1ae-157">Todos los métodos de servicio de gRPC son asíncronos.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-157">All gRPC service methods are asynchronous.</span></span>

## <a name="migrate-the-portfoliodata-library-to-net-core"></a><span data-ttu-id="ce1ae-158">Migración de la biblioteca de PortfolioData a .NET Core</span><span class="sxs-lookup"><span data-stu-id="ce1ae-158">Migrate the PortfolioData library to .NET Core</span></span>

<span data-ttu-id="ce1ae-159">En este momento, el proyecto necesita el repositorio de cartera y los modelos contenidos en la `TraderSys.PortfolioData` biblioteca de clases de la solución WCF.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-159">At this point, the project needs the Portfolio repository and models contained in the `TraderSys.PortfolioData` class library in the WCF solution.</span></span> <span data-ttu-id="ce1ae-160">La forma más fácil de llevarlos a cabo es crear una nueva biblioteca de clases mediante el cuadro de diálogo **nuevo proyecto** de Visual Studio con la plantilla biblioteca de clases (.net Standard) o desde la línea de comandos mediante el CLI de .net Core, ejecutando estos comandos desde el directorio que contiene el `TraderSys.sln` archivo:</span><span class="sxs-lookup"><span data-stu-id="ce1ae-160">The easiest way to bring them across is to create a new class library by using either the Visual Studio **New project** dialog box with the Class Library (.NET Standard) template, or from the command line by using the .NET Core CLI, running these commands from the directory that contains the `TraderSys.sln` file:</span></span>

```dotnetcli
dotnet new classlib -o src/TraderSys.PortfolioData
dotnet sln add src/TraderSys.PortfolioData
```

<span data-ttu-id="ce1ae-161">Una vez creada la biblioteca y agregada a la solución, elimine el `Class1.cs` archivo generado y copie los archivos de la biblioteca de la solución WCF en la carpeta de la nueva biblioteca de clases, manteniendo la estructura de carpetas:</span><span class="sxs-lookup"><span data-stu-id="ce1ae-161">After you've created the library and added it to the solution, delete the generated `Class1.cs` file and copy the files from the WCF solution's library into the new class library's folder, keeping the folder structure:</span></span>

```
Models
  Portfolio.cs
  PortfolioItem.cs
IPortfolioRepository.cs
PortfolioRepository.cs
```

<span data-ttu-id="ce1ae-162">Los proyectos de .NET de estilo SDK incluyen automáticamente los `.cs` archivos de o en su propio directorio, por lo que no es necesario agregarlos explícitamente al proyecto.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-162">SDK-style .NET projects automatically include any `.cs` files in or under their own directory, so you don't need to explicitly add them to the project.</span></span> <span data-ttu-id="ce1ae-163">El único paso que queda es quitar los `DataContract` `DataMember` atributos y de las `Portfolio` `PortfolioItem` clases y para que sean clases de C# antiguas:</span><span class="sxs-lookup"><span data-stu-id="ce1ae-163">The only step remaining is to remove the `DataContract` and `DataMember` attributes from the `Portfolio` and `PortfolioItem` classes so they're plain old C# classes:</span></span>

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

## <a name="use-aspnet-core-dependency-injection"></a><span data-ttu-id="ce1ae-164">Usar la inserción de dependencias ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ce1ae-164">Use ASP.NET Core dependency injection</span></span>

<span data-ttu-id="ce1ae-165">Ahora puede Agregar una referencia a esta biblioteca al proyecto de aplicación gRPC y consumir la `PortfolioRepository` clase mediante la inserción de dependencias en la implementación del servicio gRPC.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-165">Now you can add a reference to this library to the gRPC application project and consume the `PortfolioRepository` class by using dependency injection in the gRPC service implementation.</span></span> <span data-ttu-id="ce1ae-166">En la aplicación WCF, el contenedor de IoC Autofac proporcionó la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-166">In the WCF application, dependency injection was provided by the Autofac IoC container.</span></span> <span data-ttu-id="ce1ae-167">ASP.NET Core tiene incrustada la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-167">ASP.NET Core has dependency injection baked in.</span></span> <span data-ttu-id="ce1ae-168">Puede registrar el repositorio en el `ConfigureServices` método de la `Startup` clase:</span><span class="sxs-lookup"><span data-stu-id="ce1ae-168">You can register the repository in the `ConfigureServices` method in the `Startup` class:</span></span>

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

<span data-ttu-id="ce1ae-169">La `IPortfolioRepository` implementación ahora se puede especificar como un parámetro de constructor en la `PortfolioService` clase, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="ce1ae-169">The `IPortfolioRepository` implementation can now be specified as a constructor parameter in the `PortfolioService` class, as follows:</span></span>

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

## <a name="implement-the-grpc-service"></a><span data-ttu-id="ce1ae-170">Implementar el servicio gRPC</span><span class="sxs-lookup"><span data-stu-id="ce1ae-170">Implement the gRPC service</span></span>

<span data-ttu-id="ce1ae-171">Ahora que ha declarado los mensajes y el servicio en el `portfolios.proto` archivo, debe implementar los métodos de servicio en la `PortfolioService` clase que hereda de la clase generada por gRPC `Portfolios.PortfoliosBase` .</span><span class="sxs-lookup"><span data-stu-id="ce1ae-171">Now that you've declared your messages and your service in the `portfolios.proto` file, you have to implement the service methods in the `PortfolioService` class that inherits from the gRPC-generated `Portfolios.PortfoliosBase` class.</span></span> <span data-ttu-id="ce1ae-172">Los métodos se declaran como `virtual` en la clase base.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-172">The methods are declared as `virtual` in the base class.</span></span> <span data-ttu-id="ce1ae-173">Si no los invalida, devolverán un código de estado gRPC "no implementado" de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-173">If you don't override them, they'll return a gRPC "Not Implemented" status code by default.</span></span>

<span data-ttu-id="ce1ae-174">Empiece por implementar el `Get` método.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-174">Start by implementing the `Get` method.</span></span> <span data-ttu-id="ce1ae-175">La invalidación predeterminada es similar a la de este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ce1ae-175">The default override looks like this example:</span></span>

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    return base.Get(request, context);
}
```

<span data-ttu-id="ce1ae-176">El primer problema es que `request.TraderId` es una cadena y el servicio requiere un `Guid` .</span><span class="sxs-lookup"><span data-stu-id="ce1ae-176">The first problem is that `request.TraderId` is a string, and the service requires a `Guid`.</span></span> <span data-ttu-id="ce1ae-177">Aunque el formato esperado para la cadena es `UUID` , el código tiene que tratar con la posibilidad de que un autor de llamada haya enviado un valor no válido y responda adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-177">Even though the expected format for the string is `UUID`, the code has to deal with the possibility that a caller has sent an invalid value and respond appropriately.</span></span> <span data-ttu-id="ce1ae-178">El servicio puede responder con errores iniciando `RpcException` y usando el código de `InvalidArgument` estado estándar para expresar el problema:</span><span class="sxs-lookup"><span data-stu-id="ce1ae-178">The service can respond with errors by throwing an `RpcException` and use the standard `InvalidArgument` status code to express the problem:</span></span>

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

<span data-ttu-id="ce1ae-179">Después de que haya un `Guid` valor adecuado para `traderId` , puede usar el repositorio para recuperar la cartera y devolverla al cliente:</span><span class="sxs-lookup"><span data-stu-id="ce1ae-179">After there's a proper `Guid` value for `traderId`, you can use the repository to retrieve the Portfolio and return it to the client:</span></span>

```csharp
    var response = new GetResponse
    {
        Portfolio = await _repository.GetAsync(request.TraderId, request.PortfolioId)
    };
```

### <a name="map-internal-models-to-grpc-messages"></a><span data-ttu-id="ce1ae-180">Asignación de modelos internos a mensajes gRPC</span><span class="sxs-lookup"><span data-stu-id="ce1ae-180">Map internal models to gRPC messages</span></span>

<span data-ttu-id="ce1ae-181">El código anterior no funciona realmente porque el repositorio devuelve su propio modelo POCO `Portfolio` , pero gRPC necesita su propio mensaje protobuf `Portfolio` .</span><span class="sxs-lookup"><span data-stu-id="ce1ae-181">The previous code doesn't actually work because the repository is returning its own POCO model `Portfolio`, but gRPC needs its own Protobuf message `Portfolio`.</span></span> <span data-ttu-id="ce1ae-182">Al asignar Entity Framework tipos a tipos de transferencia de datos, la mejor solución es proporcionar una conversión entre ambos.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-182">As when you map Entity Framework types to data transfer types, the best solution is to provide a conversion between the two.</span></span> <span data-ttu-id="ce1ae-183">Un buen lugar para colocar el código para esta conversión se encuentra en la clase generada por protobuf, que se declara como una `partial` clase para que se pueda extender:</span><span class="sxs-lookup"><span data-stu-id="ce1ae-183">A good place to put the code for this conversion is in the Protobuf-generated class, which is declared as a `partial` class so it can be extended:</span></span>

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
> <span data-ttu-id="ce1ae-184">Puede usar una biblioteca como [automapper](https://automapper.org/) para controlar esta conversión de clases de modelo internas a tipos protobuf, siempre que configure las conversiones de tipo de nivel inferior como `string` / `Guid` o `decimal` / `double` y la asignación de lista.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-184">You could use a library like [AutoMapper](https://automapper.org/) to handle this conversion from internal model classes to Protobuf types, as long as you configure the lower-level type conversions like `string`/`Guid` or `decimal`/`double` and the list mapping.</span></span>

<span data-ttu-id="ce1ae-185">Ahora que tiene el código de conversión en su lugar, puede completar la `Get` implementación del método:</span><span class="sxs-lookup"><span data-stu-id="ce1ae-185">Now that you have the conversion code in place, you can complete the `Get` method implementation:</span></span>

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

<span data-ttu-id="ce1ae-186">La implementación del `GetAll` método es similar.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-186">The implementation of the `GetAll` method is similar.</span></span> <span data-ttu-id="ce1ae-187">Tenga en cuenta que los `repeated` campos de los mensajes protobuf se generan como `readonly` propiedades de tipo `RepeatedField<T>` , por lo que tiene que agregar elementos a ellos mediante el `AddRange` método, como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ce1ae-187">Note that the `repeated` fields on Protobuf messages are generated as `readonly` properties of type `RepeatedField<T>`, so you have to add items to them by using the `AddRange` method, like in this example:</span></span>

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

<span data-ttu-id="ce1ae-188">Después de migrar correctamente el servicio de solicitud-respuesta de WCF a gRPC, echemos un vistazo a la creación de un cliente para él desde el `.proto` archivo.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-188">Having successfully migrated the WCF request-reply service to gRPC, let's look at creating a client for it from the `.proto` file.</span></span>

## <a name="generate-client-code"></a><span data-ttu-id="ce1ae-189">Generar código de cliente</span><span class="sxs-lookup"><span data-stu-id="ce1ae-189">Generate client code</span></span>

<span data-ttu-id="ce1ae-190">Cree una biblioteca de clases de .NET Standard en la misma solución que contenga el cliente.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-190">Create a .NET Standard class library in the same solution to contain the client.</span></span> <span data-ttu-id="ce1ae-191">Este es principalmente un ejemplo de la creación de código de cliente, pero podría empaquetar dicha biblioteca mediante el uso de NuGet y distribuirlo en un repositorio interno para que otros equipos de .NET lo consuman.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-191">This is primarily an example of creating client code, but you could package such a library by using NuGet and distribute it on an internal repository for other .NET teams to consume.</span></span> <span data-ttu-id="ce1ae-192">Continúe y agregue una nueva biblioteca de clases de .NET Standard denominada `TraderSys.Portfolios.Client` a la solución y elimine el `Class1.cs` archivo.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-192">Go ahead and add a new .NET Standard class library called `TraderSys.Portfolios.Client` to the solution and delete the `Class1.cs` file.</span></span>

> [!CAUTION]
> <span data-ttu-id="ce1ae-193">El paquete NuGet de [GRPC .net. Client](https://www.nuget.org/packages/Grpc.Net.Client) requiere .net Core 3,0 (u otro tiempo de ejecución compatible con .net Standard 2,1).</span><span class="sxs-lookup"><span data-stu-id="ce1ae-193">The [Grpc.Net.Client](https://www.nuget.org/packages/Grpc.Net.Client) NuGet package requires .NET Core 3.0 (or another .NET Standard 2.1-compliant runtime).</span></span> <span data-ttu-id="ce1ae-194">Las versiones anteriores de .NET Framework y .NET Core son compatibles con el paquete NuGet [GRPC. Core](https://www.nuget.org/packages/Grpc.Core) .</span><span class="sxs-lookup"><span data-stu-id="ce1ae-194">Earlier versions of .NET Framework and .NET Core are supported by the [Grpc.Core](https://www.nuget.org/packages/Grpc.Core) NuGet package.</span></span>

<span data-ttu-id="ce1ae-195">En Visual Studio 2019, puede Agregar referencias a los servicios de gRPC de una manera similar a como se haría con la adición de referencias de servicio a proyectos de WCF en versiones anteriores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-195">In Visual Studio 2019, you can add references to gRPC services in a way that's similar to how you'd add service references to WCF projects in earlier versions of Visual Studio.</span></span> <span data-ttu-id="ce1ae-196">Las referencias de servicio y los servicios conectados se administran ahora en la misma interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-196">Service references and connected services are all managed under the same UI now.</span></span> <span data-ttu-id="ce1ae-197">Para acceder a la interfaz de usuario, haga clic con el botón secundario en el nodo **dependencias** del `TraderSys.Portfolios.Client` proyecto en explorador de soluciones y seleccione **Agregar servicio conectado**.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-197">You can access the UI by right-clicking the **Dependencies** node in the `TraderSys.Portfolios.Client` project in Solution Explorer and selecting **Add Connected Service**.</span></span> <span data-ttu-id="ce1ae-198">En la ventana de herramientas que aparece, seleccione la sección **referencias de servicio** y, a continuación, seleccione **Agregar nueva referencia de servicio de gRPC**:</span><span class="sxs-lookup"><span data-stu-id="ce1ae-198">In the tool window that appears, select the **Service References** section and then select **Add new gRPC service reference**:</span></span>

![Servicios conectados interfaz de usuario en Visual Studio 2019](media/migrate-request-reply/add-connected-service.png)

<span data-ttu-id="ce1ae-200">Busque el `portfolios.proto` archivo en el `TraderSys.Portfolios` proyecto, deje **cliente** en **Seleccione el tipo de clase que se va a generar** y, a continuación, seleccione **Aceptar**:</span><span class="sxs-lookup"><span data-stu-id="ce1ae-200">Browse to the `portfolios.proto` file in the `TraderSys.Portfolios` project, leave **Client** under **Select the type of class to be generated**, and then select **OK**:</span></span>

![Cuadro de diálogo Agregar nueva referencia de servicio de gRPC en Visual Studio 2019](media/migrate-request-reply/add-new-grpc-service-reference.png)

> [!TIP]
> <span data-ttu-id="ce1ae-202">Tenga en cuenta que este cuadro de diálogo también proporciona un campo de dirección URL.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-202">Notice that this dialog box also provides a URL field.</span></span> <span data-ttu-id="ce1ae-203">Si su organización mantiene un directorio de archivos accesible desde web `.proto` , puede crear clientes simplemente estableciendo esta dirección URL.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-203">If your organization maintains a web-accessible directory of `.proto` files, you can create clients just by setting this URL address.</span></span>

<span data-ttu-id="ce1ae-204">Cuando se usa la característica **Agregar servicio conectado** de Visual Studio, el `portfolios.proto` archivo se agrega al proyecto de biblioteca de clases como un *archivo vinculado* , en lugar de copiarse, por lo que los cambios en el archivo del proyecto de servicio se aplicarán automáticamente en el proyecto de cliente.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-204">When you use the Visual Studio **Add Connected Service** feature, the `portfolios.proto` file is added to the class library project as a *linked file* rather than copied, so changes to the file in the service project will automatically be applied in the client project.</span></span> <span data-ttu-id="ce1ae-205">El `<Protobuf>` elemento del `csproj` archivo tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="ce1ae-205">The `<Protobuf>` element in the `csproj` file looks like this:</span></span>

```xml
<Protobuf Include="..\TraderSys.Portfolios\Protos\portfolios.proto" GrpcServices="Client">
  <Link>Protos\portfolios.proto</Link>
</Protobuf>
```

> [!TIP]
> <span data-ttu-id="ce1ae-206">Si no está usando Visual Studio o prefiere trabajar desde la línea de comandos, puede usar la `dotnet-grpc` herramienta global para administrar las referencias de protobuf en un proyecto de gRPC de .net.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-206">If you're not using Visual Studio or prefer to work from the command line, you can use the `dotnet-grpc` global tool to manage Protobuf references in a .NET gRPC project.</span></span> <span data-ttu-id="ce1ae-207">Para obtener más información, consulte la [ `dotnet-grpc` documentación](/aspnet/core/grpc/dotnet-grpc)de.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-207">For more information, see the [`dotnet-grpc` documentation](/aspnet/core/grpc/dotnet-grpc).</span></span>

### <a name="use-the-portfolios-service-from-a-client-application"></a><span data-ttu-id="ce1ae-208">Usar el servicio de carteras desde una aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="ce1ae-208">Use the Portfolios service from a client application</span></span>

<span data-ttu-id="ce1ae-209">El código siguiente es un breve ejemplo de cómo usar el cliente generado en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-209">The following code is a brief example of how to use the generated client in a console application.</span></span> <span data-ttu-id="ce1ae-210">Al final de este capítulo, se describe con más detalle la exploración del código de cliente de gRPC.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-210">A more detailed exploration of the gRPC client code is at the end of this chapter.</span></span>

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

<span data-ttu-id="ce1ae-211">Ahora ha migrado una aplicación WCF básica a un ASP.NET Core servicio gRPC y ha creado un cliente para consumir el servicio desde una aplicación .NET.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-211">You've now migrated a basic WCF application to an ASP.NET Core gRPC service and created a client to consume the service from a .NET application.</span></span> <span data-ttu-id="ce1ae-212">En la siguiente sección se tratarán los servicios dúplex más implicados.</span><span class="sxs-lookup"><span data-stu-id="ce1ae-212">The next section will cover the more involved duplex services.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ce1ae-213">[Anterior](create-project.md)
>[Siguiente](migrate-duplex-services.md)</span><span class="sxs-lookup"><span data-stu-id="ce1ae-213">[Previous](create-project.md)
[Next](migrate-duplex-services.md)</span></span>
