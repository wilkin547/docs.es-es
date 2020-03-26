---
title: Migrar de ASP.NET formularios Web Forms a Blazor
description: Aprenda a abordar la migración de una aplicación de formularios Web Forms ASP.NET existente a Blazor.
author: twsouthwick
ms.author: tasou
ms.date: 09/19/2019
ms.openlocfilehash: 0a10a9a3d5ab32e16cb59a68da57116e20c53e49
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134087"
---
# <a name="migrate-from-aspnet-web-forms-to-blazor"></a><span data-ttu-id="ae8b9-103">Migrar de ASP.NET formularios Web Forms a Blazor</span><span class="sxs-lookup"><span data-stu-id="ae8b9-103">Migrate from ASP.NET Web Forms to Blazor</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="ae8b9-104">Migrar una base de código de ASP.NET formularios Web Forms a Blazor es una tarea que requiere mucho tiempo y requiere planificación.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-104">Migrating a code base from ASP.NET Web Forms to Blazor is a time-consuming task that requires planning.</span></span> <span data-ttu-id="ae8b9-105">Este capítulo describe el proceso.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-105">This chapter outlines the process.</span></span> <span data-ttu-id="ae8b9-106">Algo que puede facilitar la transición es asegurarse de que la aplicación se adhiere a una arquitectura *de N* niveles, en la que el modelo de aplicación (en este caso, formularios Web Forms) es independiente de la lógica empresarial.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-106">Something that can ease the transition is to ensure the app adheres to an *N-tier* architecture, wherein the app model (in this case, Web Forms) is separate from the business logic.</span></span> <span data-ttu-id="ae8b9-107">Esta separación lógica de capas deja claro lo que debe moverse a .NET Core y Blazor.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-107">This logical separation of layers makes it clear what needs to move to .NET Core and Blazor.</span></span>

