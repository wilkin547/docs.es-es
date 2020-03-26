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
# <a name="migrate-from-aspnet-web-forms-to-blazor"></a>Migrar de ASP.NET formularios Web Forms a Blazor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Migrar una base de código de ASP.NET formularios Web Forms a Blazor es una tarea que requiere mucho tiempo y requiere planificación. Este capítulo describe el proceso. Algo que puede facilitar la transición es asegurarse de que la aplicación se adhiere a una arquitectura *de N* niveles, en la que el modelo de aplicación (en este caso, formularios Web Forms) es independiente de la lógica empresarial. Esta separación lógica de capas deja claro lo que debe moverse a .NET Core y Blazor.

En este ejemplo, se utiliza la aplicación eShop disponible en [GitHub.](https://github.com/dotnet-architecture/eShopOnBlazor) eShop es un servicio de catálogo que proporciona capacidades CRUD a través de la entrada y validación de formularios.

¿Por qué debería migrarse una aplicación de trabajo a Blazor? Muchas veces, no hay necesidad. ASP.NET los formularios Web Forms seguirán siendo compatibles durante muchos años. Sin embargo, muchas de las características que proporciona Blazor solo se admiten en una aplicación migrada. Tales características incluyen:

- Mejoras de rendimiento en el marco, como`Span<T>`
- Capacidad para ejecutarse como WebAssembly
- Soporte multiplataforma para Linux y macOS
- Implementación local de aplicaciones o implementación de marco compartido sin afectar a otras aplicaciones

Si estas u otras características nuevas son lo suficientemente convincentes, puede haber valor en la migración de la aplicación. La migración puede tomar diferentes formas; puede ser toda la aplicación o solo ciertos puntos de conexión que requieran los cambios. La decisión de migrar se basa en última instancia en los problemas empresariales que debe resolver el desarrollador.

## <a name="server-side-versus-client-side-hosting"></a>Hospedaje del lado del servidor frente al cliente

Como se describe en el capítulo de modelos de [hospedaje,](hosting-models.md) una aplicación Blazor se puede hospedar de dos maneras diferentes: servidor y lado cliente. El modelo del lado servidor utiliza ASP.NET conexiones Core SignalR para administrar las actualizaciones de DOM mientras se ejecuta cualquier código real en el servidor. El modelo del lado cliente se ejecuta como WebAssembly dentro de un explorador y no requiere conexiones de servidor. Hay una serie de diferencias que pueden afectar a cuál es mejor para una aplicación específica:

- Se ejecuta como WebAssembly todavía está en desarrollo y puede que no admita todas las características (como el subprocesamiento) en el momento actual
- La comunicación entre el cliente y el servidor puede causar problemas de latencia en el modo del lado del servidor
- El acceso a bases de datos y servicios internos o protegidos requiere un servicio independiente con alojamiento del lado cliente

En el momento de escribir, el modelo del lado servidor se parece más a los formularios Web Forms. La mayor parte de este capítulo se centra en el modelo de hospedaje del lado servidor, ya que está listo para producción.

## <a name="create-a-new-project"></a>Creación de un nuevo proyecto

Este paso de migración inicial consiste en crear un nuevo proyecto. Este tipo de proyecto se basa en los proyectos de estilo SDK de .NET Core y simplifica gran parte de la placa reutilizable que se usó en formatos de proyecto anteriores. Para obtener más detalles, consulte el capítulo Estructura [del proyecto](project-structure.md).

Una vez creado el proyecto, instale las bibliotecas que se usaron en el proyecto anterior. En proyectos de formularios Web Forms anteriores, es posible que haya utilizado el archivo *packages.config* para enumerar los paquetes NuGet necesarios. En el nuevo proyecto de estilo SDK, *packages.config* se ha reemplazado por `<PackageReference>` elementos en el archivo de proyecto. Una ventaja de este enfoque es que todas las dependencias se instalan transitivamente. Solo enumera las dependencias de nivel superior que le importan.

Muchas de las dependencias que usa están disponibles para .NET Core, incluidos Entity Framework 6 y log4net. Si no hay ninguna versión de .NET Core o .NET Standard disponible, a menudo se puede usar la versión de .NET Framework. Puede que tu experiencia sea diferente. Cualquier API utilizada que no esté disponible en .NET Core produce un error en tiempo de ejecución. Visual Studio le notifica de dichos paquetes. Aparece un icono amarillo en el nodo **Referencias** del proyecto en el Explorador de **soluciones.**

En el proyecto eShop basado en Blazor, puede ver los paquetes que están instalados. Anteriormente, el archivo *packages.config* enumeraba todos los paquetes utilizados en el proyecto, lo que provocaba un tamaño de casi 50 líneas. Un fragmento de *packages.config* es:

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

El `<packages>` elemento incluye todas las dependencias necesarias. Es difícil identificar cuáles de estos paquetes están incluidos porque los necesita. Algunos `<package>` elementos se enumeran simplemente para satisfacer las necesidades de dependencias que necesita.

El proyecto Blazor enumera las dependencias que necesita dentro de un `<ItemGroup>` elemento en el archivo de proyecto:

```xml
<ItemGroup>
    <PackageReference Include="Autofac" Version="4.9.3" />
    <PackageReference Include="EntityFramework" Version="6.3.0-preview9-19423-04" />
    <PackageReference Include="log4net" Version="2.0.8" />
</ItemGroup>
```

Un paquete NuGet que simplifica la vida de los desarrolladores de formularios Web Forms es el paquete de [compatibilidad de Windows.](../../core/porting/windows-compat-pack.md) Aunque .NET Core es multiplataforma, algunas características solo están disponibles en Windows. Las características específicas de Windows están disponibles mediante la instalación del paquete de compatibilidad. Entre los ejemplos de estas características se incluyen el Registro, WMI y Directory Services. El paquete añade alrededor de 20.000 API y activa muchos servicios con los que ya está familiarizado. El proyecto eShop no requiere el paquete de compatibilidad; pero si los proyectos usan características específicas de Windows, el paquete facilita los esfuerzos de migración.

## <a name="enable-startup-process"></a>Habilitar el proceso de inicio

El proceso de inicio de Blazor ha cambiado de formularios Web Forms y sigue una configuración similar para otros servicios ASP.NET Core. Cuando se hospedan en el lado del servidor, los componentes de Blazor se ejecutan como parte de una aplicación normal ASP.NET Core. Cuando se hospedan en el explorador con WebAssembly, los componentes de Blazor utilizan un modelo de hospedaje similar. La diferencia es que los componentes se ejecutan como un servicio independiente de cualquiera de los procesos de back-end. De cualquier manera, el inicio es similar.

El archivo *Global.asax.cs* es la página de inicio predeterminada para los proyectos de formularios Web Forms. En el proyecto eShop, este archivo configura el contenedor Inversión de control (IoC) y controla los distintos eventos del ciclo de vida de la aplicación o solicitud. Algunos de estos eventos se controlan `Application_BeginRequest`con middleware (como ). Otros eventos requieren la invalidación de servicios específicos a través de la inserción de dependencias (DI).

A modo de ejemplo, el archivo *Global.asax.cs* para eShop contiene el siguiente código:

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

El archivo anterior se `Startup` convierte en la clase en Blazor del lado del servidor:

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

Un cambio significativo que puede notar de los formularios Web Forms es el protagonismo de di. DI ha sido un principio rector en el diseño ASP.NET Core. Admite la personalización de casi todos los aspectos del marco de trabajo de ASP.NET Core. Incluso hay un proveedor de servicios integrado que se puede usar para muchos escenarios. Si se requiere más personalización, puede ser compatible con muchos proyectos de la comunidad. Por ejemplo, puede llevar adelante su inversión en biblioteca DI de terceros.

En la aplicación eShop original, hay alguna configuración para la administración de sesiones. Puesto que Blazor del lado del servidor utiliza ASP.NET Core SignalR para la comunicación, el estado de sesión no se admite ya que las conexiones pueden producirse independientemente de un contexto HTTP. Una aplicación que usa el estado de sesión requiere la rearquitectura antes de ejecutarse como una aplicación Blazor.

Para obtener más información sobre el inicio de la aplicación, consulte [Inicio de](app-startup.md)la aplicación .

## <a name="migrate-http-modules-and-handlers-to-middleware"></a>Migrar módulos y controladores HTTP a middleware

Los módulos y controladores HTTP son patrones comunes en formularios Web Forms para controlar la canalización de solicitudes HTTP. Clases `IHttpModule` que `IHttpHandler` implementan o podrían registrarse y procesar solicitudes entrantes. Formularios Web Forms configura módulos y controladores en el archivo *web.config.* Los formularios Web Forms también se basan en gran medida en el control de eventos del ciclo de vida de la aplicación. ASP.NET Core usa middleware en su lugar. Middleware está registrado `Configure` en `Startup` el método de la clase. El orden de ejecución del middleware viene determinado por la orden de registro.

En la sección Habilitar proceso de [inicio,](#enable-startup-process) los formularios `Application_BeginRequest` Web Forms generaron un evento de ciclo de vida como método. Este evento no está disponible en ASP.NET Core. Una manera de lograr este comportamiento es implementar middleware como se ve en el ejemplo de archivo *Startup.cs.* Este middleware realiza la misma lógica y, a continuación, transfiere el control al siguiente controlador de la canalización de middleware.

Para obtener más información sobre la migración de módulos y controladores, vea [Migrar controladores y módulos HTTP a ASP.NET middleware Core](/aspnet/core/migration/http-modules).

## <a name="migrate-static-files"></a>Migrar archivos estáticos

Para servir archivos estáticos (por ejemplo, HTML, CSS, imágenes y JavaScript), los archivos deben exponerse mediante middleware. Llamar `UseStaticFiles` al método habilita la publicación de archivos estáticos desde la ruta de acceso raíz web. El directorio raíz web predeterminado es *wwwroot,* pero se puede personalizar. Como se `Configure` incluye en el `Startup` método de la clase de eShop:

```csharp
public void Configure(IApplicationBuilder app)
{
    ...

    app.UseStaticFiles();

    ...
}
```

El proyecto eShop permite el acceso básico a archivos estáticos. Hay muchas personalizaciones disponibles para el acceso a archivos estáticos. Para obtener información sobre cómo habilitar archivos predeterminados o un explorador de archivos, consulte [Archivos estáticos en ASP.NET Core](/aspnet/core/fundamentals/static-files).

## <a name="migrate-runtime-bundling-and-minification-setup"></a>Migrar la agrupación en tiempo de ejecución y la configuración de minificación

La agrupación y la minificación son técnicas de optimización del rendimiento para reducir el número y el tamaño de las solicitudes de servidor para recuperar determinados tipos de archivo. JavaScript y CSS a menudo se someten a algún tipo de agrupación o minificación antes de ser enviados al cliente. En ASP.NET formularios Web Forms, estas optimizaciones se controlan en tiempo de ejecución. Las convenciones de optimización se definen un archivo *App_Start/BundleConfig.cs.* En ASP.NET Núcleo, se adopta un enfoque más declarativo. Un archivo enumera los archivos que se van a minificar, junto con la configuración de minificación específica.

Para obtener más información sobre la agrupación y la minificación, consulte [Agrupar y minificar activos estáticos en ASP.NET Core](/aspnet/core/client-side/bundling-and-minification).

## <a name="migrate-aspx-pages"></a>Migrar páginas ASPX

Una página de una aplicación de formularios Web Forms es un archivo con la extensión *.aspx.* Una página de formularios Web Forms a menudo se puede asignar a un componente en Blazor. Un componente Blazor se crea en un archivo con la extensión *.razor.* Para el proyecto eShop, cinco páginas se convierten en una página Razor.

Por ejemplo, la vista de detalles se compone de tres archivos en el proyecto de formularios Web Forms: *Details.aspx*, *Details.aspx.cs*y *Details.aspx.designer.cs*. Al convertir a Blazor, el código subyacente y el marcado se combinan en *Details.razor*. La compilación de Razor (equivalente a lo que está en archivos *.designer.cs)* se almacena en el directorio *obj* y no se pueden ver, de forma predeterminada, en el **Explorador**de soluciones . La página de formularios Web Forms consta del siguiente marcado:

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

El código subyacente del marcado anterior incluye el código siguiente:

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

Cuando se convierte a Blazor, la página de formularios Web Forms se traduce en el código siguiente:

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

Observe que el código y el marcado están en el mismo archivo. Los servicios necesarios se `@inject` hacen accesibles con el atributo. Según `@page` la directiva, se puede `Catalog/Details/{id}` acceder a esta página en la ruta. El valor del marcador `{id}` de posición de la ruta se ha restringido a un entero. Como se describe en la sección [de enrutamiento,](pages-routing-layouts.md) a diferencia de los formularios Web Forms, un componente Razor indica explícitamente su ruta y los parámetros que se incluyen. Es posible que muchos controles de formularios Web Forms no tengan homólogos exactos en Blazor. A menudo hay un fragmento de código HTML equivalente que servirá para el mismo propósito. Por ejemplo, `<asp:Label />` el control se puede `<label>` reemplazar con un elemento HTML.

### <a name="model-validation-in-blazor"></a>Validación del modelo en Blazor

Si el código de formularios Web Forms incluye validación, puede transferir gran parte de lo que tiene con cambios poco o ningún. Una ventaja de ejecutar se ejecuta en Blazor es que se puede ejecutar la misma lógica de validación sin necesidad de JavaScript personalizado. Las anotaciones de datos facilitan la validación del modelo.

Por ejemplo, el *Create.aspx* página tiene un formulario de entrada de datos con validación. Un fragmento de código de ejemplo tendría este aspecto:

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

En Blazor, el marcado equivalente se proporciona en un archivo *Create.razor:*

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

El `EditForm` contexto incluye compatibilidad con validación y se puede ajustar alrededor de la entrada. Las anotaciones de datos son una forma común de agregar validación. Este soporte de validación `DataAnnotationsValidator` se puede agregar a través del componente. Para obtener más información sobre este mecanismo, consulte [ASP.NET formularios y validación de Blazor básico](/aspnet/core/blazor/forms-validation).

## <a name="migrate-built-in-web-forms-controls"></a>Migrar controles de formularios Web Forms integrados

*Este contenido está por llegar.*

## <a name="migrate-configuration"></a>Migración de la configuración

En un proyecto de formularios Web Forms, los datos de configuración se almacenan con mayor frecuencia en el archivo *web.config.* Se accede a `ConfigurationManager`los datos de configuración con . A menudo se requerían servicios para analizar objetos. Con .NET Framework 4.7.2, la capacidad `ConfigurationBuilders`de composición se agregó a la configuración a través de . Estos generadores permitieron a los desarrolladores agregar varios orígenes de configuración que, a continuación, se componían en tiempo de ejecución para recuperar los valores necesarios.

ASP.NET Core introdujo un sistema de configuración flexible que le permite definir el origen de configuración o los orígenes utilizados por la aplicación y la implementación. La `ConfigurationBuilder` infraestructura que puede usar en la aplicación de formularios Web Forms se modeló sin los conceptos utilizados en el sistema de configuración ASP.NET Core.

En el siguiente fragmento de código se muestra cómo el proyecto de eShop de formularios Web Forms utiliza *web.config* para almacenar valores de configuración:

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

Es común que los secretos, como las cadenas de conexión de base de datos, se almacenen en *web.config*. Los secretos se conservan inevitablemente en ubicaciones no seguras, como el control de código fuente. Con Blazor en ASP.NET Core, la configuración basada en XML anterior se reemplaza por el siguiente JSON:

```json
{
  "ConnectionStrings": {
    "CatalogDBContext": "Data Source=(localdb)\\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;"
  },
  "UseMockData": true,
  "UseCustomizationData": false
}
```

JSON es el formato de configuración predeterminado; sin embargo, ASP.NET Core admite muchos otros formatos, incluido XML. También hay varios formatos compatibles con la comunidad.

El constructor de la clase `Startup` del proyecto `IConfiguration` Blazor acepta una instancia a través de una técnica DI conocida como inyección de constructor:

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

De forma predeterminada, variables de entorno, archivos JSON (*appsettings.json* y *appsettings. Las*opciones de la línea de comandos Environment.json y el valor de la línea de comandos se registran como orígenes de configuración válidos en el objeto de configuración. Se puede acceder a `Configuration[key]`las fuentes de configuración a través de . Una técnica más avanzada consiste en enlazar los datos de configuración a objetos mediante el patrón de opciones. Para obtener más información sobre la configuración y el patrón de opciones, consulte [Configuración en ASP.NET core](/aspnet/core/fundamentals/configuration/) y El [patrón Opciones en ASP.NET Core](/aspnet/core/fundamentals/configuration/options), respectivamente.

## <a name="migrate-data-access"></a>Migrar el acceso a los datos

El acceso a datos es un aspecto importante de cualquier aplicación. El proyecto eShop almacena información de catálogo en una base de datos y recupera los datos con Entity Framework (EF) 6. Dado que EF 6 se admite en .NET Core 3.0, el proyecto puede seguir utilizándolo.

Los siguientes cambios relacionados con EF eran necesarios para eShop:

- En .NET Framework, el `DbContext` objeto acepta una cadena con el nombre del formulario *ConnectionString* y usa la cadena de conexión desde `ConfigurationManager.AppSettings[ConnectionString]` desde la que conectarse. En .NET Core, esto no se admite. Se debe proporcionar la cadena de conexión.
- Se tuvo acceso a la base de datos de forma sincrónica. Aunque esto funciona, la escalabilidad puede sufrir. Esta lógica se debe mover a un patrón asincrónico.

Aunque no hay la misma compatibilidad nativa para el enlace de conjunto de datos, Blazor proporciona flexibilidad y potencia con su compatibilidad con C- en una página de Razor. Por ejemplo, puede realizar cálculos y visualizar el resultado. Para obtener más información sobre los patrones de datos en Blazor, consulte el capítulo [Acceso a datos.](data.md)

## <a name="architectural-changes"></a>Cambios arquitectónicos

Por último, hay algunas diferencias arquitectónicas importantes a tener en cuenta al migrar a Blazor. Muchos de estos cambios se aplican a cualquier cosa basada en .NET Core o ASP.NET Core.

Dado que Blazor se basa en .NET Core, hay consideraciones para garantizar la compatibilidad con .NET Core. Algunos de los principales cambios incluyen la eliminación de las siguientes características:

- Múltiples AppDomains
- Comunicación remota
- Seguridad de acceso del código (CAS)
- Transparencia de seguridad

Para obtener más información sobre las técnicas para identificar los cambios necesarios para admitir la ejecución en .NET Core, vea [Puerto del código de .NET Framework a .NET Core](/dotnet/core/porting).

ASP.NET Core es una versión reinventada de ASP.NET y tiene algunos cambios que pueden no parecer obvios inicialmente. Los principales cambios son:

- No hay contexto de sincronización, `Thread.CurrentPrincipal`lo que significa que no hay , `HttpContext.Current`, u otros descriptores de acceso estáticos
- Sin instantáneas
- Sin cola de solicitudes

Muchas operaciones en ASP.NET Core son asincrónicas, lo que permite una descarga más fácil de las tareas enlazadas a E/S. Es importante nunca bloquear `Task.Wait()` mediante `Task.GetResult()`o , que puede agotar rápidamente los recursos del grupo de subprocesos.

## <a name="migration-conclusion"></a>Conclusión migratoria

En este punto, ha visto muchos ejemplos de lo que se necesita para mover un proyecto de formularios Web Forms a Blazor. Para obtener un ejemplo completo, consulte el proyecto [eShopOnBlazor.](https://github.com/dotnet-architecture/eShopOnBlazor)

>[!div class="step-by-step"]
>[Anterior](security-authentication-authorization.md)
