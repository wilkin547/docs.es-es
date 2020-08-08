---
title: Inicio de la aplicación
description: Obtenga información sobre cómo definir la lógica de inicio de la aplicación.
author: csharpfritz
ms.author: jefritz
ms.date: 02/25/2020
ms.openlocfilehash: 3d460750c36f64b8ad343755bd63b47af5c310d9
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87914885"
---
# <a name="app-startup"></a><span data-ttu-id="0b6b6-103">Inicio de la aplicación</span><span class="sxs-lookup"><span data-stu-id="0b6b6-103">App startup</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="0b6b6-104">Las aplicaciones escritas para ASP.NET suelen tener un `global.asax.cs` archivo que define el `Application_Start` evento que controla qué servicios están configurados y están disponibles para la representación en HTML y el procesamiento de .net.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-104">Applications that are written for ASP.NET typically have a `global.asax.cs` file that defines the `Application_Start` event that controls which services are configured and made available for both HTML rendering and .NET processing.</span></span> <span data-ttu-id="0b6b6-105">En este capítulo se examina el modo en que las cosas son ligeramente diferentes con el servidor de ASP.NET Core y el increíble.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-105">This chapter looks at how things are slightly different with ASP.NET Core and Blazor Server.</span></span>

## <a name="application_start-and-web-forms"></a><span data-ttu-id="0b6b6-106">Application_Start y formularios Web Forms</span><span class="sxs-lookup"><span data-stu-id="0b6b6-106">Application_Start and Web Forms</span></span>

<span data-ttu-id="0b6b6-107">El método predeterminado de formularios Web Forms `Application_Start` ha crecido en el propósito de los años para administrar muchas tareas de configuración.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-107">The default web forms `Application_Start` method has grown in purpose over years to handle many configuration tasks.</span></span>  <span data-ttu-id="0b6b6-108">Un nuevo proyecto de formularios Web Forms con la plantilla predeterminada en Visual Studio 2019 ahora contiene la lógica de configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="0b6b6-108">A fresh web forms project with the default template in Visual Studio 2019 now contains the following configuration logic:</span></span>

- <span data-ttu-id="0b6b6-109">`RouteConfig`-Enrutamiento de URL de la aplicación</span><span class="sxs-lookup"><span data-stu-id="0b6b6-109">`RouteConfig` - Application URL routing</span></span>
- <span data-ttu-id="0b6b6-110">`BundleConfig`-Agrupación de CSS y JavaScript y minificación</span><span class="sxs-lookup"><span data-stu-id="0b6b6-110">`BundleConfig` - CSS and JavaScript bundling and minification</span></span>

<span data-ttu-id="0b6b6-111">Cada uno de estos archivos individuales reside en la `App_Start` carpeta y solo se ejecuta una vez al principio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-111">Each of these individual files reside in the `App_Start` folder and run only once at the start of our application.</span></span>  <span data-ttu-id="0b6b6-112">`RouteConfig`en la plantilla de proyecto predeterminada, agrega el `FriendlyUrlSettings` para formularios Web Forms para permitir que las direcciones URL de la aplicación omitan la `.ASPX` extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-112">`RouteConfig` in the default project template adds the `FriendlyUrlSettings` for web forms to allow application URLs to omit the `.ASPX` file extension.</span></span>  <span data-ttu-id="0b6b6-113">La plantilla predeterminada también contiene una directiva que proporciona códigos de estado de redirección HTTP permanente (HTTP 301) para las `.ASPX` páginas a la dirección URL descriptiva con el nombre de archivo que omite la extensión.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-113">The default template also contains a directive that provides permanent HTTP redirect status codes (HTTP 301) for the `.ASPX` pages to the friendly URL with the file name that omits the extension.</span></span>

<span data-ttu-id="0b6b6-114">Con ASP.NET Core y increíbles, estos métodos se han simplificado y consolidado en la `Startup` clase o se eliminan en favor de las tecnologías web comunes.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-114">With ASP.NET Core and Blazor, these methods are either simplified and consolidated into the `Startup` class or they are eliminated in favor of common web technologies.</span></span>

