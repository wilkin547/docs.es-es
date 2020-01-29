---
title: Prueba de aplicaciones ASP.NET Core MVC
description: Diseño de aplicaciones web modernas con ASP.NET Core y Azure | Prueba de aplicaciones ASP.NET Core MVC
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: 82c9815abdd5140340f9a8ea39be23496d433889
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738387"
---
# <a name="test-aspnet-core-mvc-apps"></a>Prueba de aplicaciones ASP.NET Core MVC

> *"Si no le gusta realizar pruebas unitarias de su producto, lo más probable es que a los clientes tampoco les guste probarlo".*
 > \_- Anónimo-

En el software de cualquier complejidad se pueden producir errores inesperados en respuesta a los cambios. Por tanto, es necesario realizar pruebas después de realizar cambios en todas las aplicaciones menos en las más triviales (o las menos críticas). Las pruebas manuales son la forma más lenta, menos confiable y más costosa de probar software. Desafortunadamente, si las aplicaciones no están diseñadas para que se puedan probar, puede ser el único medio disponible. Las aplicaciones escritas de acuerdo con los principios arquitectónicos descritos en el [capítulo 4](architectural-principles.md) deben poder someterse a pruebas unitarias, y las aplicaciones ASP.NET Core también deben admitir pruebas de integración y funcionales automatizadas.

## <a name="kinds-of-automated-tests"></a>Tipos de pruebas automatizadas

Hay muchos tipos de pruebas automatizadas para las aplicaciones de software. La prueba más sencilla y de nivel más bajo es la prueba unitaria. En un nivel ligeramente superior se encuentran las pruebas de integración y las pruebas funcionales. Otros tipos de pruebas, como las de interfaz de usuario, de carga, de esfuerzo y de humo, quedan fuera del ámbito de este documento.

### <a name="unit-tests"></a>Pruebas unitarias

Una prueba unitaria prueba un único elemento de la lógica de la aplicación. Se puede describir aún más enumerando algunas de las cosas que no hace. Una prueba unitaria no prueba el funcionamiento del código con dependencias o infraestructura; eso lo comprueban las pruebas de integración. Una prueba unitaria no prueba el marco para el que se escribe el código; se debe asumir que funciona o, si se detecta que no lo hace, registrar un error y codificar una solución alternativa. Una prueba unitaria se ejecuta completamente en memoria y en proceso. No se comunica con el sistema de archivos, la red o una base de datos. Las pruebas unitarias solo deben probar el código.

Las pruebas unitarias, como solo prueban una unidad del código, sin dependencias externas, se deben ejecutar muy rápidamente. Por tanto, debe ser capaz de ejecutar conjuntos de cientos de pruebas unitarias en unos segundos. Ejecute las pruebas con frecuencia, idealmente antes de cada inserción en un repositorio de control de código fuente compartido y, por supuesto, con cada compilación automatizada en el servidor de compilación.

### <a name="integration-tests"></a>Pruebas de integración

Aunque es una buena idea encapsular el código que interactúa con la infraestructura como bases de datos y sistemas de archivos, seguirá disponiendo de parte de ese código y, probablemente le interesará probarlo. Además, debe comprobar que las capas del código interactúan según lo esperado cuando se resuelvan completamente las dependencias de la aplicación. Esta es la responsabilidad de las pruebas de integración. Las pruebas de integración tienden a ser más lentas y más difíciles de configurar que las pruebas unitarias, porque a menudo dependen de la infraestructura y de dependencias externas. Por tanto, debe evitar realizar pruebas de cosas que podrían evaluarse con pruebas unitarias en pruebas de integración. Si un escenario determinado se puede probar con una prueba unitaria, debe probarlo con una prueba unitaria. Si no es posible, considere la posibilidad de usar una prueba de integración.

Las pruebas de integración a menudo tendrán procedimientos más complejos de instalación y desmontaje que las pruebas unitarias. Por ejemplo, una prueba de integración dirigida a una base de datos real necesitará un modo de devolver la base de datos a un estado conocido antes de cada serie de pruebas. Cuando se agregan nuevas pruebas y el esquema de base de datos de producción evoluciona, estos scripts de prueba tienden a aumentar de tamaño y complejidad. En muchos sistemas de gran tamaño, no resulta práctico ejecutar conjuntos completos de pruebas de integración en las estaciones de trabajo de desarrollador antes de insertar en el repositorio los cambios en el control de código fuente compartido. En estos casos, las pruebas de integración se pueden ejecutar en un servidor de compilación.

