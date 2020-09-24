---
title: 'Seguridad: autenticación y autorización en formularios Web Forms de ASP.NET y Blazor'
description: Obtenga información sobre cómo controlar la autenticación y la autorización en formularios Web Forms de ASP.NET y Blazor .
author: ardalis
ms.author: daroth
no-loc:
- Blazor
ms.date: 09/11/2019
ms.openlocfilehash: 690e559617e4961c3cf3262a6d2d48a6bfac67cd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161300"
---
# <a name="security-authentication-and-authorization-in-aspnet-web-forms-and-no-locblazor"></a><span data-ttu-id="0e049-103">Seguridad: Autenticación y autorización en ASP.NET Web Forms y Blazor </span><span class="sxs-lookup"><span data-stu-id="0e049-103">Security: Authentication and Authorization in ASP.NET Web Forms and Blazor</span></span>

<span data-ttu-id="0e049-104">La migración de una aplicación de formularios Web Forms ASP.NET a Blazor seguramente requiere la actualización de la forma en que se realiza la autenticación y la autorización, suponiendo que la aplicación tenía autenticación configurada.</span><span class="sxs-lookup"><span data-stu-id="0e049-104">Migrating from an ASP.NET Web Forms application to Blazor will almost certainly require updating how authentication and authorization is performed, assuming the application had authentication configured.</span></span> <span data-ttu-id="0e049-105">En este capítulo se describe cómo migrar desde el modelo de proveedor universal de formularios Web Forms de ASP.NET (para la pertenencia, los roles y los perfiles de usuario) y cómo trabajar con ASP.NET Core identidad de las Blazor aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0e049-105">This chapter will cover how to migrate from the ASP.NET Web Forms universal provider model (for membership, roles, and user profiles) and how to work with ASP.NET Core Identity from Blazor apps.</span></span> <span data-ttu-id="0e049-106">Aunque en este capítulo se abordan los pasos y las consideraciones de alto nivel, se pueden encontrar los pasos detallados y los scripts en la documentación a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="0e049-106">While this chapter will cover the high level steps and considerations, the detailed steps and scripts may be found in the referenced documentation.</span></span>

## <a name="aspnet-universal-providers"></a><span data-ttu-id="0e049-107">Proveedores universales de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0e049-107">ASP.NET universal providers</span></span>

<span data-ttu-id="0e049-108">Como ASP.NET 2,0, la plataforma de formularios Web Forms de ASP.NET admite un modelo de proveedor para una variedad de características, incluida la pertenencia.</span><span class="sxs-lookup"><span data-stu-id="0e049-108">Since ASP.NET 2.0, the ASP.NET Web Forms platform has supported a provider model for a variety of features, including membership.</span></span> <span data-ttu-id="0e049-109">El proveedor de pertenencia universal, junto con el proveedor de roles opcional, se implementa muy comúnmente con aplicaciones de formularios Web Forms de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0e049-109">The universal membership provider, along with the optional role provider, is very commonly deployed with ASP.NET Web Forms applications.</span></span> <span data-ttu-id="0e049-110">Ofrece una forma sólida y segura de administrar la autenticación y la autorización que siguen funcionando bien hoy en día.</span><span class="sxs-lookup"><span data-stu-id="0e049-110">It offers a robust and secure way to manage authentication and authorization that continues to work well today.</span></span> <span data-ttu-id="0e049-111">La oferta más reciente de estos proveedores universales está disponible como un paquete NuGet, [Microsoft. Aspnet. Providers](https://www.nuget.org/packages/Microsoft.AspNet.Providers).</span><span class="sxs-lookup"><span data-stu-id="0e049-111">The most recent offering of these universal providers is available as a NuGet package, [Microsoft.AspNet.Providers](https://www.nuget.org/packages/Microsoft.AspNet.Providers).</span></span>

<span data-ttu-id="0e049-112">El proveedores universales trabajar con un esquema de base de datos SQL que incluye tablas como `aspnet_Applications` , `aspnet_Membership` , `aspnet_Roles` y `aspnet_Users` .</span><span class="sxs-lookup"><span data-stu-id="0e049-112">The Universal Providers work with a SQL database schema that includes tables like `aspnet_Applications`, `aspnet_Membership`, `aspnet_Roles`, and `aspnet_Users`.</span></span> <span data-ttu-id="0e049-113">Cuando se configura ejecutando el [ comandoaspnet_regsql.exe](/previous-versions/ms229862(v=vs.140)), los proveedores instalan tablas y procedimientos almacenados que proporcionan todas las consultas y los comandos necesarios para trabajar con los datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="0e049-113">When configured by running the [aspnet_regsql.exe command](/previous-versions/ms229862(v=vs.140)), the providers install tables and stored procedures that provide all of the necessary queries and commands necessary to work with the underlying data.</span></span> <span data-ttu-id="0e049-114">El esquema de la base de datos y estos procedimientos almacenados no son compatibles con los sistemas de identidad ASP.NET Identity y ASP.NET Core más recientes, por lo que los datos existentes se deben migrar al nuevo sistema.</span><span class="sxs-lookup"><span data-stu-id="0e049-114">The database schema and these stored procedures are not compatible with newer ASP.NET Identity and ASP.NET Core Identity systems, so existing data must be migrated into the new system.</span></span> <span data-ttu-id="0e049-115">En la figura 1 se muestra un esquema de tabla de ejemplo configurado para proveedores universales.</span><span class="sxs-lookup"><span data-stu-id="0e049-115">Figure 1 shows an example table schema configured for universal providers.</span></span>

![esquema de proveedores universales](./media/security/membership-tables.png)

<span data-ttu-id="0e049-117">El proveedor universal controla los usuarios, la pertenencia, los roles y los perfiles.</span><span class="sxs-lookup"><span data-stu-id="0e049-117">The universal provider handles users, membership, roles, and profiles.</span></span> <span data-ttu-id="0e049-118">A los usuarios se les asignan identificadores únicos globales y la información básica (userId, userName) se almacena en la `aspnet_Users` tabla.</span><span class="sxs-lookup"><span data-stu-id="0e049-118">Users are assigned globally unique identifiers and very basic information (userId, userName) is stored in the `aspnet_Users` table.</span></span> <span data-ttu-id="0e049-119">La información de autenticación, como la contraseña, el formato de contraseña, la contraseña sal, los contadores de bloqueo y los detalles, etc., se almacenan en la `aspnet_Membership` tabla.</span><span class="sxs-lookup"><span data-stu-id="0e049-119">Authentication information, such as password, password format, password salt, lockout counters and details, etc. are stored in the `aspnet_Membership` table.</span></span> <span data-ttu-id="0e049-120">Los roles constan simplemente de nombres e identificadores únicos, que se asignan a los usuarios a través de la `aspnet_UsersInRoles` tabla de asociación, lo que proporciona una relación de varios a varios.</span><span class="sxs-lookup"><span data-stu-id="0e049-120">Roles consist simply of names and unique identifiers, which are assigned to users via the `aspnet_UsersInRoles` association table, providing a many-to-many relationship.</span></span>

