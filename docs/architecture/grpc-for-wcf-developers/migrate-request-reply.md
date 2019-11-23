---
title: Migrar un servicio de solicitud-respuesta de WCF a gRPC-gRPC para desarrolladores de WCF
description: Obtenga información sobre cómo migrar un servicio de solicitud-respuesta simple de WCF a gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: f0b20e7b374438f90d83aebc6035a4e4dd94ae18
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971782"
---
# <a name="migrate-a-wcf-request-reply-service-to-a-grpc-unary-rpc"></a><span data-ttu-id="0d23d-103">Migrar un servicio de solicitud-respuesta de WCF a una RPC unaria de gRPC</span><span class="sxs-lookup"><span data-stu-id="0d23d-103">Migrate a WCF request-reply service to a gRPC unary RPC</span></span>

<span data-ttu-id="0d23d-104">En esta sección se explica cómo migrar un servicio básico de solicitud-respuesta en WCF a un servicio RPC unario en ASP.NET Core gRPC.</span><span class="sxs-lookup"><span data-stu-id="0d23d-104">This section covers how to migrate a basic request-reply service in WCF to a unary RPC service in ASP.NET Core gRPC.</span></span> <span data-ttu-id="0d23d-105">Estos servicios son los tipos de servicio más sencillos en Windows Communication Foundation (WCF) y gRPC, por lo que es un lugar excelente para comenzar.</span><span class="sxs-lookup"><span data-stu-id="0d23d-105">These services are the simplest service types in both Windows Communication Foundation (WCF) and gRPC, so it's an excellent place to start.</span></span> <span data-ttu-id="0d23d-106">Después de migrar el servicio, aprenderá a generar una biblioteca de cliente desde el mismo `.proto` archivo para consumir el servicio desde una aplicación cliente de .NET.</span><span class="sxs-lookup"><span data-stu-id="0d23d-106">After migrating the service, you'll learn how to generate a client library from the same `.proto` file to consume the service from a .NET client application.</span></span>

## <a name="the-wcf-solution"></a><span data-ttu-id="0d23d-107">La solución WCF</span><span class="sxs-lookup"><span data-stu-id="0d23d-107">The WCF solution</span></span>

<span data-ttu-id="0d23d-108">La [solución PortfoliosSample](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) incluye un servicio de cartera de solicitud-respuesta simple para descargar una sola cartera o todas las carteras de un comerciante determinado.</span><span class="sxs-lookup"><span data-stu-id="0d23d-108">The [PortfoliosSample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) includes a simple Request-Reply Portfolio service to download a single portfolio, or all portfolios for a given Trader.</span></span> <span data-ttu-id="0d23d-109">El servicio se define en la interfaz `IPortfolioService` con un atributo de `ServiceContract`:</span><span class="sxs-lookup"><span data-stu-id="0d23d-109">The service is defined in the interface `IPortfolioService` with a `ServiceContract` attribute:</span></span>

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

<span data-ttu-id="0d23d-110">El modelo de `Portfolio` es una C# clase simple marcada con [DataContract](xref:System.Runtime.Serialization.DataContractAttribute), incluida una lista de objetos `PortfolioItem`.</span><span class="sxs-lookup"><span data-stu-id="0d23d-110">The `Portfolio` model is a simple C# class marked with [DataContract](xref:System.Runtime.Serialization.DataContractAttribute), including a list of `PortfolioItem` objects.</span></span> <span data-ttu-id="0d23d-111">Estos modelos se definen en el proyecto de `TraderSys.PortfolioData`, junto con una clase de repositorio que representa una abstracción de acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="0d23d-111">These models are defined in the `TraderSys.PortfolioData` project, along with a repository class representing a data access abstraction.</span></span>

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

<span data-ttu-id="0d23d-112">La implementación de `ServiceContract` usa una clase de repositorio proporcionada a través de la inserción de dependencias que devuelve instancias de los tipos de `DataContract`.</span><span class="sxs-lookup"><span data-stu-id="0d23d-112">The `ServiceContract` implementation uses a repository class provided via dependency injection that returns instances of the `DataContract` types.</span></span>

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

## <a name="the-portfoliosproto-file"></a><span data-ttu-id="0d23d-113">El archivo portfolios. proto</span><span class="sxs-lookup"><span data-stu-id="0d23d-113">The portfolios.proto file</span></span>

<span data-ttu-id="0d23d-114">Si ha seguido las instrucciones de la sección anterior, debe tener un proyecto de gRPC con un archivo `portfolios.proto` que tenga el siguiente aspecto.</span><span class="sxs-lookup"><span data-stu-id="0d23d-114">If you followed the instructions in the previous section, you should have a gRPC project with a `portfolios.proto` file that looks like this.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

