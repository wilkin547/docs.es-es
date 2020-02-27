---
title: Desarrollo de aplicaciones ASP.NET Core MVC
description: Diseño de aplicaciones web modernas con ASP.NET Core y Azure | Desarrollo de aplicaciones ASP.NET Core MVC
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: a18b4dfc60c7d3971136f73f333b7225735710b3
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503947"
---
# <a name="develop-aspnet-core-mvc-apps"></a>Desarrollo de aplicaciones ASP.NET Core MVC

> "No es importante hacerlo bien la primera vez. Es sumamente importante hacerlo bien la última vez".  
> _- Andrew Hunt y David Thomas_

ASP.NET Core es un marco multiplataforma de código abierto para compilar aplicaciones web modernas optimizadas para la nube. Las aplicaciones ASP.NET Core son ligeras y modulares, con compatibilidad integrada para la inserción de dependencias, lo que permite una mayor capacidad de prueba y mantenimiento. Al combinarlo con MVC, que admite la creación de API web modernas además de aplicaciones basadas en vistas, ASP.NET Core es un marco eficaz con el que compilar aplicaciones web empresariales.

## <a name="mvc-and-razor-pages"></a>MVC y Razor Pages

ASP.NET Core MVC ofrece muchas características que son útiles para crear API y aplicaciones basadas en web. El término MVC significa "Modelo-Vista-Controlador", un patrón de interfaz de usuario que divide las responsabilidades de responder a las solicitudes de los usuarios en varias partes. Además de seguir este patrón, también puede implementar características en sus aplicaciones ASP.NET Core, como Razor Pages. Razor Pages está integrado en ASP.NET Core MVC y usa las mismas características de enrutamiento, enlace de modelos, etcétera. Pero, en lugar de tener archivos y carpetas independientes para los controladores, las vistas y otros elementos, y usar el enrutamiento basado en atributos, Razor Pages se coloca en una sola carpeta ("/ Páginas"). La ruta se basa en su ubicación relativa en la carpeta, y las solicitudes se controlan mediante controladores en lugar de acciones de controlador.

Al crear una aplicación ASP.NET Core, debe tener un plan en cuenta para el tipo de aplicación que quiera crear. En Visual Studio, podrá elegir entre varias plantillas. Las tres plantillas de proyecto más comunes son API web, Aplicación web y Aplicación web (Modelo-Vista-Controlador). Aunque solo puede tomar esta decisión al crear un proyecto, no es irrevocable. El proyecto API web usa controladores de Modelo-Vista-Controlador estándar; simplemente carece de las vistas de forma predeterminada. Del mismo modo, la plantilla predeterminada Aplicación web usa Razor Pages, por lo que también carece de la carpeta de vistas. Puede agregar la carpeta de vistas para estos proyectos más adelante para admitir el comportamiento basado en vistas. Los proyectos de tipo API web y Modelo-Vista-Controlador no incluyen la carpeta de páginas de forma predeterminada, pero puede agregar una más tarde para admitir el comportamiento basado en Razor Pages. Estos tres tipos de plantilla están diseñados para tres tipos de interacción predeterminada del usuario distintos: datos (API web), basada en páginas y basada en vistas. Si lo desea, puede combinar cualquiera de estos tipos en un mismo proyecto.

### <a name="why-razor-pages"></a>¿Por qué Razor Pages?

Razor Pages es el método predeterminado para nuevas aplicaciones web en Visual Studio. Razor Pages ofrece una manera más fácil de crear características de aplicaciones basadas en páginas, como los formularios que no son de aplicaciones de página única. Al usar controladores y vistas, era habitual que las aplicaciones tuvieran controladores muy grandes que funcionaban con varias dependencias y varios modelos de vista distintos, así como que devolvieran muchas vistas diferentes. Esto generaba una mayor complejidad y, a menudo, controladores que no seguían el principio de responsabilidad única o los principios de apertura y cierre de forma eficaz. Razor Pages soluciona este problema, ya que encapsula la lógica del lado servidor para una determinada "página" lógica en una aplicación web con el marcado de Razor. Una página de Razor que no tenga ninguna lógica del lado servidor simplemente puede constar de un archivo Razor (por ejemplo, "Index.cshtml"). Sin embargo, la mayoría de Razor Pages no triviales tendrá una clase de modelo de página asociado, que, por convención, tendrá el mismo nombre que el archivo Razor con una extensión ".cs" (por ejemplo, "Index.cshtml.cs").

Un modelo de página de Razor Pages combina las responsabilidades de un controlador de MVC y un modelo de vista. En lugar de controlar las solicitudes con los métodos de acción de controlador, se ejecutan los controladores de modelo de página, como "OnGet()", con lo que se representa la página asociada de forma predeterminada. Razor Pages simplifica el proceso de compilar páginas individuales en la aplicación ASP.NET Core sin dejar de proporciona todas las características arquitectónicas de ASP.NET Core MVC. Es una buena opción predeterminada para la nueva funcionalidad basada en páginas.

### <a name="when-to-use-mvc"></a>Cuándo usar MVC

Si va a crear API web, el patrón MVC tiene más sentido que Razor Pages. Si el proyecto va a exponer solo los puntos de conexión de la API Web, lo ideal es empezar a partir de la plantilla de proyecto de API web. De lo contrario, es fácil agregar controladores y puntos de conexión de API asociados a cualquier aplicación ASP.NET Core. Use el método MVC basado en vista si quiere realizar la migración de una aplicación existente de ASP.NET MVC 5 o versiones anteriores a ASP.NET Core MVC y quiere hacerlo de la forma más fácil posible. Una vez que haya realizado la migración inicial, podrá evaluar si tiene sentido adoptar Razor Pages para las nuevas características o incluso como una migración general.

Si opta por crear su aplicación web mediante Razor Pages o las vistas de MVC, la aplicación tendrá un rendimiento similar e incluirá compatibilidad con la inserción de dependencias, los filtros, el enlace de modelos, la validación y otras características.

## <a name="mapping-requests-to-responses"></a>Asignación de solicitudes a respuestas