<span data-ttu-id="0e049-121">Si el sistema existente usa roles además de la pertenencia, tendrá que migrar las cuentas de usuario, las contraseñas asociadas, los roles y la pertenencia al rol en ASP.NET Core identidad.</span><span class="sxs-lookup"><span data-stu-id="0e049-121">If your existing system is using roles in addition to membership, you will need to migrate the user accounts, the associated passwords, the roles, and the role membership into ASP.NET Core Identity.</span></span> <span data-ttu-id="0e049-122">Lo más probable es que tenga que actualizar el código en el que está realizando actualmente comprobaciones de rol mediante instrucciones if para aprovechar en su lugar filtros declarativos, atributos o aplicaciones auxiliares de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="0e049-122">You will also most likely need to update your code where you're currently performing role checks using if statements to instead leverage declarative filters, attributes, and/or tag helpers.</span></span> <span data-ttu-id="0e049-123">Revisaremos las consideraciones de migración con más detalle al final de este capítulo.</span><span class="sxs-lookup"><span data-stu-id="0e049-123">We will review migration considerations in greater detail at the end of this chapter.</span></span>

### <a name="authorization-configuration-in-web-forms"></a><span data-ttu-id="0e049-124">Configuración de autorización en formularios Web Forms</span><span class="sxs-lookup"><span data-stu-id="0e049-124">Authorization configuration in Web Forms</span></span>

<span data-ttu-id="0e049-125">Para configurar el acceso autorizado a determinadas páginas en una aplicación de formularios Web Forms ASP.NET, normalmente se especifica que no se puede tener acceso a determinadas páginas o carpetas a los usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="0e049-125">To configure authorized access to certain pages in an ASP.NET Web Forms application, typically you specify that certain pages or folders are inaccessible to anonymous users.</span></span> <span data-ttu-id="0e049-126">Esto se hace en el archivo web.config:</span><span class="sxs-lookup"><span data-stu-id="0e049-126">This is done in the web.config file:</span></span>

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

<span data-ttu-id="0e049-127">La `authentication` sección de configuración configura la autenticación de formularios para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0e049-127">The `authentication` configuration section sets up forms authentication for the application.</span></span> <span data-ttu-id="0e049-128">La `authorization` sección se usa para no permitir usuarios anónimos para toda la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0e049-128">The `authorization` section is used to disallow anonymous users for the entire application.</span></span> <span data-ttu-id="0e049-129">Sin embargo, puede proporcionar reglas de autorización más pormenorizadas en cada ubicación, así como aplicar comprobaciones de autorización basadas en roles.</span><span class="sxs-lookup"><span data-stu-id="0e049-129">However, you can provide more granular authorization rules on a per-location basis as well as apply role based authorization checks.</span></span>

```xml
<location path="login.aspx">
  <system.web>
    <authorization>
      <allow users="*" />
    </authorization>
  </system.web>
</location>
```

<span data-ttu-id="0e049-130">La configuración anterior, cuando se combina con la primera, permitiría a los usuarios anónimos tener acceso a la página de inicio de sesión, invalidando la restricción para todo el sitio en usuarios no autenticados.</span><span class="sxs-lookup"><span data-stu-id="0e049-130">The above configuration, when combined with the first one, would allow anonymous users to access the login page, overriding the site-wide restriction on non-authenticated users.</span></span>

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

<span data-ttu-id="0e049-131">La configuración anterior, cuando se combina con las demás, restringe el acceso a la `/admin` carpeta y todos los recursos que contiene a los miembros del rol "administradores".</span><span class="sxs-lookup"><span data-stu-id="0e049-131">The above configuration, when combined with the others, restricts access to the `/admin` folder and all resources within it to members of the "Administrators" role.</span></span> <span data-ttu-id="0e049-132">Esto también se puede aplicar colocando un `web.config` archivo independiente dentro de la raíz de la `/admin` carpeta.</span><span class="sxs-lookup"><span data-stu-id="0e049-132">This could also be applied by placing a separate `web.config` file within the `/admin` folder root.</span></span>

### <a name="authorization-code-in-web-forms"></a><span data-ttu-id="0e049-133">Código de autorización en formularios Web Forms</span><span class="sxs-lookup"><span data-stu-id="0e049-133">Authorization code in Web Forms</span></span>

<span data-ttu-id="0e049-134">Además de configurar el acceso mediante `web.config` , también puede configurar mediante programación el acceso y el comportamiento en la aplicación de formularios Web Forms.</span><span class="sxs-lookup"><span data-stu-id="0e049-134">In addition to configuring access using `web.config`, you can also programmatically configure access and behavior in your Web Forms application.</span></span> <span data-ttu-id="0e049-135">Por ejemplo, puede restringir la capacidad de realizar determinadas operaciones o ver determinados datos según el rol del usuario.</span><span class="sxs-lookup"><span data-stu-id="0e049-135">For instance, you can restrict the ability to perform certain operations or view certain data based on the user's role.</span></span>

<span data-ttu-id="0e049-136">Este código se puede usar tanto en la lógica de código subyacente como en la propia página:</span><span class="sxs-lookup"><span data-stu-id="0e049-136">This code can be used both in codebehind logic as well as in the page itself:</span></span>

```html
<% if (HttpContext.Current.User.IsInRole("Administrators")) { %>
  <a href="/admin">Go To Admin</a>
<% } %>
```

<span data-ttu-id="0e049-137">Además de comprobar la pertenencia al rol de usuario, también puede determinar si se autentican (aunque a menudo esto se realiza mejor con la configuración basada en la ubicación que se ha explicado anteriormente).</span><span class="sxs-lookup"><span data-stu-id="0e049-137">In addition to checking user role membership, you can also determine if they are authenticated (though often this is better done using the location-based configuration covered above).</span></span> <span data-ttu-id="0e049-138">A continuación se muestra un ejemplo de este enfoque.</span><span class="sxs-lookup"><span data-stu-id="0e049-138">Below is an example of this approach.</span></span>

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

