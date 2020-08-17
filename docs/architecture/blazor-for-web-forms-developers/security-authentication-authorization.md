---
title: 'Seguridad: autenticación y autorización en formularios Web Forms de ASP.NET y Blazor'
description: Obtenga información sobre cómo controlar la autenticación y la autorización en formularios Web Forms de ASP.NET y Blazor .
author: ardalis
ms.author: daroth
no-loc:
- Blazor
ms.date: 09/11/2019
ms.openlocfilehash: 1cc82b14a940465c26377f9181a2e20b46b0783f
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267869"
---
# <a name="security-authentication-and-authorization-in-aspnet-web-forms-and-no-locblazor"></a>Seguridad: autenticación y autorización en formularios Web Forms de ASP.NET y Blazor

La migración de una aplicación de formularios Web Forms ASP.NET a Blazor seguramente requiere la actualización de la forma en que se realiza la autenticación y la autorización, suponiendo que la aplicación tenía autenticación configurada. En este capítulo se describe cómo migrar desde el modelo de proveedor universal de formularios Web Forms de ASP.NET (para la pertenencia, los roles y los perfiles de usuario) y cómo trabajar con ASP.NET Core identidad de las Blazor aplicaciones. Aunque en este capítulo se abordan los pasos y las consideraciones de alto nivel, se pueden encontrar los pasos detallados y los scripts en la documentación a la que se hace referencia.

## <a name="aspnet-universal-providers"></a>Proveedores universales de ASP.NET