<span data-ttu-id="0d23d-115">El primer paso es migrar las clases de `DataContract` a sus equivalentes de protobuf.</span><span class="sxs-lookup"><span data-stu-id="0d23d-115">The first step is to migrate the `DataContract` classes to their Protobuf equivalents.</span></span>

## <a name="convert-the-datacontracts-to-grpc-messages"></a><span data-ttu-id="0d23d-116">Convertir los DataContract en mensajes gRPC</span><span class="sxs-lookup"><span data-stu-id="0d23d-116">Convert the DataContracts to gRPC messages</span></span>

<span data-ttu-id="0d23d-117">La clase `PortfolioItem` se convertirá primero en un mensaje protobuf, ya que la clase `Portfolio` depende de él.</span><span class="sxs-lookup"><span data-stu-id="0d23d-117">The `PortfolioItem` class will be converted to a Protobuf message first, as the `Portfolio` class depends on it.</span></span> <span data-ttu-id="0d23d-118">La clase es muy sencilla y tres de las propiedades se asignan directamente a los tipos de datos gRPC.</span><span class="sxs-lookup"><span data-stu-id="0d23d-118">The class is very simple, and three of the properties map directly to gRPC data types.</span></span> <span data-ttu-id="0d23d-119">La propiedad `Cost`, que representa el precio pagado por los recursos compartidos en compra, es un campo `decimal` y gRPC solo admite `float` o `double` para los números reales, que no son adecuados para la moneda.</span><span class="sxs-lookup"><span data-stu-id="0d23d-119">The `Cost` property, representing the price paid for the shares at purchase, is a `decimal` field, and gRPC only supports `float` or `double` for real numbers, which aren't suitable for currency.</span></span> <span data-ttu-id="0d23d-120">Dado que los precios de los recursos compartidos varían en un mínimo de un cien, el costo puede expresarse como un `int32` de céntimos.</span><span class="sxs-lookup"><span data-stu-id="0d23d-120">Since share prices vary by a minimum of one cent, the cost can be expressed as an `int32` of cents.</span></span>

> [!NOTE]
> <span data-ttu-id="0d23d-121">Recuerde usar `camelCase` para los nombres de campo en el archivo de `.proto`; el C# generador de código los convertirá en `PascalCase` automáticamente y los usuarios de otros idiomas le agradecerán que respete sus diferentes estándares de codificación.</span><span class="sxs-lookup"><span data-stu-id="0d23d-121">Remember to use `camelCase` for field names in your `.proto` file; the C# code generator will convert them to `PascalCase` for you, and users of other languages will thank you for respecting their different coding standards.</span></span>

```protobuf
message PortfolioItem {
    int32 id = 1;
    int32 share_id = 2;
    int32 holding = 3;
    int32 cost_cents = 4;
}
```

<span data-ttu-id="0d23d-122">La clase `Portfolio` es un poco más complicada.</span><span class="sxs-lookup"><span data-stu-id="0d23d-122">The `Portfolio` class is a little more complicated.</span></span> <span data-ttu-id="0d23d-123">En el código WCF, el desarrollador usaba un `Guid` para la propiedad `TraderId` y contiene un `List<PortfolioItem>`.</span><span class="sxs-lookup"><span data-stu-id="0d23d-123">In the WCF code, the developer used a `Guid` for the `TraderId` property, and contains a `List<PortfolioItem>`.</span></span> <span data-ttu-id="0d23d-124">En protobuf, que no tiene un tipo de `UUID` de primera clase, debe utilizar un `string` para el campo de `traderId` y analizarlo en su propio código.</span><span class="sxs-lookup"><span data-stu-id="0d23d-124">In Protobuf, which doesn't have a first-class `UUID` type, you should use a `string` for the `traderId` field and parse it in your own code.</span></span> <span data-ttu-id="0d23d-125">Para la lista de elementos, utilice la palabra clave `repeated` en el campo.</span><span class="sxs-lookup"><span data-stu-id="0d23d-125">For the list of items, use the `repeated` keyword on the field.</span></span>

```protobuf
message Portfolio {
    int32 id = 1;
    string trader_id = 2;
    repeated PortfolioItem items = 3;
}
```

<span data-ttu-id="0d23d-126">Ahora tenemos nuestros mensajes de datos, podemos declarar los extremos de RPC del servicio.</span><span class="sxs-lookup"><span data-stu-id="0d23d-126">Now we have our data messages, we can declare the service RPC endpoints.</span></span>

## <a name="convert-the-servicecontract-to-a-grpc-service"></a><span data-ttu-id="0d23d-127">Convertir ServiceContract en un servicio gRPC</span><span class="sxs-lookup"><span data-stu-id="0d23d-127">Convert the ServiceContract to a gRPC service</span></span>