<span data-ttu-id="ae8b9-108">En este ejemplo, se utiliza la aplicación eShop disponible en [GitHub.](https://github.com/dotnet-architecture/eShopOnBlazor)</span><span class="sxs-lookup"><span data-stu-id="ae8b9-108">For this example, the eShop app available on [GitHub](https://github.com/dotnet-architecture/eShopOnBlazor) is used.</span></span> <span data-ttu-id="ae8b9-109">eShop es un servicio de catálogo que proporciona capacidades CRUD a través de la entrada y validación de formularios.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-109">eShop is a catalog service that provides CRUD capabilities via form entry and validation.</span></span>

<span data-ttu-id="ae8b9-110">¿Por qué debería migrarse una aplicación de trabajo a Blazor?</span><span class="sxs-lookup"><span data-stu-id="ae8b9-110">Why should a working app be migrated to Blazor?</span></span> <span data-ttu-id="ae8b9-111">Muchas veces, no hay necesidad.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-111">Many times, there's no need.</span></span> <span data-ttu-id="ae8b9-112">ASP.NET los formularios Web Forms seguirán siendo compatibles durante muchos años.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-112">ASP.NET Web Forms will continue to be supported for many years.</span></span> <span data-ttu-id="ae8b9-113">Sin embargo, muchas de las características que proporciona Blazor solo se admiten en una aplicación migrada.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-113">However, many of the features that Blazor provides are only supported on a migrated app.</span></span> <span data-ttu-id="ae8b9-114">Tales características incluyen:</span><span class="sxs-lookup"><span data-stu-id="ae8b9-114">Such features include:</span></span>

- <span data-ttu-id="ae8b9-115">Mejoras de rendimiento en el marco, como`Span<T>`</span><span class="sxs-lookup"><span data-stu-id="ae8b9-115">Performance improvements in the framework such as `Span<T>`</span></span>
- <span data-ttu-id="ae8b9-116">Capacidad para ejecutarse como WebAssembly</span><span class="sxs-lookup"><span data-stu-id="ae8b9-116">Ability to run as WebAssembly</span></span>
- <span data-ttu-id="ae8b9-117">Soporte multiplataforma para Linux y macOS</span><span class="sxs-lookup"><span data-stu-id="ae8b9-117">Cross-platform support for Linux and macOS</span></span>
- <span data-ttu-id="ae8b9-118">Implementación local de aplicaciones o implementación de marco compartido sin afectar a otras aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ae8b9-118">App-local deployment or shared framework deployment without impacting other apps</span></span>

<span data-ttu-id="ae8b9-119">Si estas u otras características nuevas son lo suficientemente convincentes, puede haber valor en la migración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-119">If these or other new features are compelling enough, there may be value in migrating the app.</span></span> <span data-ttu-id="ae8b9-120">La migración puede tomar diferentes formas; puede ser toda la aplicación o solo ciertos puntos de conexión que requieran los cambios.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-120">The migration can take different shapes; it can be the entire app, or only certain endpoints that require the changes.</span></span> <span data-ttu-id="ae8b9-121">La decisión de migrar se basa en última instancia en los problemas empresariales que debe resolver el desarrollador.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-121">The decision to migrate is ultimately based on the business problems to be solved by the developer.</span></span>

## <a name="server-side-versus-client-side-hosting"></a><span data-ttu-id="ae8b9-122">Hospedaje del lado del servidor frente al cliente</span><span class="sxs-lookup"><span data-stu-id="ae8b9-122">Server-side versus client-side hosting</span></span>

<span data-ttu-id="ae8b9-123">Como se describe en el capítulo de modelos de [hospedaje,](hosting-models.md) una aplicación Blazor se puede hospedar de dos maneras diferentes: servidor y lado cliente.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-123">As described in the [hosting models](hosting-models.md) chapter, a Blazor app can be hosted in two different ways: server-side and client-side.</span></span> <span data-ttu-id="ae8b9-124">El modelo del lado servidor utiliza ASP.NET conexiones Core SignalR para administrar las actualizaciones de DOM mientras se ejecuta cualquier código real en el servidor.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-124">The server-side model uses ASP.NET Core SignalR connections to manage the DOM updates while running any actual code on the server.</span></span> <span data-ttu-id="ae8b9-125">El modelo del lado cliente se ejecuta como WebAssembly dentro de un explorador y no requiere conexiones de servidor.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-125">The client-side model runs as WebAssembly within a browser and requires no server connections.</span></span> <span data-ttu-id="ae8b9-126">Hay una serie de diferencias que pueden afectar a cuál es mejor para una aplicación específica:</span><span class="sxs-lookup"><span data-stu-id="ae8b9-126">There are a number of differences that may affect which is best for a specific app:</span></span>

- <span data-ttu-id="ae8b9-127">Se ejecuta como WebAssembly todavía está en desarrollo y puede que no admita todas las características (como el subprocesamiento) en el momento actual</span><span class="sxs-lookup"><span data-stu-id="ae8b9-127">Running as WebAssembly is still in development and may not support all features (such as threading) at the current time</span></span>
- <span data-ttu-id="ae8b9-128">La comunicación entre el cliente y el servidor puede causar problemas de latencia en el modo del lado del servidor</span><span class="sxs-lookup"><span data-stu-id="ae8b9-128">Chatty communication between the client and server may cause latency issues in server-side mode</span></span>
- <span data-ttu-id="ae8b9-129">El acceso a bases de datos y servicios internos o protegidos requiere un servicio independiente con alojamiento del lado cliente</span><span class="sxs-lookup"><span data-stu-id="ae8b9-129">Access to databases and internal or protected services require a separate service with client-side hosting</span></span>

<span data-ttu-id="ae8b9-130">En el momento de escribir, el modelo del lado servidor se parece más a los formularios Web Forms.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-130">At the time of writing, the server-side model more closely resembles Web Forms.</span></span> <span data-ttu-id="ae8b9-131">La mayor parte de este capítulo se centra en el modelo de hospedaje del lado servidor, ya que está listo para producción.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-131">Most of this chapter focuses on the server-side hosting model, as it's production-ready.</span></span>

## <a name="create-a-new-project"></a><span data-ttu-id="ae8b9-132">Creación de un nuevo proyecto</span><span class="sxs-lookup"><span data-stu-id="ae8b9-132">Create a new project</span></span>

<span data-ttu-id="ae8b9-133">Este paso de migración inicial consiste en crear un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-133">This initial migration step is to create a new project.</span></span> <span data-ttu-id="ae8b9-134">Este tipo de proyecto se basa en los proyectos de estilo SDK de .NET Core y simplifica gran parte de la placa reutilizable que se usó en formatos de proyecto anteriores.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-134">This project type is based on the SDK style projects of .NET Core and simplifies much of the boilerplate that was used in previous project formats.</span></span> <span data-ttu-id="ae8b9-135">Para obtener más detalles, consulte el capítulo Estructura [del proyecto](project-structure.md).</span><span class="sxs-lookup"><span data-stu-id="ae8b9-135">For more detail, please see the chapter on [Project Structure](project-structure.md).</span></span>

<span data-ttu-id="ae8b9-136">Una vez creado el proyecto, instale las bibliotecas que se usaron en el proyecto anterior.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-136">Once the project has been created, install the libraries that were used in the previous project.</span></span> <span data-ttu-id="ae8b9-137">En proyectos de formularios Web Forms anteriores, es posible que haya utilizado el archivo *packages.config* para enumerar los paquetes NuGet necesarios.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-137">In older Web Forms projects, you may have used the *packages.config* file to list the required NuGet packages.</span></span> <span data-ttu-id="ae8b9-138">En el nuevo proyecto de estilo SDK, *packages.config* se ha reemplazado por `<PackageReference>` elementos en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-138">In the new SDK-style project, *packages.config* has been replaced with `<PackageReference>` elements in the project file.</span></span> <span data-ttu-id="ae8b9-139">Una ventaja de este enfoque es que todas las dependencias se instalan transitivamente.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-139">A benefit to this approach is that all dependencies are installed transitively.</span></span> <span data-ttu-id="ae8b9-140">Solo enumera las dependencias de nivel superior que le importan.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-140">You only list the top-level dependencies you care about.</span></span>

<span data-ttu-id="ae8b9-141">Muchas de las dependencias que usa están disponibles para .NET Core, incluidos Entity Framework 6 y log4net.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-141">Many of the dependencies you're using are available for .NET Core, including Entity Framework 6 and log4net.</span></span> <span data-ttu-id="ae8b9-142">Si no hay ninguna versión de .NET Core o .NET Standard disponible, a menudo se puede usar la versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-142">If there's no .NET Core or .NET Standard version available, the .NET Framework version can often be used.</span></span> <span data-ttu-id="ae8b9-143">Puede que tu experiencia sea diferente.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-143">Your mileage may vary.</span></span> <span data-ttu-id="ae8b9-144">Cualquier API utilizada que no esté disponible en .NET Core produce un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-144">Any API used that isn't available in .NET Core causes a runtime error.</span></span> <span data-ttu-id="ae8b9-145">Visual Studio le notifica de dichos paquetes.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-145">Visual Studio notifies you of such packages.</span></span> <span data-ttu-id="ae8b9-146">Aparece un icono amarillo en el nodo **Referencias** del proyecto en el Explorador de **soluciones.**</span><span class="sxs-lookup"><span data-stu-id="ae8b9-146">A yellow icon appears on the project's **References** node in **Solution Explorer**.</span></span>

<span data-ttu-id="ae8b9-147">En el proyecto eShop basado en Blazor, puede ver los paquetes que están instalados.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-147">In the Blazor-based eShop project, you can see the packages that are installed.</span></span> <span data-ttu-id="ae8b9-148">Anteriormente, el archivo *packages.config* enumeraba todos los paquetes utilizados en el proyecto, lo que provocaba un tamaño de casi 50 líneas.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-148">Previously, the *packages.config* file listed every package used in the project, resulting in a file almost 50 lines long.</span></span> <span data-ttu-id="ae8b9-149">Un fragmento de *packages.config* es:</span><span class="sxs-lookup"><span data-stu-id="ae8b9-149">A snippet of *packages.config* is:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<packages>
  ...
  <package id="Microsoft.ApplicationInsights.Agent.Intercept" version="2.4.0" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.DependencyCollector" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.PerfCounterCollector" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.Web" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.WindowsServer" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.WindowsServer.TelemetryChannel" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.AspNet.FriendlyUrls" version="1.0.2" targetFramework="net472" />
  <package id="Microsoft.AspNet.FriendlyUrls.Core" version="1.0.2" targetFramework="net472" />
  <package id="Microsoft.AspNet.ScriptManager.MSAjax" version="5.0.0" targetFramework="net472" />
  <package id="Microsoft.AspNet.ScriptManager.WebForms" version="5.0.0" targetFramework="net472" />
  ...
  <package id="System.Memory" version="4.5.1" targetFramework="net472" />
  <package id="System.Numerics.Vectors" version="4.4.0" targetFramework="net472" />
  <package id="System.Runtime.CompilerServices.Unsafe" version="4.5.0" targetFramework="net472" />
  <package id="System.Threading.Channels" version="4.5.0" targetFramework="net472" />
  <package id="System.Threading.Tasks.Extensions" version="4.5.1" targetFramework="net472" />
  <package id="WebGrease" version="1.6.0" targetFramework="net472" />
</packages>
```

<span data-ttu-id="ae8b9-150">El `<packages>` elemento incluye todas las dependencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-150">The `<packages>` element includes all necessary dependencies.</span></span> <span data-ttu-id="ae8b9-151">Es difícil identificar cuáles de estos paquetes están incluidos porque los necesita.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-151">It's difficult to identify which of these packages are included because you require them.</span></span> <span data-ttu-id="ae8b9-152">Algunos `<package>` elementos se enumeran simplemente para satisfacer las necesidades de dependencias que necesita.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-152">Some `<package>` elements are listed simply to satisfy the needs of dependencies you require.</span></span>

<span data-ttu-id="ae8b9-153">El proyecto Blazor enumera las dependencias que necesita dentro de un `<ItemGroup>` elemento en el archivo de proyecto:</span><span class="sxs-lookup"><span data-stu-id="ae8b9-153">The Blazor project lists the dependencies you require within an `<ItemGroup>` element in the project file:</span></span>

```xml
<ItemGroup>
    <PackageReference Include="Autofac" Version="4.9.3" />
    <PackageReference Include="EntityFramework" Version="6.3.0-preview9-19423-04" />
    <PackageReference Include="log4net" Version="2.0.8" />
</ItemGroup>
```

<span data-ttu-id="ae8b9-154">Un paquete NuGet que simplifica la vida de los desarrolladores de formularios Web Forms es el paquete de [compatibilidad de Windows.](../../core/porting/windows-compat-pack.md)</span><span class="sxs-lookup"><span data-stu-id="ae8b9-154">One NuGet package that simplifies the life of Web Forms developers is the [Windows Compatibility Pack](../../core/porting/windows-compat-pack.md).</span></span> <span data-ttu-id="ae8b9-155">Aunque .NET Core es multiplataforma, algunas características solo están disponibles en Windows.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-155">Although .NET Core is cross-platform, some features are only available on Windows.</span></span> <span data-ttu-id="ae8b9-156">Las características específicas de Windows están disponibles mediante la instalación del paquete de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-156">Windows-specific features are made available by installing the compatibility pack.</span></span> <span data-ttu-id="ae8b9-157">Entre los ejemplos de estas características se incluyen el Registro, WMI y Directory Services.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-157">Examples of such features include the Registry, WMI, and Directory Services.</span></span> <span data-ttu-id="ae8b9-158">El paquete añade alrededor de 20.000 API y activa muchos servicios con los que ya está familiarizado.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-158">The package adds around 20,000 APIs and activates many services with which you may already be familiar.</span></span> <span data-ttu-id="ae8b9-159">El proyecto eShop no requiere el paquete de compatibilidad; pero si los proyectos usan características específicas de Windows, el paquete facilita los esfuerzos de migración.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-159">The eShop project doesn't require the compatibility pack; but if your projects use Windows-specific features, the package eases the migration efforts.</span></span>

## <a name="enable-startup-process"></a><span data-ttu-id="ae8b9-160">Habilitar el proceso de inicio</span><span class="sxs-lookup"><span data-stu-id="ae8b9-160">Enable startup process</span></span>

<span data-ttu-id="ae8b9-161">El proceso de inicio de Blazor ha cambiado de formularios Web Forms y sigue una configuración similar para otros servicios ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-161">The startup process for Blazor has changed from Web Forms and follows a similar setup for other ASP.NET Core services.</span></span> <span data-ttu-id="ae8b9-162">Cuando se hospedan en el lado del servidor, los componentes de Blazor se ejecutan como parte de una aplicación normal ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-162">When hosted server-side, Blazor components are run as part of a normal ASP.NET Core app.</span></span> <span data-ttu-id="ae8b9-163">Cuando se hospedan en el explorador con WebAssembly, los componentes de Blazor utilizan un modelo de hospedaje similar.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-163">When hosted in the browser with WebAssembly, Blazor components use a similar hosting model.</span></span> <span data-ttu-id="ae8b9-164">La diferencia es que los componentes se ejecutan como un servicio independiente de cualquiera de los procesos de back-end.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-164">The difference is the components are run as a separate service from any of the backend processes.</span></span> <span data-ttu-id="ae8b9-165">De cualquier manera, el inicio es similar.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-165">Either way, the startup is similar.</span></span>

<span data-ttu-id="ae8b9-166">El archivo *Global.asax.cs* es la página de inicio predeterminada para los proyectos de formularios Web Forms.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-166">The *Global.asax.cs* file is the default startup page for Web Forms projects.</span></span> <span data-ttu-id="ae8b9-167">En el proyecto eShop, este archivo configura el contenedor Inversión de control (IoC) y controla los distintos eventos del ciclo de vida de la aplicación o solicitud.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-167">In the eShop project, this file configures the Inversion of Control (IoC) container and handles the various lifecycle events of the app or request.</span></span> <span data-ttu-id="ae8b9-168">Algunos de estos eventos se controlan `Application_BeginRequest`con middleware (como ).</span><span class="sxs-lookup"><span data-stu-id="ae8b9-168">Some of these events are handled with middleware (such as `Application_BeginRequest`).</span></span> <span data-ttu-id="ae8b9-169">Otros eventos requieren la invalidación de servicios específicos a través de la inserción de dependencias (DI).</span><span class="sxs-lookup"><span data-stu-id="ae8b9-169">Other events require the overriding of specific services via dependency injection (DI).</span></span>

<span data-ttu-id="ae8b9-170">A modo de ejemplo, el archivo *Global.asax.cs* para eShop contiene el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="ae8b9-170">By way of example, the *Global.asax.cs* file for eShop, contains the following code:</span></span>

```csharp
public class Global : HttpApplication, IContainerProviderAccessor
{
    private static readonly ILog _log = LogManager.GetLogger(System.Reflection.MethodBase.GetCurrentMethod().DeclaringType);

    static IContainerProvider _containerProvider;
    IContainer container;

    public IContainerProvider ContainerProvider
    {
        get { return _containerProvider; }
    }

    protected void Application_Start(object sender, EventArgs e)
    {
        // Code that runs on app startup
        RouteConfig.RegisterRoutes(RouteTable.Routes);
        BundleConfig.RegisterBundles(BundleTable.Bundles);
        ConfigureContainer();
        ConfigDataBase();
    }

    /// <summary>
    /// Track the machine name and the start time for the session inside the current session
    /// </summary>
    protected void Session_Start(Object sender, EventArgs e)
    {
        HttpContext.Current.Session["MachineName"] = Environment.MachineName;
        HttpContext.Current.Session["SessionStartTime"] = DateTime.Now;
    }

    /// <summary>
    /// http://docs.autofac.org/en/latest/integration/webforms.html
    /// </summary>
    private void ConfigureContainer()
    {
        var builder = new ContainerBuilder();
        var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);
        builder.RegisterModule(new ApplicationModule(mockData));
        container = builder.Build();
        _containerProvider = new ContainerProvider(container);
    }

    private void ConfigDataBase()
    {
        var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);

        if (!mockData)
        {
            Database.SetInitializer<CatalogDBContext>(container.Resolve<CatalogDBInitializer>());
        }
    }

    protected void Application_BeginRequest(object sender, EventArgs e)
    {
        //set the property to our new object
        LogicalThreadContext.Properties["activityid"] = new ActivityIdHelper();

        LogicalThreadContext.Properties["requestinfo"] = new WebRequestInfo();

        _log.Debug("Application_BeginRequest");
    }
}
```

<span data-ttu-id="ae8b9-171">El archivo anterior se `Startup` convierte en la clase en Blazor del lado del servidor:</span><span class="sxs-lookup"><span data-stu-id="ae8b9-171">The preceding file becomes the `Startup` class in server-side Blazor:</span></span>

```csharp
public class Startup
{
    public Startup(IConfiguration configuration, IWebHostEnvironment env)
    {
        Configuration = configuration;
        Env = env;
    }

