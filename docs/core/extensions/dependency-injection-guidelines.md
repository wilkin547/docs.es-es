---
title: Instrucciones para la inserción de dependencias
description: Conozca diferentes procedimientos recomendados y guías de inserción de dependencias para el desarrollo de aplicaciones .NET.
author: IEvangelist
ms.author: dapine
ms.date: 10/29/2020
ms.topic: guide
ms.openlocfilehash: 105536df873829dc79dcca1b86d080360e71303f
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "102402208"
---
# <a name="dependency-injection-guidelines"></a>Instrucciones para la inserción de dependencias

En este artículo se proporcionan instrucciones generales y procedimientos recomendados para implementar la inserción de dependencias en aplicaciones .NET.

## <a name="design-services-for-dependency-injection"></a>Diseño de servicios para la inserción de dependencias

Al diseñar servicios para la inserción de dependencias:

- Evitar clases y miembros estáticos y con estado. Evitar crear un estado global mediante el diseño de aplicaciones para usar servicios singleton en su lugar.
- Evitar la creación directa de instancias de clases dependientes dentro de los servicios. La creación directa de instancias se acopla al código de una implementación particular.
- Cree servicios pequeños, bien factorizados y probados con facilidad.

Si una clase tiene muchas dependencias insertadas, podría ser un signo de que la clase tiene demasiadas responsabilidades e infringe el [principio de responsabilidad única (SRP)](/dotnet/standard/modern-web-apps-azure-architecture/architectural-principles#single-responsibility). Trate de mover algunas de las responsabilidades de la clase a clases nuevas para intentar refactorizarla.

### <a name="disposal-of-services"></a>Eliminación de servicios

El contenedor es responsable de la limpieza de los tipos que crea y llama a <xref:System.IDisposable.Dispose%2A> en las instancias de <xref:System.IDisposable>. El desarrollador nunca debe eliminar los servicios resueltos desde el contenedor. Si un tipo o fábrica se registra como singleton, el contenedor elimina el singleton de manera automática.

En el ejemplo siguiente, el contenedor de servicios crea los servicios y se eliminan de manera automática:

:::code language="csharp" source="snippets/configuration/console-di-disposable/TransientDisposable.cs":::

El tipo descartable anterior está diseñado para tener una duración transitoria.

:::code language="csharp" source="snippets/configuration/console-di-disposable/ScopedDisposable.cs":::

El tipo descartable anterior está diseñado para tener una duración con ámbito.

:::code language="csharp" source="snippets/configuration/console-di-disposable/SingletonDisposable.cs":::

El tipo descartable anterior está diseñado para tener una duración de singleton.

:::code language="csharp" source="snippets/configuration/console-di-disposable/Program.cs" range="1-21,41-60" highlight="":::

En la consola de depuración se muestra el siguiente resultado de ejemplo después de la ejecución:

```console
Scope 1...
ScopedDisposable.Dispose()
TransientDisposable.Dispose()

Scope 2...
ScopedDisposable.Dispose()
TransientDisposable.Dispose()

info: Microsoft.Hosting.Lifetime[0]
      Application started.Press Ctrl+C to shut down.
info: Microsoft.Hosting.Lifetime[0]
     Hosting environment: Production
info: Microsoft.Hosting.Lifetime[0]
     Content root path: .\configuration\console-di-disposable\bin\Debug\net5.0
info: Microsoft.Hosting.Lifetime[0]
     Application is shutting down...
SingletonDisposable.Dispose()
```

### <a name="services-not-created-by-the-service-container"></a>Servicios no creados por el contenedor de servicios

Observe el código siguiente:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddSingleton(new ExampleService());

    // ...
}
```

En el código anterior:

- El contenedor de servicios **no** crea la instancia de `ExampleService`.
- El marco de trabajo **no** elimina los servicios de manera automática.
- El desarrollador es responsable de la eliminación de los servicios.

### <a name="idisposable-guidance-for-transient-and-shared-instances"></a>Instrucciones de IDisposable para instancias transitorias y compartidas

#### <a name="transient-limited-lifetime"></a>Instancia transitoria, duración limitada

**Escenario**

La aplicación requiere una instancia de <xref:System.IDisposable> con una duración transitoria para cualquiera de estos escenarios:

- La instancia se resuelve en el ámbito raíz (contenedor raíz).
- La instancia se debe eliminar antes de que finalice el ámbito.

**Solución**

Use el patrón de fábrica para crear una instancia fuera del ámbito principal. En esta situación, la aplicación habitualmente tendría un método `Create` que llama directamente al constructor del tipo final. Si el tipo final tiene otras dependencias, la fábrica puede:

- Recibir un <xref:System.IServiceProvider> en su constructor.
- Usar <xref:Microsoft.Extensions.DependencyInjection.ActivatorUtilities.CreateInstance%2A?displayProperty=nameWithType> para crear instancias de la instancia fuera del contenedor, mientras usa el contenedor para sus dependencias.

#### <a name="shared-instance-limited-lifetime"></a>Instancia compartida, duración limitada

**Escenario**

La aplicación requiere una instancia de <xref:System.IDisposable> compartida en varios servicios, pero la instancia de <xref:System.IDisposable> debe tener una duración limitada.

**Solución**

Registre la instancia con una duración restringida. Use <xref:Microsoft.Extensions.DependencyInjection.IServiceScopeFactory.CreateScope%2A?displayProperty=nameWithType> para crear un <xref:Microsoft.Extensions.DependencyInjection.IServiceScope> nuevo. Use el <xref:System.IServiceProvider> del ámbito para obtener los servicios necesarios. Elimine el ámbito cuando ya no lo necesite.

#### <a name="general-idisposable-guidelines"></a>Instrucciones generales sobre `IDisposable`

- No registre instancias de <xref:System.IDisposable> con una duración transitoria. En su lugar, use el patrón de fábrica.
- No resuelva instancias de <xref:System.IDisposable> con una duración transitoria o restringida en el ámbito raíz. La única excepción a esto es si la aplicación crea o vuelve a crear y elimina <xref:System.IServiceProvider>, pero este no es un patrón ideal.
- La recepción de una dependencia de <xref:System.IDisposable> a través de las inserciones de dependencias no requiere que el receptor implemente <xref:System.IDisposable> por sí mismo. El receptor de la dependencia de <xref:System.IDisposable> no debe llamar a <xref:System.IDisposable.Dispose%2A> en esa dependencia.
- Use ámbitos para controlar las duraciones de los servicios. Los ámbitos no son jerárquicos y no hay ninguna conexión especial entre ellos.

Para más información sobre la limpieza de recursos, vea [Implementación de un método`Dispose`](../../standard/garbage-collection/implementing-dispose.md) o [Implementación de un método `DisposeAsync`](../../standard/garbage-collection/implementing-disposeasync.md). Además, tenga en cuenta el escenario [Servicios transitorios descartables capturados por el contenedor](#disposable-transient-services-captured-by-container) por su relación con la limpieza de recursos.

## <a name="default-service-container-replacement"></a>Reemplazo del contenedor de servicios predeterminado

El contenedor de servicios integrado está diseñado para atender las necesidades del marco y de la mayoría de las aplicaciones de consumidor. Se recomienda usar el contenedor integrado a menos que se necesite una característica específica no admitida por el contenedor, como:

- Inserción de propiedades
- Inserción basada en nombres
- Contenedores secundarios
- Administración personalizada del ciclo de vida
- Compatibilidad con `Func<T>` para la inicialización diferida
- Registro basado en convenciones

Los siguientes contenedores de terceros se pueden usar con aplicaciones ASP.NET Core:

- [Autofac](https://autofac.readthedocs.io/en/latest/integration/aspnetcore.html)
- [DryIoc](https://www.nuget.org/packages/DryIoc.Microsoft.DependencyInjection)
- [Grace](https://www.nuget.org/packages/Grace.DependencyInjection.Extensions)
- [LightInject](https://github.com/seesharper/LightInject.Microsoft.DependencyInjection)
- [Lamar](https://jasperfx.github.io/lamar/)
- [Stashbox](https://github.com/z4kn4fein/stashbox-extensions-dependencyinjection)
- [Unity](https://www.nuget.org/packages/Unity.Microsoft.DependencyInjection)

## <a name="thread-safety"></a>Seguridad para subprocesos

Cree servicios de singleton seguros para subprocesos. Si un servicio de singleton tiene una dependencia en un servicio transitorio, es posible que este también deba ser seguro para subprocesos, según cómo lo use el singleton.

El Factory Method de un servicio singleton, como el segundo argumento para [AddSingleton\<TService>(IServiceCollection, Func\<IServiceProvider,TService>)](xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionServiceExtensions.AddSingleton%2A), no necesita ser seguro para subprocesos. Al igual que un constructor de tipos (`static`), se garantiza que se le llame solo una vez mediante un único subproceso.

## <a name="recommendations"></a>Recomendaciones

- No se admite la resolución de servicio basada en `async/await` y `Task`. Como C# no admite constructores asincrónicos, use los métodos asincrónicos después de resolver sincrónicamente el servicio.
- Evite almacenar datos y configuraciones directamente en el contenedor de servicios. Por ejemplo, el carro de la compra de un usuario no debería agregarse al contenedor de servicios. La configuración debe usar el patrón de opciones. Del mismo modo, evite los objetos de tipo "contenedor de datos" que solo existen para permitir el acceso a otro objeto. Es mejor solicitar el elemento real que se necesita mediante la inserción de dependencias.
- Evite el acceso estático a los servicios. Por ejemplo, evite capturar [IApplicationBuilder.ApplicationServices](xref:Microsoft.AspNetCore.Builder.IApplicationBuilder.ApplicationServices) como campo estático o propiedad para su uso en otra parte.
- Mantenga los [generadores de DI](#async-di-factories-can-cause-deadlocks) rápidos y sincrónicos.
- Evite el uso del [*patrón del localizador de servicios*](#scoped-service-as-singleton). Por ejemplo, no invoque a <xref:System.IServiceProvider.GetService%2A> para obtener una instancia de servicio si puede usar la inserción de dependencias en su lugar.
- Otra variación del localizador de servicios que se debe evitar es insertar una fábrica que resuelva dependencias en tiempo de ejecución. Estas dos prácticas combinan estrategias de [Inversión de control](/dotnet/standard/modern-web-apps-azure-architecture/architectural-principles#dependency-inversion).
- Evite las llamadas a <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider%2A> en `ConfigureServices`. La llamada a `BuildServiceProvider` suele ocurrir cuando el desarrollador desea resolver un servicio en `ConfigureServices`.
- El contenedor [captura los servicios transitorios descartables](#disposable-transient-services-captured-by-container) para su eliminación. Esto puede resultar en una fuga de memoria si se resuelve desde el contenedor de nivel superior.
- Habilite la validación con ámbito para asegurarse de que la aplicación no tenga singletons que capturen los servicios con ámbito. Para más información, vea [Validación del ámbito](dependency-injection.md#scope-validation).

Al igual que sucede con todas las recomendaciones, podría verse en una situación que le obligue a ignorar alguna de ellas. Las excepciones son poco frecuentes, principalmente en casos especiales dentro del marco de trabajo mismo.

La inserción de dependencias es una *alternativa* a los patrones de acceso a objetos estáticos o globales. No podrá aprovechar las ventajas de la inserción de dependencias si la combina con el acceso a objetos estáticos.

## <a name="example-anti-patterns"></a>Antipatrones de ejemplo

Además de las instrucciones de este artículo, hay varios antipatrones que ***debe** evitar*. Algunos de estos antipatrones son aprender del desarrollo de los propios tiempos de ejecución.

> [!WARNING]
> Estos son antipatrones de ejemplo: *no* copiar el código, *no* usar estos patrones y evitar estos patrones a toda costa.

### <a name="disposable-transient-services-captured-by-container"></a>El contenedor captura los servicios transitorios descartables

Cuando se registran servicios *transitorios* que implementan <xref:System.IDisposable>, de forma predeterminada, el contenedor de DI incluirá estas referencias y ningún método <xref:System.IDisposable.Dispose> hasta que el contenedor se elimine cuando la aplicación se detenga si se resolvieron desde el contenedor, o hasta que se elimine el ámbito si se resolvieron desde un ámbito. Esto puede resultar en una fuga de memoria si se resuelve desde el nivel de contenedor.

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="18-30":::

En el antipatrón anterior, se crean instancias de 1000 objetos `ExampleDisposable` y se liberan. No se eliminarán hasta que se elimine la instancia de `serviceProvider`.

Para más información sobre cómo depurar fugas de memoria, vea [Depuración de una fuga de memoria en .NET Core](../diagnostics/debug-memory-leak.md).

### <a name="async-di-factories-can-cause-deadlocks"></a>Los generadores de DI asincrónicos pueden producir interbloqueos

El término "generadores de DI" hace referencia a los métodos de sobrecarga que existen al llamar a `Add{LIFETIME}`. Hay sobrecargas que aceptan un `Func<IServiceProvider, T>`, donde `T` es el servicio que se está registrando, y el parámetro se denomina `implementationFactory`. `implementationFactory` se puede proporcionar como una expresión lambda, una función local o un método. Si el generador es asincrónico y se usa <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType>, se producirá un interbloqueo.

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="32-45" highlight="4-8":::

En el código anterior, se proporciona una expresión lambda a `implementationFactory`, donde el cuerpo llama a <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> en un método de devolución `Task<Bar>`. Esto ***provoca un interbloqueo***. El método `GetBarAsync` simplemente emula una operación de trabajo asincrónica con <xref:System.Threading.Tasks.Task.Delay%2A?displayProperty=nameWithType> y, a continuación, llama a <xref:Microsoft.Extensions.DependencyInjection.ServiceProviderServiceExtensions.GetRequiredService%60%601(System.IServiceProvider)>.

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="47-53":::

Para más información sobre la programación asincrónica, vea [Programación asincrónica: Consejos e información importante](../../csharp/async.md#important-info-and-advice). Para más información sobre la depuración de interbloqueos, vea [Depuración de un interbloqueo en .NET Core](../diagnostics/debug-deadlock.md).

Cuando se ejecuta este antipatrón y se produce el interbloqueo, puede ver los dos subprocesos en espera de la ventana Pilas paralelas de Visual Studio. Para más información, vea [Visualización de subprocesos y tareas en la ventana Pilas paralelas](/visualstudio/debugger/using-the-parallel-stacks-window).

### <a name="captive-dependency"></a>Dependencia cautiva

El término ["dependencia cautiva"](https://blog.ploeh.dk/2014/06/02/captive-dependency) lo acuñó [Mark Seeman](https://blog.ploeh.dk/about) y hace referencia a la configuración incorrecta de la duración de los servicios, donde un servicio de mayor duración mantiene una dependencia cautiva del servicio de menor duración.

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="55-65":::

En el código anterior, `Foo` se registra como singleton y `Bar` tiene el ámbito, que en la superficie parece válido. Sin embargo, tenga en cuenta la implementación de `Foo`.

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Foo.cs" highlight="5":::

El objeto `Foo` requiere un objeto `Bar` y, como `Foo` es un singleton y `Bar` su ámbito, se trata de una configuración incorrecta. Tal y como está, solo se crearía una instancia de `Foo`, y se mantendría en `Bar` mientras dure, que será un período mayor respecto a la duración con ámbito prevista de `Bar`. Considere la posibilidad de validar ámbitos, pasando `validateScopes: true` a <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionContainerBuilderExtensions.BuildServiceProvider(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Boolean)>. Al validar los ámbitos, obtendría un <xref:System.InvalidOperationException> con un mensaje similar a "No se puede consumir el servicio 'Bar' con ámbito en el singleton 'Foo'".

Para más información, vea [Validación del ámbito](dependency-injection.md#scope-validation).

### <a name="scoped-service-as-singleton"></a>Servicio con ámbito como singleton

Al usar los servicios con ámbito, si no va a crear un ámbito o en un ámbito existente, el servicio se convierte en un singleton.

:::code language="csharp" source="snippets/configuration/di-anti-patterns/Program.cs" range="68-82" highlight="13-14":::

En el código anterior, `Bar` se recupera dentro de un <xref:Microsoft.Extensions.DependencyInjection.IServiceScope>, que es correcto. El antipatrón es la recuperación de `Bar` fuera del ámbito, y la variable se denomina `avoid` para mostrar qué recuperación de ejemplo es incorrecta.

## <a name="see-also"></a>Vea también

- [Inserción de dependencias en .NET](dependency-injection.md)
- [Tutorial: Uso de la inserción de dependencias en .NET](dependency-injection-usage.md)
