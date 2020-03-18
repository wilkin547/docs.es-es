---
title: Acerca de la autorización en microservicios y aplicaciones web de .NET
description: 'Seguridad en microservicios y aplicaciones web de .NET: obtenga información general de las opciones de autorización principales en las aplicaciones de ASP.NET Core: basadas en roles y basadas en directivas.'
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: f6b69faceac9a9b4819212cc04f89080f3ddad56
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77501765"
---
# <a name="about-authorization-in-net-microservices-and-web-applications"></a><span data-ttu-id="1b2f2-103">Acerca de la autorización en microservicios y aplicaciones web de .NET</span><span class="sxs-lookup"><span data-stu-id="1b2f2-103">About authorization in .NET microservices and web applications</span></span>

<span data-ttu-id="1b2f2-104">Después de la autenticación, las API web de ASP.NET Core deben autorizar el acceso.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-104">After authentication, ASP.NET Core Web APIs need to authorize access.</span></span> <span data-ttu-id="1b2f2-105">Este proceso permite que un servicio haga que las API estén disponibles para algunos usuarios autenticados, pero no para todos.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-105">This process allows a service to make APIs available to some authenticated users, but not to all.</span></span> <span data-ttu-id="1b2f2-106">La [autorización](/aspnet/core/security/authorization/introduction) se puede llevar a cabo según los roles de los usuarios o según una directiva personalizada, que podría incluir la inspección de notificaciones u otro tipo de heurística.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-106">[Authorization](/aspnet/core/security/authorization/introduction) can be done based on users’ roles or based on custom policy, which might include inspecting claims or other heuristics.</span></span>

<span data-ttu-id="1b2f2-107">Restringir el acceso a una ruta de ASP.NET Core MVC es tan fácil como aplicar un atributo Authorize al método de acción (o a la clase de controlador si todas las acciones del controlador requieren autorización), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1b2f2-107">Restricting access to an ASP.NET Core MVC route is as easy as applying an Authorize attribute to the action method (or to the controller’s class if all the controller’s actions require authorization), as shown in following example:</span></span>

```csharp
public class AccountController : Controller
{
    public ActionResult Login()
    {
    }

    [Authorize]
    public ActionResult Logout()
    {
    }
}
```

<span data-ttu-id="1b2f2-108">De forma predeterminada, agregar un atributo Authorize sin parámetros limitará el acceso a los usuarios autenticados para ese controlador o esa acción.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-108">By default, adding an Authorize attribute without parameters will limit access to authenticated users for that controller or action.</span></span> <span data-ttu-id="1b2f2-109">Para restringir aún más una API para que esté disponible solo para usuarios específicos, el atributo se puede expandir para especificar los roles o las directivas necesarios que los usuarios deben cumplir.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-109">To further restrict an API to be available for only specific users, the attribute can be expanded to specify required roles or policies that users must satisfy.</span></span>

## <a name="implement-role-based-authorization"></a><span data-ttu-id="1b2f2-110">Implementar la autorización basada en roles</span><span class="sxs-lookup"><span data-stu-id="1b2f2-110">Implement role-based authorization</span></span>

<span data-ttu-id="1b2f2-111">ASP.NET Core Identity tiene un concepto de roles integrado.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-111">ASP.NET Core Identity has a built-in concept of roles.</span></span> <span data-ttu-id="1b2f2-112">Además de los usuarios, ASP.NET Core Identity almacena información sobre los distintos roles que la aplicación usa y realiza un seguimiento de los usuarios que están asignados a cada rol.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-112">In addition to users, ASP.NET Core Identity stores information about different roles used by the application and keeps track of which users are assigned to which roles.</span></span> <span data-ttu-id="1b2f2-113">Estas asignaciones se pueden cambiar mediante programación con el tipo `RoleManager` que actualiza roles en almacenamiento persistente y el tipo `UserManager` que puede conceder o revocar roles de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-113">These assignments can be changed programmatically with the `RoleManager` type that updates roles in persisted storage, and the `UserManager` type that can grant or revoke roles from users.</span></span>

