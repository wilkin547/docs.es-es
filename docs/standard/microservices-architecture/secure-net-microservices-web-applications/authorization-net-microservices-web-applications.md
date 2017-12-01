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
# <a name="about-authorization-in-net-microservices-and-web-applications"></a>Acerca de la autorización en .NET microservicios y las aplicaciones web

Después de la autenticación, las API Web de ASP.NET Core necesario autorizar el acceso. Este proceso permite que las API de un servicio disponible para algunos usuarios autenticados, pero no a todos. [Autorización](https://docs.microsoft.com/aspnet/core/security/authorization/introduction) puede lleva a cabo según los roles de usuario o según una directiva personalizada, lo que puede incluir inspeccionando notificaciones u otra heurística.

Restringir el acceso a una ruta principal de ASP.NET MVC es tan fácil como aplicar un atributo de autorizar al método de acción (o clase del controlador si las acciones de todos los del controlador requieren autorización), como se muestra en el ejemplo siguiente:

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

De forma predeterminada, se agrega un atributo Authorize sin parámetros limitará el acceso a los usuarios autenticados para esa acción o controlador. Para restringir aún más una API para que esté disponible sólo usuarios específicos, se puede expandir el atributo para especificar los roles necesarios o directivas que los usuarios deben cumplir.

## <a name="implementing-role-based-authorization"></a>Implementar la autorización basada en roles

Identidad de ASP.NET Core tiene un concepto de roles integrado. Además de los usuarios, ASP.NET Core Identity almacena información sobre los distintos roles utilizados por la aplicación y realiza un seguimiento de los usuarios que están asignados a los roles. Estas asignaciones se pueden cambiar mediante programación con el tipo de RoleManager (que actualiza los roles en el almacenamiento persistente) y el tipo de UserManager (que puede asignar o quitar la asignación de usuarios de roles).

Si está realizando la autenticación con tokens de portador JWT, el middleware de autenticación de portador JWT de núcleo de ASP.NET rellenará los roles de usuario basados en notificaciones de rol que se encuentra en el token. Para limitar el acceso a una acción de MVC o el controlador para usuarios con roles específicos, puede incluir un parámetro de Roles en el encabezado de autorización, tal como se muestra en el ejemplo siguiente:

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

En este ejemplo, solo los usuarios de los roles de administrador o PowerUser pueden tener acceso a las API en el controlador ControlPanel (por ejemplo, para ejecutar la acción SetTime). La API de cierre se restringe aún más para permitir el acceso únicamente a los usuarios de la función de administrador.

Para requerir que un usuario pertenecer a varios roles, utilice varios atributos de autorizar, tal como se muestra en el ejemplo siguiente:

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

En este ejemplo, para llamar a API1, un usuario debe:

-   En el administrador *o* PowerUser rol, *y*

-   Estar en el rol RemoteEmployee, *y*

-   Satisfacer a un controlador personalizado para la autorización de CustomPolicy.

## <a name="implementing-policy-based-authorization"></a>Implementar la autorización basada en directivas

También se pueden escribir reglas de autorización personalizada con [directivas de autorización](https://docs.asp.net/en/latest/security/authorization/policies.html). En esta sección se proporciona información general. Más detalle está disponible en online [taller de autorización de ASP.NET](https://github.com/blowdart/AspNetAuthorizationWorkshop).

Directivas de autorización personalizadas se registran en el método Startup.ConfigureServices mediante el servicio. Método AddAuthorization. Este método toma a un delegado que configura un argumento AuthorizationOptions.

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

Como se muestra en el ejemplo, las directivas pueden asociarse con distintos tipos de requisitos. Después de que se registran las directivas, se pueden aplicar a una acción o controlador pasando el nombre de la directiva como el argumento de la directiva del atributo Authorize (por ejemplo, \[Authorize(Policy="EmployeesOnly")\]) pueden tener directivas varios requisitos, no solo uno (como se muestra en estos ejemplos).

En el ejemplo anterior, la primera llamada AddPolicy es simplemente una manera alternativa de la autorización por rol. Si \[Authorize(Policy="AdministratorsOnly")\] se aplica a una API, solo los usuarios del rol de administrador podrán tener acceso a él.

La segunda llamada AddPolicy muestra una manera sencilla de requieren que una notificación concreta debe estar presente para el usuario. El método RequireClaim también opcionalmente toma los valores esperados para la notificación. Si se especifican valores, el requisito se cumple sólo si el usuario tiene tanto una notificación del tipo correcto como uno de los valores especificados. Si usas el middleware de autenticación de portador JWT, todas las propiedades JWT estarán disponibles como notificaciones de usuario.

La directiva más interesante que se muestra a continuación es en el tercer método AddPolicy, ya que usa un requisito de autorización personalizada. Mediante el uso de los requisitos de autorización personalizada, puede tener un gran control sobre cómo se realiza la autorización. Para que funcione, debe implementar estos tipos:

-   Un tipo que deriva de IAuthorizationRequirement y que contiene campos que especifiquen los detalles del requisito de requisitos. En el ejemplo, se trata de un campo de antigüedad para el tipo de MinimumAgeRequirement de ejemplo.

-   Un controlador que implementa AuthorizationHandler&lt;T&gt;, donde T es el tipo de IAuthorizationRequirement que puede satisfacer el controlador. El controlador debe implementar el método HandleRequirementAsync, que comprueba si un contexto especificado que contiene información sobre el usuario satisface el requisito.

Si el usuario cumple los requisitos, una llamada al contexto. Correctamente will indican que el usuario está autorizado. Si hay varias maneras de que un usuario podría satisfacer un requisito de autorización, es pueden crear varios controladores.

Además de registrar los requisitos de directiva personalizada con llamadas AddPolicy, también tenga que registrar controladores de requisito personalizado mediante la inserción de dependencias (services. AddTransient&lt;IAuthorizationHandler, MinimumAgeHandler&gt;()).

Un ejemplo de un requisito de autorización personalizada y un controlador para la comprobación de edad de un usuario (según una notificación DateOfBirth) está disponible en el núcleo de ASP.NET [documentación de autorización](https://docs.asp.net/en/latest/security/authorization/policies.html).

## <a name="additional-resources"></a>Recursos adicionales

-   **Autenticación de ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)

-   **Autorización de ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)

-   **Autorización basada en funciones**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)

-   **Autorización personalizada basada en directivas**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)




>[!div class="step-by-step"]
[Anterior] (index.md) [siguiente] (desarrollador de aplicaciones-secretos storage.md)
