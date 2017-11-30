---
title: Desarrollo de aplicaciones MVC de ASP.NET Core
description: "Diseñar aplicaciones Web modernas con ASP.NET Core y Azure | desarrollar aplicaciones de MVC de ASP.NET Core"
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 54e7ed6fff9ac709e411d0ac1e345c63fd753201
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2017
---
# <a name="develop-aspnet-core-mvc-apps"></a>Desarrollar aplicaciones MVC de ASP.NET Core

> "No es importante hacerlo bien la primera vez. Es sumamente importante hacerlo bien la última vez."  
> _-Captura de Andrew y David Thomas_

## <a name="summary"></a>Resumen

ASP.NET Core es un marco multiplataforma de código abierto para la creación de aplicaciones web modernas optimizada para la nube. Aplicaciones de ASP.NET Core son sencillos y modular, con la compatibilidad integrada para la inyección de dependencia, habilitación de mayor capacidad de prueba y el mantenimiento. Combinar con MVC, que admite la creación de las API de web moderna además de las aplicaciones basadas en vistas, ASP.NET Core es un marco eficaz con el que se va a generar aplicaciones web empresariales.

## <a name="mapping-requests-to-responses"></a>Solicitudes de asignación a las respuestas

En esencia, las aplicaciones ASP.NET Core asignan las solicitudes entrantes a las respuestas salientes. En un nivel bajo, esto se realiza con middleware y sencilla aplicaciones de ASP.NET Core y microservicios pueden constar únicamente de middleware personalizado. Cuando se usa el núcleo de ASP.NET MVC, puede trabajar en un mayor nivel, pensar en términos de *rutas*, *controladores*, y *acciones*. Cada solicitud entrante se compara con la tabla de enrutamiento de la aplicación y, si se encuentra una ruta coincidente, se llama al método de acción asociada (pertenecientes a un controlador) para controlar la solicitud. Si no se encuentra ninguna ruta que coincida, se llama a un controlador de errores (en este caso, devolver un resultado NotFound).

Pueden utilizar aplicaciones MVC de ASP.NET Core rutas convencionales, las rutas de atributo o ambos. Rutas convencionales se definen en el código, especificación de enrutamiento *convenciones* con una sintaxis similar en el ejemplo siguiente:

```csharp
app.UseMvc(routes =>;
{
    routes.MapRoute("default","{controller=Home}/{action=Index}/{id?}");
});
```

En este ejemplo, una ruta con el nombre "default" se agregó a la tabla de enrutamiento. Define una plantilla de ruta con marcadores de posición para *controlador*, *acción*, y *identificador*. Los marcadores de posición de acción y controlador tienen el valor predeterminado especificado ("Hogar" y "Index", respectivamente), y el marcador de posición del identificador es opcional (en virtud de un "?" aplicado). La convención definidos aquí Estados que debe corresponder a la primera parte de una solicitud para el nombre del controlador, la segunda parte a la acción y, a continuación, si es necesario un tercer elemento representa un parámetro de identificador. Rutas convencionales normalmente se definen en un solo lugar para la aplicación, como en el método de configuración de la clase de inicio.

Rutas de atributo se aplica directamente a los controladores y acciones, en lugar de especificar globalmente. Esto tiene la ventaja de que mucho más sencillo detectar si está pensando en un método concreto, pero significa que la información de enrutamiento no se guarda en una posición en la aplicación. Con las rutas de atributo, se puede fácilmente especificar varias rutas para una acción determinada, así como combinar rutas entre controladores y acciones. Por ejemplo:

```csharp
[Route("Home")]
public class HomeController : Controller
{
    [Route("")] // Combines to define the route template "Home"
    [Route("Index")] // Combines to define route template "Home/Index"
    [Route("/")] // Does not combine, defines the route template ""
    public IActionResult Index() {}
```

Se pueden especificar las rutas en [HttpGet] y separan los atributos similares, evitando la necesidad de agregar [ruta\] atributos. Rutas de atributo también pueden usar tokens para reducir la necesidad de repetir los nombres de acción o controlador, tal y como se muestra a continuación:

```csharp
[Route("[controller\]")]
public class ProductsController : Controller
{
    [Route("")] // Matches 'Products'
    [Route("Index")] // Matches 'Products/Index'
    public IActionResult Index()
}
```