## <a name="blazor-server-startup-structure"></a><span data-ttu-id="0b6b6-115">Estructura de inicio del servidor extraordinaria</span><span class="sxs-lookup"><span data-stu-id="0b6b6-115">Blazor Server Startup Structure</span></span>

<span data-ttu-id="0b6b6-116">Las aplicaciones de servidor de extraordinarias residen en una aplicación ASP.NET Core 3,0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-116">Blazor Server applications reside on top of an ASP.NET Core 3.0 or later application.</span></span>  <span data-ttu-id="0b6b6-117">ASP.NET Core las aplicaciones web se configuran a través de un par de métodos en la `Startup.cs` clase en la carpeta raíz de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-117">ASP.NET Core web applications are configured through a pair of methods in the `Startup.cs` class on the root folder of the application.</span></span>  <span data-ttu-id="0b6b6-118">A continuación se muestra el contenido predeterminado de la clase de inicio</span><span class="sxs-lookup"><span data-stu-id="0b6b6-118">The Startup class's default content is listed below</span></span>

```csharp
public class Startup
{
  public Startup(IConfiguration configuration)
  {
    Configuration = configuration;
  }

  public IConfiguration Configuration { get; }

  // This method gets called by the runtime. Use this method to add services to the container.
  // For more information on how to configure your application, visit https://go.microsoft.com/fwlink/?LinkID=398940
  public void ConfigureServices(IServiceCollection services)
  {
    services.AddRazorPages();
    services.AddServerSideBlazor();
    services.AddSingleton<WeatherForecastService>();
  }

  // This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
  public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
  {
    if (env.IsDevelopment())
    {
      app.UseDeveloperExceptionPage();
    }
    else
    {
      app.UseExceptionHandler("/Error");
      // The default HSTS value is 30 days. You may want to change this for production scenarios, see https://aka.ms/aspnetcore-hsts.
      app.UseHsts();
    }

    app.UseHttpsRedirection();
    app.UseStaticFiles();

    app.UseRouting();

    app.UseEndpoints(endpoints =>
    {
      endpoints.MapBlazorHub();
      endpoints.MapFallbackToPage("/_Host");
   });
  }
 }
```

<span data-ttu-id="0b6b6-119">Al igual que el resto de ASP.NET Core, la clase startup se crea con principios de inyección de dependencia.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-119">Like the rest of ASP.NET Core, the Startup class is created with dependency injection principles.</span></span>  <span data-ttu-id="0b6b6-120">`IConfiguration`Se proporciona al constructor y se guarda en un oculto en una propiedad pública para el acceso posterior durante la configuración.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-120">The `IConfiguration` is provided to the constructor and stashed in a public property for later access during configuration.</span></span>

<span data-ttu-id="0b6b6-121">El `ConfigureServices` método introducido en ASP.net Core permite configurar los diversos servicios de ASP.net Core Framework para el contenedor de inserción de dependencias integrado de Framework.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-121">The `ConfigureServices` method introduced in ASP.NET Core allows for the various ASP.NET Core framework services to be configured for the framework's built-in dependency injection container.</span></span>  <span data-ttu-id="0b6b6-122">Los distintos `services.Add*` métodos agregan servicios que habilitan características como la autenticación, las páginas de Razor, el enrutamiento del controlador MVC, signalr y las interacciones de servidor increíbles entre muchos otros.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-122">The various `services.Add*` methods add services that enable features such as authentication, razor pages, MVC controller routing, SignalR, and Blazor Server interactions among many others.</span></span>  <span data-ttu-id="0b6b6-123">Este método no era necesario en formularios Web Forms, ya que el análisis y el control de los archivos ASPX, ASCX, ASHX y ASMX se definieron al hacer referencia a ASP.NET en el archivo de configuración de web.config.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-123">This method was not needed in web forms, as the parsing and handling of the ASPX, ASCX, ASHX, and ASMX files was defined by referencing ASP.NET in the web.config configuration file.</span></span>  <span data-ttu-id="0b6b6-124">Puede encontrar más información sobre la inserción de dependencias en ASP.NET Core en la [documentación en línea](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection).</span><span class="sxs-lookup"><span data-stu-id="0b6b6-124">More information about dependency injection in ASP.NET Core is available in the [online documentation](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection).</span></span>