### <a name="functional-tests"></a>Pruebas funcionales

Las pruebas de integración se escriben desde la perspectiva del desarrollador, para comprobar que algunos componentes del sistema funcionen correctamente entre sí. Las pruebas funcionales se escriben desde la perspectiva del usuario y comprueban la exactitud del sistema en función de sus requisitos. En el fragmento siguiente se ofrece una analogía útil para saber cómo pensar en las pruebas funcionales, en comparación con las pruebas unitarias:

> "En muchas ocasiones, el desarrollo de un sistema se asemeja a la construcción de una casa. Aunque esta analogía no es del todo correcta, podemos ampliarla para explicar la diferencia entre las pruebas unitarias y las funcionales. Las pruebas unitarias son similares a un inspector municipal que visita la obra de construcción de una casa. Se centra en los distintos sistemas internos de la casa, los cimientos, los muros, la instalación eléctrica, la fontanería y así sucesivamente. Se asegura (prueba) de que las partes de la casa funcionarán correctamente y de manera segura, es decir, cumplen el código de construcción. En este escenario, las pruebas funcionales son análogas al propietario que visita esta misma obra. Da por supuesto que los sistemas internos se comportarán de forma adecuada, que el inspector municipal está realizando su trabajo. El propietario se centra en cómo será vivir en esta casa. Le preocupa el aspecto de la casa, si las distintas habitaciones tienen un tamaño cómodo, si la casa se ajusta a las necesidades de la familia, si las ventanas están en una zona adecuada para captar el sol por la mañana. El propietario está realizando pruebas funcionales de la casa. Tiene la perspectiva del usuario. El inspector municipal está realizando pruebas unitarias en la casa. Tiene la perspectiva del constructor".