Como ASP.NET 2,0, la plataforma de formularios Web Forms de ASP.NET admite un modelo de proveedor para una variedad de características, incluida la pertenencia. El proveedor de pertenencia universal, junto con el proveedor de roles opcional, se implementa muy comúnmente con aplicaciones de formularios Web Forms de ASP.NET. Ofrece una forma sólida y segura de administrar la autenticación y la autorización que siguen funcionando bien hoy en día. La oferta más reciente de estos proveedores universales está disponible como un paquete NuGet, [Microsoft. Aspnet. Providers](https://www.nuget.org/packages/Microsoft.AspNet.Providers).

El proveedores universales trabajar con un esquema de base de datos SQL que incluye tablas como `aspnet_Applications` , `aspnet_Membership` , `aspnet_Roles` y `aspnet_Users` . Cuando se configura ejecutando el [ comandoaspnet_regsql.exe](https://docs.microsoft.com/previous-versions/ms229862(v=vs.140)), los proveedores instalan tablas y procedimientos almacenados que proporcionan todas las consultas y los comandos necesarios para trabajar con los datos subyacentes. El esquema de la base de datos y estos procedimientos almacenados no son compatibles con los sistemas de identidad ASP.NET Identity y ASP.NET Core más recientes, por lo que los datos existentes se deben migrar al nuevo sistema. En la figura 1 se muestra un esquema de tabla de ejemplo configurado para proveedores universales.

![esquema de proveedores universales](./media/security/membership-tables.png)

El proveedor universal controla los usuarios, la pertenencia, los roles y los perfiles. A los usuarios se les asignan identificadores únicos globales y la información básica (userId, userName) se almacena en la `aspnet_Users` tabla. La información de autenticación, como la contraseña, el formato de contraseña, la contraseña sal, los contadores de bloqueo y los detalles, etc., se almacenan en la `aspnet_Membership` tabla. Los roles constan simplemente de nombres e identificadores únicos, que se asignan a los usuarios a través de la `aspnet_UsersInRoles` tabla de asociación, lo que proporciona una relación de varios a varios.

Si el sistema existente usa roles además de la pertenencia, tendrá que migrar las cuentas de usuario, las contraseñas asociadas, los roles y la pertenencia al rol en ASP.NET Core identidad. Lo más probable es que tenga que actualizar el código en el que está realizando actualmente comprobaciones de rol mediante instrucciones if para aprovechar en su lugar filtros declarativos, atributos o aplicaciones auxiliares de etiquetas. Revisaremos las consideraciones de migración con más detalle al final de este capítulo.

### <a name="authorization-configuration-in-web-forms"></a>Configuración de autorización en formularios Web Forms

Para configurar el acceso autorizado a determinadas páginas en una aplicación de formularios Web Forms ASP.NET, normalmente se especifica que no se puede tener acceso a determinadas páginas o carpetas a los usuarios anónimos. Esto se hace en el archivo web.config:

```xml
<?xml version="1.0"?>
<configuration>
    <system.web>
      <authentication mode="Forms">
        <forms defaultUrl="~/home.aspx" loginUrl="~/login.aspx"
          slidingExpiration="true" timeout="2880"></forms>
      </authentication>

      <authorization>
        <deny users="?" />
      </authorization>
    </system.web>
</configuration>
```

La `authentication` sección de configuración configura la autenticación de formularios para la aplicación. La `authorization` sección se usa para no permitir usuarios anónimos para toda la aplicación. Sin embargo, puede proporcionar reglas de autorización más pormenorizadas en cada ubicación, así como aplicar comprobaciones de autorización basadas en roles.

```xml
<location path="login.aspx">
  <system.web>
    <authorization>
      <allow users="*" />
    </authorization>
  </system.web>
</location>
```

La configuración anterior, cuando se combina con la primera, permitiría a los usuarios anónimos tener acceso a la página de inicio de sesión, invalidando la restricción para todo el sitio en usuarios no autenticados.

```xml
<location path="/admin">
  <system.web>
    <authorization>
      <allow roles="Administrators" />
      <deny users="*" />
    </authorization>
  </system.web>
</location>
```

La configuración anterior, cuando se combina con las demás, restringe el acceso a la `/admin` carpeta y todos los recursos que contiene a los miembros del rol "administradores". Esto también se puede aplicar colocando un `web.config` archivo independiente dentro de la raíz de la `/admin` carpeta.

### <a name="authorization-code-in-web-forms"></a>Código de autorización en formularios Web Forms

Además de configurar el acceso mediante `web.config` , también puede configurar mediante programación el acceso y el comportamiento en la aplicación de formularios Web Forms. Por ejemplo, puede restringir la capacidad de realizar determinadas operaciones o ver determinados datos según el rol del usuario.

Este código se puede usar tanto en la lógica de código subyacente como en la propia página:

```html
<% if (HttpContext.Current.User.IsInRole("Administrators")) { %>
  <a href="/admin">Go To Admin</a>
<% } %>
```

Además de comprobar la pertenencia al rol de usuario, también puede determinar si se autentican (aunque a menudo esto se realiza mejor con la configuración basada en la ubicación que se ha explicado anteriormente). A continuación se muestra un ejemplo de este enfoque.

```csharp
protected void Page_Load(object sender, EventArgs e)
{
    if (!User.Identity.IsAuthenticated)
    {
        FormsAuthentication.RedirectToLoginPage();
    }
    if (!Roles.IsUserInRole(User.Identity.Name, "Administrators"))
    {
        MessageLabel.Text = "Only administrators can view this.";
        SecretPanel.Visible = false;
    }
}
```

En el código anterior, se usa el control de acceso basado en rol (RBAC) para determinar si determinados elementos de la página, como `SecretPanel` , son visibles según el rol del usuario actual.

Normalmente, las aplicaciones de formularios Web Forms de ASP.NET configuran la seguridad en el `web.config` archivo y, a continuación, agregan comprobaciones adicionales cuando sea necesario en `.aspx` las páginas y sus `.aspx.cs` archivos Codebehind relacionados. La mayoría de las aplicaciones aprovechan el proveedor de pertenencia universal, con frecuencia con el proveedor de roles adicional.

## <a name="aspnet-core-identity"></a>Identidad de ASP.NET Core

Aunque sigue siendo tarea con autenticación y autorización, ASP.NET Core identidad usa un conjunto diferente de abstracciones y suposiciones en comparación con los proveedores universales. Por ejemplo, el nuevo modelo de identidad admite la autenticación de terceros, lo que permite a los usuarios autenticarse mediante una cuenta de medios sociales u otro proveedor de autenticación de confianza. ASP.NET Core identidad admite la interfaz de usuario para las páginas necesarias normalmente, como inicio de sesión, cierre de sesión y registro. Aprovecha EF Core para su acceso a datos y usa las migraciones EF Core para generar el esquema necesario necesario para admitir su modelo de datos. Esta [Introducción a la identidad en ASP.net Core](https://docs.microsoft.com/aspnet/core/security/authentication/identity) proporciona una buena información general de lo que se incluye con ASP.net Core identidad y cómo empezar a trabajar con él. Si aún no ha configurado ASP.NET Core identidad en la aplicación y su base de datos, le ayudará a empezar.

### <a name="roles-claims-and-policies"></a>Roles, notificaciones y directivas

Tanto los proveedores universales como la identidad de ASP.NET Core admiten el concepto de roles. Puede crear roles para usuarios y asignar usuarios a roles. Los usuarios pueden pertenecer a cualquier número de roles y se puede comprobar la pertenencia a roles como parte de la implementación de autorización.

Además de los roles, ASP.NET Core identidad admite los conceptos de notificaciones y directivas. Aunque un rol debe corresponder específicamente a un conjunto de recursos a los que un usuario de ese rol debe poder acceder, una demanda es simplemente parte de la identidad de un usuario. Una demanda es un par de valor de nombre que representa lo que es el sujeto, no lo que puede hacer el sujeto.

Es posible inspeccionar directamente las notificaciones de un usuario y determinar en función de si se debe conceder a un usuario acceso a un recurso. Sin embargo, estas comprobaciones suelen ser repetitivas y dispersas por todo el sistema. Un enfoque mejor es definir una *Directiva*.

Una directiva de autorización se compone de uno o varios requisitos. Las directivas se registran como parte de la configuración del servicio de autorización en el `ConfigureServices` método de `Startup.cs` . Por ejemplo, el siguiente fragmento de código configura una directiva denominada "CanadiansOnly" que tiene el requisito de que el usuario tenga la demanda del país con el valor "Canadá".

```csharp
services.AddAuthorization(options =>
{
    options.AddPolicy("CanadiansOnly", policy => policy.RequireClaim(ClaimTypes.Country, "Canada"));
});
```

Puede obtener [más información sobre cómo crear directivas personalizadas en la documentación de](https://docs.microsoft.com/aspnet/core/security/authorization/policies).

Si usa directivas o roles, puede especificar que una página determinada de la Blazor aplicación requiera el rol o la Directiva con el `[Authorize]` atributo, aplicados con la `@attribute` Directiva.

Requerir un rol:

```csharp
@attribute [Authorize(Roles ="administrators")]
```

Se debe satisfacer la necesidad de una directiva:

```csharp
@attribute [Authorize(Policy ="CanadiansOnly")]
```

Si necesita tener acceso al estado de autenticación de un usuario, a los roles o a las notificaciones en el código, hay dos formas principales de lograrlo. La primera es recibir el estado de autenticación como parámetro en cascada. La segunda es para tener acceso al estado mediante un insertado `AuthenticationStateProvider` . Los detalles de cada uno de estos enfoques se describen en la [ Blazor documentación de seguridad](https://docs.microsoft.com/aspnet/core/blazor/security/).

En el código siguiente se muestra cómo recibir `AuthenticationState` como parámetro en cascada:

```csharp
[CascadingParameter]
private Task<AuthenticationState> authenticationStateTask { get; set; }
```

Con este parámetro en su lugar, puede obtener el usuario mediante este código:

```csharp
var authState = await authenticationStateTask;
var user = authState.User;
```

En el código siguiente se muestra cómo insertar `AuthenticationStateProvider` :

```csharp
@using Microsoft.AspNetCore.Components.Authorization
@inject AuthenticationStateProvider AuthenticationStateProvider
```

Con el proveedor en su lugar, puede obtener acceso al usuario con el código siguiente:

```csharp
AuthenticationState authState = await AuthenticationStateProvider.GetAuthenticationStateAsync();
ClaimsPrincipal user = authState.User;

if (user.Identity.IsAuthenticated)
{
  // work with user.Claims and/or user.Roles
}
```

**Nota:** El `AuthorizeView` componente, que se trata más adelante en este capítulo, proporciona una manera declarativa de controlar lo que un usuario ve en una página o componente.

Para trabajar con usuarios y notificaciones (en Blazor aplicaciones de servidor), es posible que también tenga que insertar un `UserManager<T>` (usar `IdentityUser` de forma predeterminada), que puede usar para enumerar y modificar las notificaciones de un usuario. En primer lugar, inserte el tipo y asígnelo a una propiedad:

```csharp
@inject UserManager<IdentityUser> MyUserManager
```

A continuación, úselo para trabajar con las notificaciones del usuario. En el ejemplo siguiente se muestra cómo agregar y conservar una demanda para un usuario:

```csharp
private async Task AddCountryClaim()
{
    var authState = await AuthenticationStateProvider.GetAuthenticationStateAsync();
    var user = authState.User;
    var identityUser = await MyUserManager.FindByNameAsync(user.Identity.Name);

    if (!user.HasClaim(c => c.Type == ClaimTypes.Country))
    {
        // stores the claim in the cookie
        ClaimsIdentity id = new ClaimsIdentity();
        id.AddClaim(new Claim(ClaimTypes.Country, "Canada"));
        user.AddIdentity(id);

        // save the claim in the database
        await MyUserManager.AddClaimAsync(identityUser, new Claim(ClaimTypes.Country, "Canada"));
    }
}
```

Si necesita trabajar con roles, siga el mismo enfoque. Es posible que tenga que insertar un `RoleManager<T>` (se usa `IdentityRole` para el tipo predeterminado) para enumerar y administrar los roles.

**Nota:** En Blazor los proyectos de Webassembly, tendrá que proporcionar las API de servidor para realizar estas operaciones (en lugar de usar `UserManager<T>` o `RoleManager<T>` directamente). Una Blazor aplicación cliente de Webassembly administraría las notificaciones y/o los roles mediante la llamada segura de puntos de conexión de API expuestos para este fin.

### <a name="migration-guide"></a>Guía de migración

La migración de los formularios Web Forms de ASP.NET y los proveedores universales a la identidad de ASP.NET Core requiere varios pasos:

1. Crear ASP.NET Core esquema de base de datos de identidad en la base de datos de destino
2. Migrar datos del esquema del proveedor universal a ASP.NET Core esquema de identidad
3. Migre la configuración de web.config a middleware y servicios, normalmente en `Startup.cs`
4. Actualice páginas individuales mediante controles y condicionales para usar aplicaciones auxiliares de etiquetas y nuevas API de identidad.

En las siguientes secciones se describen estos pasos.

### <a name="creating-the-aspnet-core-identity-schema"></a>Crear el esquema de identidad de ASP.NET Core

Hay varias maneras de crear la estructura de tabla necesaria utilizada para ASP.NET Core identidad. La más sencilla consiste en crear una nueva aplicación Web de ASP.NET Core. Elija aplicación web y, a continuación, cambie autenticación para usar cuentas de usuario individuales.

![nuevo proyecto con cuentas de usuario individuales](./media/security/individual-user-accounts.png)

Desde la línea de comandos, puede hacer lo mismo ejecutando `dotnet new webapp -au Individual` . Una vez creada la aplicación, ejecútela y regístrese en el sitio. Debe desencadenar una página como la que se muestra a continuación:

![Página aplicar migraciones](./media/security/apply-migrations-page.png)

Haga clic en el botón "aplicar migraciones" para crear las tablas de base de datos necesarias. Además, los archivos de migración deben aparecer en el proyecto, como se muestra a continuación:

![archivos de migración](./media/security/migration-files.png)

Puede ejecutar la migración usted mismo, sin ejecutar la aplicación Web, mediante esta herramienta de línea de comandos:

```powershell
dotnet ef database update
```

Si prefiere ejecutar un script para aplicar el nuevo esquema a una base de datos existente, puede crear un script de estas migraciones desde la línea de comandos. Ejecute este comando para generar el script:

```powershell
dotnet ef migrations script -o auth.sql
```

Esto producirá un script SQL en el archivo de salida `auth.sql` que se puede ejecutar en cualquier base de datos que desee. Si tiene algún problema al ejecutar los `dotnet ef` comandos, asegúrese [de que tiene las herramientas de EF Core instaladas en el sistema](https://docs.microsoft.com/ef/core/miscellaneous/cli/dotnet).

En el caso de que tenga columnas adicionales en las tablas de origen, tendrá que identificar la mejor ubicación para estas columnas en el nuevo esquema. Por lo general, las columnas que se encuentran en la `aspnet_Membership` tabla se deben asignar a la `AspNetUsers` tabla. Las columnas de `aspnet_Roles` deben estar asignadas a `AspNetRoles` . Cualquier columna adicional de la `aspnet_UsersInRoles` tabla se agregaría a la `AspNetUserRoles` tabla.

También merece la pena considerar colocar cualquier columna adicional en tablas independientes, de modo que las migraciones futuras no tengan que tener en cuenta tales personalizaciones del esquema de identidad predeterminado.

### <a name="migrating-data-from-universal-providers-to-aspnet-core-identity"></a>Migrar datos de proveedores universales a ASP.NET Core identidad

Una vez que tenga el esquema de la tabla de destino, el siguiente paso consiste en migrar los registros de usuario y de rol al nuevo esquema. Una lista completa de las diferencias de esquema, incluidas las columnas que se asignan a las columnas nuevas, se pueden encontrar [aquí](https://docs.microsoft.com/aspnet/core/migration/proper-to-2x/membership-to-core-identity).

Para migrar los usuarios de la pertenencia a las nuevas tablas de identidad, debe [seguir los pasos descritos en la documentación](https://docs.microsoft.com/aspnet/core/migration/proper-to-2x/membership-to-core-identity)de. Después de seguir estos pasos y el script proporcionado, los usuarios deberán cambiar su contraseña la próxima vez que inicien sesión.

Es posible migrar las contraseñas de usuario, pero el proceso es mucho más complicado. Requerir a los usuarios que actualicen sus contraseñas como parte del proceso de migración y animarles a usar contraseñas nuevas y únicas, es probable que mejore la seguridad global de la aplicación.

### <a name="migrating-security-settings-from-webconfig-to-startupcs"></a>Migrar la configuración de seguridad de web.config a Startup.cs

Como se indicó anteriormente, los proveedores de roles y la pertenencia a ASP.NET se configuran en el archivo de web.config de la aplicación. Como ASP.NET Core aplicaciones no están asociadas a IIS y usan un sistema independiente para la configuración, esta configuración se debe configurar en otra parte. En su mayor parte, ASP.NET Core identidad se configura en el `Startup.cs` archivo. Abra el proyecto web que se creó anteriormente (para generar el esquema de la tabla de identidad) y revise el `Startup.cs` archivo.

El método ConfigureServices predeterminado agrega compatibilidad con EF Core e identidad:

```csharp
// This method gets called by the runtime. Use this method to add services to the container.
public void ConfigureServices(IServiceCollection services)
{
    services.AddDbContext<ApplicationDbContext>(options =>
        options.UseSqlServer(
            Configuration.GetConnectionString("DefaultConnection")));

    services.AddDefaultIdentity<IdentityUser>(options => options.SignIn.RequireConfirmedAccount = true)
        .AddEntityFrameworkStores<ApplicationDbContext>();

    services.AddRazorPages();
}
```

El `AddDefaultIdentity` método de extensión se usa para configurar la identidad con el fin de usar el `ApplicationDbContext` tipo predeterminado y el tipo de marco `IdentityUser` . Si utiliza un personalizado `IdentityUser` , asegúrese de especificar aquí su tipo. Si estos métodos de extensión no funcionan en la aplicación, compruebe que tiene las instrucciones Using adecuadas y que tiene las referencias de paquete NuGet necesarias. Por ejemplo, el proyecto debe tener alguna versión de los `Microsoft.AspNetCore.Identity.EntityFrameworkCore` paquetes y a los `Microsoft.AspNetCore.Identity.UI` que se hace referencia.

También en `Startup.cs` , debería ver el middleware necesario configurado para el sitio. Concretamente, `UseAuthentication` y `UseAuthorization` deben configurarse, y en la ubicación adecuada.

```csharp

// This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
        app.UseDatabaseErrorPage();
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

    app.UseAuthentication();
    app.UseAuthorization();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapRazorPages();
    });
}
```

ASP.NET Identity no configura el acceso anónimo o basado en roles a ubicaciones desde `Startup.cs` . Tendrá que migrar los datos de configuración de autorización específicos de la ubicación a los filtros de ASP.NET Core. Tome nota de las carpetas y páginas que requerirán estas actualizaciones. Realizará estos cambios en la sección siguiente.

### <a name="updating-individual-pages-to-use-aspnet-core-identity-abstractions"></a>Actualizar páginas individuales para usar ASP.NET Core abstracciones de identidad

En la aplicación de formularios Web Forms de ASP.NET, si tiene web.config configuración para denegar el acceso a determinadas páginas o carpetas a usuarios anónimos, debe migrarlos simplemente agregando el `[Authorize]` atributo a estas páginas:

```razor
@attribute [Authorize]
```

Si aún no ha denegado el acceso excepto los usuarios que pertenecen a un rol determinado, migraría igualmente esto agregando un atributo que especifica un rol:

```razor
@attribute [Authorize(Roles ="administrators")]
```

Tenga en cuenta que el `[Authorize]` atributo solo funciona en `@page` los componentes que se alcanzan a través del Blazor enrutador. El atributo no funciona con componentes secundarios, que deben usarse en su lugar `AuthorizeView` .

Si tiene lógica en el marcado de página para determinar si se va a Mostrar código a un determinado usuario, puede reemplazarlo por el `AuthorizeView` componente. El [componente AuthorizeView](https://docs.microsoft.com/aspnet/core/blazor/security#authorizeview-component) muestra la interfaz de usuario de forma selectiva en función de si el usuario está autorizado para verlo. También expone una `context` variable que se puede utilizar para tener acceso a la información del usuario.

```razor
<AuthorizeView>
    <Authorized>
        <h1>Hello, @context.User.Identity.Name!</h1>
        <p>You can only see this content if you are authenticated.</p>
    </Authorized>
    <NotAuthorized>
        <h1>Authentication Failure!</h1>
        <p>You are not signed in.</p>
    </NotAuthorized>
</AuthorizeView>
```

Puede tener acceso al estado de autenticación dentro de la lógica de procedimientos accediendo al usuario desde un `Task<AuthenticationState` configurado con el `[CascadingParameter]` atributo. Esto le permitirá obtener acceso al usuario, lo que le permitirá determinar si se autentican y si pertenecen a un rol determinado. Si necesita evaluar una directiva con procedimientos, puede insertar una instancia de `IAuthorizationService` y llamar al `AuthorizeAsync` método en ella. En el código de ejemplo siguiente se muestra cómo obtener información del usuario y permitir que un usuario autorizado realice una tarea restringida por la `content-editor` Directiva.

```razor
@using Microsoft.AspNetCore.Authorization
@inject IAuthorizationService AuthorizationService

<button @onclick="@DoSomething">Do something important</button>

@code {
    [CascadingParameter]
    private Task<AuthenticationState> authenticationStateTask { get; set; }

    private async Task DoSomething()
    {
        var user = (await authenticationStateTask).User;

        if (user.Identity.IsAuthenticated)
        {
            // Perform an action only available to authenticated (signed-in) users.
        }

        if (user.IsInRole("admin"))
        {
            // Perform an action only available to users in the 'admin' role.
        }

        if ((await AuthorizationService.AuthorizeAsync(user, "content-editor"))
            .Succeeded)
        {
            // Perform an action only available to users satisfying the
            // 'content-editor' policy.
        }
    }
}
```

`AuthenticationState`Primero se debe configurar como valor en cascada antes de que se pueda enlazar a un parámetro en cascada como este. Esto se suele hacer mediante el `CascadingAuthenticationState` componente. Esto se hace normalmente en `App.razor` :

```razor
<CascadingAuthenticationState>
    <Router AppAssembly="@typeof(Program).Assembly">
        <Found Context="routeData">
            <AuthorizeRouteView RouteData="@routeData"
                DefaultLayout="@typeof(MainLayout)" />
        </Found>
        <NotFound>
            <LayoutView Layout="@typeof(MainLayout)">
                <p>Sorry, there's nothing at this address.</p>
            </LayoutView>
        </NotFound>
    </Router>
</CascadingAuthenticationState>
```

## <a name="summary"></a>Resumen

Blazor usa el mismo modelo de seguridad que ASP.NET Core, que es ASP.NET Core identidad. La migración de proveedores universales a ASP.NET Core identidad es relativamente sencilla, suponiendo que no se aplicó demasiada personalización al esquema de datos original. Una vez que se han migrado los datos, el trabajo con la autenticación y la autorización en las Blazor aplicaciones está bien documentado, con la compatibilidad configurable y con la mayoría de los requisitos de seguridad mediante programación.

## <a name="references"></a>Referencias

- [Introducción a la identidad en ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/identity)
- [Migración de la autenticación de pertenencia de ASP.NET a ASP.NET Core identidad 2,0](https://docs.microsoft.com/aspnet/core/migration/proper-to-2x/membership-to-core-identity)
- [Migración de la autenticación y la identidad a ASP.NET Core](https://docs.microsoft.com/aspnet/core/migration/identity)
- [BlazorAutenticación y autorización de ASP.net Core](https://docs.microsoft.com/aspnet/core/blazor/security/)

>[!div class="step-by-step"]
>[Anterior](config.md)
>[Siguiente](migration.md)