<span data-ttu-id="1b2f2-114">Si está realizando la autenticación con tokens de portador JWT, el middleware de autenticación de portador JWT de ASP.NET Core rellenará los roles de un usuario según las notificaciones de rol que se encuentren en el token.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-114">If you're authenticating with JWT bearer tokens, the ASP.NET Core JWT bearer authentication middleware will populate a user’s roles based on role claims found in the token.</span></span> <span data-ttu-id="1b2f2-115">Para limitar el acceso a una acción o un controlador de MVC a usuarios con roles específicos, puede incluir un parámetro Roles en la anotación Authorize (atributo), tal como se muestra en el fragmento de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="1b2f2-115">To limit access to an MVC action or controller to users in specific roles, you can include a Roles parameter in the Authorize annotation (attribute), as shown in the following code fragment:</span></span>

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
public class ControlPanelController : Controller
{
    public ActionResult SetTime()
    {
    }

    [Authorize(Roles = "Administrator")]
    public ActionResult ShutDown()
    {
    }
}
```

<span data-ttu-id="1b2f2-116">En este ejemplo, solo los usuarios de los roles Administrator o PowerUser pueden tener acceso a las API del controlador ControlPanel (por ejemplo, para ejecutar la acción SetTime).</span><span class="sxs-lookup"><span data-stu-id="1b2f2-116">In this example, only users in the Administrator or PowerUser roles can access APIs in the ControlPanel controller (such as executing the SetTime action).</span></span> <span data-ttu-id="1b2f2-117">La API ShutDown se restringe aún más para permitir el acceso únicamente a los usuarios con el rol Administrator.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-117">The ShutDown API is further restricted to allow access only to users in the Administrator role.</span></span>

<span data-ttu-id="1b2f2-118">Para pedir a un usuario que tenga varios roles, se usan varios atributos Authorize, como se muestra en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1b2f2-118">To require a user be in multiple roles, you use multiple Authorize attributes, as shown in the following example:</span></span>

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

<span data-ttu-id="1b2f2-119">En este ejemplo, para llamar a API1, un usuario debe:</span><span class="sxs-lookup"><span data-stu-id="1b2f2-119">In this example, to call API1, a user must:</span></span>

- <span data-ttu-id="1b2f2-120">Tener el rol Administrator *o* PowerUser *y*</span><span class="sxs-lookup"><span data-stu-id="1b2f2-120">Be in the Administrator *or* PowerUser role, *and*</span></span>

- <span data-ttu-id="1b2f2-121">Tener el rol RemoteEmployee *y*</span><span class="sxs-lookup"><span data-stu-id="1b2f2-121">Be in the RemoteEmployee role, *and*</span></span>

- <span data-ttu-id="1b2f2-122">Satisfacer a un controlador personalizado para la autorización de CustomPolicy.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-122">Satisfy a custom handler for CustomPolicy authorization.</span></span>

## <a name="implement-policy-based-authorization"></a><span data-ttu-id="1b2f2-123">Implementación de la autorización basada en directivas</span><span class="sxs-lookup"><span data-stu-id="1b2f2-123">Implement policy-based authorization</span></span>

<span data-ttu-id="1b2f2-124">También se pueden escribir reglas de autorización personalizada con [directivas de autorización](https://docs.asp.net/en/latest/security/authorization/policies.html).</span><span class="sxs-lookup"><span data-stu-id="1b2f2-124">Custom authorization rules can also be written using [authorization policies](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span> <span data-ttu-id="1b2f2-125">En esta sección se proporciona información general.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-125">This section provides an overview.</span></span> <span data-ttu-id="1b2f2-126">Para más información, consulte [ASP.NET Authorization Workshop](https://github.com/blowdart/AspNetAuthorizationWorkshop) (Taller de autorización de ASP.NET).</span><span class="sxs-lookup"><span data-stu-id="1b2f2-126">For more information, see the [ASP.NET Authorization Workshop](https://github.com/blowdart/AspNetAuthorizationWorkshop).</span></span>

<span data-ttu-id="1b2f2-127">Las directivas de autorización personalizadas se registran en el método Startup.ConfigureServices mediante el método service.AddAuthorization.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-127">Custom authorization policies are registered in the Startup.ConfigureServices method using the service.AddAuthorization method.</span></span> <span data-ttu-id="1b2f2-128">Este método toma a un delegado que configura un argumento AuthorizationOptions.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-128">This method takes a delegate that configures an AuthorizationOptions argument.</span></span>

```csharp
services.AddAuthorization(options =>
{
    options.AddPolicy("AdministratorsOnly", policy =>
        policy.RequireRole("Administrator"));

    options.AddPolicy("EmployeesOnly", policy =>
        policy.RequireClaim("EmployeeNumber"));

    options.AddPolicy("Over21", policy =>
        policy.Requirements.Add(new MinimumAgeRequirement(21)));
});
```

<span data-ttu-id="1b2f2-129">Como se muestra en el ejemplo, las directivas pueden asociarse con distintos tipos de requisitos.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-129">As shown in the example, policies can be associated with different types of requirements.</span></span> <span data-ttu-id="1b2f2-130">Una vez registradas las directivas, se pueden aplicar a una acción o a un controlador pasando el nombre de la directiva como el argumento de la directiva del atributo Authorize (por ejemplo, `[Authorize(Policy="EmployeesOnly")]`). Las directivas pueden tener varios requisitos, no solo uno (como se muestra en estos ejemplos).</span><span class="sxs-lookup"><span data-stu-id="1b2f2-130">After the policies are registered, they can be applied to an action or controller by passing the policy’s name as the Policy argument of the Authorize attribute (for example, `[Authorize(Policy="EmployeesOnly")]`) Policies can have multiple requirements, not just one (as shown in these examples).</span></span>

<span data-ttu-id="1b2f2-131">En el ejemplo anterior, la primera llamada AddPolicy es simplemente una manera alternativa de autorizar por rol.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-131">In the previous example, the first AddPolicy call is just an alternative way of authorizing by role.</span></span> <span data-ttu-id="1b2f2-132">Si `[Authorize(Policy="AdministratorsOnly")]` se aplica a una API, solo los usuarios del rol Administrator podrán tener acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-132">If `[Authorize(Policy="AdministratorsOnly")]` is applied to an API, only users in the Administrator role will be able to access it.</span></span>

<span data-ttu-id="1b2f2-133">La segunda llamada <xref:Microsoft.AspNetCore.Authorization.AuthorizationOptions.AddPolicy%2A> muestra una manera sencilla de pedir que una notificación concreta esté presente para el usuario.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-133">The second <xref:Microsoft.AspNetCore.Authorization.AuthorizationOptions.AddPolicy%2A> call demonstrates an easy way to require that a particular claim should be present for the user.</span></span> <span data-ttu-id="1b2f2-134">El método <xref:Microsoft.AspNetCore.Authorization.AuthorizationPolicyBuilder.RequireClaim%2A> también toma opcionalmente valores esperados para la notificación.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-134">The <xref:Microsoft.AspNetCore.Authorization.AuthorizationPolicyBuilder.RequireClaim%2A> method also optionally takes expected values for the claim.</span></span> <span data-ttu-id="1b2f2-135">Si se especifican valores, el requisito se cumple solo si el usuario tiene tanto una notificación del tipo correcto como uno de los valores especificados.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-135">If values are specified, the requirement is met only if the user has both a claim of the correct type and one of the specified values.</span></span> <span data-ttu-id="1b2f2-136">Si usa el middleware de autenticación de portador JWT, todas las propiedades JWT estarán disponibles como notificaciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-136">If you're using the JWT bearer authentication middleware, all JWT properties will be available as user claims.</span></span>

<span data-ttu-id="1b2f2-137">La directiva más interesante que se muestra aquí es en el tercer método `AddPolicy`, ya que usa un requisito de autorización personalizada.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-137">The most interesting policy shown here is in the third `AddPolicy` method, because it uses a custom authorization requirement.</span></span> <span data-ttu-id="1b2f2-138">Mediante el uso de los requisitos de autorización personalizada, puede tener un gran control sobre cómo se realiza la autorización.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-138">By using custom authorization requirements, you can have a great deal of control over how authorization is performed.</span></span> <span data-ttu-id="1b2f2-139">Para que funcione, debe implementar estos tipos:</span><span class="sxs-lookup"><span data-stu-id="1b2f2-139">For this to work, you must implement these types:</span></span>

- <span data-ttu-id="1b2f2-140">Un tipo Requirements que deriva de <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> y que contiene campos en que se especifican los detalles del requisito.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-140">A Requirements type that derives from <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> and that contains fields specifying the details of the requirement.</span></span> <span data-ttu-id="1b2f2-141">En el ejemplo, se trata de un campo de edad para el tipo `MinimumAgeRequirement` de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-141">In the example, this is an age field for the sample `MinimumAgeRequirement` type.</span></span>

- <span data-ttu-id="1b2f2-142">Un controlador que implementa <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601>, donde T es el tipo de <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> que el controlador puede satisfacer.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-142">A handler that implements <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601>, where T is the type of <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> that the handler can satisfy.</span></span> <span data-ttu-id="1b2f2-143">El controlador debe implementar el método <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601.HandleRequirementAsync%2A>, que comprueba si un contexto especificado que contiene información sobre el usuario satisface el requisito.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-143">The handler must implement the <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601.HandleRequirementAsync%2A> method, which checks whether a specified context that contains information about the user satisfies the requirement.</span></span>

<span data-ttu-id="1b2f2-144">Si el usuario cumple el requisito, una llamada a `context.Succeed` indicará que el usuario está autorizado.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-144">If the user meets the requirement, a call to `context.Succeed` will indicate that the user is authorized.</span></span> <span data-ttu-id="1b2f2-145">Si hay varias maneras de que un usuario pueda satisfacer un requisito de autorización, se pueden crear varios controladores.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-145">If there are multiple ways that a user might satisfy an authorization requirement, multiple handlers can be created.</span></span>

<span data-ttu-id="1b2f2-146">Además de registrar los requisitos de directiva personalizada con llamadas `AddPolicy`, también debe registrar los controladores de requisito personalizado mediante la inserción de dependencias (`services.AddTransient<IAuthorizationHandler, MinimumAgeHandler>()`).</span><span class="sxs-lookup"><span data-stu-id="1b2f2-146">In addition to registering custom policy requirements with `AddPolicy` calls, you also need to register custom requirement handlers via Dependency Injection (`services.AddTransient<IAuthorizationHandler, MinimumAgeHandler>()`).</span></span>

<span data-ttu-id="1b2f2-147">Un ejemplo de un requisito de autorización personalizada y un controlador para comprobar la edad de un usuario (según una notificación `DateOfBirth`) está disponible en la [documentación de autorización](https://docs.asp.net/en/latest/security/authorization/policies.html) de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1b2f2-147">An example of a custom authorization requirement and handler for checking a user’s age (based on a `DateOfBirth` claim) is available in the ASP.NET Core [authorization documentation](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1b2f2-148">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="1b2f2-148">Additional resources</span></span>

- <span data-ttu-id="1b2f2-149">**ASP.NET Core Authentication (Autenticación en ASP.NET Core)**  </span><span class="sxs-lookup"><span data-stu-id="1b2f2-149">**ASP.NET Core Authentication** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- <span data-ttu-id="1b2f2-150">**ASP.NET Core Authorization (Autorización en ASP.NET Core)**  </span><span class="sxs-lookup"><span data-stu-id="1b2f2-150">**ASP.NET Core Authorization** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authorization/introduction](/aspnet/core/security/authorization/introduction)

- <span data-ttu-id="1b2f2-151">**Autorización basada en roles** </span><span class="sxs-lookup"><span data-stu-id="1b2f2-151">**Role-based Authorization** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authorization/roles](/aspnet/core/security/authorization/roles)

- <span data-ttu-id="1b2f2-152">**Custom Policy-Based Authorization (Autorización personalizada basada en directivas)**  </span><span class="sxs-lookup"><span data-stu-id="1b2f2-152">**Custom Policy-Based Authorization** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authorization/policies](/aspnet/core/security/authorization/policies)

>[!div class="step-by-step"]
><span data-ttu-id="1b2f2-153">[Anterior](index.md)
>[Siguiente](developer-app-secrets-storage.md)</span><span class="sxs-lookup"><span data-stu-id="1b2f2-153">[Previous](index.md)
[Next](developer-app-secrets-storage.md)</span></span>