<span data-ttu-id="0e049-139">En el código anterior, se usa el control de acceso basado en rol (RBAC) para determinar si determinados elementos de la página, como `SecretPanel` , son visibles según el rol del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="0e049-139">In the code above, role-based access control (RBAC) is used to determine whether certain elements of the page, such as a `SecretPanel`, are visible based on the current user's role.</span></span>

<span data-ttu-id="0e049-140">Normalmente, las aplicaciones de formularios Web Forms de ASP.NET configuran la seguridad en el `web.config` archivo y, a continuación, agregan comprobaciones adicionales cuando sea necesario en `.aspx` las páginas y sus `.aspx.cs` archivos Codebehind relacionados.</span><span class="sxs-lookup"><span data-stu-id="0e049-140">Typically, ASP.NET Web Forms applications configure security within the `web.config` file and then add additional checks where needed in `.aspx` pages and their related `.aspx.cs` codebehind files.</span></span> <span data-ttu-id="0e049-141">La mayoría de las aplicaciones aprovechan el proveedor de pertenencia universal, con frecuencia con el proveedor de roles adicional.</span><span class="sxs-lookup"><span data-stu-id="0e049-141">Most applications leverage the universal membership provider, frequently with the additional role provider.</span></span>

## <a name="aspnet-core-identity"></a><span data-ttu-id="0e049-142">Identidad de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0e049-142">ASP.NET Core Identity</span></span>

<span data-ttu-id="0e049-143">Aunque sigue siendo tarea con autenticación y autorización, ASP.NET Core identidad usa un conjunto diferente de abstracciones y suposiciones en comparación con los proveedores universales.</span><span class="sxs-lookup"><span data-stu-id="0e049-143">Although still tasked with authentication and authorization, ASP.NET Core Identity uses a different set of abstractions and assumptions when compared to the universal providers.</span></span> <span data-ttu-id="0e049-144">Por ejemplo, el nuevo modelo de identidad admite la autenticación de terceros, lo que permite a los usuarios autenticarse mediante una cuenta de medios sociales u otro proveedor de autenticación de confianza.</span><span class="sxs-lookup"><span data-stu-id="0e049-144">For example, the new Identity model supports third party authentication, allowing users to authenticate using a social media account or other trusted authentication provider.</span></span> <span data-ttu-id="0e049-145">ASP.NET Core identidad admite la interfaz de usuario para las páginas necesarias normalmente, como inicio de sesión, cierre de sesión y registro.</span><span class="sxs-lookup"><span data-stu-id="0e049-145">ASP.NET Core Identity supports UI for commonly needed pages like login, logout, and register.</span></span> <span data-ttu-id="0e049-146">Aprovecha EF Core para su acceso a datos y usa las migraciones EF Core para generar el esquema necesario necesario para admitir su modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="0e049-146">It leverages EF Core for its data access, and uses EF Core migrations to generate the necessary schema required to supports its data model.</span></span> <span data-ttu-id="0e049-147">Esta [Introducción a la identidad en ASP.net Core](/aspnet/core/security/authentication/identity) proporciona una buena información general de lo que se incluye con ASP.net Core identidad y cómo empezar a trabajar con él.</span><span class="sxs-lookup"><span data-stu-id="0e049-147">This [introduction to Identity on ASP.NET Core](/aspnet/core/security/authentication/identity) provides a good overview of what is included with ASP.NET Core Identity and how to get started working with it.</span></span> <span data-ttu-id="0e049-148">Si aún no ha configurado ASP.NET Core identidad en la aplicación y su base de datos, le ayudará a empezar.</span><span class="sxs-lookup"><span data-stu-id="0e049-148">If you haven't already set up ASP.NET Core Identity in your application and its database, it will help you get started.</span></span>

### <a name="roles-claims-and-policies"></a><span data-ttu-id="0e049-149">Roles, notificaciones y directivas</span><span class="sxs-lookup"><span data-stu-id="0e049-149">Roles, claims, and policies</span></span>

<span data-ttu-id="0e049-150">Tanto los proveedores universales como la identidad de ASP.NET Core admiten el concepto de roles.</span><span class="sxs-lookup"><span data-stu-id="0e049-150">Both the universal providers and ASP.NET Core Identity support the concept of roles.</span></span> <span data-ttu-id="0e049-151">Puede crear roles para usuarios y asignar usuarios a roles.</span><span class="sxs-lookup"><span data-stu-id="0e049-151">You can create roles for users and assign users to roles.</span></span> <span data-ttu-id="0e049-152">Los usuarios pueden pertenecer a cualquier número de roles y se puede comprobar la pertenencia a roles como parte de la implementación de autorización.</span><span class="sxs-lookup"><span data-stu-id="0e049-152">Users can belong to any number of roles, and you can verify role membership as part of your authorization implementation.</span></span>

<span data-ttu-id="0e049-153">Además de los roles, ASP.NET Core identidad admite los conceptos de notificaciones y directivas.</span><span class="sxs-lookup"><span data-stu-id="0e049-153">In addition to roles, ASP.NET Core identity supports the concepts of claims and policies.</span></span> <span data-ttu-id="0e049-154">Aunque un rol debe corresponder específicamente a un conjunto de recursos a los que un usuario de ese rol debe poder acceder, una demanda es simplemente parte de la identidad de un usuario.</span><span class="sxs-lookup"><span data-stu-id="0e049-154">While a role should specifically correspond to a set of resources a user in that role should be able to access, a claim is simply part of a user's identity.</span></span> <span data-ttu-id="0e049-155">Una demanda es un par de valor de nombre que representa lo que es el sujeto, no lo que puede hacer el sujeto.</span><span class="sxs-lookup"><span data-stu-id="0e049-155">A claim is a name value pair that represents what the subject is, not what the subject can do.</span></span>

<span data-ttu-id="0e049-156">Es posible inspeccionar directamente las notificaciones de un usuario y determinar en función de si se debe conceder a un usuario acceso a un recurso.</span><span class="sxs-lookup"><span data-stu-id="0e049-156">It is possible to directly inspect a user's claims and determine based on these whether a user should be given access to a resource.</span></span> <span data-ttu-id="0e049-157">Sin embargo, estas comprobaciones suelen ser repetitivas y dispersas por todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="0e049-157">However, such checks are often repetitive and scattered throughout the system.</span></span> <span data-ttu-id="0e049-158">Un enfoque mejor es definir una *Directiva*.</span><span class="sxs-lookup"><span data-stu-id="0e049-158">A better approach is to define a *policy*.</span></span>