<span data-ttu-id="0d23d-128">El método `Get` de WCF toma dos parámetros: `Guid traderId` y `int portfolioId`.</span><span class="sxs-lookup"><span data-stu-id="0d23d-128">The WCF `Get` method takes two parameters: `Guid traderId` and `int portfolioId`.</span></span> <span data-ttu-id="0d23d-129">los métodos de servicio de gRPC solo pueden tomar un parámetro único, por lo que se debe crear un mensaje que contenga los dos valores.</span><span class="sxs-lookup"><span data-stu-id="0d23d-129">gRPC service methods can only take a single parameter, so a message must be created to hold the two values.</span></span> <span data-ttu-id="0d23d-130">Es habitual asignar un nombre a estos objetos de solicitud con el mismo nombre que el método y el sufijo `Request`.</span><span class="sxs-lookup"><span data-stu-id="0d23d-130">It's common practice to name these request objects with the same name as the method and the suffix `Request`.</span></span> <span data-ttu-id="0d23d-131">De nuevo, `string` se usa para el campo `traderId` en lugar de `Guid`.</span><span class="sxs-lookup"><span data-stu-id="0d23d-131">Again, `string` is being used for the `traderId` field instead of `Guid`.</span></span>

<span data-ttu-id="0d23d-132">El servicio podría devolver solo un mensaje de `Portfolio` directamente, pero de nuevo, esto podría afectar a la compatibilidad con versiones anteriores en el futuro.</span><span class="sxs-lookup"><span data-stu-id="0d23d-132">The service could just return a `Portfolio` message directly, but again, this could impact backward compatibility in the future.</span></span> <span data-ttu-id="0d23d-133">Se recomienda definir `Request` y mensajes de `Response` independientes para cada método de un servicio, incluso si muchos de ellos son los mismos en este momento, por lo que debe declarar un mensaje de `GetResponse` con un solo `Portfolio` campo.</span><span class="sxs-lookup"><span data-stu-id="0d23d-133">It's a good practice to define separate `Request` and `Response` messages for every method in a service, even if many of them are the same right now, so declare a `GetResponse` message with a single `Portfolio` field.</span></span>

<span data-ttu-id="0d23d-134">En el ejemplo siguiente se muestra la declaración del método de servicio gRPC mediante el mensaje `GetRequest`:</span><span class="sxs-lookup"><span data-stu-id="0d23d-134">The following example shows the declaration of the gRPC service method using the `GetRequest` message:</span></span>

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

<span data-ttu-id="0d23d-135">El método `GetAll` de WCF solo toma un parámetro, `traderId`, por lo que podría parecer que uno podría especificar `string` como el tipo de parámetro, pero gRPC requiere un tipo de mensaje definido.</span><span class="sxs-lookup"><span data-stu-id="0d23d-135">The WCF `GetAll` method only takes a single parameter, `traderId`, so it might seem that one could specify `string` as the parameter type, but gRPC requires a defined message type.</span></span> <span data-ttu-id="0d23d-136">Este requisito ayuda a exigir la práctica del uso de mensajes personalizados para todas las entradas y salidas, para mantener la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="0d23d-136">This requirement helps to enforce the practice of using custom messages for all inputs and outputs, for future backward compatibility.</span></span>

<span data-ttu-id="0d23d-137">El método WCF también devolvió un `List<Portfolio>`, pero por la misma razón no permite tipos de parámetros simples, gRPC no permitirá `repeated Portfolio` como un tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="0d23d-137">The WCF method also returned a `List<Portfolio>`, but for the same reason it doesn't allow simple parameter types, gRPC won't allow `repeated Portfolio` as a return type.</span></span> <span data-ttu-id="0d23d-138">En su lugar, cree un tipo de `GetAllResponse` para encapsular la lista.</span><span class="sxs-lookup"><span data-stu-id="0d23d-138">Instead, create a `GetAllResponse` type to wrap the list.</span></span>

> [!WARNING]
> <span data-ttu-id="0d23d-139">Es posible que se sienta tentado a crear un mensaje de `PortfolioList` o similar y usarlo en varios métodos de servicio, pero debe resistir esta tentación.</span><span class="sxs-lookup"><span data-stu-id="0d23d-139">You may be tempted to create a `PortfolioList` message or similar and use it across multiple service methods, but you should resist this temptation.</span></span> <span data-ttu-id="0d23d-140">No es posible saber cómo pueden evolucionar los distintos métodos de un servicio en el futuro, así que mantenga sus mensajes específicos y separados de forma limpia.</span><span class="sxs-lookup"><span data-stu-id="0d23d-140">It's impossible to know how the various methods on a service may evolve in the future, so keep their messages specific and cleanly separated.</span></span>

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

<span data-ttu-id="0d23d-141">Si guarda el proyecto con estos cambios, el destino de compilación gRPC se ejecutará en segundo plano y generará todos los tipos de mensaje protobuf y una clase base que se puede heredar para implementar el servicio.</span><span class="sxs-lookup"><span data-stu-id="0d23d-141">If you save your project with these changes, the gRPC build target will run in the background and generate all the Protobuf message types and a base class you can inherit to implement the service.</span></span>