Fuente: [Unit Testing versus Functional Tests](https://www.softwaretestingtricks.com/2007/01/unit-testing-versus-functional-tests.html) (Diferencias entre pruebas unitarias y pruebas funcionales)

Me gusta decir: "Como desarrolladores, fallamos de dos maneras: creamos algo de forma incorrecta o creamos algo incorrecto". Las pruebas unitarias aseguran que se cree algo de forma correcta y las pruebas funcionales que se cree algo correcto.

Como las pruebas funcionales operan en el nivel de sistema, pueden requerir cierto grado de automatización de la interfaz de usuario. Al igual que las pruebas de integración, también suelen funcionar con algún tipo de infraestructura de pruebas. Esto hace que sean más lentas y frágiles que las pruebas unitarias y las de integración. Solo se deben tener las pruebas funcionales necesarias para estar seguro de que el sistema se comporta tal y como esperan los usuarios.

### <a name="testing-pyramid"></a>Pirámide de pruebas

Martin Fowler escribió sobre la pirámide de pruebas, de la que se muestra un ejemplo en la figura 9-1.

![Pirámide de pruebas](./media/image9-1.png)

**Figura 9-1**. Pirámide de pruebas

Los diferentes niveles de la pirámide y sus tamaños relativos representan distintos tipos de pruebas y cuántas se deben escribir para la aplicación. Como se puede ver, la recomendación es tener una base grande de pruebas unitarias, respaldada por un nivel más pequeño de pruebas de integración, con un nivel incluso más pequeño de pruebas funcionales. Idealmente, cada nivel solo debería incluir las pruebas que no se puedan realizar de forma adecuada en un nivel inferior. Tenga presente la pirámide de pruebas al tratar de decidir qué tipo de prueba necesita para un escenario determinado.

### <a name="what-to-test"></a>Qué se va a probar

Un problema común para los desarrolladores sin experiencia con la escritura de pruebas automatizadas es determinar lo que se debe probar. Un buen punto de partida es probar la lógica condicional. Siempre que haya un método con un comportamiento que cambia en función de una instrucción condicional (if-else, switch, etc.), debería poder dar idear al menos un par de pruebas que confirmen el comportamiento correcto para determinadas condiciones. Si el código tiene condiciones de error, es conveniente escribir al menos una prueba para la "ruta feliz" a través del código (sin errores) y al menos una prueba para la "ruta triste" (con errores o resultados pocos frecuentes) para confirmar que la aplicación se comporta según lo previsto ante los errores. Por último, intente centrarse en probar cosas en las que se pueda producir un error, en lugar de centrarse en métricas como la cobertura de código. Por lo general, es mejor tener más cobertura de código que menos. Pero escribir algunas pruebas más de un método muy complejo y esencial para la empresa suele ser un mejor uso del tiempo que escribir pruebas para propiedades automáticas solo para mejorar la métrica de cobertura del código de prueba.

## <a name="organizing-test-projects"></a>Organización de los proyectos de prueba

Los proyectos de prueba se pueden organizar de la manera que mejor funcione. Es una buena idea separar las pruebas por tipo (prueba unitaria, prueba de integración) y por lo que van a probar (por proyecto, por espacio de nombres). Que esta separación conste de carpetas dentro de un único proyecto de prueba o de varios es una decisión de diseño. Lo más sencillo es un proyecto, pero para proyectos grandes con muchas pruebas, o bien para ejecutar más fácilmente otros conjuntos de pruebas, es posible que le interese tener varios proyectos de prueba distintos. Muchos equipos organizan los proyectos de prueba en función del proyecto que se está probando, que para las aplicaciones con más de unos pocos proyectos puede provocar un gran número de proyectos de prueba, en especial si se siguen dividiendo según el tipo de pruebas de cada proyecto. Un enfoque de compromiso consiste en disponer de un proyecto por tipo de prueba, por aplicación, con carpetas dentro de los proyectos de prueba para indicar el proyecto (y la clase) que se van a probar.

Un enfoque común consiste en organizar los proyectos de la aplicación en una carpeta "src" y los proyectos de prueba en una carpeta "tests" paralela. Si esta organización le parece útil, puede crear carpetas de solución coincidentes en Visual Studio.

![Organización de las pruebas en la solución](./media/image9-2.png)

**Figura 9-2**. Organización de las pruebas en la solución

Puede usar el marco de pruebas que prefiera. El marco de trabajo xUnit funciona bien y es en el que se escriben todas las pruebas de ASP.NET Core y EF Core. Puede agregar un proyecto de prueba de xUnit en Visual Studio con la plantilla que se muestra en la figura 9-3 o desde la CLI mediante dotnet new xunit.

![Agregar un proyecto de prueba de xUnit en Visual Studio](./media/image9-3.png)

**Figura 9-3**. Agregar un proyecto de prueba de xUnit en Visual Studio

### <a name="test-naming"></a>Nombres de pruebas

Debe asignar nombres a las pruebas de forma coherente, con un nombre que indique lo que hace cada prueba. Un enfoque con el que he tenido buenos resultados consiste en asignar nombres a las clases de prueba en función de la clase y el método que estén probando. Esto da como resultado muchas clases de prueba pequeñas, pero deja muy claro la responsabilidad de cada una. Con el nombre de la clase de prueba configurado para identificar la clase y el método que se van a probar, se puede usar el nombre del método de prueba para especificar el comportamiento que se está probando. Esto debe incluir el comportamiento esperado y las entradas o suposiciones que deban producir este comportamiento. Algunos nombres de prueba de ejemplo:

- `CatalogControllerGetImage.CallsImageServiceWithId`

- `CatalogControllerGetImage.LogsWarningGivenImageMissingException`

- `CatalogControllerGetImage.ReturnsFileResultWithBytesGivenSuccess`

- `CatalogControllerGetImage.ReturnsNotFoundResultGivenImageMissingException`

Una variante de este enfoque finaliza cada nombre de clase de prueba con "Should" (Debería) y modifica ligeramente el tiempo:

- `CatalogControllerGetImage`**Should**`.`**Call**`ImageServiceWithId`

- `CatalogControllerGetImage`**Should**`.`**Log**`WarningGivenImageMissingException`

Para algunos equipos el segundo método de nomenclatura es más claro, aunque un poco más detallado. En cualquier caso, intente usar una convención de nomenclatura que proporcione información del comportamiento de la prueba, para que cuando se produzca un error en una o varias pruebas, sea obvio a partir de los nombres en qué casos se ha producido el error. Evite asignar nombre a las pruebas de forma vaga, como ControllerTests.Test1, dado que eso no ofrece ningún valor cuando se ven en los resultados de las pruebas.

Si sigue una convención de nomenclatura como la anterior que genera muchas clases de prueba pequeñas, es aconsejable organizar más las pruebas mediante carpetas y espacios de nombres. En la figura 9-4 se muestra un enfoque para organizar las pruebas por carpeta en varios proyectos de prueba.

![Organización de las clases de prueba por carpeta en función de la clase que se prueba](./media/image9-4.png)

**Figura 9-4.** Organización de las clases de prueba por carpeta en función de la clase que se está probando.

Evidentemente, si una clase de aplicación determinada tiene muchos métodos para probar (y, por tanto, muchas clases de prueba), tiene sentido colocarlos en una carpeta correspondiente a la clase de aplicación. Esta organización es similar a cómo se podrían organizar los archivos en carpetas en otra parte. Si tiene más de tres o cuatro archivos relacionados en una carpeta que contiene otros muchos archivos, suele resultar útil moverlos a su propia subcarpeta.

## <a name="unit-testing-aspnet-core-apps"></a>Pruebas unitarias de aplicaciones ASP.NET Core

En una aplicación ASP.NET Core bien diseñada, la mayor parte de la complejidad y la lógica de negocios se encapsulará en entidades de negocio y una variedad de servicios. La propia aplicación ASP.NET Core MVC con sus controladores, filtros, modelos de vista y vistas, no debería requerir muchas pruebas unitarias. Gran parte de la funcionalidad de una acción determinada se encuentra fuera del propio método de acción. Comprobar si el enrutamiento funciona correctamente o el control de errores global, no se puede realizar de forma eficaz con una prueba unitaria. Del mismo modo, los filtros, incluidos los de autenticación y validación del modelo y los de autorización, no se pueden someter a pruebas unitarias. Sin estas fuentes de comportamiento, la mayoría de los métodos de acción deberían ser pequeños, y delegar la mayor parte de su trabajo a servicios que se puedan probar de forma independiente al controlador que los usa.

En ocasiones tendrá que refactorizar el código para poder realizar pruebas unitarias en él. Con frecuencia, esto implica la identificación de abstracciones y el uso de la inserción de dependencias para tener acceso a la abstracción en el código que se quiere probar, en lugar de codificar directamente en la infraestructura. Por ejemplo, considere este método de acción simple para mostrar imágenes:

```csharp
[HttpGet("[controller]/pic/{id}")]
public IActionResult GetImage(int id)
{
    var contentRoot = _env.ContentRootPath + "//Pics";
    var path = Path.Combine(contentRoot, id + ".png");
    Byte[] b = System.IO.File.ReadAllBytes(path);
    return File(b, "image/png");
}
```

La realización de pruebas unitarias en este método se complica debido a su dependencia directa de `System.IO.File`, que usa para leer el sistema de archivos. Puede probar este comportamiento para asegurarse de que funciona de la forma esperada, pero si lo hace con archivos reales será una prueba de integración. Cabe mencionar que no se puede realizar la prueba unitaria de la ruta de este método: verá cómo hacerlo con una prueba funcional en breve.

Si no se pueden realizar directamente pruebas unitarias del comportamiento del sistema de archivos y no se puede probar la ruta, ¿qué se puede probar? Después de la refactorización para que las pruebas unitarias sean posibles, puede detectar varios casos de prueba y comportamiento que falta, como el control de errores. ¿Qué hace el método cuando no se encuentra un archivo? ¿Qué debería hacer? En este ejemplo, el método refactorizado tiene el aspecto siguiente:

```csharp
[HttpGet("[controller]/pic/{id}")]
public IActionResult GetImage(int id)
{
    byte[] imageBytes;
    try
    {
        imageBytes = _imageService.GetImageBytesById(id);
    }
    catch (CatalogImageMissingException ex)
    {
        _logger.LogWarning($"No image found for id: {id}");
        return NotFound();
    }
    return File(imageBytes, "image/png");
}
```

\_logger e \_imageService se insertan como dependencias. Ahora se puede probar que el mismo identificador que se pasa al método de acción se pasa a \_imageService, y que los bytes resultantes se devuelven como parte de FileResult. También se puede probar que el registro de errores se está realizando de la forma esperada y que se devuelve un resultado de NotFound si la imagen no se encuentra, suponiendo que se trate de un comportamiento importante de la aplicación (es decir, no solo código temporal que el desarrollador agregó para diagnosticar un problema). La lógica real del archivo se ha trasladado a un servicio de implementación independiente y se ha ampliado para devolver una excepción específica de la aplicación en el caso de un archivo que falta. Puede probar esta implementación de forma independiente, con una prueba de integración.

En la mayoría de los casos, es recomendable que use controladores de excepciones globales en los controladores, por lo que la cantidad de lógica que contengan debería ser mínima y probablemente no valga la pena realizar pruebas unitarias. Debería realizar la mayoría de las pruebas de acciones de controlador usando pruebas funcionales y la clase `TestServer`, que se describe a continuación.

## <a name="integration-testing-aspnet-core-apps"></a>Pruebas de integración en aplicaciones ASP.NET Core

La mayoría de las pruebas de integración en las aplicaciones ASP.NET Core deberían consistir en la prueba de servicios y otros tipos de implementación definidos en el proyecto de la infraestructura. Por ejemplo, podría [probar que EF Core actualiza y recupera correctamente los datos que espera](https://docs.microsoft.com/ef/core/miscellaneous/testing/) de las clases de acceso a los datos que residen en el proyecto de infraestructura. La mejor manera de probar si el proyecto de ASP.NET Core MVC se comporta correctamente es realizar pruebas funcionales en la aplicación que se ejecuta en un host de prueba.

## <a name="functional-testing-aspnet-core-apps"></a>Pruebas funcionales en aplicaciones ASP.NET Core

Para las aplicaciones ASP.NET Core, la clase `TestServer` facilita considerablemente la escritura de pruebas funcionales. Para configurar un elemento `TestServer`, use directamente un elemento `WebHostBuilder` (como lo haría para su aplicación), o bien el tipo `WebApplicationFactory` (disponible a partir de la versión 2.1). Debe intentar que el host de prueba coincida lo máximo posible con el host de producción para que las pruebas ejecuten un comportamiento similar al que tendrá la aplicación en la fase de producción. La clase `WebApplicationFactory` es útil para configurar ContentRoot de TestServer, que ASP.NET Core usa para localizar recursos estáticos como las vistas.

Puede crear pruebas funcionales sencillas si crea una clase de prueba que implemente IClassFixture\<WebApplicationFactory\<TEntry>> donde TEntry es la clase de inicio de la aplicación web. Después de agregar esto, el accesorio de prueba puede crear un cliente con el método CreateClient de la fábrica:

```cs
public class BasicWebTests : IClassFixture<WebApplicationFactory<Startup>>
{
    protected readonly HttpClient _client;

    public BaseWebTest(WebApplicationFactory<Startup> factory)
    {
        _client = factory.CreateClient();
    }

    // write tests that use _client
}
```

Con frecuencia, le interesará configurar opciones adicionales del sitio antes de ejecutar cada prueba, como configurar la aplicación para que use un almacén de datos en memoria y, después, propagar datos de prueba en la aplicación. Para ello, debe crear una subclase de WebApplicationFactory\<TEntry> propia y reemplazar su método ConfigureWebHost. El ejemplo siguiente es del proyecto eShopOnWeb FunctionalTests y se usa como parte de las pruebas en la aplicación web principal.

```cs
using Microsoft.AspNetCore.Hosting;
using Microsoft.AspNetCore.Mvc.Testing;
using Microsoft.EntityFrameworkCore;
using Microsoft.eShopWeb.Infrastructure.Data;
using Microsoft.eShopWeb.Infrastructure.Identity;
using Microsoft.eShopWeb.Web;
using Microsoft.Extensions.DependencyInjection;
using Microsoft.Extensions.Logging;
using System;

namespace Microsoft.eShopWeb.FunctionalTests.Web.Controllers
{
    public class CustomWebApplicationFactory<TStartup>
    : WebApplicationFactory<Startup>
    {
        protected override void ConfigureWebHost(IWebHostBuilder builder)
        {
            builder.ConfigureServices(services =>
            {
                // Create a new service provider.
                var serviceProvider = new ServiceCollection()
                    .AddEntityFrameworkInMemoryDatabase()
                    .BuildServiceProvider();

                // Add a database context (ApplicationDbContext) using an in-memory
                // database for testing.
                services.AddDbContext<CatalogContext>(options =>
                {
                    options.UseInMemoryDatabase("InMemoryDbForTesting");
                    options.UseInternalServiceProvider(serviceProvider);
                });

                services.AddDbContext<AppIdentityDbContext>(options =>
                {
                    options.UseInMemoryDatabase("Identity");
                    options.UseInternalServiceProvider(serviceProvider);
                });

                // Build the service provider.
                var sp = services.BuildServiceProvider();

                // Create a scope to obtain a reference to the database
                // context (ApplicationDbContext).
                using (var scope = sp.CreateScope())
                {
                    var scopedServices = scope.ServiceProvider;
                    var db = scopedServices.GetRequiredService<CatalogContext>();
                    var loggerFactory = scopedServices.GetRequiredService<ILoggerFactory>();

                    var logger = scopedServices
                        .GetRequiredService<ILogger<CustomWebApplicationFactory<TStartup>>>();

                    // Ensure the database is created.
                    db.Database.EnsureCreated();

                    try
                    {
                        // Seed the database with test data.
                        CatalogContextSeed.SeedAsync(db, loggerFactory).Wait();
                    }
                    catch (Exception ex)
                    {
                        logger.LogError(ex, $"An error occurred seeding the " +
                            "database with test messages. Error: {ex.Message}");
                    }
                }
            });
        }
    }
}
```

Las pruebas pueden hacer uso de esta clase WebApplicationFactory personalizada para crear a un cliente y, después, realizar solicitudes a la aplicación mediante esta instancia de cliente. La aplicación tendrá datos propagados que se pueden usar como parte de las aserciones de la prueba. La prueba que encontrará a continuación comprueba que la página principal de la aplicación eShopOnWeb se carga correctamente y que incluye una lista de productos que se ha agregado a la aplicación como parte de los datos de inicialización.

```cs
using Microsoft.eShopWeb.FunctionalTests.Web.Controllers;
using Microsoft.eShopWeb.Web;
using System.Net.Http;
using System.Threading.Tasks;
using Xunit;

namespace Microsoft.eShopWeb.FunctionalTests.WebRazorPages
{
    public class HomePageOnGet : IClassFixture<CustomWebApplicationFactory<Startup>>
    {
        public HomePageOnGet(CustomWebApplicationFactory<Startup> factory)
        {
            Client = factory.CreateClient();
        }

        public HttpClient Client { get; }

        [Fact]
        public async Task ReturnsHomePageWithProductListing()
        {
            // Arrange & Act
            var response = await Client.GetAsync("/");
            response.EnsureSuccessStatusCode();
            var stringResponse = await response.Content.ReadAsStringAsync();

            // Assert
            Assert.Contains(".NET Bot Black Sweatshirt", stringResponse);
        }
    }
}
```

Esta prueba funcional ejecuta la pila de la aplicación ASP.NET Core MVC o Razor Pages completa, incluidos todo el software intermedio, filtros, enlazadores, etc., que puedan estar definidos. Comprueba que una ruta determinada ("/") devuelve el código de estado correcto esperado y la salida HTML. Lo hace sin configurar un servidor web real y de ese modo evita gran parte de la fragilidad que supone el uso de un servidor web real para realizar pruebas (por ejemplo, problemas con la configuración de firewall). Las pruebas funcionales que se ejecutan en TestServer normalmente son más lentas que las pruebas unitarias y de integración, pero son mucho más rápidas que las que se ejecutarían a través de la red a un servidor web de prueba. Debe usar las pruebas funcionales para garantizar que la pila de front-end de la aplicación funciona según lo previsto. Estas pruebas son especialmente útiles al buscar duplicados en controladores o páginas, y solucionar la duplicación mediante la adición de filtros. Idealmente, esta refactorización no cambiará el comportamiento de la aplicación, y un conjunto de pruebas funcionales comprobará que sea así.

> ### <a name="references--test-aspnet-core-mvc-apps"></a>Referencias: prueba de aplicaciones ASP.NET Core MVC
>
> - **Pruebas y depuración en ASP.NET Core** \
>   <https://docs.microsoft.com/aspnet/core/testing/>
> - **Convención de nomenclatura de prueba unitaria** \
>   <https://ardalis.com/unit-test-naming-convention>
> - **Pruebas de EF Core** \
>   <https://docs.microsoft.com/ef/core/miscellaneous/testing/>
> - **Pruebas de integración en ASP.NET Core** \
>   <https://docs.microsoft.com/aspnet/core/test/integration-tests>
> - **Reunión de la comunidad de ASP.NET del 15 de mayo de 2018: pruebas de MVC con Javier C. Nelson** - Vídeo de YouTube \
>   <https://www.youtube.com/watch?v=wtOE-xmFJkw&list=PL1rZQsJPBU2StolNg0aqvQswETPcYnNKL&index=5>

>[!div class="step-by-step"]
>[Anterior](work-with-data-in-asp-net-core-apps.md)
>[Siguiente](development-process-for-azure.md)