<span data-ttu-id="0e049-159">Una directiva de autorización se compone de uno o varios requisitos.</span><span class="sxs-lookup"><span data-stu-id="0e049-159">An authorization policy consists of one or more requirements.</span></span> <span data-ttu-id="0e049-160">Las directivas se registran como parte de la configuración del servicio de autorización en el `ConfigureServices` método de `Startup.cs` .</span><span class="sxs-lookup"><span data-stu-id="0e049-160">Policies are registered as part of the authorization service configuration in the `ConfigureServices` method of `Startup.cs`.</span></span> <span data-ttu-id="0e049-161">Por ejemplo, el siguiente fragmento de código configura una directiva denominada "CanadiansOnly" que tiene el requisito de que el usuario tenga la demanda del país con el valor "Canadá".</span><span class="sxs-lookup"><span data-stu-id="0e049-161">For example, the following code snippet configures a policy called "CanadiansOnly" which has the requirement that the user have the Country claim with the value of "Canada".</span></span>

```csharp
services.AddAuthorization(options =>
{
    options.AddPolicy("CanadiansOnly", policy => policy.RequireClaim(ClaimTypes.Country, "Canada"));
});
```

<span data-ttu-id="0e049-162">Puede obtener [más información sobre cómo crear directivas personalizadas en la documentación de](/aspnet/core/security/authorization/policies).</span><span class="sxs-lookup"><span data-stu-id="0e049-162">You can [learn more about how to create custom policies in the documentation](/aspnet/core/security/authorization/policies).</span></span>

<span data-ttu-id="0e049-163">Si usa directivas o roles, puede especificar que una página determinada de la Blazor aplicación requiera el rol o la Directiva con el `[Authorize]` atributo, aplicados con la `@attribute` Directiva.</span><span class="sxs-lookup"><span data-stu-id="0e049-163">Whether you're using policies or roles, you can specify that a particular page in your Blazor application require that role or policy with the `[Authorize]` attribute, applied with the `@attribute` directive.</span></span>

<span data-ttu-id="0e049-164">Requerir un rol:</span><span class="sxs-lookup"><span data-stu-id="0e049-164">Requiring a role:</span></span>

```csharp
@attribute [Authorize(Roles ="administrators")]
```

<span data-ttu-id="0e049-165">Se debe satisfacer la necesidad de una directiva:</span><span class="sxs-lookup"><span data-stu-id="0e049-165">Requiring a policy be satisfied:</span></span>

```csharp
@attribute [Authorize(Policy ="CanadiansOnly")]
```

<span data-ttu-id="0e049-166">Si necesita tener acceso al estado de autenticación de un usuario, a los roles o a las notificaciones en el código, hay dos formas principales de lograrlo.</span><span class="sxs-lookup"><span data-stu-id="0e049-166">If you need access to a user's authentication state, roles, or claims in your code, there are two primary ways to achieve this.</span></span> <span data-ttu-id="0e049-167">La primera es recibir el estado de autenticación como parámetro en cascada.</span><span class="sxs-lookup"><span data-stu-id="0e049-167">The first is to receive the authentication state as a cascading parameter.</span></span> <span data-ttu-id="0e049-168">La segunda es para tener acceso al estado mediante un insertado `AuthenticationStateProvider` .</span><span class="sxs-lookup"><span data-stu-id="0e049-168">The second is to access the state using an injected `AuthenticationStateProvider`.</span></span> <span data-ttu-id="0e049-169">Los detalles de cada uno de estos enfoques se describen en la [ Blazor documentación de seguridad](/aspnet/core/blazor/security/).</span><span class="sxs-lookup"><span data-stu-id="0e049-169">The details of each of these approaches are described in the [Blazor Security documentation](/aspnet/core/blazor/security/).</span></span>

<span data-ttu-id="0e049-170">En el código siguiente se muestra cómo recibir `AuthenticationState` como parámetro en cascada:</span><span class="sxs-lookup"><span data-stu-id="0e049-170">The following code shows how to receive the `AuthenticationState` as a cascading parameter:</span></span>

```csharp
[CascadingParameter]
private Task<AuthenticationState> authenticationStateTask { get; set; }
```

<span data-ttu-id="0e049-171">Con este parámetro en su lugar, puede obtener el usuario mediante este código:</span><span class="sxs-lookup"><span data-stu-id="0e049-171">With this parameter in place, you can get the user using this code:</span></span>

```csharp
var authState = await authenticationStateTask;
var user = authState.User;
```

<span data-ttu-id="0e049-172">En el código siguiente se muestra cómo insertar `AuthenticationStateProvider` :</span><span class="sxs-lookup"><span data-stu-id="0e049-172">The following code shows how to inject the `AuthenticationStateProvider`:</span></span>

```csharp
@using Microsoft.AspNetCore.Components.Authorization
@inject AuthenticationStateProvider AuthenticationStateProvider
```

<span data-ttu-id="0e049-173">Con el proveedor en su lugar, puede obtener acceso al usuario con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0e049-173">With the provider in place, you can gain access to the user with the following code:</span></span>

```csharp
AuthenticationState authState = await AuthenticationStateProvider.GetAuthenticationStateAsync();
ClaimsPrincipal user = authState.User;

if (user.Identity.IsAuthenticated)
{
  // work with user.Claims and/or user.Roles
}
```

<span data-ttu-id="0e049-174">**Nota:** El `AuthorizeView` componente, que se trata más adelante en este capítulo, proporciona una manera declarativa de controlar lo que un usuario ve en una página o componente.</span><span class="sxs-lookup"><span data-stu-id="0e049-174">**Note:** The `AuthorizeView` component, covered later in this chapter, provides a declarative way to control what a user sees on a page or component.</span></span>