<span data-ttu-id="0d23d-142">Abra la clase `Services/GreeterService.cs` y elimine el código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0d23d-142">Open up the `Services/GreeterService.cs` class and delete the example code.</span></span> <span data-ttu-id="0d23d-143">Ahora puede Agregar la implementación del servicio de cartera.</span><span class="sxs-lookup"><span data-stu-id="0d23d-143">Now you can add the Portfolio service implementation.</span></span> <span data-ttu-id="0d23d-144">La clase base generada estará en el espacio de nombres `Protos` y se genera como una clase anidada.</span><span class="sxs-lookup"><span data-stu-id="0d23d-144">The generated base class will be in the `Protos` namespace and is generated as a nested class.</span></span> <span data-ttu-id="0d23d-145">gRPC crea una clase estática con el mismo nombre que el servicio en el archivo `.proto` y, a continuación, una clase base con el sufijo `Base` dentro de esa clase estática, por lo que se `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`el identificador completo para el tipo base.</span><span class="sxs-lookup"><span data-stu-id="0d23d-145">gRPC creates a static class with the same name as the service in the `.proto` file, and then a base class with the suffix `Base` inside that static class, so the full identifier for the base type is `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`.</span></span>

```csharp
namespace TraderSys.Portfolios.Services
{
    public class PortfolioService : Protos.Portfolios.PortfoliosBase
    {
    }
}
```

<span data-ttu-id="0d23d-146">La clase base declara métodos `virtual` para `Get` y `GetAll` que se pueden invalidar para implementar el servicio.</span><span class="sxs-lookup"><span data-stu-id="0d23d-146">The base class declares `virtual` methods for `Get` and `GetAll` that can be overridden to implement the service.</span></span> <span data-ttu-id="0d23d-147">Los métodos son `virtual` en lugar de `abstract` para que, si no los implemente, el servicio pueda devolver un código de estado de gRPC explícito `Unimplemented`, de forma muy similar a C# como podría iniciar una `NotImplementedException` en código normal.</span><span class="sxs-lookup"><span data-stu-id="0d23d-147">The methods are `virtual` rather than `abstract` so that if you don't implement them, the service can return an explicit gRPC `Unimplemented` status code, much like you might throw a `NotImplementedException` in regular C# code.</span></span>

<span data-ttu-id="0d23d-148">La firma para todos los métodos de servicio unario gRPC en ASP.NET Core es coherente.</span><span class="sxs-lookup"><span data-stu-id="0d23d-148">The signature for all gRPC unary service methods in ASP.NET Core is consistent.</span></span> <span data-ttu-id="0d23d-149">Hay dos parámetros: el primero es el tipo de mensaje declarado en el archivo `.proto` y el segundo es un `ServerCallContext` que funciona de forma similar a la `HttpContext` de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="0d23d-149">There are two parameters: the first is the message type declared in the `.proto` file, and the second is a `ServerCallContext` that works similarly to the `HttpContext` from ASP.NET Core.</span></span> <span data-ttu-id="0d23d-150">De hecho, hay un método de extensión denominado `GetHttpContext` en la clase `ServerCallContext` que se puede usar para obtener el `HttpContext`subyacente, aunque no es necesario usarlo a menudo.</span><span class="sxs-lookup"><span data-stu-id="0d23d-150">In fact, there's an extension method called `GetHttpContext` on the `ServerCallContext` class that you can use to get the underlying `HttpContext`, although you shouldn't need to use it often.</span></span> <span data-ttu-id="0d23d-151">Echemos un vistazo a `ServerCallContext` más adelante en este capítulo y también en el capítulo en el que se describe la autenticación.</span><span class="sxs-lookup"><span data-stu-id="0d23d-151">We'll take a look at `ServerCallContext` later in this chapter, and also in the chapter that discusses authentication.</span></span>

<span data-ttu-id="0d23d-152">El tipo de valor devuelto del método es una `Task<T>` donde `T` es el tipo de mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="0d23d-152">The method's return type is a `Task<T>` where `T` is the response message type.</span></span> <span data-ttu-id="0d23d-153">Todos los métodos de servicio de gRPC son asíncronos.</span><span class="sxs-lookup"><span data-stu-id="0d23d-153">All gRPC service methods are asynchronous.</span></span>

## <a name="migrate-the-portfoliodata-library-to-net-core"></a><span data-ttu-id="0d23d-154">Migración de la biblioteca de PortfolioData a .NET Core</span><span class="sxs-lookup"><span data-stu-id="0d23d-154">Migrate the PortfolioData library to .NET Core</span></span>