    public IConfiguration Configuration { get; }

    public IWebHostEnvironment Env { get; }

    // This method gets called by the runtime. Use this method to add services to the container.
    // For more information on how to configure your application, visit https://go.microsoft.com/fwlink/?LinkID=398940
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddRazorPages();
        services.AddServerSideBlazor();

        if (Configuration.GetValue<bool>("UseMockData"))
        {
            services.AddSingleton<ICatalogService, CatalogServiceMock>();
        }
        else
        {
            services.AddScoped<ICatalogService, CatalogService>();
            services.AddScoped<IDatabaseInitializer<CatalogDBContext>, CatalogDBInitializer>();
            services.AddSingleton<CatalogItemHiLoGenerator>();
            services.AddScoped(_ => new CatalogDBContext(Configuration.GetConnectionString("CatalogDBContext")));
        }
    }

    // This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
    public void Configure(IApplicationBuilder app, ILoggerFactory loggerFactory)
    {
        loggerFactory.AddLog4Net("log4Net.xml");

        if (Env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }
        else
        {
            app.UseExceptionHandler("/Home/Error");
        }

        // Middleware for Application_BeginRequest
        app.Use((ctx, next) =>
        {
            LogicalThreadContext.Properties["activityid"] = new ActivityIdHelper(ctx);
            LogicalThreadContext.Properties["requestinfo"] = new WebRequestInfo(ctx);
            return next();
        });

        app.UseStaticFiles();

        app.UseRouting();

        app.UseEndpoints(endpoints =>
        {
            endpoints.MapBlazorHub();
            endpoints.MapFallbackToPage("/_Host");
        });

        ConfigDataBase(app);
    }

    private void ConfigDataBase(IApplicationBuilder app)
    {
        using (var scope = app.ApplicationServices.CreateScope())
        {
            var initializer = scope.ServiceProvider.GetService<IDatabaseInitializer<CatalogDBContext>>();

            if (initializer != null)
            {
                Database.SetInitializer(initializer);
            }
        }
    }
}
```

<span data-ttu-id="ae8b9-172">Un cambio significativo que puede notar de los formularios Web Forms es el protagonismo de di.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-172">One significant change you may notice from Web Forms is the prominence of DI.</span></span> <span data-ttu-id="ae8b9-173">DI ha sido un principio rector en el diseño ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-173">DI has been a guiding principle in the ASP.NET Core design.</span></span> <span data-ttu-id="ae8b9-174">Admite la personalización de casi todos los aspectos del marco de trabajo de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-174">It supports customization of almost all aspects of the ASP.NET Core framework.</span></span> <span data-ttu-id="ae8b9-175">Incluso hay un proveedor de servicios integrado que se puede usar para muchos escenarios.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-175">There's even a built-in service provider that can be used for many scenarios.</span></span> <span data-ttu-id="ae8b9-176">Si se requiere más personalización, puede ser compatible con muchos proyectos de la comunidad.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-176">If more customization is required, it can be supported by the many community projects.</span></span> <span data-ttu-id="ae8b9-177">Por ejemplo, puede llevar adelante su inversión en biblioteca DI de terceros.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-177">For example, you can carry forward your third-party DI library investment.</span></span>

<span data-ttu-id="ae8b9-178">En la aplicación eShop original, hay alguna configuración para la administración de sesiones.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-178">In the original eShop app, there's some configuration for session management.</span></span> <span data-ttu-id="ae8b9-179">Puesto que Blazor del lado del servidor utiliza ASP.NET Core SignalR para la comunicación, el estado de sesión no se admite ya que las conexiones pueden producirse independientemente de un contexto HTTP.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-179">Since server-side Blazor uses ASP.NET Core SignalR for communication, session state isn't supported as the connections may occur independent of an HTTP context.</span></span> <span data-ttu-id="ae8b9-180">Una aplicación que usa el estado de sesión requiere la rearquitectura antes de ejecutarse como una aplicación Blazor.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-180">An app that uses session state requires rearchitecting before running as a Blazor app.</span></span>

<span data-ttu-id="ae8b9-181">Para obtener más información sobre el inicio de la aplicación, consulte [Inicio de](app-startup.md)la aplicación .</span><span class="sxs-lookup"><span data-stu-id="ae8b9-181">For more information about app startup, see [App startup](app-startup.md).</span></span>

## <a name="migrate-http-modules-and-handlers-to-middleware"></a><span data-ttu-id="ae8b9-182">Migrar módulos y controladores HTTP a middleware</span><span class="sxs-lookup"><span data-stu-id="ae8b9-182">Migrate HTTP modules and handlers to middleware</span></span>

<span data-ttu-id="ae8b9-183">Los módulos y controladores HTTP son patrones comunes en formularios Web Forms para controlar la canalización de solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-183">HTTP modules and handlers are common patterns in Web Forms to control the HTTP request pipeline.</span></span> <span data-ttu-id="ae8b9-184">Clases `IHttpModule` que `IHttpHandler` implementan o podrían registrarse y procesar solicitudes entrantes.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-184">Classes that implement `IHttpModule` or `IHttpHandler` could be registered and process incoming requests.</span></span> <span data-ttu-id="ae8b9-185">Formularios Web Forms configura módulos y controladores en el archivo *web.config.*</span><span class="sxs-lookup"><span data-stu-id="ae8b9-185">Web Forms configures modules and handlers in the *web.config* file.</span></span> <span data-ttu-id="ae8b9-186">Los formularios Web Forms también se basan en gran medida en el control de eventos del ciclo de vida de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-186">Web Forms is also heavily based on app lifecycle event handling.</span></span> <span data-ttu-id="ae8b9-187">ASP.NET Core usa middleware en su lugar.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-187">ASP.NET Core uses middleware instead.</span></span> <span data-ttu-id="ae8b9-188">Middleware está registrado `Configure` en `Startup` el método de la clase.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-188">Middleware is registered in the `Configure` method of the `Startup` class.</span></span> <span data-ttu-id="ae8b9-189">El orden de ejecución del middleware viene determinado por la orden de registro.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-189">Middleware execution order is determined by the registration order.</span></span>

<span data-ttu-id="ae8b9-190">En la sección Habilitar proceso de [inicio,](#enable-startup-process) los formularios `Application_BeginRequest` Web Forms generaron un evento de ciclo de vida como método.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-190">In the [Enable startup process](#enable-startup-process) section, a lifecycle event was raised by Web Forms as the `Application_BeginRequest` method.</span></span> <span data-ttu-id="ae8b9-191">Este evento no está disponible en ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-191">This event isn't available in ASP.NET Core.</span></span> <span data-ttu-id="ae8b9-192">Una manera de lograr este comportamiento es implementar middleware como se ve en el ejemplo de archivo *Startup.cs.*</span><span class="sxs-lookup"><span data-stu-id="ae8b9-192">One way to achieve this behavior is to implement middleware as seen in the *Startup.cs* file example.</span></span> <span data-ttu-id="ae8b9-193">Este middleware realiza la misma lógica y, a continuación, transfiere el control al siguiente controlador de la canalización de middleware.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-193">This middleware does the same logic and then transfers control to the next handler in the middleware pipeline.</span></span>

<span data-ttu-id="ae8b9-194">Para obtener más información sobre la migración de módulos y controladores, vea [Migrar controladores y módulos HTTP a ASP.NET middleware Core](/aspnet/core/migration/http-modules).</span><span class="sxs-lookup"><span data-stu-id="ae8b9-194">For more information on migrating modules and handlers, see [Migrate HTTP handlers and modules to ASP.NET Core middleware](/aspnet/core/migration/http-modules).</span></span>

## <a name="migrate-static-files"></a><span data-ttu-id="ae8b9-195">Migrar archivos estáticos</span><span class="sxs-lookup"><span data-stu-id="ae8b9-195">Migrate static files</span></span>

<span data-ttu-id="ae8b9-196">Para servir archivos estáticos (por ejemplo, HTML, CSS, imágenes y JavaScript), los archivos deben exponerse mediante middleware.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-196">To serve static files (for example, HTML, CSS, images, and JavaScript), the files must be exposed by middleware.</span></span> <span data-ttu-id="ae8b9-197">Llamar `UseStaticFiles` al método habilita la publicación de archivos estáticos desde la ruta de acceso raíz web.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-197">Calling the `UseStaticFiles` method enables the serving of static files from the web root path.</span></span> <span data-ttu-id="ae8b9-198">El directorio raíz web predeterminado es *wwwroot,* pero se puede personalizar.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-198">The default web root directory is *wwwroot*, but it can be customized.</span></span> <span data-ttu-id="ae8b9-199">Como se `Configure` incluye en el `Startup` método de la clase de eShop:</span><span class="sxs-lookup"><span data-stu-id="ae8b9-199">As included in the `Configure` method of eShop's `Startup` class:</span></span>

```csharp
public void Configure(IApplicationBuilder app)
{
    ...

    app.UseStaticFiles();

    ...
}
```

<span data-ttu-id="ae8b9-200">El proyecto eShop permite el acceso básico a archivos estáticos.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-200">The eShop project enables basic static file access.</span></span> <span data-ttu-id="ae8b9-201">Hay muchas personalizaciones disponibles para el acceso a archivos estáticos.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-201">There are many customizations available for static file access.</span></span> <span data-ttu-id="ae8b9-202">Para obtener información sobre cómo habilitar archivos predeterminados o un explorador de archivos, consulte [Archivos estáticos en ASP.NET Core](/aspnet/core/fundamentals/static-files).</span><span class="sxs-lookup"><span data-stu-id="ae8b9-202">For information on enabling default files or a file browser, see [Static files in ASP.NET Core](/aspnet/core/fundamentals/static-files).</span></span>

## <a name="migrate-runtime-bundling-and-minification-setup"></a><span data-ttu-id="ae8b9-203">Migrar la agrupación en tiempo de ejecución y la configuración de minificación</span><span class="sxs-lookup"><span data-stu-id="ae8b9-203">Migrate runtime bundling and minification setup</span></span>

<span data-ttu-id="ae8b9-204">La agrupación y la minificación son técnicas de optimización del rendimiento para reducir el número y el tamaño de las solicitudes de servidor para recuperar determinados tipos de archivo.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-204">Bundling and minification are performance optimization techniques for reducing the number and size of server requests to retrieve certain file types.</span></span> <span data-ttu-id="ae8b9-205">JavaScript y CSS a menudo se someten a algún tipo de agrupación o minificación antes de ser enviados al cliente.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-205">JavaScript and CSS often undergo some form of bundling or minification before being sent to the client.</span></span> <span data-ttu-id="ae8b9-206">En ASP.NET formularios Web Forms, estas optimizaciones se controlan en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-206">In ASP.NET Web Forms, these optimizations are handled at runtime.</span></span> <span data-ttu-id="ae8b9-207">Las convenciones de optimización se definen un archivo *App_Start/BundleConfig.cs.*</span><span class="sxs-lookup"><span data-stu-id="ae8b9-207">The optimization conventions are defined an *App_Start/BundleConfig.cs* file.</span></span> <span data-ttu-id="ae8b9-208">En ASP.NET Núcleo, se adopta un enfoque más declarativo.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-208">In ASP.NET Core, a more declarative approach is adopted.</span></span> <span data-ttu-id="ae8b9-209">Un archivo enumera los archivos que se van a minificar, junto con la configuración de minificación específica.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-209">A file lists the files to be minified, along with specific minification settings.</span></span>

<span data-ttu-id="ae8b9-210">Para obtener más información sobre la agrupación y la minificación, consulte [Agrupar y minificar activos estáticos en ASP.NET Core](/aspnet/core/client-side/bundling-and-minification).</span><span class="sxs-lookup"><span data-stu-id="ae8b9-210">For more information on bundling and minification, see [Bundle and minify static assets in ASP.NET Core](/aspnet/core/client-side/bundling-and-minification).</span></span>

## <a name="migrate-aspx-pages"></a><span data-ttu-id="ae8b9-211">Migrar páginas ASPX</span><span class="sxs-lookup"><span data-stu-id="ae8b9-211">Migrate ASPX pages</span></span>

<span data-ttu-id="ae8b9-212">Una página de una aplicación de formularios Web Forms es un archivo con la extensión *.aspx.*</span><span class="sxs-lookup"><span data-stu-id="ae8b9-212">A page in a Web Forms app is a file with the *.aspx* extension.</span></span> <span data-ttu-id="ae8b9-213">Una página de formularios Web Forms a menudo se puede asignar a un componente en Blazor.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-213">A Web Forms page can often be mapped to a component in Blazor.</span></span> <span data-ttu-id="ae8b9-214">Un componente Blazor se crea en un archivo con la extensión *.razor.*</span><span class="sxs-lookup"><span data-stu-id="ae8b9-214">A Blazor component is authored in a file with the *.razor* extension.</span></span> <span data-ttu-id="ae8b9-215">Para el proyecto eShop, cinco páginas se convierten en una página Razor.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-215">For the eShop project, five pages are converted to a Razor page.</span></span>

<span data-ttu-id="ae8b9-216">Por ejemplo, la vista de detalles se compone de tres archivos en el proyecto de formularios Web Forms: *Details.aspx*, *Details.aspx.cs*y *Details.aspx.designer.cs*.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-216">For example, the details view is comprised of three files in the Web Forms project: *Details.aspx*, *Details.aspx.cs*, and *Details.aspx.designer.cs*.</span></span> <span data-ttu-id="ae8b9-217">Al convertir a Blazor, el código subyacente y el marcado se combinan en *Details.razor*.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-217">When converting to Blazor, the code-behind and markup are combined into *Details.razor*.</span></span> <span data-ttu-id="ae8b9-218">La compilación de Razor (equivalente a lo que está en archivos *.designer.cs)* se almacena en el directorio *obj* y no se pueden ver, de forma predeterminada, en el **Explorador**de soluciones .</span><span class="sxs-lookup"><span data-stu-id="ae8b9-218">Razor compilation (equivalent to what's in *.designer.cs* files) is stored in the *obj* directory and aren't, by default, viewable in **Solution Explorer**.</span></span> <span data-ttu-id="ae8b9-219">La página de formularios Web Forms consta del siguiente marcado:</span><span class="sxs-lookup"><span data-stu-id="ae8b9-219">The Web Forms page consists of the following markup:</span></span>

```aspx-csharp
<%@ Page Title="Details" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Details.aspx.cs" Inherits="eShopLegacyWebForms.Catalog.Details" %>