<span data-ttu-id="0e049-175">Para trabajar con usuarios y notificaciones (en Blazor aplicaciones de servidor), es posible que también tenga que insertar un `UserManager<T>` (usar `IdentityUser` de forma predeterminada), que puede usar para enumerar y modificar las notificaciones de un usuario.</span><span class="sxs-lookup"><span data-stu-id="0e049-175">To work with users and claims (in Blazor Server applications) you may also need to inject a `UserManager<T>` (use `IdentityUser` for default) which you can use to enumerate and modify claims for a user.</span></span> <span data-ttu-id="0e049-176">En primer lugar, inserte el tipo y asígnelo a una propiedad:</span><span class="sxs-lookup"><span data-stu-id="0e049-176">First inject the type and assign it to a property:</span></span>

```csharp
@inject UserManager<IdentityUser> MyUserManager
```

<span data-ttu-id="0e049-177">A continuación, úselo para trabajar con las notificaciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="0e049-177">Then use it to work with the user's claims.</span></span> <span data-ttu-id="0e049-178">En el ejemplo siguiente se muestra cómo agregar y conservar una demanda para un usuario:</span><span class="sxs-lookup"><span data-stu-id="0e049-178">The following sample shows how to add and persist a claim on a user:</span></span>

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

<span data-ttu-id="0e049-179">Si necesita trabajar con roles, siga el mismo enfoque.</span><span class="sxs-lookup"><span data-stu-id="0e049-179">If you need to work with roles, follow the same approach.</span></span> <span data-ttu-id="0e049-180">Es posible que tenga que insertar un `RoleManager<T>` (se usa `IdentityRole` para el tipo predeterminado) para enumerar y administrar los roles.</span><span class="sxs-lookup"><span data-stu-id="0e049-180">You may need to inject a `RoleManager<T>` (use `IdentityRole` for default type) to list and manage the roles themselves.</span></span>

<span data-ttu-id="0e049-181">**Nota:** En Blazor los proyectos de Webassembly, tendrá que proporcionar las API de servidor para realizar estas operaciones (en lugar de usar `UserManager<T>` o `RoleManager<T>` directamente).</span><span class="sxs-lookup"><span data-stu-id="0e049-181">**Note:** In Blazor WebAssembly projects, you will need to provide server APIs to perform these operations (instead of using `UserManager<T>` or `RoleManager<T>` directly).</span></span> <span data-ttu-id="0e049-182">Una Blazor aplicación cliente de Webassembly administraría las notificaciones y/o los roles mediante la llamada segura de puntos de conexión de API expuestos para este fin.</span><span class="sxs-lookup"><span data-stu-id="0e049-182">A Blazor WebAssembly client application would manage claims and/or roles by securely calling API endpoints exposed for this purpose.</span></span>

### <a name="migration-guide"></a><span data-ttu-id="0e049-183">Guía de migración</span><span class="sxs-lookup"><span data-stu-id="0e049-183">Migration guide</span></span>

<span data-ttu-id="0e049-184">La migración de los formularios Web Forms de ASP.NET y los proveedores universales a la identidad de ASP.NET Core requiere varios pasos:</span><span class="sxs-lookup"><span data-stu-id="0e049-184">Migrating from ASP.NET Web Forms and universal providers to ASP.NET Core Identity requires several steps:</span></span>

1. <span data-ttu-id="0e049-185">Crear ASP.NET Core esquema de base de datos de identidad en la base de datos de destino</span><span class="sxs-lookup"><span data-stu-id="0e049-185">Create ASP.NET Core Identity database schema in destination database</span></span>
2. <span data-ttu-id="0e049-186">Migrar datos del esquema del proveedor universal a ASP.NET Core esquema de identidad</span><span class="sxs-lookup"><span data-stu-id="0e049-186">Migrate data from universal provider schema to ASP.NET Core Identity schema</span></span>
3. <span data-ttu-id="0e049-187">Migre la configuración de web.config a middleware y servicios, normalmente en `Startup.cs`</span><span class="sxs-lookup"><span data-stu-id="0e049-187">Migrate configuration from web.config to middleware and services, typically in `Startup.cs`</span></span>
4. <span data-ttu-id="0e049-188">Actualice páginas individuales mediante controles y condicionales para usar aplicaciones auxiliares de etiquetas y nuevas API de identidad.</span><span class="sxs-lookup"><span data-stu-id="0e049-188">Update individual pages using controls and conditionals to use tag helpers and new identity APIs.</span></span>

<span data-ttu-id="0e049-189">En las siguientes secciones se describen estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0e049-189">Each of these steps is described in detail in the following sections.</span></span>

### <a name="creating-the-aspnet-core-identity-schema"></a><span data-ttu-id="0e049-190">Crear el esquema de identidad de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0e049-190">Creating the ASP.NET Core Identity schema</span></span>

<span data-ttu-id="0e049-191">Hay varias maneras de crear la estructura de tabla necesaria utilizada para ASP.NET Core identidad.</span><span class="sxs-lookup"><span data-stu-id="0e049-191">There are several ways to create the necessary table structure used for ASP.NET Core Identity.</span></span> <span data-ttu-id="0e049-192">La más sencilla consiste en crear una nueva aplicación Web de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="0e049-192">The simplest is to create a new ASP.NET Core Web application.</span></span> <span data-ttu-id="0e049-193">Elija aplicación web y, a continuación, cambie autenticación para usar cuentas de usuario individuales.</span><span class="sxs-lookup"><span data-stu-id="0e049-193">Choose Web Application and then change Authentication to use Individual User Accounts.</span></span>

![nuevo proyecto con cuentas de usuario individuales](./media/security/individual-user-accounts.png)

<span data-ttu-id="0e049-195">Desde la línea de comandos, puede hacer lo mismo ejecutando `dotnet new webapp -au Individual` .</span><span class="sxs-lookup"><span data-stu-id="0e049-195">From the command line, you can do the same thing by running `dotnet new webapp -au Individual`.</span></span> <span data-ttu-id="0e049-196">Una vez creada la aplicación, ejecútela y regístrese en el sitio.</span><span class="sxs-lookup"><span data-stu-id="0e049-196">Once the app has been created, run it and register on the site.</span></span> <span data-ttu-id="0e049-197">Debe desencadenar una página como la que se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="0e049-197">You should trigger a page like the one shown below:</span></span>

![Página aplicar migraciones](./media/security/apply-migrations-page.png)

<span data-ttu-id="0e049-199">Haga clic en el botón "aplicar migraciones" para crear las tablas de base de datos necesarias.</span><span class="sxs-lookup"><span data-stu-id="0e049-199">Click on the "Apply Migrations" button and the necessary database tables should be created for you.</span></span> <span data-ttu-id="0e049-200">Además, los archivos de migración deben aparecer en el proyecto, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="0e049-200">In addition, the migration files should appear in your project, as shown:</span></span>