<span data-ttu-id="0d23d-155">En este momento, el proyecto necesita el repositorio y los modelos de cartera incluidos en la biblioteca de clases de `TraderSys.PortfolioData` en la solución WCF.</span><span class="sxs-lookup"><span data-stu-id="0d23d-155">At this point, the project needs the Portfolio repository and models contained in the `TraderSys.PortfolioData` class library in the WCF solution.</span></span> <span data-ttu-id="0d23d-156">La forma más fácil de llevarlos a cabo es crear una nueva biblioteca de clases mediante el cuadro de diálogo **nuevo proyecto** de Visual Studio con la plantilla *biblioteca de clases (.net Standard)* o desde la línea de comandos mediante el CLI de .net Core, ejecutando los siguientes comandos desde el directorio que contiene el archivo `TraderSys.sln`.</span><span class="sxs-lookup"><span data-stu-id="0d23d-156">The easiest way to bring them across is to create a new class library using either the Visual Studio **New project** dialog with the *Class Library (.NET Standard)* template, or from the command line using the .NET Core CLI, running the following commands from the directory containing the `TraderSys.sln` file.</span></span>

```dotnetcli
dotnet new classlib -o src/TraderSys.PortfolioData
dotnet sln add src/TraderSys.PortfolioData
```

<span data-ttu-id="0d23d-157">Una vez que la biblioteca se haya creado y agregado a la solución, elimine el archivo de `Class1.cs` generado y copie los archivos de la biblioteca de la solución WCF en la carpeta de la nueva biblioteca de clases, manteniendo la estructura de carpetas.</span><span class="sxs-lookup"><span data-stu-id="0d23d-157">Once the library has been created and added to the solution, delete the generated `Class1.cs` file and copy the files from the WCF solution's library into the new class library's folder, keeping the folder structure.</span></span>

```
Models
  Portfolio.cs
  PortfolioItem.cs
IPortfolioRepository.cs
PortfolioRepository.cs
```

<span data-ttu-id="0d23d-158">Los proyectos de .NET de estilo SDK incluyen automáticamente los archivos `.cs` en su propio directorio, por lo que no es necesario agregarlos explícitamente al proyecto.</span><span class="sxs-lookup"><span data-stu-id="0d23d-158">SDK-style .NET projects automatically include any `.cs` files in or under their own directory, so there's no need to explicitly add them to the project.</span></span> <span data-ttu-id="0d23d-159">El único paso que queda es quitar los atributos `DataContract` y `DataMember` de las clases `Portfolio` y `PortfolioItem` para que sean clases antiguas C# sin formato.</span><span class="sxs-lookup"><span data-stu-id="0d23d-159">The only step remaining is to remove the `DataContract` and `DataMember` attributes from the `Portfolio` and `PortfolioItem` classes so they're plain old C# classes.</span></span>

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

## <a name="use-aspnet-core-dependency-injection"></a><span data-ttu-id="0d23d-160">Usar la inserción de dependencias ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0d23d-160">Use ASP.NET Core dependency injection</span></span>

<span data-ttu-id="0d23d-161">Ahora puede Agregar una referencia a esta biblioteca al proyecto de aplicación gRPC y consumir la clase `PortfolioRepository` mediante la inserción de dependencias en la implementación del servicio gRPC.</span><span class="sxs-lookup"><span data-stu-id="0d23d-161">Now you can add a reference to this library to the gRPC application project and consume the `PortfolioRepository` class using dependency injection in the gRPC service implementation.</span></span> <span data-ttu-id="0d23d-162">En la aplicación WCF, el contenedor de IoC Autofac proporcionó la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="0d23d-162">In the WCF application, dependency injection was provided by the Autofac IoC container.</span></span> <span data-ttu-id="0d23d-163">ASP.NET Core tiene incrustada la inserción de dependencias; el repositorio se puede registrar en el método `ConfigureServices` de la clase `Startup`.</span><span class="sxs-lookup"><span data-stu-id="0d23d-163">ASP.NET Core has dependency injection baked in; the repository can be registered in the `ConfigureServices` method in the `Startup` class.</span></span>

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

<span data-ttu-id="0d23d-164">La implementación de `IPortfolioRepository` ahora se puede especificar como un parámetro de constructor en la clase `PortfolioService`, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="0d23d-164">The `IPortfolioRepository` implementation can now be specified as a constructor parameter in the `PortfolioService` class, as follows:</span></span>

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

## <a name="implement-the-grpc-service"></a><span data-ttu-id="0d23d-165">Implementar el servicio gRPC</span><span class="sxs-lookup"><span data-stu-id="0d23d-165">Implement the gRPC service</span></span>

