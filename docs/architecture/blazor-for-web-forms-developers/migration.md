---
title: Migre desde formularios Web Forms de ASP.NET a Blazor
description: Aprenda a enfocar la migración de una aplicación de formularios Web Forms de ASP.NET existente a Blazor .
author: twsouthwick
ms.author: tasou
no-loc:
- Blazor
- WebAssembly
ms.date: 09/19/2019
ms.openlocfilehash: ca3d8747b02602c89aec187ea0826e658fb0cbc4
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267807"
---
# <a name="migrate-from-aspnet-web-forms-to-no-locblazor"></a>Migre desde formularios Web Forms de ASP.NET a Blazor

La migración de una base de código de formularios Web Forms de ASP.NET a Blazor es una tarea que requiere mucho tiempo y requiere planeación. En este capítulo se describe el proceso. Algo que puede facilitar la transición es asegurarse de que la aplicación se adhiera a una arquitectura de *N niveles* , donde el modelo de la aplicación (en este caso, los formularios Web Forms) es independiente de la lógica de negocios. Esta separación lógica de las capas permite desactivar lo que necesita pasar a .NET Core y Blazor .

En este ejemplo, se usa la aplicación de eShop disponible en [GitHub](https://github.com/dotnet-architecture/eShopOnBlazor) . eShop es un servicio de catálogo que proporciona capacidades CRUD mediante la entrada de formulario y la validación.

¿Por qué se debe migrar a una aplicación en funcionamiento Blazor ? Muchas veces, no es necesario. Los formularios Web Forms de ASP.NET seguirán siendo compatibles durante muchos años. Sin embargo, muchas de las características que Blazor proporciona solo se admiten en una aplicación migrada. Estas características incluyen:

- Mejoras de rendimiento en el marco de trabajo como `Span<T>`
- Capacidad para ejecutarse como WebAssembly
- Compatibilidad entre plataformas para Linux y macOS
- Implementación local de la aplicación o implementación de un marco compartido sin afectar a otras aplicaciones

Si estas u otras características nuevas son lo suficientemente atractivas, puede haber un valor en la migración de la aplicación. La migración puede tomar distintas formas; puede ser toda la aplicación o solo determinados puntos de conexión que requieran los cambios. La decisión de migrar se basa en última instancia en los problemas empresariales que el desarrollador debe resolver.

## <a name="server-side-versus-client-side-hosting"></a>En el lado servidor frente al hospedaje del lado cliente

Como se describe en el capítulo [modelos de hospedaje](hosting-models.md) , una Blazor aplicación se puede hospedar de dos maneras diferentes: lado servidor y lado cliente. El modelo de servidor usa ASP.NET Core las conexiones de Signalr para administrar las actualizaciones del DOM mientras se ejecuta cualquier código real en el servidor. El modelo de cliente se ejecuta como WebAssembly dentro de un explorador y no requiere ninguna conexión de servidor. Hay una serie de diferencias que pueden afectar a lo mejor para una aplicación específica:

- Ejecutar como WebAssembly sigue en desarrollo y es posible que no admita todas las características (como los subprocesos) en el momento actual.
- La comunicación entre el cliente y el servidor puede producir problemas de latencia en el modo de servidor
- El acceso a las bases de datos y a los servicios internos o protegidos requiere un servicio independiente con hospedaje en el lado cliente.

En el momento de escribir este documento, el modelo del lado servidor se parece más al de los formularios Web Forms. La mayor parte de este capítulo se centra en el modelo de hospedaje del lado servidor, ya que está listo para la producción.

## <a name="create-a-new-project"></a>Creación de un nuevo proyecto

Este paso de migración inicial consiste en crear un nuevo proyecto. Este tipo de proyecto se basa en los proyectos de estilo SDK de .NET Core y simplifica gran parte del texto reutilizable que se usó en los formatos de proyecto anteriores. Para obtener más información, consulte el capítulo sobre la [estructura del proyecto](project-structure.md).

Una vez creado el proyecto, instale las bibliotecas que se usaron en el proyecto anterior. En los proyectos de formularios Web Forms anteriores, es posible que haya usado el archivo *packages.config* para mostrar los paquetes de NuGet necesarios. En el nuevo proyecto de estilo SDK, *packages.config* se ha reemplazado por `<PackageReference>` elementos en el archivo de proyecto. Una ventaja de este enfoque es que todas las dependencias se instalan de forma transitiva. Solo se muestran las dependencias de nivel superior que le interesan.

Muchas de las dependencias que está usando están disponibles para .NET Core, como Entity Framework 6 y log4net. Si no hay ninguna versión de .NET Core o .NET Standard disponible, a menudo se puede usar la versión de .NET Framework. Puede que tu experiencia sea diferente. Cualquier API usada que no esté disponible en .NET Core producirá un error en tiempo de ejecución. Visual Studio le informa de estos paquetes. Aparece un icono amarillo en el nodo **referencias** del proyecto en **Explorador de soluciones**.

En el Blazor proyecto de eShop basado en, puede ver los paquetes que están instalados. Anteriormente, el archivo de *packages.config* mostraba todos los paquetes usados en el proyecto, lo que generaba un archivo de casi 50 líneas de longitud. Un fragmento de *packages.config* es:

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

El `<packages>` elemento incluye todas las dependencias necesarias. Es difícil identificar cuál de estos paquetes se incluyen porque los necesita. Algunos `<package>` elementos se enumeran simplemente para satisfacer las necesidades de las dependencias que necesita.

El Blazor proyecto muestra las dependencias que necesita dentro de un `<ItemGroup>` elemento en el archivo de proyecto:

```xml
<ItemGroup>
    <PackageReference Include="Autofac" Version="4.9.3" />
    <PackageReference Include="EntityFramework" Version="6.3.0-preview9-19423-04" />
    <PackageReference Include="log4net" Version="2.0.8" />
</ItemGroup>
```

Un paquete NuGet que simplifica la vida de los desarrolladores de formularios Web Forms es el [paquete de compatibilidad de Windows](../../core/porting/windows-compat-pack.md). Aunque .NET Core es multiplataforma, algunas características solo están disponibles en Windows. Las características específicas de Windows se ponen a disposición mediante la instalación del paquete de compatibilidad. Entre los ejemplos de estas características se incluyen el registro, WMI y servicios de directorio. El paquete agrega alrededor de 20.000 API y activa muchos servicios con los que es posible que ya esté familiarizado. El proyecto de eShop no requiere el paquete de compatibilidad; pero si los proyectos usan características específicas de Windows, el paquete facilita el trabajo de migración.

## <a name="enable-startup-process"></a>Habilitar proceso de inicio

El proceso de inicio de Blazor ha cambiado de los formularios Web Forms y sigue una configuración similar para otros servicios de ASP.net Core. Cuando el lado servidor hospedado, Blazor los componentes se ejecutan como parte de una aplicación de ASP.net Core normal. Cuando se hospeda en el explorador con WebAssembly , Blazor los componentes utilizan un modelo de hospedaje similar. La diferencia es que los componentes se ejecutan como un servicio independiente de cualquiera de los procesos de back-end. En cualquier caso, el inicio es similar.

El archivo *global.asax.CS* es la página de inicio predeterminada para los proyectos de formularios Web Forms. En el proyecto de eShop, este archivo configura el contenedor de inversión de control (IoC) y controla los distintos eventos de ciclo de vida de la aplicación o solicitud. Algunos de estos eventos se controlan con middleware (como `Application_BeginRequest` ). Otros eventos requieren la invalidación de servicios específicos a través de la inserción de dependencias (DI).

Por ejemplo, el archivo *global.asax.CS* de eShop contiene el código siguiente:

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
    /// https://autofaccn.readthedocs.io/en/latest/integration/webforms.html
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

El archivo anterior se convierte `Startup` en la clase en el lado servidor Blazor :

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

Un cambio importante que puede observar de los formularios Web Forms es el importancia de DI. DI ha sido un principio de GUID en el diseño de ASP.NET Core. Admite la personalización de casi todos los aspectos del marco de ASP.NET Core. Hay incluso un proveedor de servicios integrado que se puede usar para muchos escenarios. Si se requiere más personalización, puede ser compatible con los numerosos proyectos de la comunidad. Por ejemplo, puede llevar a cabo la inversión de la biblioteca de DI de terceros.

En la aplicación de eShop original, hay alguna configuración para la administración de sesiones. Puesto que el servidor Blazor usa ASP.net Core signalr para la comunicación, no se admite el estado de sesión, ya que las conexiones pueden producirse independientemente de un contexto http. Una aplicación que usa el estado de sesión requiere que se rediseñe antes de ejecutarse como una Blazor aplicación.

Para obtener más información sobre el inicio de la aplicación, consulte inicio de la [aplicación](app-startup.md).

## <a name="migrate-http-modules-and-handlers-to-middleware"></a>Migración de módulos y controladores HTTP a middleware

Los módulos y controladores HTTP son patrones comunes en formularios Web Forms para controlar la canalización de solicitudes HTTP. Clases que implementan `IHttpModule` o que `IHttpHandler` se pueden registrar y procesar solicitudes entrantes. Formularios Web Forms configura módulos y controladores en el archivo de *web.config* . Los formularios Web Forms también se basan principalmente en el control de eventos del ciclo de vida de la aplicación. En su lugar, ASP.NET Core usa middleware. El middleware se registra en el `Configure` método de la `Startup` clase. El orden de ejecución del middleware viene determinado por el orden de registro.

En la sección [Habilitar proceso de inicio](#enable-startup-process) , Web Forms generó un evento de ciclo de vida como el `Application_BeginRequest` método. Este evento no está disponible en ASP.NET Core. Una manera de lograr este comportamiento es implementar el middleware tal como se aprecia en el ejemplo de archivo *Startup.CS* . Este middleware realiza la misma lógica y, a continuación, transfiere el control al siguiente controlador en la canalización de middleware.

Para obtener más información sobre cómo migrar módulos y controladores, consulte [migración de controladores y módulos http a middleware de ASP.net Core](/aspnet/core/migration/http-modules).

## <a name="migrate-static-files"></a>Migrar archivos estáticos

Para servir archivos estáticos (por ejemplo, HTML, CSS, imágenes y JavaScript), los archivos deben estar expuestos por middleware. La llamada al `UseStaticFiles` método habilita el servicio de archivos estáticos de la ruta de acceso raíz Web. El directorio raíz Web predeterminado es *wwwroot*, pero se puede personalizar. Tal y como se incluye en el `Configure` método de la clase de eShop `Startup` :

```csharp
public void Configure(IApplicationBuilder app)
{
    ...

    app.UseStaticFiles();

    ...
}
```

El proyecto de eShop permite el acceso a archivos estáticos básicos. Hay muchas personalizaciones disponibles para el acceso a archivos estáticos. Para obtener información sobre cómo habilitar archivos predeterminados o un explorador de archivos, consulte [archivos estáticos en ASP.net Core](/aspnet/core/fundamentals/static-files).

## <a name="migrate-runtime-bundling-and-minification-setup"></a>Migrar la configuración de agrupación y minificación de tiempo de ejecución

La agrupación y minificación son técnicas de optimización del rendimiento para reducir el número y el tamaño de las solicitudes de servidor para recuperar determinados tipos de archivo. JavaScript y CSS suelen someterse a una forma de agrupación o minificación antes de enviarse al cliente. En los formularios Web Forms de ASP.NET, estas optimizaciones se controlan en tiempo de ejecución. Las convenciones de optimización se definen como un archivo *App_Start/bundleconfig.CS* . En ASP.NET Core, se adopta un enfoque más declarativo. Un archivo enumera los archivos que se van a reducida, junto con la configuración específica de minificación.

Para obtener más información sobre la agrupación y la minificación, consulte [agrupación y minimizar de recursos estáticos en ASP.net Core](/aspnet/core/client-side/bundling-and-minification).

## <a name="migrate-aspx-pages"></a>Migrar páginas ASPX

Una página de una aplicación de formularios Web Forms es un archivo con la extensión *. aspx* . Una página de formularios Web Forms a menudo se puede asignar a un componente en Blazor . Un Blazor componente se crea en un archivo con la extensión *. Razor* . En el caso del proyecto de eShop, se convierten cinco páginas en una página de Razor.

Por ejemplo, la vista de detalles consta de tres archivos en el proyecto de formularios Web Forms: *details. aspx*, *details.aspx.CS*y *details.aspx.Designer.CS*. Al convertir a Blazor , el código subyacente y el marcado se combinan en *details. Razor*. La compilación de Razor (equivalente a lo que se encuentra en los archivos *. Designer.CS* ) se almacena en el directorio *obj* y no es visible de forma predeterminada en **Explorador de soluciones**. La página de formularios Web Forms consta del siguiente marcado:

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

Cuando se convierte en Blazor , la página de formularios Web Forms se convierte en el código siguiente:

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

Observe que el código y el marcado están en el mismo archivo. Los servicios necesarios se hacen accesibles con el `@inject` atributo. Según la `@page` Directiva, se puede tener acceso a esta página en la `Catalog/Details/{id}` ruta. El valor del marcador de posición de la ruta se ha `{id}` restringido a un entero. Como se describe en la sección [enrutamiento](pages-routing-layouts.md) , a diferencia de los formularios Web Forms, un componente Razor indica explícitamente su ruta y los parámetros que se incluyen. Es posible que muchos controles de formularios Web Forms no tengan homólogos exactos en Blazor . A menudo hay un fragmento de código HTML equivalente que tendrá el mismo propósito. Por ejemplo, el `<asp:Label />` control se puede reemplazar por un `<label>` elemento HTML.

### <a name="model-validation-in-no-locblazor"></a>Validación de modelos en Blazor

Si el código de formularios Web Forms incluye validación, puede transferir gran parte de lo que tiene con cambios poco a no. Una ventaja de ejecutar en Blazor es que se puede ejecutar la misma lógica de validación sin necesidad de JavaScript personalizado. Las anotaciones de datos permiten la validación sencilla del modelo.

Por ejemplo, la página *Create. aspx* tiene un formulario de entrada de datos con validación. Un fragmento de código de ejemplo tendría el siguiente aspecto:

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

En Blazor , el marcado equivalente se proporciona en un archivo *Create. Razor* :

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

El `EditForm` contexto incluye compatibilidad con la validación y se puede ajustar en torno a la entrada. Las anotaciones de datos son una manera común de agregar validación. Esta compatibilidad de validación se puede Agregar a través del `DataAnnotationsValidator` componente. Para obtener más información sobre este mecanismo, consulte [ASP.net Core Blazor Forms and Validation](/aspnet/core/blazor/forms-validation).

## <a name="migrate-built-in-web-forms-controls"></a>Migrar controles de formularios Web Forms integrados

*Este contenido estará disponible próximamente.*

## <a name="migrate-configuration"></a>Migración de la configuración

En un proyecto de formularios Web Forms, los datos de configuración se almacenan normalmente en el archivo *web.config* . Se tiene acceso a los datos de configuración con `ConfigurationManager` . A menudo, los servicios debían analizar objetos. Con .NET Framework 4.7.2, composición se agregó a la configuración a través de `ConfigurationBuilders` . Estos generadores permitían a los desarrolladores agregar varios orígenes de configuración que luego se componían en tiempo de ejecución para recuperar los valores necesarios.

ASP.NET Core presentó un sistema de configuración flexible que le permite definir el origen de configuración o los orígenes usados por la aplicación y la implementación. La `ConfigurationBuilder` infraestructura que puede usar en la aplicación de formularios Web Forms se modelaba después de los conceptos usados en el sistema de configuración de ASP.net Core.

El siguiente fragmento de código muestra cómo el proyecto de eShop de formularios Web Forms usa *web.config* para almacenar los valores de configuración:

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

Es habitual que los secretos, como las cadenas de conexión de base de datos, se almacenen en el *web.config*. Los secretos se conservan inevitablemente en ubicaciones no seguras, como el control de código fuente. Con Blazor en ASP.net Core, la configuración basada en XML anterior se reemplaza por el siguiente JSON:

```json
{
  "ConnectionStrings": {
    "CatalogDBContext": "Data Source=(localdb)\\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;"
  },
  "UseMockData": true,
  "UseCustomizationData": false
}
```

JSON es el formato de configuración predeterminado; sin embargo, ASP.NET Core admite muchos otros formatos, incluido XML. También hay varios formatos admitidos por la comunidad.

El constructor de la Blazor clase del proyecto `Startup` acepta una `IConfiguration` instancia a través de una técnica de di conocida como inserción del constructor:

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

De forma predeterminada, las variables de entorno, los archivos JSON (*appsettings.jsen* y *appSettings. { Environment}. JSON*) y las opciones de línea de comandos se registran como orígenes de configuración válidos en el objeto de configuración. Se puede tener acceso a los orígenes de configuración a través de `Configuration[key]` . Una técnica más avanzada consiste en enlazar los datos de configuración a los objetos mediante el patrón de opciones. Para obtener más información sobre la configuración y el patrón de opciones, vea [configuración en ASP.net Core](/aspnet/core/fundamentals/configuration/) y [patrón de opciones en ASP.net Core](/aspnet/core/fundamentals/configuration/options), respectivamente.

## <a name="migrate-data-access"></a>Migración del acceso a datos

El acceso a datos es un aspecto importante de cualquier aplicación. El proyecto de eShop almacena información de catálogo en una base de datos y recupera los datos con Entity Framework (EF) 6. Dado que EF 6 es compatible con .NET Core 3,0, el proyecto puede seguir utilizándolo.

Los siguientes cambios relacionados con EF eran necesarios para eShop:

- En .NET Framework, el `DbContext` objeto acepta una cadena con el formato *Name = ConnectionString* y utiliza la cadena de conexión de `ConfigurationManager.AppSettings[ConnectionString]` para conectarse. No se admite en .NET Core. Se debe proporcionar la cadena de conexión.
- Se ha tenido acceso a la base de datos de forma sincrónica. Aunque esto funciona, la escalabilidad puede verse afectada. Esta lógica debe moverse a un patrón asincrónico.

Aunque no hay la misma compatibilidad nativa para el enlace de conjuntos de DataSet, Blazor proporciona flexibilidad y capacidad con su compatibilidad con C# en una página de Razor. Por ejemplo, puede realizar cálculos y mostrar el resultado. Para obtener más información sobre los patrones de datos en Blazor , vea el capítulo de [acceso a datos](data.md) .

## <a name="architectural-changes"></a>Cambios de arquitectura

Por último, hay algunas diferencias arquitectónicas importantes a tener en cuenta a la hora de migrar a Blazor . Muchos de estos cambios se aplican a cualquier elemento basado en .NET Core o en ASP.NET Core.

Dado que Blazor se basa en .net Core, existen consideraciones para garantizar la compatibilidad en .net Core. Algunos de los cambios principales incluyen la eliminación de las siguientes características:

- Varios AppDomains
- Comunicación remota
- Seguridad de acceso del código (CAS)
- Transparencia de seguridad

Para obtener más información sobre las técnicas para identificar los cambios necesarios para admitir la ejecución en .NET Core, vea [portar el código de .NET Framework a .net Core](/dotnet/core/porting).

ASP.NET Core es una versión Reimaginada de ASP.NET y tiene algunos cambios que es posible que no parezcan inicialmente obvios. Los principales cambios son:

- Sin contexto de sincronización, lo que significa que no hay ningún `HttpContext.Current` , `Thread.CurrentPrincipal` u otros descriptores de acceso estáticos
- Sin copias sombra
- Sin cola de solicitudes

Muchas operaciones en ASP.NET Core son asincrónicas, lo que permite una descarga más sencilla de las tareas enlazadas a e/s. Es importante no bloquear nunca mediante `Task.Wait()` o `Task.GetResult()` , lo que puede agotar rápidamente los recursos del grupo de subprocesos.

## <a name="migration-conclusion"></a>Conclusión de la migración

En este punto, ha visto muchos ejemplos de lo que se necesita para trasladar un proyecto de formularios Web Forms a Blazor . Para obtener un ejemplo completo, vea el proyecto [eShopOn Blazor ](https://github.com/dotnet-architecture/eShopOnBlazor) .

>[!div class="step-by-step"]
>[Anterior](security-authentication-authorization.md)