<asp:Content ID="Details" ContentPlaceHolderID="MainContent" runat="server">
    <h2 class="esh-body-title">Details</h2>

    <div class="container">
        <div class="row">
            <asp:Image runat="server" CssClass="col-md-6 esh-picture" ImageUrl='<%#"/Pics/" + product.PictureFileName%>' />
            <dl class="col-md-6 dl-horizontal">
                <dt>Name
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.Name%>' />
                </dd>

                <dt>Description
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.Description%>' />
                </dd>

                <dt>Brand
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.CatalogBrand.Brand%>' />
                </dd>

                <dt>Type
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.CatalogType.Type%>' />
                </dd>
                <dt>Price
                </dt>

                <dd>
                    <asp:Label CssClass="esh-price" runat="server" Text='<%#product.Price%>' />
                </dd>

                <dt>Picture name
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.PictureFileName%>' />
                </dd>

                <dt>Stock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.AvailableStock%>' />
                </dd>

                <dt>Restock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.RestockThreshold%>' />
                </dd>

                <dt>Max stock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.MaxStockThreshold%>' />
                </dd>

            </dl>
        </div>

        <div class="form-actions no-color esh-link-list">
            <a runat="server" href='<%# GetRouteUrl("EditProductRoute", new {id =product.Id}) %>' class="esh-link-item">Edit
            </a>
            |
            <a runat="server" href="~" class="esh-link-item">Back to list
            </a>
        </div>

    </div>