Una vez que una determinada solicitud se ha asociado a una ruta, pero antes de la acción se denomina método, llevará a cabo MVC de ASP.NET Core [enlace de modelo](https://docs.microsoft.com/aspnet/core/mvc/models/model-binding) y [validación de modelos](https://docs.microsoft.com/aspnet/core/mvc/models/validation) en la solicitud. Enlace de modelos es responsable de convertir los datos entrantes de HTTP en los tipos de .NET especificados como parámetros del método de acción que se llame a. Por ejemplo, si el método de acción espera un parámetro de identificador de tipo int, el enlace de modelos intentará proporciona este parámetro de un valor que se proporciona como parte de la solicitud. Para ello, el enlace de modelos busca valores en un formulario expuesto, los valores en la misma ruta y los valores de cadena de consulta. Suponiendo que se encuentra un valor de identificador, se convertirá en un entero antes de que se pasa en el método de acción.

Después de enlazar el modelo, pero antes de llamar al método de acción, se produce la validación del modelo. Validación del modelo usa atributos opcionales en el tipo de modelo y puede ayudar a garantizar que el objeto de modelo proporcionado cumple determinados requisitos de datos. Ciertos valores se pueden especificar como necesario, o que estén limitadas a una longitud o un intervalo numérico determinados, etcetera. Si se especifican los atributos de validación, pero el modelo no cumple sus requisitos, la propiedad ModelState.IsValid será false y el conjunto de reglas de validación con errores estará disponible para enviar al cliente que realiza la solicitud.

Si usas la validación del modelo, debe ser siempre comprueba que el modelo es válido antes de realizar los comandos de modificación de estado, para asegurarse de que la aplicación no está dañada por datos no válidos. Puede usar un [filtro](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) para evitar la necesidad de agregar código para esto en cada acción. Filtros MVC de ASP.NET Core proporcionan una manera de interceptar los grupos de solicitudes, para que se pueden aplicar directivas comunes y preocupaciones transversales según un destino. Los filtros pueden aplicarse a las acciones individuales, controladores de todo o de forma global para una aplicación.

Para las API web, ASP.NET Core MVC admite [ *negociación de contenido*](https://docs.microsoft.com/aspnet/core/mvc/models/formatting), lo que permite las solicitudes especificar cómo se deben aplicar el formato de las respuestas. En función de los encabezados proporcionados en la solicitud, acciones devolver datos dará formato a la respuesta en XML, JSON o en otro formato compatible. Esta característica permite a la misma API ser usada por varios clientes con requisitos de formato de datos diferentes.

> ### <a name="references--mapping-requests-to-responses"></a>Referencias: asignar solicitudes a respuestas
> - **El enrutamiento a las acciones de controlador**
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/routing>
> - **Enlace de modelo** https://docs.microsoft.com/aspnet/core/mvc/models/model-binding
> - **Validación de modelos**
> <https://docs.microsoft.com/aspnet/core/mvc/models/validation>
> - **Filtros** https://docs.microsoft.com/aspnet/core/mvc/controllers/filters

## <a name="working-with-dependencies"></a>Trabajar con dependencias

ASP.NET Core tiene compatibilidad integrada para e internamente hace uso de una técnica conocida como [inyección de dependencia](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection). Inserción de dependencias es una técnica que habilita el acoplamiento flexible entre las distintas partes de una aplicación. Un acoplamiento más flexible es deseable, porque es más fácil aislar las partes de la aplicación, lo que permite probar o reemplazo. También resulta menos probable que un cambio en una parte de la aplicación tendrá un impacto inesperado en otro lugar de la aplicación. Inyección de dependencia se basa en el principio de la inversión de dependencia y, a menudo es clave para lograr el principio abierto o cerrado. Al evaluar el funcionamiento de la aplicación con sus dependencias, tenga cuidado de no la [estáticos adhesivos para sus](http://deviq.com/static-cling/) código olor y recordar la aforismo "[es una novedad adherencia](http://ardalis.com/new-is-glue)."

Estáticos adhesivos para sus se produce cuando las clases de realizan llamadas a métodos estáticos o tener acceso a propiedades estáticas, que tiene efectos secundarios o dependencias en la infraestructura. Por ejemplo, si tiene un método que llama a un método estático, que a su vez se escribe en una base de datos, el método está asociado estrechamente con la base de datos. Todo lo que interrumpe esa llamada de la base de datos interrumpirá el método. Estos métodos de prueba es muy difícil, ya que dichas pruebas exigir comerciales bibliotecas simulación para simular las llamadas estáticas o solo se pueden probar con una base de datos de prueba en su lugar. Llamadas estáticas que no tienen ninguna dependencia de infraestructura, sobre todo aquellas que son completamente independientes, son válidas llamar y no tienen ningún impacto en el acoplamiento o capacidad de prueba (más allá de acoplamiento código a la propia llamada estática).

Muchos desarrolladores comprender los riesgos de estáticos adhesivos para sus y estado global, pero se sigue estrechamente su código para implementaciones específicas a través de la creación directa de instancias. "Nueva es adherencia" está pensado para ser un aviso de este acoplamiento y no un condemnation general del uso de la palabra clave new. Al igual que con las llamadas de método estático, nuevas instancias de tipos que normalmente no tienen ninguna dependencia externa no estrechamente acoplar código a detalles de implementación o dificultar la prueba. Pero cada vez que se crea una instancia de una clase, tomar solo un breve momento a tener en cuenta si tiene sentido codificar esa instancia específica en esa ubicación concreta, o si sería un mejor diseño para solicitar dicha instancia como una dependencia.

### <a name="declare-your-dependencies"></a>Declarar las dependencias

Núcleo de ASP.NET se basa en tener métodos y clases declaran sus dependencias, cómo solicitarlos como argumentos. Las aplicaciones de ASP.NET normalmente se configuran en una clase de inicio, que a su vez está configurado para admitir la inserción de dependencias en varios puntos. Si la clase de inicio tiene un constructor, pueden solicitar las dependencias a través del constructor, de este modo:

```csharp
public class Startup
{
    public Startup(IHostingEnvironment env)
    {
        var builder = new ConfigurationBuilder()
        .SetBasePath(env.ContentRootPath)
        .AddJsonFile("appsettings.json", optional: false, reloadOnChange: true)
        .AddJsonFile(\$"appsettings.{env.EnvironmentName}.json", optional: true);
    }
}
```

La clase de inicio es interesante de que no hay ningún requisito de tipo explícito para él. No hereda de una clase base de inicio especial ni lo implemente cualquier interfaz determinada. Puede darle un constructor, o no, y puede especificar tantos parámetros en el constructor como desee. Cuando el host de web que ha configurado para la aplicación se inicia, llamará a la clase de inicio que se ha indicado que usar y usará la inserción de dependencias para rellenar las dependencias que requiere la clase de inicio. Por supuesto, si se solicitan los parámetros que no están configurados en el contenedor de servicios utilizado por ASP.NET Core, obtendrá una excepción, pero siempre que se respete las dependencias del contenedor conoce, puede solicitar que desee.

Inyección de dependencia se integra en las aplicaciones de ASP.NET Core desde el principio, cuando se crea la instancia de inicio. No detenga no existe para la clase de inicio. También puede solicitar las dependencias en el método Configure:

```csharp
public void Configure(IApplicationBuilder app,
    IHostingEnvironment env,
    ILoggerFactory loggerFactory)
{

}
```

El método ConfigureServices es la excepción a este comportamiento; debe tomar un solo parámetro de tipo IServiceCollection. Admite la inyección de dependencia, ya que por un lado es responsable de agregar objetos al contenedor de servicios, y en el otro tiene acceso a todos los servicios actualmente configurados a través del parámetro IServiceCollection realmente no es necesario. Por lo tanto, puede trabajar con dependencias definidas en la colección de servicios de ASP.NET Core en todas las partes de la clase de inicio, ya sea solicitando el servicio como un parámetro necesario o cuando se trabaja con el IServiceCollection en ConfigureServices.

> [!NOTE]
> Si necesita asegurarse determinados servicios estén disponibles para la clase de inicio, puede configurarlos mediante WebHostBuilder y el método ConfigureServices.

La clase de inicio es un modelo de cómo estructurar otras partes de la aplicación ASP.NET Core, controladores de middleware de filtros para sus propios servicios. En cada caso, debe seguir la [principio de dependencias explícitas](http://deviq.com/explicit-dependencies-principle/), solicitar las dependencias en lugar de directamente cómo crearlos y aprovechamiento de inserción de dependencias en toda la aplicación. Tenga cuidado de dónde y cómo se directamente crear instancias de implementaciones, especialmente los servicios y los objetos que funcionan con la infraestructura o tengan efectos secundarios. Prefiere trabajar con abstracciones definidas en el núcleo de la aplicación y se pasa como argumentos al codificar referencias a tipos de implementación específica.

## <a name="structuring-the-application"></a>Estructurar la aplicación

Aplicaciones monolíticas suelen tengan un único punto de entrada. En el caso de una aplicación web de ASP.NET Core, el punto de entrada será el proyecto web de ASP.NET Core. Sin embargo, eso no significa que la solución debe constar de simplemente un solo proyecto. Resulta útil dividir la aplicación en diferentes capas para seguir la separación de intereses. Una vez que se divide en capas, resulta útil ir más allá de las carpetas para separar los proyectos, que pueden ayudarle a conseguir una mejor encapsulación. El mejor método para lograr estos objetivos con una aplicación de ASP.NET Core es una variación de la arquitectura de limpieza se describe en el capítulo 5. Después de este enfoque, solución de la aplicación estará compuesta por bibliotecas independientes para la interfaz de usuario, la infraestructura y ApplicationCore.

Además de estos proyectos, proyectos de prueba independiente también se incluyen (pruebas se describen en el capítulo 9).

Modelo de objetos e interfaces de la aplicación deben colocarse en el proyecto ApplicationCore. Este proyecto tendrá el menor número de dependencias como sea posible, y los otros proyectos de la solución hará referencia a él. Las entidades empresariales que deban conservarse se definen en el proyecto ApplicationCore, como son servicios que no dependen directamente de infraestructura.

Detalles de implementación, por ejemplo, cómo se realiza la persistencia o cómo se pueden enviar notificaciones a un usuario, se mantienen en el proyecto de infraestructura. Este proyecto hará referencia a paquetes específico de la implementación como Entity Framework Core, pero no debe exponer los detalles acerca de estas implementaciones fuera del proyecto. Servicios de infraestructura y los repositorios deben implementar las interfaces que se definen en el proyecto ApplicationCore, y sus implementaciones de persistencia están responsables de recuperar y almacenar las entidades definidas en ApplicationCore.

El propio proyecto de ASP.NET Core es responsable de cualquier problema de nivel de interfaz de usuario, pero no debe incluir los detalles de infraestructura o de lógica empresarial. De hecho, idealmente no debería incluso tienen una dependencia en el proyecto de infraestructura, que le ayudará a garantizar que ninguna dependencia entre los dos proyectos se introdujo por accidente. Esto puede lograrse mediante un contenedor de DI de terceros como StructureMap, que le permite definir reglas de DI en clases de registro en cada proyecto.

Otro enfoque para desacoplar la aplicación de detalles de implementación es que el microservicios de llamada de aplicación, que quizás se implementan en los contenedores de Docker individuales. Esto proporciona incluso mayor separación de problemas y el desacoplamiento que aprovechan DI entre dos proyectos, pero tiene una complejidad adicional.

### <a name="feature-organization"></a>Organización de característica

De forma predeterminada, las aplicaciones de ASP.NET Core organizan su estructura de carpetas para que incluya controladores y vistas y con frecuencia ViewModels. Código de cliente para admitir estas estructuras de servidor normalmente se almacena por separado en la carpeta wwwroot. Sin embargo, las aplicaciones grandes pueden surgir problemas con esta organización, puesto que funciona en cualquier característica determinada a menudo requiere saltar entre estas carpetas. De esta forma obtiene cada vez más difícil a medida que aumenta el número de archivos y subcarpetas en cada carpeta, lo que da lugar a una gran cantidad de desplazarse a través del explorador de soluciones. Una solución a este problema consiste en organizar el código de aplicación por *característica* en lugar de por tipo de archivo. Este estilo profesional se conoce normalmente como carpetas de características o intervalos de característica (Vea también: [segmentos verticales](http://deviq.com/vertical-slices/)).

Núcleo de ASP.NET MVC admite áreas para este propósito. Uso de áreas, puede crear un conjunto independiente de controladores y vistas carpetas (así como los modelos asociados) en cada carpeta de área. Figura 7-1 muestra una estructura de carpetas de ejemplo, el uso de áreas.

![](./media/image7-1.png)

Organización de área de ejemplo de la figura 7-1

Al utilizar áreas, debe utilizar atributos para decorar los controladores con el nombre del área a la que pertenecen:

```csharp
[Area("Catalog")]
public class HomeController
{}
```

También debe agregar compatibilidad de área para sus rutas:

```csharp
app.UseMvc(routes =>
{
    // Areas support
    routes.MapRoute(
    name: "areaRoute",
    template: "{area:exists}/{controller=Home}/{action=Index}/{id?}");
    routes.MapRoute(
    name: "default",
    template: "{controller=Home}/{action=Index}/{id?}");
});
```

Además de la compatibilidad integrada para las áreas, también puede utilizar su propia estructura de carpetas y convenciones en lugar de atributos y las rutas personalizadas. Esto le permitiría tener carpetas de características que no incluyen carpetas independientes para las vistas, controladores, etc., manteniendo la jerarquía más plana y facilitando la tarea ver que todos los archivos en un único lugar para cada característica relacionados.

ASP.NET Core usa tipos integrados convención para controlar su comportamiento. Puede modificar o reemplazar estas convenciones. Por ejemplo, puede crear una convención que obtendrá automáticamente el nombre de característica para un controlador determinado en función de su espacio de nombres (que normalmente se correlaciona con la carpeta en la que se encuentra el controlador):

```csharp
FeatureConvention : IControllerModelConvention
{
    public void Apply(ControllerModel controller)
    {
        controller.Properties.Add("feature",
        GetFeatureName(controller.ControllerType));
    }

    private string GetFeatureName(TypeInfo controllerType)
    {
        string[] tokens = controllerType.FullName.Split('.');
        if (!tokens.Any(t => t == "Features")) return "";
        string featureName = tokens
        .SkipWhile(t => !t.Equals("features",
        StringComparison.CurrentCultureIgnoreCase))
        .Skip(1)
        .Take(1)
        .FirstOrDefault();
        return featureName;
    }
}
```

A continuación, especifique esta convención como una opción al agregar compatibilidad para MVC a la aplicación en ConfigureServices:

```csharp
services.AddMvc(o => o.Conventions.Add(new FeatureConvention()));
```

Núcleo de ASP.NET MVC también usa una convención localizar vistas. Puede reemplazarlo con una convención personalizada para que las vistas se ubicará en las carpetas de característica (mediante el nombre de la característica proporcionado por el FeatureConvention, anteriormente). Puede obtener más información sobre este enfoque y descargar un ejemplo funcional desde el artículo de MSDN, [segmentos de la característica de MVC de ASP.NET Core](https://msdn.microsoft.com/magazine/mt763233.aspx).

### <a name="cross-cutting-concerns"></a>Problemas de corte del cruce

Medida que desarrolle aplicaciones, resulta cada vez más importante separe preocupaciones transversales para eliminar la duplicación y mantener su coherencia. Algunos ejemplos de preocupaciones transversales en aplicaciones de ASP.NET Core son autenticación, las reglas de validación del modelo, el almacenamiento en caché de salida y control de errores, aunque hay muchas otras. Núcleo de ASP.NET MVC [filtros](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) permite ejecutar código antes o después de algunos pasos de la canalización de procesamiento de la solicitud. Por ejemplo, un filtro puede ejecutarse antes y después enlace del modelo, antes y después de una acción, o antes y después de resultado de la acción. También puede utilizar un filtro de autorización para controlar el acceso al resto de la canalización. Las figuras 7-2 se muestra cómo solicitar flujos de ejecución a través de filtros, si ha configurado.

![La solicitud se procesa a través de los filtros de autorización, filtros de recursos, enlace de modelos, filtros de acción, ejecución de acciones y conversión del resultado de acción, los filtros de excepción, filtros de resultados y ejecución de resultado. A la salida, solo se procesa la solicitud por filtros de resultados y los filtros de recursos antes de convertirse en una respuesta que se envía al cliente.](./media/image7-2.png)

Ejecución de la solicitud de la figura 7-2 a través de los filtros y la canalización de solicitud.

Normalmente, los filtros se implementan como atributos, para que pueda aplicar controladores o acciones. Cuando se agrega de esta forma, los filtros especificados en la invalidación de nivel de acción o se basan en filtros especificados en el nivel de controlador, que a su vez invalidar filtros globales. Por ejemplo, el \[ruta\] atributo se puede usar para crear rutas entre controladores y acciones. Del mismo modo, autorización se puede configurar en el nivel de controlador y, a continuación, se reemplaza por acciones individuales, como se muestra en el ejemplo siguiente:

```csharp
[Authorize]
public class AccountController : Controller

{
    [AllowAnonymous]
    public async Task<IActionResult> Login() {}
    public async Task<IActionResult> ForgotPassword() {}
}
```

El primer método, inicio de sesión, utiliza el filtro de AllowAnonymous (atributo) para invalidar el filtro de autorización establecido en el nivel de controlador. La acción de contraseña olvidada (y cualquier otra acción en la clase que no tiene un atributo AllowAnonymous) requerirá una solicitud autenticada.

Filtros pueden usarse para eliminar la duplicación en forma de control directivas para las API de errores comunes. Por ejemplo, una directiva de API típica es devolver una respuesta NotFound a las solicitudes que hacen referencia a las claves que no existen y una respuesta BadRequest si se produce un error de validación del modelo. El ejemplo siguiente muestra estas dos directivas en acción:

```csharp
[HttpPut("{id}")]
public async Task<IActionResult> Put(int id, [FromBody]Author author)
{
    if ((await _authorRepository.ListAsync()).All(a => a.Id != id))
    {
        return NotFound(id);
    }
    if (!ModelState.IsValid)
    {
        return BadRequest(ModelState);
    }
    author.Id = id;
    await _authorRepository.UpdateAsync(author);
    return Ok();
}
```

No se permiten los métodos de acción a llenarse con condicional código similar al siguiente. En su lugar, extraer las directivas en los filtros que se pueden aplicar según sea necesario. En este ejemplo, la comprobación de validación del modelo, lo que puede ocurrir siempre que se envía un comando a la API, puede reemplazarse por el atributo siguiente:

```csharp
public class ValidateModelAttribute : ActionFilterAttribute
{
    public override void OnActionExecuting(ActionExecutingContext context)
    {
        if (!context.ModelState.IsValid)
        {
            context.Result = new BadRequestObjectResult(context.ModelState);
        }
    }
}
```

Del mismo modo, puede utilizar un filtro para comprobar si un registro existe y devolver un error 404 antes de ejecuta la acción, lo que elimina la necesidad de realizar estas comprobaciones en la acción. Una vez que ha extraído las convenciones comunes y organizan la solución para separar la lógica de negocio y código de infraestructura de la interfaz de usuario, los métodos de acción de MVC deben ser sumamente ligero:

```csharp
// PUT api/authors/2/5
[HttpPut("{id}")]
[ValidateAuthorExists]
public async Task<IActionResult> Put(int id, [FromBody]Author author)
{
    await _authorRepository.UpdateAsync(author);
    return Ok();
}
```

Puede leer más sobre la implementación de filtros y descargar un ejemplo funcional desde el artículo de MSDN, [Real World ASP.NET Core MVC filtros](https://msdn.microsoft.com/magazine/mt767699.aspx).

> ### <a name="references--structuring-applications"></a>Referencias: estructura de aplicaciones
> - **Áreas**  
> <https://docs.Microsoft.com/ASPNET/Core/MVC/Controllers/Areas>
> - **MSDN: sectores de características principales de ASP.NET MVC**
>  <https://msdn.microsoft.com/magazine/mt763233.aspx>
> - **Filtros**  
> <https://docs.Microsoft.com/ASPNET/Core/MVC/Controllers/Filters>
> - **MSDN: filtros MVC de ASP.NET Core mundo Real**  
> <https://msdn.Microsoft.com/magazine/mt767699.aspx>

## <a name="security"></a>Seguridad

Proteger aplicaciones web es un tema grande, con muchas consideraciones. En su nivel más básico, seguridad, hay que asegurarse de que saber quién es procedentes de una solicitud determinada y, a continuación, asegurarse de que dicha solicitud solo tiene acceso a los recursos que debería. La autenticación es el proceso de comparación de las credenciales proporcionadas con una solicitud a los de un almacén de datos de confianza, para ver si la solicitud se debe tratar como procedente de una entidad conocida. La autorización es el proceso de restringir el acceso a determinados recursos en función de la identidad del usuario. Un problema de seguridad de terceros protege las solicitudes contra el espionaje por terceros, para el que debe al menos [Asegúrese de que la aplicación usa SSL](https://docs.microsoft.com/aspnet/core/security/enforcing-ssl).

### <a name="authentication"></a>Autenticación

Identidad de ASP.NET Core es un sistema de pertenencia que puede utilizar para admitir la funcionalidad de inicio de sesión para la aplicación. Tiene compatibilidad con cuentas de usuario locales, así como compatibilidad con proveedores de inicio de sesión externo desde proveedores como Microsoft Account, Twitter, Facebook, Google y mucho más. Además de ASP.NET Core Identity, la aplicación puede utilizar la autenticación de windows o un proveedor de identidades de terceros, como [Identity Server](https://github.com/IdentityServer/IdentityServer4).

Identidad de ASP.NET Core se incluye en las nuevas plantillas de proyecto si se selecciona la opción de cuentas de usuario individuales. Esta plantilla incluye compatibilidad para el registro, inicio de sesión, los inicios de sesión externos, el olvido de contraseñas y una funcionalidad adicional.

![](./media/image7-3.png)

Figura 7-3 seleccionar cuentas de usuario individuales dispongan de identidad preconfigurado.

Compatibilidad con identidad se configura en Inicio, tanto en ConfigureServices y configurar:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // Add framework services.
    services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
    .AddEntityFrameworkStores<ApplicationDbContext>()
    .AddDefaultTokenProviders();
    services.AddMvc();
}

public void Configure(IApplicationBuilder app)
{
    app.UseStaticFiles();
    app.UseIdentity();
    app.UseMvc(routes =>
    {
        routes.MapRoute(
        name: "default",
        template: "{controller=Home}/{action=Index}/{id?}");
    });
}
```

Es importante que UseIdentity aparecen antes de UseMvc en el método Configure. Al configurar la identidad en ConfigureServices, observará una llamada a AddDefaultTokenProviders. Esto no tiene nada que ver con tokens que pueden utilizarse para proteger las comunicaciones web, pero en su lugar, hace referencia a los proveedores que crean solicitudes que se pueden enviar a los usuarios a través de SMS o correo electrónico puedan confirmar su identidad.

Puede obtener más información acerca de [configuración de autenticación en dos fases](https://docs.microsoft.com/aspnet/core/security/authentication/2fa) y [habilitar proveedores de inicio de sesión externo](https://docs.microsoft.com/aspnet/core/security/authentication/social/) de los documentos de ASP.NET Core oficiales.

### <a name="authorization"></a>Autorización

La forma más sencilla de autorización implica restringir el acceso a los usuarios anónimos. Esto puede lograrse mediante la aplicación simplemente la \[Authorize\] atributo a ciertos controladores o acciones. Si se usan funciones, se puede ampliar aún más el atributo para restringir el acceso a los usuarios que pertenecen a determinados roles, tal como se muestra:

```csharp
[Authorize(Roles = "HRManager,Finance")]
public class SalaryController : Controller
{

}
```

En este caso, los usuarios que pertenecen a los roles HRManager o finanzas (o ambos) pueda tener acceso a la SalaryController. Para requerir que un usuario pertenece a varios roles (no solo uno de varios), puede aplicar el atributo varias veces, especificar un rol necesario cada vez.

Especifican ciertos conjuntos de funciones como cadenas en muchas diferentes controladores y acciones pueden dar lugar a repetición no deseado. Puede configurar directivas de autorización, que encapsula las reglas de autorización, y, a continuación, especificar la directiva en lugar de los roles individuales al aplicar el \[Authorize\] atributo:

```csharp
[Authorize(Policy = "CanViewPrivateReport")]
public IActionResult ExecutiveSalaryReport()
{
    return View();
}
```

Con las directivas de esta manera, puede separar los tipos de acciones que se está restringidos de las reglas que se aplican a él o roles específicos. Más adelante, si crea un nuevo rol que necesita tener acceso a determinados recursos, puede simplemente actualizar una directiva, en lugar de actualizar cada lista de roles en cada \[Authorize\] atributo.

#### <a name="claims"></a>Notificaciones

Las notificaciones son pares nombre-valor que representan las propiedades de un usuario autenticado. Por ejemplo, podría almacenar el número de empleado de los usuarios como una notificación. Notificaciones, a continuación, pueden utilizarse como parte de las directivas de autorización. Puede crear una directiva denominada "EmployeeOnly" que requiere la existencia de una notificación denominada "EmployeeNumber", como se muestra en este ejemplo:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc();
    services.AddAuthorization(options =>
    {
        options.AddPolicy("EmployeeOnly", policy => policy.RequireClaim("EmployeeNumber"));
    });
}
```

Esta directiva puede usarse con el \[Authorize\] atributo para proteger cualquier controlador o acción, como se describió anteriormente.

#### <a name="securing-web-apis"></a>Proteger las API Web

Las API de web mayoría deben implementar un sistema de autenticación basado en tokens. Autenticación de token es sin estado y está diseñada para que sea escalable. En un sistema basado en tokens de autenticación, el cliente debe autenticarse primero con el proveedor de autenticación. Si se realiza correctamente, el cliente emite un token, que es simplemente una cadena criptográficamente significativa de caracteres. Cuando el cliente, a continuación, necesita emitir una solicitud a una API, agrega este token como un encabezado en la solicitud. El servidor, a continuación, valida el token que se encuentra en el encabezado de solicitud antes de completar la solicitud. Figura 7-4 se muestra este proceso.

![TokenAuth](./media/image7-4.png)

**Figura 7-4.** Autenticación basada en token para las API Web.

> ### <a name="references--security"></a>Referencias: seguridad
> - **Información general de documentos de seguridad**  
> https://docs.Microsoft.com/ASPNET/Core/Security/
> - **Exigir SSL en una aplicación ASP.NET básica**  
> <https://docs.Microsoft.com/ASPNET/Core/Security/enforcing-SSL>
> - **Introducción a Identity**  
> <https://docs.Microsoft.com/ASPNET/Core/Security/Authentication/Identity>
> - **Introducción a la autorización**  
> <https://docs.Microsoft.com/ASPNET/Core/Security/Authorization/Introduction>
> - **Autenticación y autorización para las aplicaciones de API de servicio de aplicaciones de Azure**  
> <https://docs.Microsoft.com/Azure/App-Service-API/App-Service-API-Authentication>

## <a name="client-communication"></a>Comunicación de cliente

Además de servir páginas y responde a las solicitudes de datos a través de las API web, aplicaciones de ASP.NET Core pueden comunicarse directamente con los clientes conectados. Esta comunicación saliente puede utilizar una amplia variedad de tecnologías de transporte, siendo los más comunes WebSockets. Núcleo de ASP.NET SignalR es una biblioteca que simplifica el proceso para el tipo de funcionalidad de comunicación de servidor a cliente en tiempo real a sus aplicaciones. SignalR admite una variedad de tecnologías de transporte, incluyendo WebSockets y abstrae alejadas varios de los detalles de implementación del programador.

Núcleo de ASP.NET SignalR está actualmente en fase de desarrollo y estará disponible en la próxima versión de ASP.NET Core. Sin embargo, otros [Abrir origen WebSockets bibliotecas](https://github.com/radu-matei/websocket-manager) están disponibles actualmente.

Comunicación de cliente en tiempo real, si usando WebSockets directamente u otras técnicas, son útiles en una variedad de escenarios de aplicación. Estos son algunos ejemplos:

-   Aplicaciones de salón de chat en vivo

-   Supervisión de aplicaciones

-   Actualizaciones de progreso de trabajo

-   Notificaciones

-   Aplicaciones de formularios interactivos

Al compilar la comunicación de cliente en las aplicaciones, normalmente hay dos componentes:

-   Administrador de conexiones de servidor (concentrador de SignalR, WebSocketManager WebSocketHandler)

-   Biblioteca de cliente

Los clientes no están limitados a los exploradores, aplicaciones móviles, aplicaciones de consola, y otras aplicaciones nativas también pueden comunicarse con SignalR/WebSockets. El programa simple siguiente devuelve todo el contenido enviado a una aplicación de chat en la consola, como parte de una aplicación de ejemplo WebSocketManager:

```csharp
public class Program
{
    private static Connection _connection;
    public static void Main(string[] args)
    {
        StartConnectionAsync();
        _connection.On("receiveMessage", (arguments) =>;
        {
            Console.WriteLine(\$"{arguments\[0\]} said: {arguments\[1\]}");
        });
        Console.ReadLine();
        StopConnectionAsync();
    }
    
    public static async Task StartConnectionAsync()
    {
        _connection = new Connection();
        await _connection.StartConnectionAsync("ws://localhost:65110/chat");
    }
    
    public static async Task StopConnectionAsync()
    {
        await _connection.StopConnectionAsync();
    }
```

Considere la posibilidad de experimentan maneras en que las aplicaciones comunican directamente con aplicaciones de cliente, tenga en cuenta si la comunicación en tiempo real mejoraría el usuario de la aplicación.

> ### <a name="references--client-communication"></a>Referencias: la comunicación del cliente
> - **Núcleo de ASP.NET SignalR**  
> <https://github.com/ASPNET/SignalR>
> - **Administrador de WebSocket**  
> https://github.com/Radu-matei/websocket-Manager

## <a name="domain-driven-design--should-you-apply-it"></a>¿Diseño – controlada por el dominio debe aplicarla?

Diseño controlada por el dominio (DDD) es un enfoque de agile para la creación de software que resalta centrarse en el *dominio de negocio*. Coloca un gran énfasis en la comunicación e interacción con expert(s) de dominio de negocio que se puede asociar a los desarrolladores de cómo funciona el sistema del mundo real. Por ejemplo, si está creando un sistema que controla las operaciones estándar, su experto de dominio puede ser un intermediario de cotizaciones con experiencia. DDD está diseñado para resolver problemas empresariales grandes y complejas y a menudo no es adecuado para aplicaciones pequeñas y sencillas, como la inversión en la descripción y el dominio de modelado no vale la pena.

Al compilar software sigue un enfoque DDD, su equipo (incluidas las partes interesadas no técnicas y colaboradores) se debe desarrollar un *lenguaje ubicuo* para el problema de espacio. Es decir, debe utilizarse la misma terminología para las estructuras que podrían existir para conservar el concepto (por ejemplo, tablas de base de datos), el equivalente de software y el concepto del mundo real que se está modelando. Por lo tanto, los conceptos descritos en el lenguaje ubicuo deberían ser la base para su *modelo de dominio*.

El modelo de dominio se compone de objetos que interactúan entre sí para representar el comportamiento del sistema. Estos objetos pueden estar en las siguientes categorías:

-   [Entidades](http://deviq.com/entity/), que representan objetos con un subproceso de identidad. Las entidades se almacenan normalmente en la persistencia con una clave por el que puede recuperar después.

-   [Agregados](http://deviq.com/aggregate-pattern/), que representan grupos de objetos que se deben conservar como una unidad.

-   [Objetos de valor](http://deviq.com/value-object/), que representan los conceptos que se pueda comparar basándose en la suma de los valores de propiedad. Por ejemplo, DateRange que consta de una fecha de inicio y finalización.

-   [Eventos de dominio](https://martinfowler.com/eaaDev/DomainEvent.html), que representan lo que ocurre en el sistema que resulten de interés a otras partes del sistema.

Tenga en cuenta que un modelo de dominio DDD debe encapsular un comportamiento complejo dentro del modelo. Las entidades, en particular, no debe simplemente colecciones de propiedades. Cuando el modelo de dominio no tiene comportamiento y simplemente representa el estado del sistema, se dice que un [anemic modelo](http://deviq.com/anemic-model/), que no es deseable en DDD.

Además de estos tipos de modelo, DDD normalmente emplea una variedad de modelos:

-   [Repositorio](http://deviq.com/repository-pattern/), para resumiendo los detalles de persistencia.

-   [Generador](https://en.wikipedia.org/wiki/Factory_method_pattern), para encapsular la creación de objetos complejos.

-   Eventos de dominio, separe el comportamiento dependiente de desencadenar el comportamiento.

-   [Servicios](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/), para encapsular un comportamiento complejo o detalles de la implementación de infraestructura.

-   [Comando](https://en.wikipedia.org/wiki/Command_pattern), para separar emitir comandos y ejecutar el comando propio.

-   [Especificación de](http://deviq.com/specification-pattern/), para encapsular los detalles de la consulta.

DDD también recomienda el uso de la arquitectura de limpieza se ha descrito anteriormente, lo que permite un acoplamiento, encapsulación y el código que se pueda comprobar fácilmente utilizando pruebas unitarias.

### <a name="when-should-you-apply-ddd"></a>¿Cuándo debe aplicar DDD

DDD es ideal para aplicaciones de gran tamaño con complejidad significativos para el negocio (no sólo técnicas). La aplicación debe requieren el conocimiento de expertos de dominio. Debe haber un comportamiento importante en el modelo de dominio, que representa las reglas de negocios e interacciones más allá de simplemente almacenar y recuperar el estado actual de registros de diversos almacenes de datos.

### <a name="when-shouldnt-you-apply-ddd"></a>Cuando no debería aplicar DDD

DDD implica la inversión ya realizada en el modelado, la arquitectura y comunicación que no puede garantizarse para pequeñas aplicaciones o las aplicaciones que son esencialmente simplemente CRUD (crear/leer/actualizar/eliminar). Si decide enfocar la aplicación siga DDD, pero descubre que el dominio tiene un modelo anemic con ningún comportamiento, necesitará reconsiderar su enfoque. La aplicación no necesita DDD, o puede que necesite asistencia refactorizar la aplicación para encapsular la lógica de negocios en el modelo de dominio, en lugar de en la interfaz de usuario o la base de datos.

Un enfoque híbrido sería usar solo DDD para las áreas más complejas o transaccionales de la aplicación, pero no para CRUD más sencillo o partes de solo lectura de la aplicación. Por ejemplo, no necesitan tener las restricciones de un agregado si está consultando datos para mostrar un informe o para visualizar los datos para un panel. Es absolutamente aceptable tener un modelo independiente y más fácil lectura para dichos requisitos.

> ### <a name="references--domain-driven-design"></a>Referencias: diseño basado en dominio
> - **DDD en términos sencillos (StackOverflow respuesta)**  
> <https://StackOverflow.com/Questions/1222392/CAN-someone-EXPLAIN-Domain-Driven-Design-ddd-in-Plain-English-Please/1222488#1222488>

## <a name="deployment"></a>Implementación

Hay unos pocos pasos implicados en el proceso de implementación de la aplicación de ASP.NET Core, independientemente de donde se hospedará. Es el primer paso publicar la aplicación, lo que puede hacer con el dotnet publicar el comando de CLI. Se compila la aplicación y se colocarán todos los archivos necesarios para ejecutar la aplicación en una carpeta designada. Cuando se implementa desde Visual Studio, este paso se realiza automáticamente. La carpeta de publicación contiene archivos .exe y .dll para la aplicación y sus dependencias. Una aplicación independiente también incluirá una versión de .NET runtime. Las aplicaciones de ASP.NET Core también incluyen archivos de configuración, activos de cliente estático y las vistas de MVC.

Las aplicaciones de ASP.NET Core son aplicaciones de consola que se deben iniciar cuando el servidor se inicia y se reinicia si se bloquea la aplicación (o servidor). Un administrador de procesos se puede utilizar para automatizar este proceso. Los administradores de proceso más comunes para ASP.NET Core son Nginx y Apache en Linux y IIS o el servicio de Windows en Windows.

Además de un administrador de procesos, las aplicaciones de ASP.NET Core hospedadas en el servidor de web Kestrel deben usar un servidor proxy inverso. Un servidor proxy inverso recibe las solicitudes HTTP de internet y reenvía a Kestrel después de un control preliminar. Servidores proxy inversos proporcionan un nivel de seguridad para la aplicación y son necesarios para las implementaciones de borde (expuestas al tráfico de Internet). Kestrel es relativamente nuevo y todavía no ofrece defensas frente a ciertos ataques. Kestrel también no admiten el hospedaje de varias aplicaciones en el mismo puerto, por lo que no se puede usar técnicas como encabezados de host con él para habilitar el hospedaje de varias aplicaciones en el mismo puerto y dirección IP.

![Kestrel a Internet](./media/image7-5.png)

Figura 7-5 ASP.NET hospedados en Kestrel detrás de un servidor proxy inverso

Es otro escenario en el que un proxy inverso puede ser útil proteger varias aplicaciones que usan SSL/HTTPS. En este caso, solo el proxy inverso necesitaría tener SSL configurado. Comunicación entre el servidor proxy inverso y Kestrel llevara a cabo a través de HTTP, como se muestra en la figura 7-6.

![](./media/image7-6.png)

Figura 7-6 ASP.NET hospedados detrás de un servidor proxy inverso protegidas mediante HTTPS

Un enfoque cada vez más popular que se va a hospedar la aplicación de ASP.NET Core en un contenedor de Docker, que a continuación, se hospeda localmente o implementar en Azure para hospedar en la nube. El contenedor Docker podría contener el código de aplicación que se ejecuta en Kestrel y se implementaría detrás de un servidor proxy inverso, como se indicó anteriormente.

Si está hospedando la aplicación en Azure, puede usar la puerta de enlace de aplicaciones de Microsoft Azure como un dispositivo virtual dedicado para proporcionar varios servicios. Además de actuar como un proxy inverso para las aplicaciones individuales, puerta de enlace de aplicación también puede ofrecer las siguientes características:

-   Equilibrio de carga HTTP

-   Descarga SSL (SSL solo para Internet)

-   SSL de extremo a extremo

-   Enrutamiento de varios sitios (consolidar hasta 20 sitios en una sola puerta de enlace de aplicaciones)

-   Servidor de aplicaciones Web

-   Compatibilidad con websocket para

-   Diagnósticos avanzados

*Más información acerca de las opciones de implementación de Azure en el capítulo 10.*

> ### <a name="references--deployment"></a>Referencias: implementación
> - **Información general de implementación y hospedaje**  
> <https://docs.Microsoft.com/ASPNET/Core/Publishing/>
> - **Cuándo utilizar Kestrel con un proxy inverso**  
> <https://docs.Microsoft.com/ASPNET/Core/Fundamentals/Servers/kestrel#When-to-Use-kestrel-with-a-Reverse-proxy>
> - **Host de aplicaciones de ASP.NET Core en Docker**  
> <https://docs.Microsoft.com/ASPNET/Core/Publishing/docker>
> - **Introducción a la puerta de enlace de aplicación de Azure**  
> <https://docs.Microsoft.com/Azure/Application-Gateway/Application-Gateway-Introduction>

>[!div class="step-by-step"]
[Anterior] (común-client-lado-web-technologies.md) [siguiente] (work-with-data-in-asp-net-core-apps.md)