<span data-ttu-id="0d23d-166">Ahora que ha declarado los mensajes y el servicio en el archivo `portfolios.proto`, tiene que implementar los métodos de servicio en la clase `PortfolioService` que hereda de la clase `Portfolios.PortfoliosBase` generada por gRPC.</span><span class="sxs-lookup"><span data-stu-id="0d23d-166">Now that you've declared your messages and your service in the `portfolios.proto` file, you have to implement the service methods in the `PortfolioService` class that inherits from the gRPC-generated `Portfolios.PortfoliosBase` class.</span></span> <span data-ttu-id="0d23d-167">Los métodos se declaran como `virtual` en la clase base.</span><span class="sxs-lookup"><span data-stu-id="0d23d-167">The methods are declared as `virtual` in the base class.</span></span> <span data-ttu-id="0d23d-168">Si no los invalida, devolverán un código de estado gRPC "no implementado" de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0d23d-168">If you don't override them, they'll return a gRPC "Not Implemented" status code by default.</span></span>

<span data-ttu-id="0d23d-169">Empiece por implementar el método `Get`.</span><span class="sxs-lookup"><span data-stu-id="0d23d-169">Start by implementing the `Get` method.</span></span> <span data-ttu-id="0d23d-170">La invalidación predeterminada es similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d23d-170">The default override looks like the following example:</span></span>

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    return base.Get(request, context);
}
```

<span data-ttu-id="0d23d-171">El primer problema es que `request.TraderId` es una cadena y el servicio requiere un `Guid`.</span><span class="sxs-lookup"><span data-stu-id="0d23d-171">The first issue is that `request.TraderId` is a string, and the service requires a `Guid`.</span></span> <span data-ttu-id="0d23d-172">Aunque el formato esperado para la cadena es un `UUID`, el código tiene que tratar con la posibilidad de que un autor de llamada haya enviado un valor no válido y de responder adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="0d23d-172">Even though the expected format for the string is a `UUID`, the code has to deal with the possibility that a caller has sent an invalid value and respond appropriately.</span></span> <span data-ttu-id="0d23d-173">El servicio puede responder con errores iniciando una `RpcException`y usar el código de estado de `InvalidArgument` estándar para expresar el problema.</span><span class="sxs-lookup"><span data-stu-id="0d23d-173">The service can respond with errors by throwing an `RpcException`, and use the standard `InvalidArgument` status code to express the problem.</span></span>

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

<span data-ttu-id="0d23d-174">Una vez que hay un valor de `Guid` adecuado para `traderId`, el repositorio se puede usar para recuperar la cartera y devolverla al cliente.</span><span class="sxs-lookup"><span data-stu-id="0d23d-174">Once there's a proper `Guid` value for `traderId`, the repository can be used to retrieve the Portfolio and return it to the client.</span></span>

```csharp
    var response = new GetResponse
    {
        Portfolio = await _repository.GetAsync(request.TraderId, request.PortfolioId)
    };