En su núcleo, las aplicaciones ASP.NET Core asignan las solicitudes entrantes a las respuestas salientes. En un nivel bajo, esto se realiza mediante software intermedio y las aplicaciones y microservicios sencillos de ASP.NET Core pueden constar únicamente de software intermedio personalizado. Cuando se usa ASP.NET Core MVC, se puede trabajar en un cierto nivel superior y pensar en términos de _rutas_, _controladores_ y _acciones_. Cada solicitud entrante se compara con la tabla de enrutamiento de la aplicación y, si se encuentra una ruta coincidente, se llama al método de acción asociado (perteneciente a un controlador) para controlar la solicitud. Si no se encuentra ninguna ruta que coincida, se llama a un controlador de errores (en este caso, se devuelve un resultado de NotFound).

Las aplicaciones ASP.NET Core MVC pueden usar rutas convencionales, rutas de atributo o las dos. Las rutas convencionales se definen en el código, especificando _convenciones_ de enrutamiento con una sintaxis similar a la del ejemplo siguiente:

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapControllerRoute(name: "default", pattern: "{controller=Home}/{action=Index}/{id?}");
});
```

En este ejemplo, se agregó una ruta con el nombre "default" a la tabla de enrutamiento. Define una plantilla de ruta con marcadores de posición para _controlador_, _acción_ e _identificador_. Los marcadores de posición de acción y controlador tienen el valor predeterminado especificado ("Home" e "Index", respectivamente), y el marcador de posición del identificador es opcional (en virtud de la aplicación de "?"). La convención que se define aquí indica que la primera parte de una solicitud se debe corresponder al nombre del controlador, la segunda parte a la acción y después, si es necesario, una tercera parte representará un parámetro de identificador. Las rutas convencionales normalmente se definen en un solo lugar para la aplicación, por ejemplo, en el método Configure de la clase Startup.

Las rutas de atributo se aplican directamente a los controladores y acciones, en lugar de especificarse globalmente. Esto tiene la ventaja de que son mucho más sencillas de detectar cuando se examina un método concreto, pero significa que la información de enrutamiento no se mantiene en un lugar de la aplicación. Con las rutas de atributo, se pueden especificar fácilmente varias rutas para una acción determinada, así como combinar rutas entre controladores y acciones. Por ejemplo:

```csharp
[Route("Home")]
public class HomeController : Controller
{
    [Route("")] // Combines to define the route template "Home"
    [Route("Index")] // Combines to define route template "Home/Index"
    [Route("/")] // Does not combine, defines the route template ""
    public IActionResult Index() {}
}
```

Las rutas se pueden especificar en atributos [HttpGet] y similares, evitando la necesidad de agregar atributos [Route] independientes. Las rutas de atributo también pueden usar tokens para reducir la necesidad de repetir los nombres de acciones o controladores, como se muestra a continuación:

```csharp
[Route("[controller]")]
public class ProductsController : Controller
{
    [Route("")] // Matches 'Products'
    [Route("Index")] // Matches 'Products/Index'
    public IActionResult Index() {}
}
```

Razor Pages no usa el enrutamiento de atributos. Puede especificar información de la plantilla de ruta adicional para una Razor Page como parte de su directiva de `@page`:

```csharp
@page "{id:int}"
```

En el ejemplo anterior, la página en cuestión coincidiría con una ruta con un parámetro `id` de número entero. Por ejemplo, la página *Products.cshtml*, que se encuentra en la raíz de `/Pages`, tendría esta ruta:

```csharp
"/Products/123"
```

Una vez que una determinada solicitud se ha asociado a una ruta, pero antes de llamar al método de acción, ASP.NET Core MVC realizará el [enlace del modelo](/aspnet/core/mvc/models/model-binding) y la [validación del modelo](/aspnet/core/mvc/models/validation) en la solicitud. El enlace del modelo es responsable de convertir los datos HTTP entrantes en los tipos de .NET especificados como parámetros del método de acción que se va a llamar. Por ejemplo, si el método de acción espera un parámetro de identificador de tipo int, el enlace de modelos intentará proporcionar este parámetro de un valor que se proporciona como parte de la solicitud. Para ello, el enlace de modelos busca valores en un formulario enviado, valores en la propia misma ruta y valores de cadena de consulta. Suponiendo que se encuentra un valor de identificador, se convertirá en un entero antes de pasarlo al método de acción.

Después de enlazar el modelo, pero antes de llamar al método de acción, se produce la validación del modelo. La validación del modelo usa atributos opcionales en el tipo de modelo y puede ayudar a garantizar que el objeto de modelo proporcionado cumple determinados requisitos de datos. Se pueden especificar determinados valores como obligatorios, o limitarlos a una longitud o un intervalo numérico determinados, etc. Si se especifican atributos de validación, pero el modelo no cumple sus requisitos, la propiedad ModelState.IsValid será false y el conjunto de reglas de validación con errores estará disponible para enviarlo al cliente que realiza la solicitud.

Si se usa la validación del modelo, siempre se debe comprobar que el modelo es válido antes de ejecutar cualquier comando de modificación del estado, para asegurarse de que la aplicación no resulta dañada por datos no válidos. Se puede usar un [filtro](/aspnet/core/mvc/controllers/filters) para evitar la necesidad de agregar código para esto en todas las acciones. Los filtros de ASP.NET Core MVC ofrecen una manera de interceptar grupos de solicitudes, para poder aplicar directivas comunes e intereses transversales por cada destino. Los filtros se pueden aplicar a acciones individuales, controladores completos o de forma global para una aplicación.

Para las API web, ASP.NET Core MVC admite la [_negociación de contenido_](/aspnet/core/mvc/models/formatting), lo que permite a las solicitudes especificar cómo se debe aplicar formato a las respuestas. Según los encabezados proporcionados en la solicitud, las acciones que devuelven datos darán formato a la respuesta en XML, JSON o en otro formato compatible. Esta característica permite usar la misma API en varios clientes con requisitos de formato de datos diferentes.

Para los proyectos de API web, debería valorarse el uso del atributo `[ApiController]`, que se puede aplicar a controladores individuales, a una clase de controlador base o a todo el ensamblado. Este atributo agrega la comprobación de validación de modelos automática; cualquier acción con una modelo no válido devolverá una solicitud BadRequest con los detalles de los errores de validación. El atributo también requiere que todas las acciones tengan una ruta de atributo, en lugar de utilizar una ruta convencional, y devuelve información más detallada de ProblemDetails en respuesta a los errores.

> ### <a name="references--mapping-requests-to-responses"></a>Referencias: asignación de solicitudes a respuestas
>
> - **Routing to Controller Actions (Enrutamiento a acciones del controlador)** 
 > <https://docs.microsoft.com/aspnet/core/mvc/controllers/routing>
> - **Enlace de modelos**
 > <https://docs.microsoft.com/aspnet/core/mvc/models/model-binding>
> - **Model Validation (Validación de modelos)** 
 > <https://docs.microsoft.com/aspnet/core/mvc/models/validation>
> - **Filtros**
 > <https://docs.microsoft.com/aspnet/core/mvc/controllers/filters>
> - **Atributo ApiController**
 > <https://docs.microsoft.com/aspnet/core/web-api/>

## <a name="working-with-dependencies"></a>Trabajar con dependencias

ASP.NET Core tiene compatibilidad integrada con una técnica conocida como [inserción de dependencias](/aspnet/core/fundamentals/dependency-injection) y la usa de manera interna. La inserción de dependencias es una técnica que permite el acoplamiento flexible entre los distintos elementos de una aplicación. El acoplamiento más flexible es deseable porque facilita aislar los elementos de la aplicación, lo que permite realizar pruebas o reemplazos. También hace que sea menos probable que un cambio en un elemento de la aplicación tenga un impacto inesperado en otro lugar de la aplicación. La inserción de dependencias se basa en el principio de inversión de dependencias y suele ser es clave para lograr el principio abierto o cerrado. Al evaluar el funcionamiento de la aplicación con sus dependencias, tenga cuidado del problema de la [estática](https://deviq.com/static-cling/) en el código y recuerde el aforismo "[lo nuevo se pega](https://ardalis.com/new-is-glue)".

La estática se produce cuando las clases realizan llamadas a métodos estáticos, o bien tienen acceso a propiedades estáticas, que tienen efectos secundarios o dependencias en la infraestructura. Por ejemplo, si tiene un método que llama a un método estático, que a su vez escribe en una base de datos, el método está estrechamente acoplado a la base de datos. Todo lo que interrumpa esa llamada a la base de datos interrumpirá el método. Es muy difícil probar este tipo de métodos, ya que esas pruebas requieren bibliotecas de simulación comerciales para simular las llamadas estáticas o solo se pueden probar con una base de datos de prueba. Las llamadas estáticas que no tienen ninguna dependencia de la infraestructura, sobre todo las que son completamente sin estado, se pueden llamar sin problemas y no tienen ningún impacto en el acoplamiento o la capacidad de prueba (más allá del acoplamiento de código a la propia llamada estática).

Muchos desarrolladores comprenden los riesgos de la estática y el estado global, pero siguen acoplando estrechamente el código a implementaciones específicas a través de la creación directa de instancias. "Lo nuevo se pega" está pensado para ser un aviso de este acoplamiento y no un rechazo general del uso de la palabra clave `new`. Como sucede con las llamadas de métodos estáticos, las instancias nuevas de tipos que no tienen dependencias externas normalmente no acoplan estrechamente código a los detalles de implementación ni dificultan las pruebas. Pero cada vez que se crea una instancia de una clase, dedique un instante a considerar si tiene sentido integrar como parte del código esa instancia específica en esa ubicación concreta, o si un mejor diseño sería solicitar esa instancia como una dependencia.

### <a name="declare-your-dependencies"></a>Declarar las dependencias

ASP.NET Core se basa en hacer que los métodos y las clases declaren sus dependencias y las soliciten como argumentos. Las aplicaciones ASP.NET normalmente se configuran en una clase de inicio, que a su vez se configura para admitir la inserción de dependencias en varios puntos. Si la clase de inicio tiene un constructor, puede solicitar las dependencias a través del constructor, de este modo:

```csharp
public class Startup
{
    public Startup(IHostingEnvironment env)
    {
        var builder = new ConfigurationBuilder()
            .SetBasePath(env.ContentRootPath)
            .AddJsonFile("appsettings.json", optional: false, reloadOnChange: true)
            .AddJsonFile($"appsettings.{env.EnvironmentName}.json", optional: true);
    }
}
```

La clase de inicio es interesante en el sentido de que no hay requisitos de tipos explícitos para ella. No hereda de una clase base de inicio especial, ni implementa ninguna interfaz determinada. Se le puede asignar un constructor, o no, y se pueden especificar tantos parámetros en el constructor como se quiera. Cuando se inicia el host web configurado para la aplicación, llamará a la clase de inicio que se le ha indicado que use y usará la inserción de dependencias para rellenar todas las dependencias que la clase de inicio requiera. Por supuesto, si se solicitan parámetros que no están configurados en el contenedor de servicios que usa ASP.NET Core, se obtendrá una excepción, pero siempre que se respeten las dependencias que el contenedor conoce, se puede solicitar lo que se quiera.

La inserción de dependencias se integra en las aplicaciones ASP.NET Core desde el principio, cuando se crea la instancia de la clase de inicio. No se detiene ahí para la clase de inicio. Las dependencias también se pueden solicitar en el método Configure:

```csharp
public void Configure(IApplicationBuilder app,
    IHostingEnvironment env,
    ILoggerFactory loggerFactory)
{

}
```

El método ConfigureServices es la excepción a este comportamiento; solo debe tomar un parámetro de tipo IServiceCollection. Realmente no necesita admitir la inserción de dependencias, ya que por un lado es responsable de agregar objetos al contenedor de servicios y, por otro, tiene acceso a todos los servicios configurados actualmente a través del parámetro IServiceCollection. Por tanto, se puede trabajar con las dependencias definidas en la colección de servicios de ASP.NET Core en todos los elementos de la clase de inicio, ya sea solicitando el servicio necesario como un parámetro o trabajando con IServiceCollection en ConfigureServices.

> [!NOTE]
> Si necesita asegurarse de que determinados servicios estén disponibles para la clase de inicio, puede configurarlos mediante IWebHostBuilder y su método ConfigureServices en la llamada CreateDefaultBuilder.

La clase de inicio es un modelo de cómo estructurar otros elementos de la aplicación ASP.NET Core, desde controladores a software intermedio o filtros para sus propios servicios. En cada caso, se debe seguir el [principio de dependencias explícitas](https://deviq.com/explicit-dependencies-principle/), y solicitar las dependencias en lugar de crearlas directamente, y aprovechar la inserción de dependencias en toda la aplicación. Tenga cuidado de dónde y cómo se crean instancias directas de las implementaciones, especialmente de servicios y objetos que funcionan con la infraestructura o tienen efectos secundarios. Es preferible trabajar con abstracciones definidas en el núcleo de la aplicación y pasadas como argumentos que integrar las referencias como parte del código en tipos de implementación específicos.

## <a name="structuring-the-application"></a>Estructuración de la aplicación

Las aplicaciones monolíticas suelen tener un único punto de entrada. En el caso de una aplicación web ASP.NET Core, el punto de entrada será el proyecto web ASP.NET Core. Pero eso no significa que la solución deba constar simplemente de un solo proyecto. Resulta útil dividir la aplicación en diferentes capas para seguir la separación de intereses. Una vez dividida en capas, resulta útil ir más allá de las carpetas para separar los proyectos, lo que puede ayudar a conseguir una mejor encapsulación. El mejor método para lograr estos objetivos con una aplicación ASP.NET Core consiste en una variación de la arquitectura limpia que se describe en el capítulo 5. Al seguir este enfoque, la solución de la aplicación estará compuesta por bibliotecas independientes para la interfaz de usuario, la infraestructura y ApplicationCore.

Además de estos proyectos, también se incluyen proyectos de prueba independientes (las pruebas se describen en el capítulo 9).

El modelo de objetos y las interfaces de la aplicación se deben colocar en el proyecto ApplicationCore. Este proyecto tendrá el menor número posible de dependencias y los otros proyectos de la solución le harán referencia. Las entidades de negocio que deban conservarse se definen en el proyecto ApplicationCore, al igual que los servicios que no dependen directamente de la infraestructura.

Los detalles de implementación, por ejemplo, cómo se realiza la persistencia o cómo se pueden enviar notificaciones a un usuario, se mantienen en el proyecto de infraestructura. Este proyecto hará referencia a paquetes específicos de la implementación como Entity Framework Core, pero no debe exponer detalles sobre estas implementaciones fuera del proyecto. Los servicios de infraestructura y los repositorios deben implementar interfaces definidas en el proyecto ApplicationCore, y sus implementaciones de persistencia serán responsables de recuperar y almacenar las entidades definidas en ApplicationCore.

El propio proyecto de interfaz de usuario de ASP.NET Core es responsable de cualquier interés del nivel de la interfaz de usuario, pero no debe incluir lógica empresarial o detalles de infraestructura. De hecho, idealmente ni siquiera debería tener una dependencia en el proyecto de infraestructura, lo que ayudará a garantizar que no se introduce por accidente ninguna dependencia entre los dos proyectos. Esto se puede lograr mediante un contenedor de DI de terceros, como Autofac, que permite definir reglas de DI en clases del módulo en cada proyecto.

Otro enfoque para desacoplar la aplicación de los detalles de implementación consiste en hacer que la aplicación llame a microservicios, posiblemente implementados en contenedores de Docker individuales. Esto proporciona una separación de intereses y desacoplamiento incluso mayor que aprovechar la DI entre dos proyectos, pero tiene una complejidad adicional.

### <a name="feature-organization"></a>Organización de las características

De forma predeterminada, las aplicaciones ASP.NET Core organizan su estructura de carpetas para que incluir controladores y vistas, y con frecuencia ViewModels. El código del lado cliente para admitir estas estructuras del lado servidor normalmente se almacena por separado en la carpeta wwwroot. Pero es posible que esta organización genere problemas en aplicaciones grandes, puesto que trabajar con cualquier característica determinada a menudo requiere saltar entre estas carpetas. Esto se complica cada vez más a medida que aumenta el número de archivos y subcarpetas en cada carpeta, lo que da lugar a una gran cantidad de desplazamiento por el Explorador de soluciones. Una solución a este problema consiste en organizar el código de aplicación por _característica_ en lugar de por tipo de archivo. Este estilo profesional se conoce normalmente como carpetas de características o [sectores de características](https://docs.microsoft.com/archive/msdn-magazine/2016/september/asp-net-core-feature-slices-for-asp-net-core-mvc) (vea también: [Vertical Slice](https://deviq.com/vertical-slices/) (Sectores verticales).

ASP.NET Core MVC admite las áreas para este propósito. Con las áreas, se pueden crear conjuntos independientes de carpetas de controladores y vistas (así como los modelos asociados) en cada carpeta de área. En la figura 7-1 se muestra una estructura de carpetas de ejemplo, en la que se usan áreas.

![Organización de áreas de ejemplo](./media/image7-1.png)

**Figura 7-1**. Organización de áreas de ejemplo

Cuando se usan las áreas, se deben usar atributos para decorar los controladores con el nombre del área a la que pertenecen:

```csharp
[Area("Catalog")]
public class HomeController
{}
```

También se debe agregar compatibilidad con las áreas a las rutas:

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapControllerRoute(name: "areaRoute", pattern: "{area:exists}/{controller=Home}/{action=Index}/{id?}");
    endpoints.MapControllerRoute(name: "default", pattern: "{controller=Home}/{action=Index}/{id?}");
});
```