</asp:Content>
```

<span data-ttu-id="ae8b9-220">El código subyacente del marcado anterior incluye el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ae8b9-220">The preceding markup's code-behind includes the following code:</span></span>

```csharp
using eShopLegacyWebForms.Models;
using eShopLegacyWebForms.Services;
using log4net;
using System;
using System.Web.UI;

namespace eShopLegacyWebForms.Catalog
{
    public partial class Details : System.Web.UI.Page
    {
        private static readonly ILog _log = LogManager.GetLogger(System.Reflection.MethodBase.GetCurrentMethod().DeclaringType);

        protected CatalogItem product;

        public ICatalogService CatalogService { get; set; }

        protected void Page_Load(object sender, EventArgs e)
        {
            var productId = Convert.ToInt32(Page.RouteData.Values["id"]);
            _log.Info($"Now loading... /Catalog/Details.aspx?id={productId}");
            product = CatalogService.FindCatalogItem(productId);

            this.DataBind();
        }
    }
}
```

<span data-ttu-id="ae8b9-221">Cuando se convierte a Blazor, la página de formularios Web Forms se traduce en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ae8b9-221">When converted to Blazor, the Web Forms page translates to the following code:</span></span>

```razor
@page "/Catalog/Details/{id:int}"
@inject ICatalogService CatalogService
@inject ILogger<Details> Logger