```

### <a name="map-internal-models-to-grpc-messages"></a><span data-ttu-id="0d23d-175">Asignación de modelos internos a mensajes gRPC</span><span class="sxs-lookup"><span data-stu-id="0d23d-175">Map internal models to gRPC messages</span></span>

<span data-ttu-id="0d23d-176">El código anterior no funciona realmente porque el repositorio devuelve su propio modelo POCO `Portfolio`, pero gRPC necesita *su* propio mensaje de protobuf `Portfolio`.</span><span class="sxs-lookup"><span data-stu-id="0d23d-176">The previous code doesn't actually work because the repository is returning its own POCO model `Portfolio`, but gRPC needs *its* own Protobuf message `Portfolio`.</span></span> <span data-ttu-id="0d23d-177">De forma muy similar a la asignación de tipos de Entity Framework a tipos de transferencia de datos, la mejor solución es proporcionar una conversión entre ambos.</span><span class="sxs-lookup"><span data-stu-id="0d23d-177">Much like mapping Entity Framework types to data transfer types, the best solution is to provide conversion between the two.</span></span> <span data-ttu-id="0d23d-178">Un buen lugar para colocar el código para esto es en la clase generada por protobuf, que se declara como una clase `partial` para que se pueda extender.</span><span class="sxs-lookup"><span data-stu-id="0d23d-178">A good place to put the code for this is in the Protobuf-generated class, which is declared as a `partial` class so it can be extended.</span></span>

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
> <span data-ttu-id="0d23d-179">Puede usar una biblioteca como [automapper](https://automapper.org/) para controlar esta conversión de las clases de modelo internas a tipos protobuf, siempre y cuando configure las conversiones de tipo de nivel inferior, como `string`/`Guid` o `decimal`/`double` y la asignación de lista.</span><span class="sxs-lookup"><span data-stu-id="0d23d-179">You could use a library like [AutoMapper](https://automapper.org/) to handle this conversion from internal model classes to Protobuf types, as long as you configure the lower-level type conversions like `string`/`Guid` or `decimal`/`double` and the list mapping.</span></span>

<span data-ttu-id="0d23d-180">Con el código de conversión en su lugar, se puede completar la implementación del método `Get`.</span><span class="sxs-lookup"><span data-stu-id="0d23d-180">With the conversion code in place, the `Get` method implementation can be completed.</span></span>

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

<span data-ttu-id="0d23d-181">La implementación del método `GetAll` es similar.</span><span class="sxs-lookup"><span data-stu-id="0d23d-181">The implementation of the `GetAll` method is similar.</span></span> <span data-ttu-id="0d23d-182">Tenga en cuenta que los campos de `repeated` en los mensajes protobuf se generan como propiedades `readonly` de tipo `RepeatedField<T>`, por lo que tiene que agregar elementos a ellos mediante el método `AddRange`, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d23d-182">Note that the `repeated` fields on Protobuf messages are generated as `readonly` properties of type `RepeatedField<T>`, so you have to add items to them using the `AddRange` method, like in the following example:</span></span>

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

<span data-ttu-id="0d23d-183">Después de migrar correctamente el servicio de solicitud-respuesta de WCF a gRPC, echemos un vistazo a la creación de un cliente para él desde el archivo de `.proto`.</span><span class="sxs-lookup"><span data-stu-id="0d23d-183">Having successfully migrated the WCF request-reply service to gRPC, let's look at creating a client for it from the `.proto` file.</span></span>

## <a name="generate-client-code"></a><span data-ttu-id="0d23d-184">Generar código de cliente</span><span class="sxs-lookup"><span data-stu-id="0d23d-184">Generate client code</span></span>

<span data-ttu-id="0d23d-185">Cree una biblioteca de clases de .NET Standard en la misma solución que contenga el cliente.</span><span class="sxs-lookup"><span data-stu-id="0d23d-185">Create a .NET Standard class library in the same solution to contain the client.</span></span> <span data-ttu-id="0d23d-186">Este es principalmente un ejemplo de la creación de código de cliente, pero podría empaquetar dicha biblioteca mediante NuGet y distribuirla en un repositorio interno para que otros equipos de .NET lo consuman.</span><span class="sxs-lookup"><span data-stu-id="0d23d-186">This is primarily an example of creating client code, but you could package such a library using NuGet and distribute it on an internal repository for other .NET teams to consume.</span></span> <span data-ttu-id="0d23d-187">Continúe y agregue una nueva biblioteca de clases .NET Standard denominada `TraderSys.Portfolios.Client` a la solución y elimine el archivo `Class1.cs`.</span><span class="sxs-lookup"><span data-stu-id="0d23d-187">Go ahead and add a new .NET Standard Class Library called `TraderSys.Portfolios.Client` to the solution and delete the `Class1.cs` file.</span></span>

> [!CAUTION]
> <span data-ttu-id="0d23d-188">El paquete NuGet de [GRPC .net. Client](https://www.nuget.org/packages/Grpc.Net.Client) requiere .net Core 3,0 (u otro tiempo de ejecución compatible con .net Standard 2,1).</span><span class="sxs-lookup"><span data-stu-id="0d23d-188">The [Grpc.Net.Client](https://www.nuget.org/packages/Grpc.Net.Client) NuGet package requires .NET Core 3.0 (or another .NET Standard 2.1-compliant runtime).</span></span> <span data-ttu-id="0d23d-189">Las versiones anteriores de .NET Framework y .NET Core son compatibles con el paquete NuGet [GRPC. Core](https://www.nuget.org/packages/Grpc.Core) .</span><span class="sxs-lookup"><span data-stu-id="0d23d-189">Earlier versions of .NET Framework and .NET Core are supported by the [Grpc.Core](https://www.nuget.org/packages/Grpc.Core) NuGet package.</span></span>

<span data-ttu-id="0d23d-190">En Visual Studio 2019, puede Agregar referencias a los servicios de gRPC de forma similar a la manera en que se agregaron las referencias de servicio a los proyectos de WCF en versiones anteriores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0d23d-190">In Visual Studio 2019, you can add references to gRPC services similar to the way you'd add Service References to WCF projects in earlier versions of Visual Studio.</span></span> <span data-ttu-id="0d23d-191">Las referencias de servicio y Servicios conectados se administran ahora en la misma interfaz de usuario, a la que se puede tener acceso haciendo clic con el botón secundario en el nodo **dependencias** del proyecto `TraderSys.Portfolios.Client` en explorador de soluciones y seleccionando **Agregar servicio conectado**.</span><span class="sxs-lookup"><span data-stu-id="0d23d-191">Service References and Connected Services are all managed under the same UI now, which you can access by right-clicking the **Dependencies** node in the `TraderSys.Portfolios.Client` project in Solution Explorer and selecting **Add Connected Service**.</span></span> <span data-ttu-id="0d23d-192">En la ventana de herramientas que aparece, seleccione la sección **referencias de servicio** y haga clic en **Agregar nueva referencia de servicio de gRPC**.</span><span class="sxs-lookup"><span data-stu-id="0d23d-192">In the tool window that appears, select the **Service References** section and click **Add new gRPC service reference**.</span></span>

![La interfaz de usuario de Servicios conectados en Visual Studio 2019](media/migrate-request-reply/add-connected-service.png)

<span data-ttu-id="0d23d-194">Busque el archivo de `portfolios.proto` en el proyecto `TraderSys.Portfolios`, deje el **tipo de clase que se va a generar** como **cliente**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0d23d-194">Browse to the `portfolios.proto` file in the `TraderSys.Portfolios` project, leave the **type of class to be generated** as **Client**, and click **OK**.</span></span>

![Cuadro de diálogo Agregar nueva referencia de servicio de gRPC en Visual Studio 2019](media/migrate-request-reply/add-new-grpc-service-reference.png)

> [!TIP]
> <span data-ttu-id="0d23d-196">Tenga en cuenta que este cuadro de diálogo también proporciona un campo de dirección URL.</span><span class="sxs-lookup"><span data-stu-id="0d23d-196">Notice that this dialog also provides a URL field.</span></span> <span data-ttu-id="0d23d-197">Si su organización mantiene un directorio accesible desde web de `.proto` archivos, puede crear clientes simplemente estableciendo esta dirección URL.</span><span class="sxs-lookup"><span data-stu-id="0d23d-197">If your organization maintains a web-accessible directory of `.proto` files, you can create clients just by setting this URL address.</span></span>

<span data-ttu-id="0d23d-198">Cuando se usa la característica **Agregar servicio conectado** de Visual Studio, el archivo de `portfolios.proto` se agrega al proyecto de biblioteca de clases como un *archivo vinculado*, en lugar de copiarse, por lo que los cambios en el archivo del proyecto de servicio se aplicarán automáticamente en el proyecto de cliente.</span><span class="sxs-lookup"><span data-stu-id="0d23d-198">When using the Visual Studio **Add Connected Service** feature, the `portfolios.proto` file is added to the Class Library project as a *linked file*, rather than copied, so changes to the file in the service project will automatically be applied in the client project.</span></span> <span data-ttu-id="0d23d-199">El elemento `<Protobuf>` del archivo `csproj` tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="0d23d-199">The `<Protobuf>` element in the `csproj` file looks like this:</span></span>

```xml
<Protobuf Include="..\TraderSys.Portfolios\Protos\portfolios.proto" GrpcServices="Client">
  <Link>Protos\portfolios.proto</Link>