Además de la compatibilidad integrada con las áreas, también se puede usar una estructura de carpetas propia y convenciones en lugar de atributos y rutas personalizadas. Esto permitiría tener carpetas de características que no incluyeran carpetas independientes para vistas, controladores, etc., manteniendo la jerarquía más plana y facilitando la tarea de ver todos los archivos relacionados en un único lugar para cada característica.

ASP.NET Core usa tipos de convención integrados para controlar su comportamiento. Estas convenciones se pueden modificar o reemplazar. Por ejemplo, se puede crear una convención que obtenga automáticamente el nombre de característica de un controlador determinado en función de su espacio de nombres (lo que normalmente se correlaciona con la carpeta en la que se encuentra el controlador):

```csharp
public class FeatureConvention : IControllerModelConvention
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

Después, esta convención se especifica como una opción al agregar compatibilidad para MVC a la aplicación en ConfigureServices:

```csharp
services.AddMvc(o => o.Conventions.Add(new FeatureConvention()));
```

ASP.NET Core MVC también usa una convención para localizar vistas. Se puede reemplazar con una convención personalizada para que las vistas se ubiquen en las carpetas de características (mediante el nombre de la característica proporcionado por FeatureConvention, anteriormente). Puede obtener más información sobre este enfoque y descargar un ejemplo funcional en el artículo de MSDN Magazine [Sectores de características para ASP.NET Core MVC](https://docs.microsoft.com/archive/msdn-magazine/2016/september/asp-net-core-feature-slices-for-asp-net-core-mvc).

### <a name="cross-cutting-concerns"></a>Intereses transversales

A medida que las aplicaciones aumentan de tamaño, resulta cada vez más importante separar los intereses transversales para eliminar la duplicación y mantener la coherencia. Algunos ejemplos de intereses transversales en aplicaciones ASP.NET Core son la autenticación, las reglas de validación del modelo, el almacenamiento en caché de salida y el control de errores, aunque hay muchos otros. Los [filtros](/aspnet/core/mvc/controllers/filters) de ASP.NET Core MVC permiten ejecutar código antes o después de ciertas fases de la canalización de procesamiento de la solicitud. Por ejemplo, se puede ejecutar un filtro antes y después del enlace del modelo, antes y después de una acción, o antes y después del resultado de una acción. También se puede usar un filtro de autorización para controlar el acceso al resto de la canalización. En la figura 7-2 se muestra cómo solicitar flujos de ejecución a través de filtros, si se han configurado.

![La solicitud se procesa a través de las fases Filtros de autorización, Filtros de recursos, Enlace de modelos, Filtros de acciones, Ejecución de acciones/Conversión del resultado de acción, Filtros de excepción, Filtros de resultados y Ejecución del resultado. Como resultado, la solicitud solo se procesa por las fases Filtros de resultados y Filtros de recursos antes de convertirse en una respuesta para enviarla al cliente.](./media/image7-2.png)

**Figura 7-2**. Ejecución de la solicitud a través de los filtros y la canalización de solicitud.

Normalmente, los filtros se implementan como atributos, para que se puedan aplicar a controladores o acciones, o incluso de forma global. Cuando se agregan de esta forma, los filtros especificados en el nivel de acción invalidan o se basan en los filtros especificados en el nivel de controlador, que a su vez invalidan los filtros globales. Por ejemplo, el atributo \[Route\] se puede usar para crear rutas entre controladores y acciones. Del mismo modo, la autorización se puede configurar en el nivel de controlador y, después, reemplazarse por acciones individuales, como se muestra en el ejemplo siguiente:

```csharp
[Authorize]
public class AccountController : Controller

