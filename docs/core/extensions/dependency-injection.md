---
title: Inserción de dependencias en .NET
description: Obtenga información sobre la manera en que .NET implementa la inserción de dependencias y cómo se usa.
author: IEvangelist
ms.author: dapine
ms.date: 10/28/2020
ms.topic: overview
ms.openlocfilehash: cc030e32846690b6544b99030800b50055a3113e
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "102402192"
---
# <a name="dependency-injection-in-net"></a>Inserción de dependencias en .NET

.NET admite el patrón de diseño de software de inserción de dependencias (DI), que es una técnica para conseguir la [inversión de control (IoC)](../../architecture/modern-web-apps-azure/architectural-principles.md#dependency-inversion) entre clases y sus dependencias. La inserción de dependencias en .NET es un [ciudadano de primera clase](https://en.wikipedia.org/wiki/First-class_citizen), junto con la configuración, el registro y el patrón de opciones.

Una *dependencia* es un objeto del que depende otro objeto. Examine la clase `MessageWriter` siguiente con un método `Write` del que dependen otras clases:

```csharp
public class MessageWriter
{
    public void Write(string message)
    {
        Console.WriteLine($"MessageWriter.Write(message: \"{message}\")");
    }
}
```

Una clase puede crear una instancia de la clase `MessageWriter` para usar su método `Write`. En el ejemplo siguiente, la clase `MessageWriter` es una dependencia de la clase `Worker`:

```csharp
public class Worker : BackgroundService
{
    private readonly MessageWriter _messageWriter = new MessageWriter();

    protected override async Task ExecuteAsync(CancellationToken stoppingToken)
    {
        while (!stoppingToken.IsCancellationRequested)
        {
            _messageWriter.Write($"Worker running at: {DateTimeOffset.Now}");
            await Task.Delay(1000, stoppingToken);
        }
    }
}
```

La clase crea y depende directamente de la clase `MessageWriter`. Las dependencias codificadas de forma rígida, como en el ejemplo anterior, son problemáticas y deben evitarse por las razones siguientes:

- Para reemplazar `MessageWriter` por una implementación diferente, se debe modificar la clase `Worker`.
- Si `MessageWriter` tiene dependencias, deben configurarse según la clase `Worker`. En un proyecto grande con varias clases que dependen de `MessageWriter`, el código de configuración se dispersa por la aplicación.
- Esta implementación es difícil para realizar pruebas unitarias. La aplicación debe usar una clase `MessageWriter` como boceto o código auxiliar, que no es posible con este enfoque.

La inserción de dependencias aborda estos problemas mediante:

- Uso de una interfaz o clase base para abstraer la implementación de dependencias.
- Registro de la dependencia en un contenedor de servicios. .NET proporciona un contenedor de servicios integrado, <xref:System.IServiceProvider>. Normalmente, los servicios se registran al iniciar la aplicación y se anexan a una interfaz <xref:Microsoft.Extensions.DependencyInjection.IServiceCollection>. Una vez que se agregan todos los servicios, se usa <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A> para crear el contenedor de servicios.
- *Inserción* del servicio en el constructor de la clase en la que se usa. El marco de trabajo asume la responsabilidad de crear una instancia de la dependencia y de desecharla cuando ya no es necesaria.

Por ejemplo, la interfaz `IMessageWriter` define el método `Write`:

:::code language="csharp" source="snippets/configuration/dependency-injection/IMessageWriter.cs":::

Esta interfaz se implementa mediante un tipo concreto, `MessageWriter`:

:::code language="csharp" source="snippets/configuration/dependency-injection/MessageWriter.cs":::

El código de ejemplo registra el servicio `IMessageWriter` con el tipo concreto `MessageWriter`. El método <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddScoped%2A> registra el servicio mediante una duración con ámbito, definida como la duración de una única solicitud. Las [duraciones del servicio](#service-lifetimes) se describen más adelante en este artículo.

:::code language="csharp" source="snippets/configuration/dependency-injection/Program.cs" highlight="16":::

En la aplicación de ejemplo, el servicio `IMessageWriter` se solicita y usa para llamar al método `Write`:

:::code language="csharp" source="snippets/configuration/dependency-injection/Worker.cs":::

Mediante el uso del patrón de DI, el servicio de trabajo:

- No usa el tipo concreto `MessageWriter`, solo la interfaz `IMessageWriter` que lo implementa. Esto facilita el cambio de la implementación que el controlador utiliza sin modificar el controlador.
- No crea una instancia de `MessageWriter`, la crea el contenedor de DI.

La implementación de la interfaz de `IMessageWriter` se puede mejorar mediante el uso de la API de registro integrada:

:::code language="csharp" source="snippets/configuration/dependency-injection/LoggingMessageWriter.cs":::

El método `ConfigureServices` actualizado registra la nueva implementación de `IMessageWriter`:

```csharp
static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureServices((_, services) =>
            services.AddHostedService<Worker>()
                    .AddScoped<IMessageWriter, LoggingMessageWriter>());
```

`LoggingMessageWriter` depende de <xref:Microsoft.Extensions.Logging.ILogger%601>, el que solicita en el constructor. `ILogger<TCategoryName>` es un [servicio proporcionado por el marco de trabajo](#framework-provided-services).

No es raro usar la inserción de dependencias de forma encadenada. Cada dependencia solicitada a su vez solicita sus propias dependencias. El contenedor resuelve las dependencias del gráfico y devuelve el servicio totalmente resuelto. El conjunto colectivo de dependencias que deben resolverse suele denominarse *árbol de dependencias*, *gráfico de dependencias* o *gráfico de objetos*.

El contenedor resuelve `ILogger<TCategoryName>` aprovechando las ventajas de los [tipos abiertos (genéricos)](/dotnet/csharp/language-reference/language-specification/types#open-and-closed-types), lo que elimina la necesidad de registrar todos los [tipos construidos (genéricos)](/dotnet/csharp/language-reference/language-specification/types#constructed-types).

En la terminología de la inserción de dependencias, un servicio:

- Por lo general, es un objeto que proporciona un servicio a otros objetos, como el servicio `IMessageWriter`.
- No está relacionado con un servicio web, aunque el servicio puede utilizar un servicio web.

El marco de trabajo proporciona un sistema de registro sólido. Las implementaciones de `IMessageWriter` que se muestran en los ejemplos anteriores se escribieron para mostrar la inserción de DI básica, no para implementar el registro. La mayoría de las aplicaciones no deberían tener que escribir registradores. En el código siguiente se muestra cómo usar el registro predeterminado, que solo requiere que `Worker` se registre en `ConfigureServices` como un servicio hospedado <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionHostedServiceExtensions.AddHostedService%2A>:

```csharp
public class Worker : BackgroundService
{
    private readonly ILogger<Worker> _logger;

    public Worker(ILogger<Worker> logger) =>
        _logger = logger;

    protected override async Task ExecuteAsync(CancellationToken stoppingToken)
    {
        while (!stoppingToken.IsCancellationRequested)
        {
            _logger.LogInformation("Worker running at: {time}", DateTimeOffset.Now);
            await Task.Delay(1000, stoppingToken);
        }
    }
}
```

Con el código anterior, no es necesario actualizar `ConfigureServices` porque el registro se proporciona a través del marco de trabajo.

## <a name="register-groups-of-services-with-extension-methods"></a>Registro de grupos de servicios con métodos de extensión

Las extensiones de Microsoft usan una convención para registrar un grupo de servicios relacionados. La convención es usar un único método de extensión de `Add{GROUP_NAME}` para registrar todos los servicios requeridos por una característica de marco. Por ejemplo, el método de extensión <xref:Microsoft.Extensions.DependencyInjection.OptionsServiceCollectionExtensions.AddOptions%2A> registra todos los servicios necesarios para usar las opciones.

## <a name="framework-provided-services"></a>Servicios proporcionados por el marco de trabajo

El método `ConfigureServices` registra los servicios que la aplicación usa, incluidas las características de plataforma. Inicialmente, el valor `IServiceCollection` proporcionado a `ConfigureServices` tiene los servicios definidos por el marco en función de [cómo se configurara el host](generic-host.md#host-configuration). En el caso de las aplicaciones basadas en las plantillas de .NET, el marco de trabajo registra cientos de servicios.

En la tabla siguiente se ilustra una pequeña muestra de estos servicios registrados por el marco:

| Tipo de servicio                                                                       | Período de duración  |
|------------------------------------------------------------------------------------|-----------|
| <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime>                       | Singleton |
| <xref:Microsoft.Extensions.Logging.ILogger%601?displayProperty=fullName>           | Singleton |
| <xref:Microsoft.Extensions.Logging.ILoggerFactory?displayProperty=fullName>        | Singleton |
| <xref:Microsoft.Extensions.ObjectPool.ObjectPoolProvider?displayProperty=fullName> | Singleton |
| <xref:Microsoft.Extensions.Options.IConfigureOptions%601?displayProperty=fullName> | Transitorio |
| <xref:Microsoft.Extensions.Options.IOptions%601?displayProperty=fullName>          | Singleton |
| <xref:System.Diagnostics.DiagnosticListener?displayProperty=fullName>              | Singleton |
| <xref:System.Diagnostics.DiagnosticSource?displayProperty=fullName>                | Singleton |

## <a name="service-lifetimes"></a>Duraciones de servicios

Los servicios se pueden registrar con una de las duraciones siguientes:

- Transitorio
- Con ámbito
- Singleton

En las secciones siguientes se describen cada una de las duraciones anteriores. Elija una duración adecuada para cada servicio registrado.

### <a name="transient"></a>Transitorio

Los servicios de duración transitoria se crean cada vez que el contenedor del servicio los solicita. Esta duración funciona mejor para servicios sin estado ligeros. Registre los servicios transitorios con <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddTransient%2A>.

En las aplicaciones que procesan solicitudes, los servicios transitorios se eliminan al final de la solicitud.

### <a name="scoped"></a>Con ámbito

En el caso de las aplicaciones web, una duración con ámbito indica que los servicios se crean una vez por solicitud de cliente (conexión). Registre los servicios con ámbito con <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddScoped%2A>.

En las aplicaciones que procesan solicitudes, los servicios con ámbito se eliminan al final de la solicitud.

Cuando se usa Entity Framework Core, el método de extensión <xref:Microsoft.Extensions.DependencyInjection.EntityFrameworkServiceCollectionExtensions.AddDbContext%2A> registra tipos de `DbContext` con una duración de ámbito de forma predeterminada.

> [!NOTE]
> **No** resuelva un servicio con ámbito desde un singleton y tenga cuidado de no hacerlo indirectamente, por ejemplo, a través de un servicio transitorio. Puede dar lugar a que el servicio adopte un estado incorrecto al procesar solicitudes posteriores. Basta con:
>
> - Resolver un servicio singleton desde un servicio con ámbito o transitorio.
> - Resolver un servicio con ámbito desde otro servicio con ámbito o transitorio.

De manera predeterminada, en el entorno de desarrollo, resolver un servicio desde otro servicio con una duración más larga genera una excepción. Para más información, vea [Validación del ámbito](#scope-validation).

### <a name="singleton"></a>Singleton

Los servicios de duración de singleton se crean de alguna de las formas siguientes:

- La primera vez que se solicitan.
- Mediante el desarrollador, al proporcionar una instancia de implementación directamente al contenedor. Este enfoque rara vez es necesario.

Cada solicitud siguiente de la implementación del servicio desde el contenedor de inserción de dependencias utiliza la misma instancia. Si la aplicación requiere un comportamiento de singleton, permita que el contenedor de servicios administre la duración del servicio. No implemente el modelo de diseño singleton y proporcione el código para desechar el singleton. Los servicios nunca deben desecharse mediante el código que haya resuelto el servicio del contenedor. Si un tipo o fábrica se registra como singleton, el contenedor elimina el singleton de manera automática.

Registre los servicios singleton con <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddSingleton%2A>. Los servicios singleton deben ser seguros para los subprocesos y se suelen usar en servicios sin estado.

En las aplicaciones que procesan solicitudes, los servicios singleton se eliminan cuando <xref:Microsoft.Extensions.DependencyInjection.ServiceProvider> se elimina al cerrarse la aplicación. Como no se libera memoria hasta que se apaga la aplicación, se debe tener en cuenta el uso de memoria con un servicio singleton.

> [!WARNING]
> _*_No_*_ resuelva un servicio con ámbito desde un singleton. Puede dar lugar a que el servicio adopte un estado incorrecto al procesar solicitudes posteriores. Basta con resolver un servicio singleton desde un servicio con ámbito o transitorio.

## <a name="service-registration-methods"></a>Métodos de registro del servicio

El marco proporciona métodos de extensión de registro del servicio que resultan útiles en escenarios específicos:

| Método | Automático<br>objeto<br>eliminación | Múltiple<br>implementaciones | Transferencia de argumentos |
|--|:-:|:-:|:-:|
| `Add{LIFETIME}<{SERVICE}, {IMPLEMENTATION}>()`<br><br>Ejemplo:<br><br>`services.AddSingleton<IMyDep, MyDep>();` | Sí | Sí | No |
| `Add{LIFETIME}<{SERVICE}>(sp => new {IMPLEMENTATION})`<br><br>Ejemplos:<br><br>`services.AddSingleton<IMyDep>(sp => new MyDep());`<br>`services.AddSingleton<IMyDep>(sp => new MyDep(99));` | Sí | Sí | Sí |
| `Add{LIFETIME}<{IMPLEMENTATION}>()`<br><br>Ejemplo:<br><br>`services.AddSingleton<MyDep>();` | Sí | No | No |
| `AddSingleton<{SERVICE}>(new {IMPLEMENTATION})`<br><br>Ejemplos:<br><br>`services.AddSingleton<IMyDep>(new MyDep());`<br>`services.AddSingleton<IMyDep>(new MyDep(99));` | No | Sí | Sí |
| `AddSingleton(new {IMPLEMENTATION})`<br><br>Ejemplos:<br><br>`services.AddSingleton(new MyDep());`<br>`services.AddSingleton(new MyDep(99));` | No | No | Sí |

Para obtener más información sobre el tipo de eliminación, consulte la sección [Eliminación de servicios](dependency-injection-guidelines.md#disposal-of-services).

El registro de un servicio con un solo tipo de implementación es equivalente al registro de ese servicio con la misma implementación y el mismo tipo de servicio. Por eso no se pueden registrar varias implementaciones de un servicio mediante los métodos que no toman un tipo de servicio explícito. Estos métodos pueden registrar varias instancias de un servicio, pero todos tienen el mismo tipo de *implementación*.

Cualquiera de los métodos de registro de servicio anteriores se puede usar para registrar varias instancias de servicio del mismo tipo de servicio. En el ejemplo siguiente se llama a `AddSingleton` dos veces con `IMessageWriter` como tipo de servicio. La segunda llamada a `AddSingleton` invalida la anterior cuando se resuelve como `IMessageWriter`, y se agrega a la anterior cuando varios servicios se resuelven mediante `IEnumerable<IMessageWriter>`. Los servicios aparecen en el orden en que se han registrado al resolverse mediante `IEnumerable<{SERVICE}>`.

:::code language="csharp" source="snippets/configuration/console-di-ienumerable/Program.cs" highlight="19-24":::

El código fuente de ejemplo anterior registra dos implementaciones de `IMessageWriter`.

:::code language="csharp" source="snippets/configuration/console-di-ienumerable/ExampleService.cs" highlight="9-18":::

`ExampleService` define dos parámetros de constructor, un único `IMessageWriter` y un `IEnumerable<IMessageWriter>`. El `IMessageWriter` único es la última implementación registrada, mientras que `IEnumerable<IMessageWriter>` representa todas las implementaciones registradas.

El marco también proporciona métodos de extensión `TryAdd{LIFETIME}`, que registran el servicio solo si todavía no hay registrada una implementación.

En el ejemplo siguiente, la llamada a `AddSingleton` registra `ConsoleMessageWriter` como una implementación para `IMessageWriter`. La llamada a `TryAddSingleton` no tiene ningún efecto porque `IMessageWriter` ya tiene una implementación registrada:

```csharp
services.AddSingleton<IMessageWriter, ConsoleMessageWriter>();
services.TryAddSingleton<IMessageWriter, LoggingMessageWriter>();
```

`TryAddSingleton` no tiene ningún efecto, puesto que ya se agregó y "try" generará un error. `ExampleService` impondría lo siguiente:

```csharp
public class ExampleService
{
    public ExampleService(
        IMessageWriter messageWriter,
        IEnumerable<IMessageWriter> messageWriters)
    {
        Trace.Assert(messageWriter is ConsoleMessageWriter);
        Trace.Assert(messageWriters.Single() is ConsoleMessageWriter);
    }
}
```

Para más información, consulte:

- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAdd%2A>
- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddTransient%2A>
- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddScoped%2A>
- <xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddSingleton%2A>

Los métodos [TryAddEnumerable(ServiceDescriptor)](xref:Microsoft.Extensions.DependencyInjection.Extensions.ServiceCollectionDescriptorExtensions.TryAddEnumerable%2A) registran el servicio solo si todavía no hay una implementación *del mismo tipo*. A través de `IEnumerable<{SERVICE}>` se resuelven varios servicios. Al registrar los servicios, agregue una instancia si no se ha agregado ya una del mismo tipo. Los autores de bibliotecas usan `TryAddEnumerable` para evitar el registro de varias copias de una implementación en el contenedor.

En el ejemplo siguiente, la primera llamada a `TryAddEnumerable` registra `MessageWriter` como una implementación para `IMessageWriter1`. La segunda llamada registra `MessageWriter` para `IMessageWriter2`. La tercera llamada no tiene ningún efecto porque `IMessageWriter1` ya tiene una implementación registrada de `MessageWriter`:

```csharp
public interface IMessageWriter1 { }
public interface IMessageWriter2 { }

public class MessageWriter : IMessageWriter1, IMessageWriter2
{
}

services.TryAddEnumerable(ServiceDescriptor.Singleton<IMessageWriter1, MessageWriter>());
services.TryAddEnumerable(ServiceDescriptor.Singleton<IMessageWriter2, MessageWriter>());
services.TryAddEnumerable(ServiceDescriptor.Singleton<IMessageWriter1, MessageWriter>());
```

Normalmente, el registro del servicio es independiente, excepto cuando se registran varias implementaciones del mismo tipo.

`IServiceCollection` es una colección de objetos <xref:Microsoft.Extensions.DependencyInjection.ServiceDescriptor>. En el ejemplo siguiente se muestra cómo registrar un servicio mediante la creación e incorporación de un elemento `ServiceDescriptor`:

```csharp
string secretKey = Configuration["SecretKey"];
var descriptor = new ServiceDescriptor(
    typeof(IMessageWriter),
    _ => new DefaultMessageWriter(secretKey),
    ServiceLifetime.Transient);

services.Add(descriptor);
```

Los métodos `Add{LIFETIME}` integrados usan el mismo enfoque. Por ejemplo, consulte el [código fuente de AddScoped](https://github.com/dotnet/extensions/blob/v3.1.8/src/DependencyInjection/DI.Abstractions/src/ServiceCollectionServiceExtensions.cs#L216-L237).

### <a name="constructor-injection-behavior"></a>Comportamiento de inserción de constructor

Los servicios se pueden resolver mediante el uso de:

- <xref:System.IServiceProvider>
- <xref:Microsoft.Extensions.DependencyInjection.ActivatorUtilities>:
  - Crea objetos que no están registrados en el contenedor.
  - Se utiliza con algunas características de Framework.

Los constructores pueden aceptar argumentos que no se proporcionan mediante la inserción de dependencias, pero los argumentos deben asignar valores predeterminados.

Cuando se resuelven los servicios mediante `IServiceProvider` o `ActivatorUtilities`, la inserción del constructor requiere un constructor *público*.

Cuando se resuelven los servicios mediante `ActivatorUtilities`, la inserción del constructor requiere que exista solo un constructor aplicable. Se admiten las sobrecargas de constructor, pero solo puede existir una sobrecarga cuyos argumentos pueda cumplir la inserción de dependencias.

## <a name="scope-validation"></a>Validación del ámbito

Cuando la aplicación se ejecuta en el entorno `Development` y llama a [CreateDefaultBuilder](generic-host.md#default-builder-settings) para compilar el host, el proveedor de servicios predeterminado realiza comprobaciones para confirmar lo siguiente:

- Los servicios con ámbito no se resuelven desde el proveedor de servicios raíz.
- Los servicios con ámbito no se insertan en singletons.

El proveedor de servicios raíz se crea cuando se llama a <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A>. La vigencia del proveedor de servicios raíz es la misma que la de la aplicación cuando el proveedor se inicia con la aplicación, y se elimina cuando la aplicación se cierra.

De la eliminación de los servicios con ámbito se encarga el contenedor que los creó. Si un servicio con ámbito se crea en el contenedor raíz, su duración sube a la del singleton, ya que solo lo puede eliminar el contenedor raíz cuando la aplicación se cierra. Al validar los ámbitos de servicio, este tipo de situaciones se detectan cuando se llama a `BuildServiceProvider`.

## <a name="see-also"></a>Vea también

- [Uso de la inserción de dependencias en .NET](dependency-injection-usage.md)
- [Instrucciones para la inserción de dependencias](dependency-injection-guidelines.md)
- [Inserción de dependencias en ASP.NET Core](/aspnet/core/fundamentals/dependency-injection)
- [Patrones de la Conferencia NDC para el desarrollo de aplicaciones de inserción de dependencias](https://www.youtube.com/watch?v=x-C-CNBVTaY)
- [Principio de dependencias explícitas](../../architecture/modern-web-apps-azure/architectural-principles.md#explicit-dependencies)
- [Los contenedores de inversión de control y el patrón de inserción de dependencias (Martin Fowler)](https://www.martinfowler.com/articles/injection.html)
- Los errores de DI deben crearse en el repositorio [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues).
