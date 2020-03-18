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
# <a name="about-authorization-in-net-microservices-and-web-applications"></a>Acerca de la autorización en microservicios y aplicaciones web de .NET

Después de la autenticación, las API web de ASP.NET Core deben autorizar el acceso. Este proceso permite que un servicio haga que las API estén disponibles para algunos usuarios autenticados, pero no para todos. La [autorización](/aspnet/core/security/authorization/introduction) se puede llevar a cabo según los roles de los usuarios o según una directiva personalizada, que podría incluir la inspección de notificaciones u otro tipo de heurística.

Restringir el acceso a una ruta de ASP.NET Core MVC es tan fácil como aplicar un atributo Authorize al método de acción (o a la clase de controlador si todas las acciones del controlador requieren autorización), como se muestra en el ejemplo siguiente:

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

De forma predeterminada, agregar un atributo Authorize sin parámetros limitará el acceso a los usuarios autenticados para ese controlador o esa acción. Para restringir aún más una API para que esté disponible solo para usuarios específicos, el atributo se puede expandir para especificar los roles o las directivas necesarios que los usuarios deben cumplir.

## <a name="implement-role-based-authorization"></a>Implementar la autorización basada en roles

ASP.NET Core Identity tiene un concepto de roles integrado. Además de los usuarios, ASP.NET Core Identity almacena información sobre los distintos roles que la aplicación usa y realiza un seguimiento de los usuarios que están asignados a cada rol. Estas asignaciones se pueden cambiar mediante programación con el tipo `RoleManager` que actualiza roles en almacenamiento persistente y el tipo `UserManager` que puede conceder o revocar roles de los usuarios.

Si está realizando la autenticación con tokens de portador JWT, el middleware de autenticación de portador JWT de ASP.NET Core rellenará los roles de un usuario según las notificaciones de rol que se encuentren en el token. Para limitar el acceso a una acción o un controlador de MVC a usuarios con roles específicos, puede incluir un parámetro Roles en la anotación Authorize (atributo), tal como se muestra en el fragmento de código siguiente:

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

En este ejemplo, solo los usuarios de los roles Administrator o PowerUser pueden tener acceso a las API del controlador ControlPanel (por ejemplo, para ejecutar la acción SetTime). La API ShutDown se restringe aún más para permitir el acceso únicamente a los usuarios con el rol Administrator.

Para pedir a un usuario que tenga varios roles, se usan varios atributos Authorize, como se muestra en este ejemplo:

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

En este ejemplo, para llamar a API1, un usuario debe:

- Tener el rol Administrator *o* PowerUser *y*

- Tener el rol RemoteEmployee *y*

- Satisfacer a un controlador personalizado para la autorización de CustomPolicy.

## <a name="implement-policy-based-authorization"></a>Implementación de la autorización basada en directivas

También se pueden escribir reglas de autorización personalizada con [directivas de autorización](https://docs.asp.net/en/latest/security/authorization/policies.html). En esta sección se proporciona información general. Para más información, consulte [ASP.NET Authorization Workshop](https://github.com/blowdart/AspNetAuthorizationWorkshop) (Taller de autorización de ASP.NET).

Las directivas de autorización personalizadas se registran en el método Startup.ConfigureServices mediante el método service.AddAuthorization. Este método toma a un delegado que configura un argumento AuthorizationOptions.

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

Como se muestra en el ejemplo, las directivas pueden asociarse con distintos tipos de requisitos. Una vez registradas las directivas, se pueden aplicar a una acción o a un controlador pasando el nombre de la directiva como el argumento de la directiva del atributo Authorize (por ejemplo, `[Authorize(Policy="EmployeesOnly")]`). Las directivas pueden tener varios requisitos, no solo uno (como se muestra en estos ejemplos).

En el ejemplo anterior, la primera llamada AddPolicy es simplemente una manera alternativa de autorizar por rol. Si `[Authorize(Policy="AdministratorsOnly")]` se aplica a una API, solo los usuarios del rol Administrator podrán tener acceso a ella.

La segunda llamada <xref:Microsoft.AspNetCore.Authorization.AuthorizationOptions.AddPolicy%2A> muestra una manera sencilla de pedir que una notificación concreta esté presente para el usuario. El método <xref:Microsoft.AspNetCore.Authorization.AuthorizationPolicyBuilder.RequireClaim%2A> también toma opcionalmente valores esperados para la notificación. Si se especifican valores, el requisito se cumple solo si el usuario tiene tanto una notificación del tipo correcto como uno de los valores especificados. Si usa el middleware de autenticación de portador JWT, todas las propiedades JWT estarán disponibles como notificaciones de usuario.

La directiva más interesante que se muestra aquí es en el tercer método `AddPolicy`, ya que usa un requisito de autorización personalizada. Mediante el uso de los requisitos de autorización personalizada, puede tener un gran control sobre cómo se realiza la autorización. Para que funcione, debe implementar estos tipos:

- Un tipo Requirements que deriva de <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> y que contiene campos en que se especifican los detalles del requisito. En el ejemplo, se trata de un campo de edad para el tipo `MinimumAgeRequirement` de ejemplo.

- Un controlador que implementa <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601>, donde T es el tipo de <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> que el controlador puede satisfacer. El controlador debe implementar el método <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601.HandleRequirementAsync%2A>, que comprueba si un contexto especificado que contiene información sobre el usuario satisface el requisito.

Si el usuario cumple el requisito, una llamada a `context.Succeed` indicará que el usuario está autorizado. Si hay varias maneras de que un usuario pueda satisfacer un requisito de autorización, se pueden crear varios controladores.

Además de registrar los requisitos de directiva personalizada con llamadas `AddPolicy`, también debe registrar los controladores de requisito personalizado mediante la inserción de dependencias (`services.AddTransient<IAuthorizationHandler, MinimumAgeHandler>()`).

Un ejemplo de un requisito de autorización personalizada y un controlador para comprobar la edad de un usuario (según una notificación `DateOfBirth`) está disponible en la [documentación de autorización](https://docs.asp.net/en/latest/security/authorization/policies.html) de ASP.NET Core.

## <a name="additional-resources"></a>Recursos adicionales

- **ASP.NET Core Authentication (Autenticación en ASP.NET Core)**  \
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- **ASP.NET Core Authorization (Autorización en ASP.NET Core)**  \
  [https://docs.microsoft.com/aspnet/core/security/authorization/introduction](/aspnet/core/security/authorization/introduction)

- **Autorización basada en roles** \
  [https://docs.microsoft.com/aspnet/core/security/authorization/roles](/aspnet/core/security/authorization/roles)

- **Custom Policy-Based Authorization (Autorización personalizada basada en directivas)**  \
  [https://docs.microsoft.com/aspnet/core/security/authorization/policies](/aspnet/core/security/authorization/policies)

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](developer-app-secrets-storage.md)