</Protobuf>
```

> [!TIP]
> <span data-ttu-id="0d23d-200">Si no usa Visual Studio o prefiere trabajar desde la línea de comandos, puede usar la herramienta global **dotnet-GRPC** para administrar las referencias de protobuf dentro de un proyecto de GRPC de .net.</span><span class="sxs-lookup"><span data-stu-id="0d23d-200">If you are not using Visual Studio or prefer to work from the command line, you can use the **dotnet-grpc** global tool to manage Protobuf references within a .NET gRPC project.</span></span> <span data-ttu-id="0d23d-201">[Consulte la documentación de **dotnet-GRPC** para obtener más información](https://docs.microsoft.com/aspnet/core/grpc/dotnet-grpc).</span><span class="sxs-lookup"><span data-stu-id="0d23d-201">[Refer to the **dotnet-grpc** documentation for more information](https://docs.microsoft.com/aspnet/core/grpc/dotnet-grpc).</span></span>

### <a name="use-the-portfolios-service-from-a-client-application"></a><span data-ttu-id="0d23d-202">Usar el servicio de carteras desde una aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="0d23d-202">Use the Portfolios service from a client application</span></span>

<span data-ttu-id="0d23d-203">El código siguiente es un breve ejemplo del uso del cliente generado en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="0d23d-203">The following code is a brief example of using the generated client in a console application.</span></span> <span data-ttu-id="0d23d-204">Al final de este capítulo, se describe con más detalle la exploración del código de cliente de gRPC.</span><span class="sxs-lookup"><span data-stu-id="0d23d-204">A more detailed exploration of the gRPC client code is at the end of this chapter.</span></span>

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

<span data-ttu-id="0d23d-205">Ahora, ha migrado una aplicación WCF básica a un ASP.NET Core servicio gRPC y ha creado un cliente para consumir el servicio desde una aplicación .NET.</span><span class="sxs-lookup"><span data-stu-id="0d23d-205">Now, you've migrated a basic WCF application to an ASP.NET Core gRPC service and created a client to consume the service from a .NET application.</span></span> <span data-ttu-id="0d23d-206">En la siguiente sección se tratarán los servicios de "dúplex" más implicados.</span><span class="sxs-lookup"><span data-stu-id="0d23d-206">The next section will cover the more involved "duplex" services.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0d23d-207">[Anterior](create-project.md)
>[Siguiente](migrate-duplex-services.md)</span><span class="sxs-lookup"><span data-stu-id="0d23d-207">[Previous](create-project.md)
[Next](migrate-duplex-services.md)</span></span>