<span data-ttu-id="0b6b6-125">El `Configure` método introduce el concepto de la canalización http en ASP.net Core.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-125">The `Configure` method introduces the concept of the HTTP pipeline to ASP.NET Core.</span></span>  <span data-ttu-id="0b6b6-126">En este método, se declara desde la parte superior a la inferior el [middleware](middleware.md) que controlará todas las solicitudes enviadas a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-126">In this method, we declare from top to bottom the [Middleware](middleware.md) that will handle every request sent to our application.</span></span> <span data-ttu-id="0b6b6-127">La mayoría de estas características en la configuración predeterminada estaban diseminadas en los archivos de configuración de formularios Web Forms y ahora se encuentran en un solo lugar para facilitar la referencia.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-127">Most of these features in the default configuration were scattered across the web forms configuration files and are now in one place for ease of reference.</span></span>

<span data-ttu-id="0b6b6-128">Ya no es la configuración de la página de errores personalizada colocada en un `web.config` archivo, sino que ahora está configurada para mostrarse siempre si el entorno de la aplicación no tiene la etiqueta `Development` .</span><span class="sxs-lookup"><span data-stu-id="0b6b6-128">No longer is the configuration of the custom error page placed in a `web.config` file, but now is configured to always be shown if the application environment is not labeled `Development`.</span></span>  <span data-ttu-id="0b6b6-129">Además, ASP.NET Core aplicaciones ahora están configuradas para atender páginas seguras con TLS de forma predeterminada con la `UseHttpsRedirection` llamada al método.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-129">Additionally, ASP.NET Core applications are now configured to serve secure pages with TLS by default with the `UseHttpsRedirection` method call.</span></span>

<span data-ttu-id="0b6b6-130">A continuación, se muestra un método de configuración inesperado en `UseStaticFiles` .</span><span class="sxs-lookup"><span data-stu-id="0b6b6-130">Next, an unexpected configuration method is listed to `UseStaticFiles`.</span></span>  <span data-ttu-id="0b6b6-131">En ASP.NET Core, la compatibilidad con las solicitudes de archivos estáticos (por ejemplo, JavaScript, CSS y archivos de imagen) debe estar habilitada explícitamente, y solo los archivos de la carpeta *wwwroot* de la aplicación se pueden direccionar públicamente de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-131">In ASP.NET Core, support for requests for static files (like JavaScript, CSS, and image files) must be explicitly enabled, and only files in the app's *wwwroot* folder are publicly addressable by default.</span></span>

<span data-ttu-id="0b6b6-132">La siguiente línea es la primera que replica una de las opciones de configuración de formularios Web Forms: `UseRouting` .</span><span class="sxs-lookup"><span data-stu-id="0b6b6-132">The next line is the first that replicates one of the configuration options from web forms: `UseRouting`.</span></span>  <span data-ttu-id="0b6b6-133">Este método agrega la ASP.NET Core enrutador a la canalización y se puede configurar aquí o en los archivos individuales a los que puede tener en cuenta el enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-133">This method adds the ASP.NET Core router to the pipeline and it can be either configured here or in the individual files that it can consider routing to.</span></span>  <span data-ttu-id="0b6b6-134">Puede encontrar más información sobre la configuración de enrutamiento en la [sección enrutamiento](pages-routing-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="0b6b6-134">More information about routing configuration can be found in the [Routing section](pages-routing-layouts.md).</span></span>