<h2 class="esh-body-title">Details</h2>

<div class="container">
    <div class="row">
        <img class="col-md-6 esh-picture" src="@($"/Pics/{_item.PictureFileName}")">

        <dl class="col-md-6 dl-horizontal">
            <dt>
                Name
            </dt>

            <dd>
                @_item.Name
            </dd>

            <dt>
                Description
            </dt>

            <dd>
                @_item.Description
            </dd>

            <dt>
                Brand
            </dt>

            <dd>
                @_item.CatalogBrand.Brand
            </dd>

            <dt>
                Type
            </dt>

            <dd>
                @_item.CatalogType.Type
            </dd>
            <dt>
                Price
            </dt>

            <dd>
                @_item.Price
            </dd>

            <dt>
                Picture name
            </dt>

            <dd>
                @_item.PictureFileName
            </dd>

            <dt>
                Stock
            </dt>

            <dd>
                @_item.AvailableStock
            </dd>

            <dt>
                Restock
            </dt>

            <dd>
                @_item.RestockThreshold
            </dd>

            <dt>
                Max stock
            </dt>

            <dd>
                @_item.MaxStockThreshold
            </dd>

        </dl>
    </div>

    <div class="form-actions no-color esh-link-list">
        <a href="@($"/Catalog/Edit/{_item.Id}")" class="esh-link-item">
            Edit
        </a>
        |
        <a href="/" class="esh-link-item">
            Back to list
        </a>
    </div>

</div>

@code {
    private CatalogItem _item;

    [Parameter]
    public int Id { get; set; }

    protected override void OnInitialized()
    {
        Logger.LogInformation("Now loading... /Catalog/Details/{Id}", Id);

        _item = CatalogService.FindCatalogItem(Id);
    }
}
```

<span data-ttu-id="ae8b9-222">Observe que el código y el marcado están en el mismo archivo.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-222">Notice that the code and markup are in the same file.</span></span> <span data-ttu-id="ae8b9-223">Los servicios necesarios se `@inject` hacen accesibles con el atributo.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-223">Any required services are made accessible with the `@inject` attribute.</span></span> <span data-ttu-id="ae8b9-224">Según `@page` la directiva, se puede `Catalog/Details/{id}` acceder a esta página en la ruta.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-224">Per the `@page` directive, this page can be accessed at the `Catalog/Details/{id}` route.</span></span> <span data-ttu-id="ae8b9-225">El valor del marcador `{id}` de posición de la ruta se ha restringido a un entero.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-225">The value of the route's `{id}` placeholder has been constrained to an integer.</span></span> <span data-ttu-id="ae8b9-226">Como se describe en la sección [de enrutamiento,](pages-routing-layouts.md) a diferencia de los formularios Web Forms, un componente Razor indica explícitamente su ruta y los parámetros que se incluyen.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-226">As described in the [routing](pages-routing-layouts.md) section, unlike Web Forms, a Razor component explicitly states its route and any parameters that are included.</span></span> <span data-ttu-id="ae8b9-227">Es posible que muchos controles de formularios Web Forms no tengan homólogos exactos en Blazor.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-227">Many Web Forms controls may not have exact counterparts in Blazor.</span></span> <span data-ttu-id="ae8b9-228">A menudo hay un fragmento de código HTML equivalente que servirá para el mismo propósito.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-228">There's often an equivalent HTML snippet that will serve the same purpose.</span></span> <span data-ttu-id="ae8b9-229">Por ejemplo, `<asp:Label />` el control se puede `<label>` reemplazar con un elemento HTML.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-229">For example, the `<asp:Label />` control can be replaced with an HTML `<label>` element.</span></span>

### <a name="model-validation-in-blazor"></a><span data-ttu-id="ae8b9-230">Validación del modelo en Blazor</span><span class="sxs-lookup"><span data-stu-id="ae8b9-230">Model validation in Blazor</span></span>

<span data-ttu-id="ae8b9-231">Si el código de formularios Web Forms incluye validación, puede transferir gran parte de lo que tiene con cambios poco o ningún.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-231">If your Web Forms code includes validation, you can transfer much of what you have with little-to-no changes.</span></span> <span data-ttu-id="ae8b9-232">Una ventaja de ejecutar se ejecuta en Blazor es que se puede ejecutar la misma lógica de validación sin necesidad de JavaScript personalizado.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-232">A benefit to running in Blazor is that the same validation logic can be run without needing custom JavaScript.</span></span> <span data-ttu-id="ae8b9-233">Las anotaciones de datos facilitan la validación del modelo.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-233">Data annotations enable easy model validation.</span></span>

<span data-ttu-id="ae8b9-234">Por ejemplo, el *Create.aspx* página tiene un formulario de entrada de datos con validación.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-234">For example, the *Create.aspx* page has a data entry form with validation.</span></span> <span data-ttu-id="ae8b9-235">Un fragmento de código de ejemplo tendría este aspecto:</span><span class="sxs-lookup"><span data-stu-id="ae8b9-235">An example snippet would look like this:</span></span>

```aspx
<div class="form-group">
    <label class="control-label col-md-2">Name</label>
    <div class="col-md-3">
        <asp:TextBox ID="Name" runat="server" CssClass="form-control"></asp:TextBox>
        <asp:RequiredFieldValidator runat="server" ControlToValidate="Name" Display="Dynamic"
            CssClass="field-validation-valid text-danger" ErrorMessage="The Name field is required." />
    </div>
</div>
```

<span data-ttu-id="ae8b9-236">En Blazor, el marcado equivalente se proporciona en un archivo *Create.razor:*</span><span class="sxs-lookup"><span data-stu-id="ae8b9-236">In Blazor, the equivalent markup is provided in a *Create.razor* file:</span></span>

```razor
<EditForm Model="_item" OnValidSubmit="@...">
    <DataAnnotationsValidator />

    <div class="form-group">
        <label class="control-label col-md-2">Name</label>
        <div class="col-md-3">
            <InputText class="form-control" @bind-Value="_item.Name" />
            <ValidationMessage For="(() => _item.Name)" />
        </div>
    </div>

    ...
