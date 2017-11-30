---
title: "Acerca de la autorización en .NET microservicios y las aplicaciones web"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Acerca de la autorización en .NET microservicios y las aplicaciones web"
keywords: Docker, microservicios, ASP.NET, contenedor
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 51adda4f5bdb28154f17b9a988ee2d887bf1d461
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="about-authorization-in-net-microservices-and-web-applications"></a><span data-ttu-id="657b1-104">Acerca de la autorización en .NET microservicios y las aplicaciones web</span><span class="sxs-lookup"><span data-stu-id="657b1-104">About authorization in .NET microservices and web applications</span></span>

<span data-ttu-id="657b1-105">Después de la autenticación, las API Web de ASP.NET Core necesario autorizar el acceso.</span><span class="sxs-lookup"><span data-stu-id="657b1-105">After authentication, ASP.NET Core Web APIs need to authorize access.</span></span> <span data-ttu-id="657b1-106">Este proceso permite que las API de un servicio disponible para algunos usuarios autenticados, pero no a todos.</span><span class="sxs-lookup"><span data-stu-id="657b1-106">This process allows a service to make APIs available to some authenticated users, but not to all.</span></span> <span data-ttu-id="657b1-107">[Autorización](https://docs.microsoft.com/aspnet/core/security/authorization/introduction) puede lleva a cabo según los roles de usuario o según una directiva personalizada, lo que puede incluir inspeccionando notificaciones u otra heurística.</span><span class="sxs-lookup"><span data-stu-id="657b1-107">[Authorization](https://docs.microsoft.com/aspnet/core/security/authorization/introduction) can be done based on users’ roles or based on custom policy, which might include inspecting claims or other heuristics.</span></span>

<span data-ttu-id="657b1-108">Restringir el acceso a una ruta principal de ASP.NET MVC es tan fácil como aplicar un atributo de autorizar al método de acción (o clase del controlador si las acciones de todos los del controlador requieren autorización), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="657b1-108">Restricting access to an ASP.NET Core MVC route is as easy as applying an Authorize attribute to the action method (or to the controller’s class if all the controller’s actions require authorization), as shown in following example:</span></span>

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

<span data-ttu-id="657b1-109">De forma predeterminada, se agrega un atributo Authorize sin parámetros limitará el acceso a los usuarios autenticados para esa acción o controlador.</span><span class="sxs-lookup"><span data-stu-id="657b1-109">By default, adding an Authorize attribute without parameters will limit access to authenticated users for that controller or action.</span></span> <span data-ttu-id="657b1-110">Para restringir aún más una API para que esté disponible sólo usuarios específicos, se puede expandir el atributo para especificar los roles necesarios o directivas que los usuarios deben cumplir.</span><span class="sxs-lookup"><span data-stu-id="657b1-110">To further restrict an API to be available for only specific users, the attribute can be expanded to specify required roles or policies that users must satisfy.</span></span>

## <a name="implementing-role-based-authorization"></a><span data-ttu-id="657b1-111">Implementar la autorización basada en roles</span><span class="sxs-lookup"><span data-stu-id="657b1-111">Implementing role-based authorization</span></span>

<span data-ttu-id="657b1-112">Identidad de ASP.NET Core tiene un concepto de roles integrado.</span><span class="sxs-lookup"><span data-stu-id="657b1-112">ASP.NET Core Identity has a built-in concept of roles.</span></span> <span data-ttu-id="657b1-113">Además de los usuarios, ASP.NET Core Identity almacena información sobre los distintos roles utilizados por la aplicación y realiza un seguimiento de los usuarios que están asignados a los roles.</span><span class="sxs-lookup"><span data-stu-id="657b1-113">In addition to users, ASP.NET Core Identity stores information about different roles used by the application and keeps track of which users are assigned to which roles.</span></span> <span data-ttu-id="657b1-114">Estas asignaciones se pueden cambiar mediante programación con el tipo de RoleManager (que actualiza los roles en el almacenamiento persistente) y el tipo de UserManager (que puede asignar o quitar la asignación de usuarios de roles).</span><span class="sxs-lookup"><span data-stu-id="657b1-114">These assignments can be changed programmatically with the RoleManager type (which updates roles in persisted storage) and UserManager type (which can assign or unassign users from roles).</span></span>

<span data-ttu-id="657b1-115">Si está realizando la autenticación con tokens de portador JWT, el middleware de autenticación de portador JWT de núcleo de ASP.NET rellenará los roles de usuario basados en notificaciones de rol que se encuentra en el token.</span><span class="sxs-lookup"><span data-stu-id="657b1-115">If you are authenticating with JWT bearer tokens, the ASP.NET Core JWT bearer authentication middleware will populate a user’s roles based on role claims found in the token.</span></span> <span data-ttu-id="657b1-116">Para limitar el acceso a una acción de MVC o el controlador para usuarios con roles específicos, puede incluir un parámetro de Roles en el encabezado de autorización, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="657b1-116">To limit access to an MVC action or controller to users in specific roles, you can include a Roles parameter in the Authorize header, as shown in the following example:</span></span>

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

<span data-ttu-id="657b1-117">En este ejemplo, solo los usuarios de los roles de administrador o PowerUser pueden tener acceso a las API en el controlador ControlPanel (por ejemplo, para ejecutar la acción SetTime).</span><span class="sxs-lookup"><span data-stu-id="657b1-117">In this example, only users in the Administrator or PowerUser roles can access APIs in the ControlPanel controller (such as executing the SetTime action).</span></span> <span data-ttu-id="657b1-118">La API de cierre se restringe aún más para permitir el acceso únicamente a los usuarios de la función de administrador.</span><span class="sxs-lookup"><span data-stu-id="657b1-118">The ShutDown API is further restricted to allow access only to users in the Administrator role.</span></span>

<span data-ttu-id="657b1-119">Para requerir que un usuario pertenecer a varios roles, utilice varios atributos de autorizar, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="657b1-119">To require a user be in multiple roles, you use multiple Authorize attributes, as shown in the following example:</span></span>

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

<span data-ttu-id="657b1-120">En este ejemplo, para llamar a API1, un usuario debe:</span><span class="sxs-lookup"><span data-stu-id="657b1-120">In this example, to call API1, a user must:</span></span>

-   <span data-ttu-id="657b1-121">En el administrador *o* PowerUser rol, *y*</span><span class="sxs-lookup"><span data-stu-id="657b1-121">Be in the Adminstrator *or* PowerUser role, *and*</span></span>

-   <span data-ttu-id="657b1-122">Estar en el rol RemoteEmployee, *y*</span><span class="sxs-lookup"><span data-stu-id="657b1-122">Be in the RemoteEmployee role, *and*</span></span>

-   <span data-ttu-id="657b1-123">Satisfacer a un controlador personalizado para la autorización de CustomPolicy.</span><span class="sxs-lookup"><span data-stu-id="657b1-123">Satisfy a custom handler for CustomPolicy authorization.</span></span>

## <a name="implementing-policy-based-authorization"></a><span data-ttu-id="657b1-124">Implementar la autorización basada en directivas</span><span class="sxs-lookup"><span data-stu-id="657b1-124">Implementing policy-based authorization</span></span>

<span data-ttu-id="657b1-125">También se pueden escribir reglas de autorización personalizada con [directivas de autorización](https://docs.asp.net/en/latest/security/authorization/policies.html).</span><span class="sxs-lookup"><span data-stu-id="657b1-125">Custom authorization rules can also be written using [authorization policies](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span> <span data-ttu-id="657b1-126">En esta sección se proporciona información general.</span><span class="sxs-lookup"><span data-stu-id="657b1-126">In this section we provide an overview.</span></span> <span data-ttu-id="657b1-127">Más detalle está disponible en online [taller de autorización de ASP.NET](https://github.com/blowdart/AspNetAuthorizationWorkshop).</span><span class="sxs-lookup"><span data-stu-id="657b1-127">More detail is available in the online [ASP.NET Authorization Workshop](https://github.com/blowdart/AspNetAuthorizationWorkshop).</span></span>

<span data-ttu-id="657b1-128">Directivas de autorización personalizadas se registran en el método Startup.ConfigureServices mediante el servicio. Método AddAuthorization.</span><span class="sxs-lookup"><span data-stu-id="657b1-128">Custom authorization policies are registered in the Startup.ConfigureServices method using the service.AddAuthorization method.</span></span> <span data-ttu-id="657b1-129">Este método toma a un delegado que configura un argumento AuthorizationOptions.</span><span class="sxs-lookup"><span data-stu-id="657b1-129">This method takes a delegate that configures an AuthorizationOptions argument.</span></span>

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

<span data-ttu-id="657b1-130">Como se muestra en el ejemplo, las directivas pueden asociarse con distintos tipos de requisitos.</span><span class="sxs-lookup"><span data-stu-id="657b1-130">As shown in the example, policies can be associated with different types of requirements.</span></span> <span data-ttu-id="657b1-131">Después de que se registran las directivas, se pueden aplicar a una acción o controlador pasando el nombre de la directiva como el argumento de la directiva del atributo Authorize (por ejemplo, \[Authorize(Policy="EmployeesOnly")\]) pueden tener directivas varios requisitos, no solo uno (como se muestra en estos ejemplos).</span><span class="sxs-lookup"><span data-stu-id="657b1-131">After the policies are registered, they can be applied to an action or controller by passing the policy’s name as the Policy argument of the Authorize attribute (for example, \[Authorize(Policy="EmployeesOnly")\]) Policies can have multiple requirements, not just one (as shown in these examples).</span></span>

<span data-ttu-id="657b1-132">En el ejemplo anterior, la primera llamada AddPolicy es simplemente una manera alternativa de la autorización por rol.</span><span class="sxs-lookup"><span data-stu-id="657b1-132">In the previous example, the first AddPolicy call is just an alternative way of authorizing by role.</span></span> <span data-ttu-id="657b1-133">Si \[Authorize(Policy="AdministratorsOnly")\] se aplica a una API, solo los usuarios del rol de administrador podrán tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="657b1-133">If \[Authorize(Policy="AdministratorsOnly")\] is applied to an API, only users in the Administrator role will be able to access it.</span></span>

<span data-ttu-id="657b1-134">La segunda llamada AddPolicy muestra una manera sencilla de requieren que una notificación concreta debe estar presente para el usuario.</span><span class="sxs-lookup"><span data-stu-id="657b1-134">The second AddPolicy call demonstrates an easy way to require that a particular claim should be present for the user.</span></span> <span data-ttu-id="657b1-135">El método RequireClaim también opcionalmente toma los valores esperados para la notificación.</span><span class="sxs-lookup"><span data-stu-id="657b1-135">The RequireClaim method also optionally takes expected values for the claim.</span></span> <span data-ttu-id="657b1-136">Si se especifican valores, el requisito se cumple sólo si el usuario tiene tanto una notificación del tipo correcto como uno de los valores especificados.</span><span class="sxs-lookup"><span data-stu-id="657b1-136">If values are specified, the requirement is met only if the user has both a claim of the correct type and one of the specified values.</span></span> <span data-ttu-id="657b1-137">Si usas el middleware de autenticación de portador JWT, todas las propiedades JWT estarán disponibles como notificaciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="657b1-137">If you are using the JWT bearer authentication middleware, all JWT properties will be available as user claims.</span></span>

<span data-ttu-id="657b1-138">La directiva más interesante que se muestra a continuación es en el tercer método AddPolicy, ya que usa un requisito de autorización personalizada.</span><span class="sxs-lookup"><span data-stu-id="657b1-138">The most interesting policy shown here is in the third AddPolicy method, because it uses a custom authorization requirement.</span></span> <span data-ttu-id="657b1-139">Mediante el uso de los requisitos de autorización personalizada, puede tener un gran control sobre cómo se realiza la autorización.</span><span class="sxs-lookup"><span data-stu-id="657b1-139">By using custom authorization requirements, you can have a great deal of control over how authorization is performed.</span></span> <span data-ttu-id="657b1-140">Para que funcione, debe implementar estos tipos:</span><span class="sxs-lookup"><span data-stu-id="657b1-140">For this to work, you must implement these types:</span></span>

-   <span data-ttu-id="657b1-141">Un tipo que deriva de IAuthorizationRequirement y que contiene campos que especifiquen los detalles del requisito de requisitos.</span><span class="sxs-lookup"><span data-stu-id="657b1-141">A Requirements type that derives from IAuthorizationRequirement and that contains fields specifying the details of the requirement.</span></span> <span data-ttu-id="657b1-142">En el ejemplo, se trata de un campo de antigüedad para el tipo de MinimumAgeRequirement de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="657b1-142">In the example, this is an age field for the sample MinimumAgeRequirement type.</span></span>

-   <span data-ttu-id="657b1-143">Un controlador que implementa AuthorizationHandler&lt;T&gt;, donde T es el tipo de IAuthorizationRequirement que puede satisfacer el controlador.</span><span class="sxs-lookup"><span data-stu-id="657b1-143">A handler that implements AuthorizationHandler&lt;T&gt;, where T is the type of IAuthorizationRequirement that the handler can satisfy.</span></span> <span data-ttu-id="657b1-144">El controlador debe implementar el método HandleRequirementAsync, que comprueba si un contexto especificado que contiene información sobre el usuario satisface el requisito.</span><span class="sxs-lookup"><span data-stu-id="657b1-144">The handler must implement the HandleRequirementAsync method, which checks whether a specified context that contains information about the user satisfies the requirement.</span></span>

<span data-ttu-id="657b1-145">Si el usuario cumple los requisitos, una llamada al contexto. Correctamente will indican que el usuario está autorizado.</span><span class="sxs-lookup"><span data-stu-id="657b1-145">If the user meets the requirement, a call to context.Succeed will indicate that the user is authorized.</span></span> <span data-ttu-id="657b1-146">Si hay varias maneras de que un usuario podría satisfacer un requisito de autorización, es pueden crear varios controladores.</span><span class="sxs-lookup"><span data-stu-id="657b1-146">If there are multiple ways that a user might satisfy an authorization requirement, multiple handlers can be created.</span></span>

<span data-ttu-id="657b1-147">Además de registrar los requisitos de directiva personalizada con llamadas AddPolicy, también tenga que registrar controladores de requisito personalizado mediante la inserción de dependencias (services. AddTransient&lt;IAuthorizationHandler, MinimumAgeHandler&gt;()).</span><span class="sxs-lookup"><span data-stu-id="657b1-147">In addition to registering custom policy requirements with AddPolicy calls, you also need to register custom requirement handlers via Dependency Injection (services.AddTransient&lt;IAuthorizationHandler, MinimumAgeHandler&gt;()).</span></span>

<span data-ttu-id="657b1-148">Un ejemplo de un requisito de autorización personalizada y un controlador para la comprobación de edad de un usuario (según una notificación DateOfBirth) está disponible en el núcleo de ASP.NET [documentación de autorización](https://docs.asp.net/en/latest/security/authorization/policies.html).</span><span class="sxs-lookup"><span data-stu-id="657b1-148">An example of a custom authorization requirement and handler for checking a user’s age (based on a DateOfBirth claim) is available in the ASP.NET Core [authorization documentation](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="657b1-149">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="657b1-149">Additional resources</span></span>

-   <span data-ttu-id="657b1-150">**Autenticación de ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span><span class="sxs-lookup"><span data-stu-id="657b1-150">**ASP.NET Core Authentication**
[*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span></span>

-   <span data-ttu-id="657b1-151">**Autorización de ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)</span><span class="sxs-lookup"><span data-stu-id="657b1-151">**ASP.NET Core Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)</span></span>

-   <span data-ttu-id="657b1-152">**Autorización basada en funciones**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)</span><span class="sxs-lookup"><span data-stu-id="657b1-152">**Role based Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)</span></span>

-   <span data-ttu-id="657b1-153">**Autorización personalizada basada en directivas**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)</span><span class="sxs-lookup"><span data-stu-id="657b1-153">**Custom Policy-Based Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="657b1-154">[Anterior] (index.md) [siguiente] (desarrollador de aplicaciones-secretos storage.md)</span><span class="sxs-lookup"><span data-stu-id="657b1-154">[Previous] (index.md) [Next] (developer-app-secrets-storage.md)</span></span>