![archivos de migración](./media/security/migration-files.png)

<span data-ttu-id="0e049-202">Puede ejecutar la migración usted mismo, sin ejecutar la aplicación Web, mediante esta herramienta de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="0e049-202">You can run the migration yourself, without running the web application, using this command line tool:</span></span>

```powershell
dotnet ef database update
```

<span data-ttu-id="0e049-203">Si prefiere ejecutar un script para aplicar el nuevo esquema a una base de datos existente, puede crear un script de estas migraciones desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0e049-203">If you would rather run a script to apply the new schema to an existing database, you can script these migrations from the command line.</span></span> <span data-ttu-id="0e049-204">Ejecute este comando para generar el script:</span><span class="sxs-lookup"><span data-stu-id="0e049-204">Run this command to generate the script:</span></span>

```powershell
dotnet ef migrations script -o auth.sql
```

<span data-ttu-id="0e049-205">Esto producirá un script SQL en el archivo de salida `auth.sql` que se puede ejecutar en cualquier base de datos que desee.</span><span class="sxs-lookup"><span data-stu-id="0e049-205">This will produce a SQL script in the output file `auth.sql` which can then be run against whatever database you like.</span></span> <span data-ttu-id="0e049-206">Si tiene algún problema al ejecutar los `dotnet ef` comandos, asegúrese [de que tiene las herramientas de EF Core instaladas en el sistema](/ef/core/miscellaneous/cli/dotnet).</span><span class="sxs-lookup"><span data-stu-id="0e049-206">If you have any trouble running `dotnet ef` commands, [make sure you have the EF Core tools installed on your system](/ef/core/miscellaneous/cli/dotnet).</span></span>

<span data-ttu-id="0e049-207">En el caso de que tenga columnas adicionales en las tablas de origen, tendrá que identificar la mejor ubicación para estas columnas en el nuevo esquema.</span><span class="sxs-lookup"><span data-stu-id="0e049-207">In the event you have additional columns on your source tables, you will need to identify the best location for these columns in the new schema.</span></span> <span data-ttu-id="0e049-208">Por lo general, las columnas que se encuentran en la `aspnet_Membership` tabla se deben asignar a la `AspNetUsers` tabla.</span><span class="sxs-lookup"><span data-stu-id="0e049-208">Generally, columns found on the `aspnet_Membership` table should be mapped to the `AspNetUsers` table.</span></span> <span data-ttu-id="0e049-209">Las columnas de `aspnet_Roles` deben estar asignadas a `AspNetRoles` .</span><span class="sxs-lookup"><span data-stu-id="0e049-209">Columns on `aspnet_Roles` should be mapped to `AspNetRoles`.</span></span> <span data-ttu-id="0e049-210">Cualquier columna adicional de la `aspnet_UsersInRoles` tabla se agregaría a la `AspNetUserRoles` tabla.</span><span class="sxs-lookup"><span data-stu-id="0e049-210">Any additional columns on the `aspnet_UsersInRoles` table would be added to the `AspNetUserRoles` table.</span></span>

<span data-ttu-id="0e049-211">También merece la pena considerar colocar cualquier columna adicional en tablas independientes, de modo que las migraciones futuras no tengan que tener en cuenta tales personalizaciones del esquema de identidad predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0e049-211">It's also worth considering putting any additional columns on separate tables, so that future migrations won't need to take into account such customizations of the default identity schema.</span></span>

### <a name="migrating-data-from-universal-providers-to-aspnet-core-identity"></a><span data-ttu-id="0e049-212">Migrar datos de proveedores universales a ASP.NET Core identidad</span><span class="sxs-lookup"><span data-stu-id="0e049-212">Migrating data from universal providers to ASP.NET Core Identity</span></span>

<span data-ttu-id="0e049-213">Una vez que tenga el esquema de la tabla de destino, el siguiente paso consiste en migrar los registros de usuario y de rol al nuevo esquema.</span><span class="sxs-lookup"><span data-stu-id="0e049-213">Once you have the destination table schema in place, the next step is to migrate your user and role records to the new schema.</span></span> <span data-ttu-id="0e049-214">Una lista completa de las diferencias de esquema, incluidas las columnas que se asignan a las columnas nuevas, se pueden encontrar [aquí](/aspnet/core/migration/proper-to-2x/membership-to-core-identity).</span><span class="sxs-lookup"><span data-stu-id="0e049-214">A complete list of the schema differences, including which columns map to which new columns, can be found [here](/aspnet/core/migration/proper-to-2x/membership-to-core-identity).</span></span>

<span data-ttu-id="0e049-215">Para migrar los usuarios de la pertenencia a las nuevas tablas de identidad, debe [seguir los pasos descritos en la documentación](/aspnet/core/migration/proper-to-2x/membership-to-core-identity)de.</span><span class="sxs-lookup"><span data-stu-id="0e049-215">To migrate your users from membership to the new identity tables, you should [follow the steps described in the documentation](/aspnet/core/migration/proper-to-2x/membership-to-core-identity).</span></span> <span data-ttu-id="0e049-216">Después de seguir estos pasos y el script proporcionado, los usuarios deberán cambiar su contraseña la próxima vez que inicien sesión.</span><span class="sxs-lookup"><span data-stu-id="0e049-216">After following these steps and the script provided, your users will need to change their password the next time they log in.</span></span>

<span data-ttu-id="0e049-217">Es posible migrar las contraseñas de usuario, pero el proceso es mucho más complicado.</span><span class="sxs-lookup"><span data-stu-id="0e049-217">It is possible to migrate user passwords but the process is much more involved.</span></span> <span data-ttu-id="0e049-218">Requerir a los usuarios que actualicen sus contraseñas como parte del proceso de migración y animarles a usar contraseñas nuevas y únicas, es probable que mejore la seguridad global de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0e049-218">Requiring users to update their passwords as part of the migration process, and encouraging them to use new, unique passwords, is likely to enhance the overall security of the application.</span></span>

### <a name="migrating-security-settings-from-webconfig-to-startupcs"></a><span data-ttu-id="0e049-219">Migrar la configuración de seguridad de web.config a Startup.cs</span><span class="sxs-lookup"><span data-stu-id="0e049-219">Migrating security settings from web.config to Startup.cs</span></span>