{
    [AllowAnonymous] // overrides the Authorize attribute
    public async Task<IActionResult> Login() {}
    public async Task<IActionResult> ForgotPassword() {}
}
```

En el primer método, Login, se usa el filtro AllowAnonymous (atributo) para invalidar el filtro Authorize establecido en el nivel de controlador. La acción ForgotPassword (y cualquier otra acción de la clase que no tenga un atributo AllowAnonymous) requerirá una solicitud autenticada.

Los filtros se pueden usar para eliminar la duplicación en forma de directivas de control de errores comunes para las API. Por ejemplo, una directiva de API típica es devolver una respuesta NotFound a las solicitudes que hacen referencia a claves que no existen y una respuesta BadRequest si se produce un error en la validación del modelo. En el ejemplo siguiente se muestran estas dos directivas en funcionamiento:

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

No permita que los métodos de acción se llenen con código condicional similar a este. En su lugar, extraiga las directivas en filtros que se puedan aplicar según sea necesario. En este ejemplo, la comprobación de validación del modelo, que debería producirse siempre que se envíe un comando a la API, se puede reemplazar por el atributo siguiente:

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

Puede agregar el elemento `ValidateModelAttribute` al proyecto como una dependencia de NuGet ; para ello, debe incluir el paquete [Ardalis.ValidateModel](https://www.nuget.org/packages/Ardalis.ValidateModel). Para las API, puede usar el atributo `ApiController` para aplicar este comportamiento sin tener que usar un filtro `ValidateModel` independiente.

Del mismo modo, se puede usar un filtro para comprobar si existe un registro y devolver un error 404 antes de ejecutar la acción, lo que elimina la necesidad de realizar estas comprobaciones en la acción. Una vez que se han extraído las convenciones comunes y se ha organizado la solución para separar el código de infraestructura y la lógica de negocio de la interfaz de usuario, los métodos de acción de MVC deben ser sumamente ligeros:

```csharp
[HttpPut("{id}")]
[ValidateAuthorExists]
public async Task<IActionResult> Put(int id, [FromBody]Author author)
{
    await _authorRepository.UpdateAsync(author);
    return Ok();
}
```

Puede obtener más detalles sobre la implementación de filtros y descargar un ejemplo funcional en el artículo de MSDN Magazine [ASP.NET Core: filtros reales de ASP.NET Core MVC](https://docs.microsoft.com/archive/msdn-magazine/2016/august/asp-net-core-real-world-asp-net-core-mvc-filters).

> ### <a name="references--structuring-applications"></a>Referencias: estructuración de aplicaciones
>
> - **Áreas**  
>   <https://docs.microsoft.com/aspnet/core/mvc/controllers/areas>
> - **MSDN Magazine: Sectores de características para ASP.NET Core MVC**  
>   <https://docs.microsoft.com/archive/msdn-magazine/2016/september/asp-net-core-feature-slices-for-asp-net-core-mvc>
> - **Filtros**  
>   <https://docs.microsoft.com/aspnet/core/mvc/controllers/filters>
> - **MSDN Magazine: filtros reales de ASP.NET Core MVC**  
>   <https://docs.microsoft.com/archive/msdn-magazine/2016/august/asp-net-core-real-world-asp-net-core-mvc-filters>

## <a name="security"></a>Seguridad

La protección de las aplicaciones web es un tema amplio, con muchas consideraciones. En su nivel más básico, la seguridad implica asegurarse de saber de quién procede una solicitud determinada y, después, asegurarse de que la solicitud solo tiene acceso a los recursos que debe. La autenticación es el proceso de comparación de las credenciales proporcionadas con una solicitud con las de un almacén de datos de confianza, para ver si la solicitud se debe tratar como procedente de una entidad conocida. La autorización es el proceso de restringir el acceso a determinados recursos en función de la identidad del usuario. Un tercer interés de seguridad es proteger las solicitudes contra el espionaje por parte de terceros, para lo que al menos se debe [asegurar de que la aplicación usa SSL](/aspnet/core/security/enforcing-ssl).

### <a name="authentication"></a>Autenticación

ASP.NET Core Identity es un sistema de pertenencia que se puede usar para admitir la funcionalidad de inicio de sesión para la aplicación. Tiene compatibilidad con cuentas de usuario locales y también con proveedores de inicio de sesión externo como Microsoft Account, Twitter, Facebook, Google y muchos más. Además de ASP.NET Core Identity, la aplicación puede usar la autenticación de Windows o un proveedor de identidades de terceros como [Identity Server](https://github.com/IdentityServer/IdentityServer4).

ASP.NET Core Identity se incluye en las nuevas plantillas de proyecto si se selecciona la opción Cuentas de usuario individuales. Esta plantilla incluye compatibilidad para el registro, inicio de sesión, inicios de sesión externos, contraseñas olvidadas y funcionalidad adicional.

![Selección de cuentas de usuario individuales para preconfigurar Identity](./media/image7-3.png)

**Figura 7-3**. Figura 7-3 Selección de Cuentas de usuario individuales para preconfigurar Identity.

La compatibilidad con Identity se configura en Startup, tanto en ConfigureServices y Configure:

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
    app.UseEndpoints(endpoints =>
    {
        endpoints.MapControllerRoute(name: "default", pattern: "{controller=Home}/{action=Index}/{id?}");
    });
}
```