</EditForm>
```

<span data-ttu-id="ae8b9-237">El `EditForm` contexto incluye compatibilidad con validación y se puede ajustar alrededor de la entrada.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-237">The `EditForm` context includes validation support and can be wrapped around input.</span></span> <span data-ttu-id="ae8b9-238">Las anotaciones de datos son una forma común de agregar validación.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-238">Data annotations are a common way to add validation.</span></span> <span data-ttu-id="ae8b9-239">Este soporte de validación `DataAnnotationsValidator` se puede agregar a través del componente.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-239">Such validation support can be added via the `DataAnnotationsValidator` component.</span></span> <span data-ttu-id="ae8b9-240">Para obtener más información sobre este mecanismo, consulte [ASP.NET formularios y validación de Blazor básico](/aspnet/core/blazor/forms-validation).</span><span class="sxs-lookup"><span data-stu-id="ae8b9-240">For more information on this mechanism, see [ASP.NET Core Blazor forms and validation](/aspnet/core/blazor/forms-validation).</span></span>

## <a name="migrate-built-in-web-forms-controls"></a><span data-ttu-id="ae8b9-241">Migrar controles de formularios Web Forms integrados</span><span class="sxs-lookup"><span data-stu-id="ae8b9-241">Migrate built-in Web Forms controls</span></span>

<span data-ttu-id="ae8b9-242">*Este contenido está por llegar.*</span><span class="sxs-lookup"><span data-stu-id="ae8b9-242">*This content is coming soon.*</span></span>

## <a name="migrate-configuration"></a><span data-ttu-id="ae8b9-243">Migración de la configuración</span><span class="sxs-lookup"><span data-stu-id="ae8b9-243">Migrate configuration</span></span>

<span data-ttu-id="ae8b9-244">En un proyecto de formularios Web Forms, los datos de configuración se almacenan con mayor frecuencia en el archivo *web.config.*</span><span class="sxs-lookup"><span data-stu-id="ae8b9-244">In a Web Forms project, configuration data is most commonly stored in the *web.config* file.</span></span> <span data-ttu-id="ae8b9-245">Se accede a `ConfigurationManager`los datos de configuración con .</span><span class="sxs-lookup"><span data-stu-id="ae8b9-245">The configuration data is accessed with `ConfigurationManager`.</span></span> <span data-ttu-id="ae8b9-246">A menudo se requerían servicios para analizar objetos.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-246">Services were often required to parse objects.</span></span> <span data-ttu-id="ae8b9-247">Con .NET Framework 4.7.2, la capacidad `ConfigurationBuilders`de composición se agregó a la configuración a través de .</span><span class="sxs-lookup"><span data-stu-id="ae8b9-247">With .NET Framework 4.7.2, composability was added to configuration via `ConfigurationBuilders`.</span></span> <span data-ttu-id="ae8b9-248">Estos generadores permitieron a los desarrolladores agregar varios orígenes de configuración que, a continuación, se componían en tiempo de ejecución para recuperar los valores necesarios.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-248">These builders allowed developers to add various sources for configuration that was then composed at runtime to retrieve the necessary values.</span></span>

<span data-ttu-id="ae8b9-249">ASP.NET Core introdujo un sistema de configuración flexible que le permite definir el origen de configuración o los orígenes utilizados por la aplicación y la implementación.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-249">ASP.NET Core introduced a flexible configuration system that allows you to define the configuration source or sources used by your app and deployment.</span></span> <span data-ttu-id="ae8b9-250">La `ConfigurationBuilder` infraestructura que puede usar en la aplicación de formularios Web Forms se modeló sin los conceptos utilizados en el sistema de configuración ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-250">The `ConfigurationBuilder` infrastructure that you may be using in your Web Forms app was modeled after the concepts used in the ASP.NET Core configuration system.</span></span>

<span data-ttu-id="ae8b9-251">En el siguiente fragmento de código se muestra cómo el proyecto de eShop de formularios Web Forms utiliza *web.config* para almacenar valores de configuración:</span><span class="sxs-lookup"><span data-stu-id="ae8b9-251">The following snippet demonstrates how the Web Forms eShop project uses *web.config* to store configuration values:</span></span>

```xml
<configuration>
  <configSections>
    <section name="entityFramework" type="System.Data.Entity.Internal.ConfigFile.EntityFrameworkSection, EntityFramework, Version=6.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" requirePermission="false" />
  </configSections>
  <connectionStrings>
    <add name="CatalogDBContext" connectionString="Data Source=(localdb)\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;" providerName="System.Data.SqlClient" />
  </connectionStrings>
  <appSettings>
    <add key="UseMockData" value="true" />
    <add key="UseCustomizationData" value="false" />
  </appSettings>
</configuration>
```

<span data-ttu-id="ae8b9-252">Es común que los secretos, como las cadenas de conexión de base de datos, se almacenen en *web.config*. Los secretos se conservan inevitablemente en ubicaciones no seguras, como el control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-252">It's common for secrets, such as database connection strings, to be stored within the *web.config*. The secrets are inevitably persisted in unsecure locations, such as source control.</span></span> <span data-ttu-id="ae8b9-253">Con Blazor en ASP.NET Core, la configuración basada en XML anterior se reemplaza por el siguiente JSON:</span><span class="sxs-lookup"><span data-stu-id="ae8b9-253">With Blazor on ASP.NET Core, the preceding XML-based configuration is replaced with the following JSON:</span></span>

```json
{
  "ConnectionStrings": {
    "CatalogDBContext": "Data Source=(localdb)\\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;"
  },
  "UseMockData": true,
  "UseCustomizationData": false
}
```

<span data-ttu-id="ae8b9-254">JSON es el formato de configuración predeterminado; sin embargo, ASP.NET Core admite muchos otros formatos, incluido XML.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-254">JSON is the default configuration format; however, ASP.NET Core supports many other formats, including XML.</span></span> <span data-ttu-id="ae8b9-255">También hay varios formatos compatibles con la comunidad.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-255">There are also several community-supported formats.</span></span>

<span data-ttu-id="ae8b9-256">El constructor de la clase `Startup` del proyecto `IConfiguration` Blazor acepta una instancia a través de una técnica DI conocida como inyección de constructor:</span><span class="sxs-lookup"><span data-stu-id="ae8b9-256">The constructor in the Blazor project's `Startup` class accepts an `IConfiguration` instance through a DI technique known as constructor injection:</span></span>

```csharp
public class Startup
{
    public Startup(IConfiguration configuration, IWebHostEnvironment env)
    {
        Configuration = configuration;
        Env = env;
    }