<span data-ttu-id="0e049-220">Como se indicó anteriormente, los proveedores de roles y la pertenencia a ASP.NET se configuran en el archivo de web.config de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0e049-220">As noted above, ASP.NET membership and role providers are configured in the application's web.config file.</span></span> <span data-ttu-id="0e049-221">Como ASP.NET Core aplicaciones no están asociadas a IIS y usan un sistema independiente para la configuración, esta configuración se debe configurar en otra parte.</span><span class="sxs-lookup"><span data-stu-id="0e049-221">Since ASP.NET Core apps are not tied to IIS and use a separate system for configuration, these settings must be configured elsewhere.</span></span> <span data-ttu-id="0e049-222">En su mayor parte, ASP.NET Core identidad se configura en el `Startup.cs` archivo.</span><span class="sxs-lookup"><span data-stu-id="0e049-222">For the most part, ASP.NET Core Identity is configured in the `Startup.cs` file.</span></span> <span data-ttu-id="0e049-223">Abra el proyecto web que se creó anteriormente (para generar el esquema de la tabla de identidad) y revise el `Startup.cs` archivo.</span><span class="sxs-lookup"><span data-stu-id="0e049-223">Open the web project that was created earlier (to generate the identity table schema) and review its `Startup.cs` file.</span></span>

<span data-ttu-id="0e049-224">El método ConfigureServices predeterminado agrega compatibilidad con EF Core e identidad:</span><span class="sxs-lookup"><span data-stu-id="0e049-224">The default ConfigureServices method adds support for EF Core and Identity:</span></span>

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

<span data-ttu-id="0e049-225">El `AddDefaultIdentity` método de extensión se usa para configurar la identidad con el fin de usar el `ApplicationDbContext` tipo predeterminado y el tipo de marco `IdentityUser` .</span><span class="sxs-lookup"><span data-stu-id="0e049-225">The `AddDefaultIdentity` extension method is used to configure Identity to use the default `ApplicationDbContext` and the framework's `IdentityUser` type.</span></span> <span data-ttu-id="0e049-226">Si utiliza un personalizado `IdentityUser` , asegúrese de especificar aquí su tipo.</span><span class="sxs-lookup"><span data-stu-id="0e049-226">If you're using a custom `IdentityUser`, be sure to specify its type here.</span></span> <span data-ttu-id="0e049-227">Si estos métodos de extensión no funcionan en la aplicación, compruebe que tiene las instrucciones Using adecuadas y que tiene las referencias de paquete NuGet necesarias.</span><span class="sxs-lookup"><span data-stu-id="0e049-227">If these extension methods aren't working in your application, check that you have the appropriate using statements and that you have the necessary NuGet package references.</span></span> <span data-ttu-id="0e049-228">Por ejemplo, el proyecto debe tener alguna versión de los `Microsoft.AspNetCore.Identity.EntityFrameworkCore` paquetes y a los `Microsoft.AspNetCore.Identity.UI` que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="0e049-228">For example, your project should have some version of the `Microsoft.AspNetCore.Identity.EntityFrameworkCore` and `Microsoft.AspNetCore.Identity.UI` packages referenced.</span></span>

<span data-ttu-id="0e049-229">También en `Startup.cs` , debería ver el middleware necesario configurado para el sitio.</span><span class="sxs-lookup"><span data-stu-id="0e049-229">Also in `Startup.cs` you should see the necessary middleware configured for the site.</span></span> <span data-ttu-id="0e049-230">Concretamente, `UseAuthentication` y `UseAuthorization` deben configurarse, y en la ubicación adecuada.</span><span class="sxs-lookup"><span data-stu-id="0e049-230">Specifically, `UseAuthentication` and `UseAuthorization` should be set up, and in the proper location.</span></span>

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

<span data-ttu-id="0e049-231">ASP.NET Identity no configura el acceso anónimo o basado en roles a ubicaciones desde `Startup.cs` .</span><span class="sxs-lookup"><span data-stu-id="0e049-231">ASP.NET Identity does not configure anonymous or role-based access to locations from `Startup.cs`.</span></span> <span data-ttu-id="0e049-232">Tendrá que migrar los datos de configuración de autorización específicos de la ubicación a los filtros de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="0e049-232">You will need to migrate any location-specific authorization configuration data to filters in ASP.NET Core.</span></span> <span data-ttu-id="0e049-233">Tome nota de las carpetas y páginas que requerirán estas actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="0e049-233">Make note of which folders and pages will require such updates.</span></span> <span data-ttu-id="0e049-234">Realizará estos cambios en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="0e049-234">You will make these changes in the next section.</span></span>

### <a name="updating-individual-pages-to-use-aspnet-core-identity-abstractions"></a><span data-ttu-id="0e049-235">Actualizar páginas individuales para usar ASP.NET Core abstracciones de identidad</span><span class="sxs-lookup"><span data-stu-id="0e049-235">Updating individual pages to use ASP.NET Core Identity abstractions</span></span>

<span data-ttu-id="0e049-236">En la aplicación de formularios Web Forms de ASP.NET, si tiene web.config configuración para denegar el acceso a determinadas páginas o carpetas a usuarios anónimos, debe migrarlos simplemente agregando el `[Authorize]` atributo a estas páginas:</span><span class="sxs-lookup"><span data-stu-id="0e049-236">In your ASP.NET Web Forms application, if you had web.config settings to deny access to certain pages or folders to anonymous users, you would migrate these by simply adding the `[Authorize]` attribute to such pages:</span></span>

```razor
@attribute [Authorize]
```

<span data-ttu-id="0e049-237">Si aún no ha denegado el acceso excepto los usuarios que pertenecen a un rol determinado, migraría igualmente esto agregando un atributo que especifica un rol:</span><span class="sxs-lookup"><span data-stu-id="0e049-237">If you further had denied access except to those users belonging to a certain role, you would likewise migrate this by adding an attribute specifying a role:</span></span>

```razor
@attribute [Authorize(Roles ="administrators")]
```

<span data-ttu-id="0e049-238">Tenga en cuenta que el `[Authorize]` atributo solo funciona en `@page` los componentes que se alcanzan a través del Blazor enrutador.</span><span class="sxs-lookup"><span data-stu-id="0e049-238">Note that the `[Authorize]` attribute only works on `@page` components that are reached via the Blazor Router.</span></span> <span data-ttu-id="0e049-239">El atributo no funciona con componentes secundarios, que deben usarse en su lugar `AuthorizeView` .</span><span class="sxs-lookup"><span data-stu-id="0e049-239">The attribute does not work with child components, which should instead use `AuthorizeView`.</span></span>