Es importante que UseIdentity aparezca antes de UseMvc en el método Configure. Al configurar Identity en ConfigureServices, observará una llamada a AddDefaultTokenProviders. Esto no tiene nada que ver con los tokens que se pueden usar para proteger las comunicaciones web, sino que, en su lugar, hace referencia a los proveedores que crean mensajes que se pueden enviar a los usuarios a través de SMS o correo electrónico para que confirmen su identidad.

Puede obtener más información sobre la [configuración de la autenticación en dos fases](/aspnet/core/security/authentication/2fa) y la [habilitación de proveedores de inicio de sesión externos](/aspnet/core/security/authentication/social/) en la documentación oficial de ASP.NET Core.

### <a name="authorization"></a>Autorización

La forma más sencilla de autorización implica restringir el acceso a los usuarios anónimos. Esto se puede lograr mediante la aplicación del atributo \[Authorize\] a determinados controladores o acciones. Si se usan roles, el atributo se puede ampliar más para restringir el acceso a los usuarios que pertenecen a roles concretos, como se muestra a continuación:

```csharp
[Authorize(Roles = "HRManager,Finance")]
public class SalaryController : Controller
{

}
```

En este caso, los usuarios que pertenecen a los roles HRManager o Finance (o a ambos) tendrían acceso a SalaryController. Para requerir que un usuario pertenezca a varios roles (no solo a uno de varios), se puede aplicar el atributo varias veces y especificar un rol necesario cada vez.