<span data-ttu-id="0b6b6-135">La última instrucción de este método define los extremos en los que está escuchando el ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-135">The final statement in this method defines the endpoints that ASP.NET Core is listening on.</span></span>  <span data-ttu-id="0b6b6-136">Estas son las ubicaciones accesibles desde web a las que se puede tener acceso en el servidor Web y que reciben algún contenido controlado por .NET y que se le devuelven.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-136">These are the web accessible locations that you can access on the web server and receive some content handled by .NET and returned to you.</span></span>  <span data-ttu-id="0b6b6-137">La primera entrada `MapBlazorHub` configura un concentrador signalr para utilizarlo en el suministro de la conexión persistente y en tiempo real al servidor en el que se controla el estado y la representación de los componentes increíbles.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-137">The first entry, `MapBlazorHub` configures a SignalR hub for use in providing the real-time and persistent connection to the server where the state and rendering of Blazor components is handled.</span></span>  <span data-ttu-id="0b6b6-138">La `MapFallbackToPage` llamada al método indica la ubicación accesible desde la Web de la página que inicia la aplicación increíblemente alta y también configura la aplicación para controlar las solicitudes de vinculación profunda desde el lado cliente.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-138">The `MapFallbackToPage` method call indicates the web-accessible location of the page that starts the Blazor application and also configures the application to handle deep-linking requests from the client-side.</span></span>  <span data-ttu-id="0b6b6-139">Verá esta característica en el trabajo si abre un explorador y navega directamente a la ruta de control más impresionante de la aplicación, como `/counter` en la plantilla de proyecto predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-139">You will see this feature at work if you open a browser and navigate directly to Blazor handled route in your application, such as `/counter` in the default project template.</span></span> <span data-ttu-id="0b6b6-140">La solicitud se controla mediante la página de reserva de *_Host. cshtml* , que luego ejecuta el enrutador increíble y representa la página del contador.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-140">The request gets handled by the *_Host.cshtml* fallback page, which then runs the Blazor router and renders the counter page.</span></span>

## <a name="upgrading-the-bundleconfig-process"></a><span data-ttu-id="0b6b6-141">Actualización del proceso BundleConfig</span><span class="sxs-lookup"><span data-stu-id="0b6b6-141">Upgrading the BundleConfig Process</span></span>

<span data-ttu-id="0b6b6-142">Las tecnologías para la agrupación de recursos, como hojas de estilos CSS y archivos JavaScript, han evolucionado significativamente, con otras tecnologías que proporcionan herramientas y técnicas que se están desarrollando con rapidez para administrar estos recursos.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-142">Technologies for bundling assets like CSS stylesheets and JavaScript files have evolved significantly, with other technologies providing quickly evolving tools and techniques for managing these resources.</span></span>  <span data-ttu-id="0b6b6-143">Para este fin, se recomienda usar una herramienta de línea de comandos de nodo como el uso de los recursos estáticos, como,</span><span class="sxs-lookup"><span data-stu-id="0b6b6-143">To this end, we recommend using a Node command-line tool such as Grunt / Gulp / WebPack to package your static assets.</span></span>

<span data-ttu-id="0b6b6-144">Las herramientas de línea de comandos de disgustas, Gulp y WebPack, así como sus configuraciones asociadas, se pueden agregar a la aplicación y ASP.NET Core omitirán silenciosamente esos archivos durante el proceso de compilación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-144">The Grunt, Gulp, and WebPack command-line tools and their associated configurations can be added to your application and ASP.NET Core will quietly ignore those files during the application build process.</span></span>  <span data-ttu-id="0b6b6-145">Puede Agregar una llamada para ejecutar sus tareas agregando un `Target` dentro del archivo de proyecto con una sintaxis similar a la siguiente que desencadenaría un script de Gulp y el `min` destino dentro de ese script.</span><span class="sxs-lookup"><span data-stu-id="0b6b6-145">You can add a call to run their tasks by adding a `Target` inside your project file with syntax similar to the following that would trigger a gulp script and the `min` target inside that script</span></span>

```xml
<Target Name="MyPreCompileTarget" BeforeTargets="Build">
  <Exec Command="gulp min" />
</Target>
```

<span data-ttu-id="0b6b6-146">Puede encontrar más información sobre las dos estrategias para administrar los archivos CSS y JavaScript en la [agrupación y minimizar de recursos estáticos en ASP.net Core documentación de](https://docs.microsoft.com/aspnet/core/client-side/bundling-and-minification) .</span><span class="sxs-lookup"><span data-stu-id="0b6b6-146">More details about both strategies to manage your CSS and JavaScript files are available in the [Bundle and minify static assets in ASP.NET Core](https://docs.microsoft.com/aspnet/core/client-side/bundling-and-minification) documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0b6b6-147">[Anterior](project-structure.md)
>[Siguiente](components.md)</span><span class="sxs-lookup"><span data-stu-id="0b6b6-147">[Previous](project-structure.md)
[Next](components.md)</span></span>