<span data-ttu-id="0e049-240">Si tiene lógica en el marcado de página para determinar si se va a Mostrar código a un determinado usuario, puede reemplazarlo por el `AuthorizeView` componente.</span><span class="sxs-lookup"><span data-stu-id="0e049-240">If you have logic within page markup for determining whether to display some code to a certain user, you can replace this with the `AuthorizeView` component.</span></span> <span data-ttu-id="0e049-241">El [componente AuthorizeView](/aspnet/core/blazor/security#authorizeview-component) muestra la interfaz de usuario de forma selectiva en función de si el usuario está autorizado para verlo.</span><span class="sxs-lookup"><span data-stu-id="0e049-241">The [AuthorizeView component](/aspnet/core/blazor/security#authorizeview-component) selectively displays UI depending on whether the user is authorized to see it.</span></span> <span data-ttu-id="0e049-242">También expone una `context` variable que se puede utilizar para tener acceso a la información del usuario.</span><span class="sxs-lookup"><span data-stu-id="0e049-242">It also exposes a `context` variable that can be used to access user information.</span></span>

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

<span data-ttu-id="0e049-243">Puede tener acceso al estado de autenticación dentro de la lógica de procedimientos accediendo al usuario desde un `Task<AuthenticationState` configurado con el `[CascadingParameter]` atributo.</span><span class="sxs-lookup"><span data-stu-id="0e049-243">You can access authentication state within procedural logic by accessing the user from a `Task<AuthenticationState` configured with the `[CascadingParameter]` attribute.</span></span> <span data-ttu-id="0e049-244">Esto le permitirá obtener acceso al usuario, lo que le permitirá determinar si se autentican y si pertenecen a un rol determinado.</span><span class="sxs-lookup"><span data-stu-id="0e049-244">This will get you access to the user, which can let you determine if they are authenticated and if they belong to a particular role.</span></span> <span data-ttu-id="0e049-245">Si necesita evaluar una directiva con procedimientos, puede insertar una instancia de `IAuthorizationService` y llamar al `AuthorizeAsync` método en ella.</span><span class="sxs-lookup"><span data-stu-id="0e049-245">If you need to evaluate a policy procedurally, you can inject an instance of the `IAuthorizationService` and calls the `AuthorizeAsync` method on it.</span></span> <span data-ttu-id="0e049-246">En el código de ejemplo siguiente se muestra cómo obtener información del usuario y permitir que un usuario autorizado realice una tarea restringida por la `content-editor` Directiva.</span><span class="sxs-lookup"><span data-stu-id="0e049-246">The following sample code demonstrates how to get user information and allow an authorized user to perform a task restricted by the `content-editor` policy.</span></span>

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

<span data-ttu-id="0e049-247">`AuthenticationState`Primero se debe configurar como valor en cascada antes de que se pueda enlazar a un parámetro en cascada como este.</span><span class="sxs-lookup"><span data-stu-id="0e049-247">The `AuthenticationState` does first need to be setup as a cascading value before it can be bound to a cascading parameter like this.</span></span> <span data-ttu-id="0e049-248">Esto se suele hacer mediante el `CascadingAuthenticationState` componente.</span><span class="sxs-lookup"><span data-stu-id="0e049-248">That's typically done using the `CascadingAuthenticationState` component.</span></span> <span data-ttu-id="0e049-249">Esto se hace normalmente en `App.razor` :</span><span class="sxs-lookup"><span data-stu-id="0e049-249">This is typically done in `App.razor`:</span></span>

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

## <a name="summary"></a><span data-ttu-id="0e049-250">Resumen</span><span class="sxs-lookup"><span data-stu-id="0e049-250">Summary</span></span>

<span data-ttu-id="0e049-251">Blazor usa el mismo modelo de seguridad que ASP.NET Core, que es ASP.NET Core identidad.</span><span class="sxs-lookup"><span data-stu-id="0e049-251">Blazor uses the same security model as ASP.NET Core, which is ASP.NET Core Identity.</span></span> <span data-ttu-id="0e049-252">La migración de proveedores universales a ASP.NET Core identidad es relativamente sencilla, suponiendo que no se aplicó demasiada personalización al esquema de datos original.</span><span class="sxs-lookup"><span data-stu-id="0e049-252">Migrating from universal providers to ASP.NET Core Identity is relatively straightforward, assuming not too much customization was applied to the original data schema.</span></span> <span data-ttu-id="0e049-253">Una vez que se han migrado los datos, el trabajo con la autenticación y la autorización en las Blazor aplicaciones está bien documentado, con la compatibilidad configurable y con la mayoría de los requisitos de seguridad mediante programación.</span><span class="sxs-lookup"><span data-stu-id="0e049-253">Once the data has been migrated, working with authentication and authorization in Blazor apps is well-documented, with configurable as well as programmatic support for most security requirements.</span></span>

## <a name="references"></a><span data-ttu-id="0e049-254">Referencias</span><span class="sxs-lookup"><span data-stu-id="0e049-254">References</span></span>

- [<span data-ttu-id="0e049-255">Introducción a la identidad en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0e049-255">Introduction to Identity on ASP.NET Core</span></span>](/aspnet/core/security/authentication/identity)
- [<span data-ttu-id="0e049-256">Migración de la autenticación de pertenencia de ASP.NET a ASP.NET Core identidad 2,0</span><span class="sxs-lookup"><span data-stu-id="0e049-256">Migrate from ASP.NET Membership authentication to ASP.NET Core 2.0 Identity</span></span>](/aspnet/core/migration/proper-to-2x/membership-to-core-identity)
- [<span data-ttu-id="0e049-257">Migración de la autenticación y la identidad a ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0e049-257">Migrate Authentication and Identity to ASP.NET Core</span></span>](/aspnet/core/migration/identity)
- [<span data-ttu-id="0e049-258">BlazorAutenticación y autorización de ASP.net Core</span><span class="sxs-lookup"><span data-stu-id="0e049-258">ASP.NET Core Blazor authentication and authorization</span></span>](/aspnet/core/blazor/security/)

>[!div class="step-by-step"]
><span data-ttu-id="0e049-259">[Anterior](config.md)
>[Siguiente](migration.md)</span><span class="sxs-lookup"><span data-stu-id="0e049-259">[Previous](config.md)
[Next](migration.md)</span></span>