La especificación de determinados conjuntos de roles como cadenas en muchos controladores y acciones diferentes puede dar lugar a repeticiones no deseadas. Se pueden configurar directivas de autorización, que encapsulan las reglas de autorización y, después, especificar la directiva en lugar de roles individuales al aplicar el atributo \[Authorize\]:

```csharp
[Authorize(Policy = "CanViewPrivateReport")]
public IActionResult ExecutiveSalaryReport()
{
    return View();
}
```

Al usar las directivas de esta manera, se pueden separar los tipos de acciones que se restringen de las reglas o roles específicos a los que se aplican. Más adelante, si se crea un rol que necesita tener acceso a recursos concretos, se puede actualizar simplemente una directiva, en lugar de actualizar cada lista de roles en todos los atributos \[Authorize\].

#### <a name="claims"></a>Notificaciones

Las notificaciones son pares nombre-valor que representan las propiedades de un usuario autenticado. Por ejemplo, es posible almacenar el número de empleado de los usuarios como una notificación. Después, las notificaciones se pueden usar como parte de las directivas de autorización. Podría crear una directiva denominada "EmployeeOnly" que requiera la existencia de una notificación denominada "EmployeeNumber", como se muestra en este ejemplo:

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

Después, esta directiva se podría usar con el atributo \[Authorize\] para proteger cualquier controlador o acción, como se describió anteriormente.

#### <a name="securing-web-apis"></a>Protección de las API web

La mayoría de las API web deben implementar un sistema de autenticación basado en tokens. La autenticación por tokens carece de estado y está diseñada para que sea escalable. En un sistema de autenticación basado en tokens, el cliente debe autenticarse primero con el proveedor de autenticación. Si se realiza correctamente, se emite un token para el cliente, que simplemente es una cadena de caracteres criptográficamente significativa. Después, cuando el cliente tiene que emitir una solicitud a una API, agrega este token como un encabezado a la solicitud. Luego, el servidor valida el token que se encuentra en el encabezado de solicitud antes de completar la solicitud. En la figura 7-4 se muestra este proceso.

![TokenAuth](./media/image7-4.png)

**Figura 7-4.** Autenticación basada en tokens para las API web.