    ...
}
```

<span data-ttu-id="ae8b9-257">De forma predeterminada, variables de entorno, archivos JSON (*appsettings.json* y *appsettings. Las*opciones de la línea de comandos Environment.json y el valor de la línea de comandos se registran como orígenes de configuración válidos en el objeto de configuración.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-257">By default, environment variables, JSON files (*appsettings.json* and *appsettings.{Environment}.json*), and command-line options are registered as valid configuration sources in the configuration object.</span></span> <span data-ttu-id="ae8b9-258">Se puede acceder a `Configuration[key]`las fuentes de configuración a través de .</span><span class="sxs-lookup"><span data-stu-id="ae8b9-258">The configuration sources can be accessed via `Configuration[key]`.</span></span> <span data-ttu-id="ae8b9-259">Una técnica más avanzada consiste en enlazar los datos de configuración a objetos mediante el patrón de opciones.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-259">A more advanced technique is to bind the configuration data to objects using the options pattern.</span></span> <span data-ttu-id="ae8b9-260">Para obtener más información sobre la configuración y el patrón de opciones, consulte [Configuración en ASP.NET core](/aspnet/core/fundamentals/configuration/) y El [patrón Opciones en ASP.NET Core](/aspnet/core/fundamentals/configuration/options), respectivamente.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-260">For more information on configuration and the options pattern, see [Configuration in ASP.NET Core](/aspnet/core/fundamentals/configuration/) and [Options pattern in ASP.NET Core](/aspnet/core/fundamentals/configuration/options), respectively.</span></span>

## <a name="migrate-data-access"></a><span data-ttu-id="ae8b9-261">Migrar el acceso a los datos</span><span class="sxs-lookup"><span data-stu-id="ae8b9-261">Migrate data access</span></span>

<span data-ttu-id="ae8b9-262">El acceso a datos es un aspecto importante de cualquier aplicación.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-262">Data access is an important aspect of any app.</span></span> <span data-ttu-id="ae8b9-263">El proyecto eShop almacena información de catálogo en una base de datos y recupera los datos con Entity Framework (EF) 6.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-263">The eShop project stores catalog information in a database and retrieves the data with Entity Framework (EF) 6.</span></span> <span data-ttu-id="ae8b9-264">Dado que EF 6 se admite en .NET Core 3.0, el proyecto puede seguir utilizándolo.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-264">Since EF 6 is supported in .NET Core 3.0, the project can continue to use it.</span></span>

<span data-ttu-id="ae8b9-265">Los siguientes cambios relacionados con EF eran necesarios para eShop:</span><span class="sxs-lookup"><span data-stu-id="ae8b9-265">The following EF-related changes were necessary to eShop:</span></span>

- <span data-ttu-id="ae8b9-266">En .NET Framework, el `DbContext` objeto acepta una cadena con el nombre del formulario *ConnectionString* y usa la cadena de conexión desde `ConfigurationManager.AppSettings[ConnectionString]` desde la que conectarse.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-266">In .NET Framework, the `DbContext` object accepts a string of the form *name=ConnectionString* and uses the connection string from `ConfigurationManager.AppSettings[ConnectionString]` to connect.</span></span> <span data-ttu-id="ae8b9-267">En .NET Core, esto no se admite.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-267">In .NET Core, this isn't supported.</span></span> <span data-ttu-id="ae8b9-268">Se debe proporcionar la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-268">The connection string must be supplied.</span></span>
- <span data-ttu-id="ae8b9-269">Se tuvo acceso a la base de datos de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-269">The database was accessed in a synchronous way.</span></span> <span data-ttu-id="ae8b9-270">Aunque esto funciona, la escalabilidad puede sufrir.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-270">Though this works, scalability may suffer.</span></span> <span data-ttu-id="ae8b9-271">Esta lógica se debe mover a un patrón asincrónico.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-271">This logic should be moved to an asynchronous pattern.</span></span>

<span data-ttu-id="ae8b9-272">Aunque no hay la misma compatibilidad nativa para el enlace de conjunto de datos, Blazor proporciona flexibilidad y potencia con su compatibilidad con C- en una página de Razor.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-272">Although there isn't the same native support for dataset binding, Blazor provides flexibility and power with its C# support in a Razor page.</span></span> <span data-ttu-id="ae8b9-273">Por ejemplo, puede realizar cálculos y visualizar el resultado.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-273">For example, you can perform calculations and display the result.</span></span> <span data-ttu-id="ae8b9-274">Para obtener más información sobre los patrones de datos en Blazor, consulte el capítulo [Acceso a datos.](data.md)</span><span class="sxs-lookup"><span data-stu-id="ae8b9-274">For more information on data patterns in Blazor, see the [Data access](data.md) chapter.</span></span>

## <a name="architectural-changes"></a><span data-ttu-id="ae8b9-275">Cambios arquitectónicos</span><span class="sxs-lookup"><span data-stu-id="ae8b9-275">Architectural changes</span></span>

<span data-ttu-id="ae8b9-276">Por último, hay algunas diferencias arquitectónicas importantes a tener en cuenta al migrar a Blazor.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-276">Finally, there are some important architectural differences to consider when migrating to Blazor.</span></span> <span data-ttu-id="ae8b9-277">Muchos de estos cambios se aplican a cualquier cosa basada en .NET Core o ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-277">Many of these changes are applicable to anything based on .NET Core or ASP.NET Core.</span></span>

<span data-ttu-id="ae8b9-278">Dado que Blazor se basa en .NET Core, hay consideraciones para garantizar la compatibilidad con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-278">Because Blazor is built on .NET Core, there are considerations in ensuring support on .NET Core.</span></span> <span data-ttu-id="ae8b9-279">Algunos de los principales cambios incluyen la eliminación de las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="ae8b9-279">Some of the major changes include the removal of the following features:</span></span>

- <span data-ttu-id="ae8b9-280">Múltiples AppDomains</span><span class="sxs-lookup"><span data-stu-id="ae8b9-280">Multiple AppDomains</span></span>
- <span data-ttu-id="ae8b9-281">Comunicación remota</span><span class="sxs-lookup"><span data-stu-id="ae8b9-281">Remoting</span></span>
- <span data-ttu-id="ae8b9-282">Seguridad de acceso del código (CAS)</span><span class="sxs-lookup"><span data-stu-id="ae8b9-282">Code Access Security (CAS)</span></span>
- <span data-ttu-id="ae8b9-283">Transparencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="ae8b9-283">Security Transparency</span></span>

<span data-ttu-id="ae8b9-284">Para obtener más información sobre las técnicas para identificar los cambios necesarios para admitir la ejecución en .NET Core, vea [Puerto del código de .NET Framework a .NET Core](/dotnet/core/porting).</span><span class="sxs-lookup"><span data-stu-id="ae8b9-284">For more information on techniques to identify necessary changes to support running on .NET Core, see [Port your code from .NET Framework to .NET Core](/dotnet/core/porting).</span></span>

<span data-ttu-id="ae8b9-285">ASP.NET Core es una versión reinventada de ASP.NET y tiene algunos cambios que pueden no parecer obvios inicialmente.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-285">ASP.NET Core is a reimagined version of ASP.NET and has some changes that may not initially seem obvious.</span></span> <span data-ttu-id="ae8b9-286">Los principales cambios son:</span><span class="sxs-lookup"><span data-stu-id="ae8b9-286">The main changes are:</span></span>

- <span data-ttu-id="ae8b9-287">No hay contexto de sincronización, `Thread.CurrentPrincipal`lo que significa que no hay , `HttpContext.Current`, u otros descriptores de acceso estáticos</span><span class="sxs-lookup"><span data-stu-id="ae8b9-287">No synchronization context, which means there's no `HttpContext.Current`, `Thread.CurrentPrincipal`, or other static accessors</span></span>
- <span data-ttu-id="ae8b9-288">Sin instantáneas</span><span class="sxs-lookup"><span data-stu-id="ae8b9-288">No shadow copying</span></span>
- <span data-ttu-id="ae8b9-289">Sin cola de solicitudes</span><span class="sxs-lookup"><span data-stu-id="ae8b9-289">No request queue</span></span>

<span data-ttu-id="ae8b9-290">Muchas operaciones en ASP.NET Core son asincrónicas, lo que permite una descarga más fácil de las tareas enlazadas a E/S.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-290">Many operations in ASP.NET Core are asynchronous, which allows easier off-loading of I/O-bound tasks.</span></span> <span data-ttu-id="ae8b9-291">Es importante nunca bloquear `Task.Wait()` mediante `Task.GetResult()`o , que puede agotar rápidamente los recursos del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-291">It's important to never block by using `Task.Wait()` or `Task.GetResult()`, which can quickly exhaust thread pool resources.</span></span>

## <a name="migration-conclusion"></a><span data-ttu-id="ae8b9-292">Conclusión migratoria</span><span class="sxs-lookup"><span data-stu-id="ae8b9-292">Migration conclusion</span></span>

<span data-ttu-id="ae8b9-293">En este punto, ha visto muchos ejemplos de lo que se necesita para mover un proyecto de formularios Web Forms a Blazor.</span><span class="sxs-lookup"><span data-stu-id="ae8b9-293">At this point, you've seen many examples of what it takes to move a Web Forms project to Blazor.</span></span> <span data-ttu-id="ae8b9-294">Para obtener un ejemplo completo, consulte el proyecto [eShopOnBlazor.](https://github.com/dotnet-architecture/eShopOnBlazor)</span><span class="sxs-lookup"><span data-stu-id="ae8b9-294">For a full example, see the [eShopOnBlazor](https://github.com/dotnet-architecture/eShopOnBlazor) project.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="ae8b9-295">Anterior</span><span class="sxs-lookup"><span data-stu-id="ae8b9-295">Previous</span></span>](security-authentication-authorization.md)