Puede crear su propio servicio de autenticación, realizar la integración con Azure AD y OAuth o implementar un servicio mediante una herramienta de código abierto como [IdentityServer](https://github.com/IdentityServer).

#### <a name="custom-security"></a>Seguridad personalizada

Tenga especial cuidado al crear una implementación de criptografía, una pertenencia de usuarios o un sistema de generación de tokens propios. Existen muchas alternativas comerciales y de código abierto disponibles que seguramente ofrecerán una mayor seguridad que una implementación personalizada.

> ### <a name="references--security"></a>Referencias: seguridad
>
> - **Introducción a la seguridad de ASP.NET Core**  
>   https://docs.microsoft.com/aspnet/core/security/
> - **Exigir SSL en una aplicación ASP.NET básica**  
>   <https://docs.microsoft.com/aspnet/core/security/enforcing-ssl>
> - **Introducción a Identity**  
>   <https://docs.microsoft.com/aspnet/core/security/authentication/identity>
> - **Introducción a la autorización**  
>   <https://docs.microsoft.com/aspnet/core/security/authorization/introduction>
> - **Autenticación y autorización para aplicaciones de API en Azure App Service**  
>   <https://docs.microsoft.com/azure/app-service-api/app-service-api-authentication>
> - **Servidor de identidades**  
>   <https://github.com/IdentityServer>

## <a name="client-communication"></a>Comunicación de cliente

Además de servir páginas y responder a las solicitudes de datos a través de las API web, las aplicaciones ASP.NET Core se pueden comunicar directamente con los clientes conectados. En esta comunicación de salida se puede usar una amplia variedad de tecnologías de transporte, siendo WebSockets la más común. ASP.NET Core SignalR es una biblioteca que simplifica la funcionalidad de agregar comunicación de servidor a cliente en tiempo real en las aplicaciones. SignalR admite diversas tecnologías de transporte, incluyendo WebSockets, y abstrae muchos de los detalles de implementación del desarrollador.

La comunicación de cliente en tiempo real, con independencia de que se use WebSockets directamente u otras técnicas, es útil en una variedad de escenarios de aplicación. Estos son algunos ejemplos:

- Aplicaciones de salón de chat en vivo

- Aplicaciones de supervisión

- Actualizaciones de progreso de trabajo

- Notificaciones

- Aplicaciones de formularios interactivos

Al compilar la comunicación de cliente en las aplicaciones, normalmente hay dos componentes:

- El administrador de conexiones del lado servidor (SignalR Hub, WebSocketManager WebSocketHandler)

- La biblioteca del lado cliente

Los clientes no están limitados a los exploradores: aplicaciones móviles, aplicaciones de consola y otras aplicaciones nativas también se pueden comunicar mediante SignalR/WebSockets. El siguiente programa sencillo devuelve a la consola todo el contenido enviado a una aplicación de chat, como parte de una aplicación de ejemplo WebSocketManager:

```csharp
public class Program
{
    private static Connection _connection;
    public static void Main(string[] args)
    {
        StartConnectionAsync();
        _connection.On("receiveMessage", (arguments) =>
        {
            Console.WriteLine($"{arguments[0]} said: {arguments[1]}");
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
}
```

Considere las formas en que las aplicaciones se comunican directamente con las aplicaciones cliente, y considere si la comunicación en tiempo real mejoraría la experiencia del usuario de la aplicación.

> ### <a name="references--client-communication"></a>Referencias: comunicación de cliente
>
> - **SignalR de ASP.NET Core**  
>   <https://github.com/dotnet/aspnetcore/tree/master/src/SignalR>
> - **Administrador de WebSocket**  
>   https://github.com/radu-matei/websocket-manager

## <a name="domain-driven-design--should-you-apply-it"></a>¿Se debe aplicar el diseño controlado por dominios?

El Diseño controlado por dominios (DDD) es un enfoque ágil para la creación de software que resalta centrarse en el _dominio de negocio_. Coloca un gran énfasis en la comunicación e interacción con los expertos de dominio de negocio, que pueden identificarse con los desarrolladores sobre cómo funciona el sistema del mundo real. Por ejemplo, si está creando un sistema que controla cotizaciones de bolsa, es posible que el experto de dominio sea un broker de bolsa con experiencia. DDD está diseñado para resolver problemas empresariales grandes y complejos, y no suele ser adecuado para aplicaciones más pequeñas y sencillas, dado que la inversión necesaria para comprender y modelar el dominio no es rentable.

Al compilar software con un enfoque de DDD, el equipo (incluidas las partes interesadas sin experiencia técnica y los colaboradores) deberían desarrollar un _lenguaje ubicuo_ para el espacio del problema. Es decir, se debe usar la misma terminología para el concepto del mundo real que se está modelando, el equivalente de software y las estructuras que podrían existir para conservar el concepto (por ejemplo, las tablas de base de datos). Por tanto, los conceptos descritos en el lenguaje ubicuo deberían ser la base del _modelo de dominio_.

El modelo de dominio se compone de objetos que interactúan entre sí para representar el comportamiento del sistema. Estos objetos se dividen en las categorías siguientes:

- [Entidades](https://deviq.com/entity/), que representan objetos con un subproceso de identidad. Normalmente las entidades se almacenan en la persistencia con una clave por la que después se pueden recuperar.

- [Agregados](https://deviq.com/aggregate-pattern/), que representan grupos de objetos que se deben conservar como una unidad.

- [Objetos de valor](https://deviq.com/value-object/), que representan conceptos que se pueden comparar en función de la suma de sus valores de propiedad. Por ejemplo, DateRange consta de una fecha de inicio y una fecha de finalización.

- [Eventos de dominio](https://martinfowler.com/eaaDev/DomainEvent.html), que representan lo que ocurre en el sistema que resulta de interés para otros elementos del sistema.

Un modelo de dominio de DDD debe encapsular un comportamiento complejo dentro del modelo. Las entidades, en concreto, no deben ser simplemente colecciones de propiedades. Cuando el modelo de dominio carece de comportamiento y simplemente representa el estado del sistema, se dice que es un [modelo anémico](https://deviq.com/anemic-model/), lo que no es deseable en DDD.

Además de estos tipos de modelo, DDD normalmente emplea diversos modelos:

- [Repositorio](https://deviq.com/repository-pattern/), para abstraer los detalles de persistencia.

- [Generador](https://en.wikipedia.org/wiki/Factory_method_pattern), para encapsular la creación de objetos complejos.

- Eventos de dominio, para desacoplar el comportamiento dependiente del comportamiento de generación.

- [Servicios](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/), para encapsular un comportamiento complejo o los detalles de implementación de la infraestructura.

- [Comando](https://en.wikipedia.org/wiki/Command_pattern), para desacoplar la emisión de comandos y la ejecución del propio comando.

- [Especificación](https://deviq.com/specification-pattern/), para encapsular los detalles de la consulta.

DDD también recomienda el uso de la arquitectura limpia que se describió anteriormente, lo que permite acoplamiento débil, encapsulación y código que se pueda comprobar fácilmente mediante pruebas unitarias.

### <a name="when-should-you-apply-ddd"></a>Casos en los que se debe aplicar DDD

DDD es ideal para aplicaciones de gran tamaño con complejidad de negocio significativa (no solo técnica). La aplicación debe requerir el conocimiento de expertos de dominio. Debe haber un comportamiento importante en el propio modelo de dominio, que represente las reglas de negocio e interacciones más allá de simplemente almacenar y recuperar el estado actual de diferentes registros desde almacenes de datos.

### <a name="when-shouldnt-you-apply-ddd"></a>Casos en los que no se debe aplicar DDD

DDD implica invertir en modelado, arquitectura y comunicación, lo que puede que no esté garantizado para aplicaciones más pequeñas o aplicaciones que esencialmente son de tipo CRUD (crear/leer/actualizar/eliminar). Si se elige el enfoque de DDD para la aplicación, pero se descubre que el dominio tiene un modelo anémico sin comportamiento, es posible que haya que reconsiderar el enfoque. O la aplicación no necesita DDD o es posible que necesite asistencia para refactorizarla con el fin de encapsular la lógica de negocios en el modelo de dominio, en lugar de la interfaz de usuario o la base de datos.

Un enfoque híbrido consistiría en usar DDD solo para las áreas más complejas o transaccionales de la aplicación, pero no para partes CRUD más sencillas o de solo lectura. Por ejemplo, no es necesario tener las restricciones de un agregado si se están consultando datos para mostrar un informe o para visualizar datos para un panel. Es absolutamente aceptable tener un modelo de lectura más sencillo e independiente para estos requisitos.

> ### <a name="references--domain-driven-design"></a>Referencias: diseño controlado por dominios
>
> - **DDD in Plain English (StackOverflow Answer)** (DDD en términos sencillos [respuesta en StackOverflow])  
>   <https://stackoverflow.com/questions/1222392/can-someone-explain-domain-driven-design-ddd-in-plain-english-please/1222488#1222488>

## <a name="deployment"></a>Implementación

En el proceso de implementación de la aplicación ASP.NET Core hay algunos pasos implicados, independientemente de dónde se vaya a hospedar. El primer paso consiste en publicar la aplicación, lo que se puede hacer con el comando de CLI `dotnet publish`. Esto compilará la aplicación y colocará todos los archivos necesarios para ejecutarla en una carpeta designada. Cuando se implementa desde Visual Studio, este paso se realiza de forma automática. La carpeta publish contiene archivos .exe y .dll de la aplicación y sus dependencias. Una aplicación independiente también incluirá una versión del runtime de .NET. Las aplicaciones ASP.NET Core también incluyen archivos de configuración, activos de cliente estáticos y vistas MVC.

Las aplicaciones ASP.NET Core son aplicaciones de consola que se deben iniciar cuando se inicia el servidor y reiniciarse si la aplicación (o el servidor) se bloquea. Para automatizar este proceso se puede usar un administrador de procesos. Los administradores de procesos más comunes para ASP.NET Core son Nginx y Apache en Linux, e IIS y Servicio de Windows en Windows.

Además de un administrador de procesos, las aplicaciones de ASP.NET Core pueden usar un servidor proxy inverso. Un servidor proxy inverso recibe las solicitudes HTTP de Internet y las reenvía a Kestrel después de un control preliminar. Los servidores proxy inversos proporcionan una capa de seguridad para la aplicación. Kestrel tampoco admite el hospedaje de varias aplicaciones en el mismo puerto, por lo que no se pueden usar técnicas como los encabezados de host con él para habilitar el hospedaje de varias aplicaciones en el mismo puerto y dirección IP.

![Kestrel a Internet](./media/image7-5.png)

**Figura 7-5**. ASP.NET hospedado en Kestrel detrás de un servidor proxy inverso

Otro escenario en el que un proxy inverso puede ser útil es para proteger varias aplicaciones mediante SSL/HTTPS. En este caso, solo sería necesario configurar SSL en el proxy inverso. La comunicación entre el servidor proxy inverso y Kestrel se podría llevar a cabo a través de HTTP, como se muestra en la figura 7-6.

![ASP.NET hospedado detrás de un servidor proxy inverso protegido mediante HTTPS](./media/image7-6.png)

**Figura 7-6**. ASP.NET hospedado detrás de un servidor proxy inverso protegido mediante HTTPS

Un enfoque cada vez más popular consiste en hospedar la aplicación ASP.NET Core en un contenedor de Docker, que después se puede hospedar localmente o implementar en Azure para hospedaje basado en la nube. El contenedor de Docker podría contener el código de aplicación que se ejecuta en Kestrel y se implementaría detrás de un servidor proxy inverso, como se mostró anteriormente.

Si la aplicación se va a hospedar en Azure, se puede usar Microsoft Azure Application Gateway como un dispositivo virtual dedicado para proporcionar varios servicios. Además de actuar como un proxy inverso para aplicaciones individuales, Application Gateway también puede ofrecer las características siguientes:

- Equilibrio de carga HTTP

- Descarga SSL (SSL solo para Internet)

- SSL de extremo a extremo

- Enrutamiento de varios sitios (hasta 20 sitios consolidados en una sola instancia de Application Gateway)

- Firewall de aplicación web

- Compatibilidad de WebSocket

- Diagnósticos avanzados

_Más información sobre las opciones de implementación de Azure en el [capítulo 10](development-process-for-azure.md)._

> ### <a name="references--deployment"></a>Referencias: implementación
>
> - **Información general sobre implementación y hospedaje**  
>   <https://docs.microsoft.com/aspnet/core/publishing/>
> - **Casos en los que usar Kestrel con un proxy inverso**  
>   <https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel#when-to-use-kestrel-with-a-reverse-proxy>
> - **Hospedar aplicaciones ASP.NET Core en contenedores de Docker**  
>   <https://docs.microsoft.com/aspnet/core/publishing/docker>
> - **Introducción a Azure Application Gateway**  
>   <https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction>

>[!div class="step-by-step"]
>[Anterior](common-client-side-web-technologies.md)
>[Siguiente](work-with-data-in-asp-net-core-apps.md)
