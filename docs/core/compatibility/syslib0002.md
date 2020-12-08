---
title: Error SYSLIB0002
description: Obtenga información sobre la obsolescencia que genera el error en tiempo de compilación SYSLIB0002.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 36ecde3c52845a6594c4d04e167df48142038654
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437505"
---
# <a name="syslib0002-principalpermissionattribute-is-obsolete"></a><span data-ttu-id="de1e2-103">SYSLIB0002: PrincipalPermissionAttribute está obsoleto</span><span class="sxs-lookup"><span data-stu-id="de1e2-103">SYSLIB0002: PrincipalPermissionAttribute is obsolete</span></span>

<span data-ttu-id="de1e2-104">El constructor <xref:System.Security.Permissions.PrincipalPermissionAttribute> está obsoleto y genera un error en tiempo de compilación`SYSLIB0002` a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="de1e2-104">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> constructor is obsolete and produces compile-time error `SYSLIB0002`, starting in .NET 5.0.</span></span> <span data-ttu-id="de1e2-105">No se puede crear una instancia de este atributo ni aplicarlo a un método.</span><span class="sxs-lookup"><span data-stu-id="de1e2-105">You cannot instantiate this attribute or apply it to a method.</span></span>

<span data-ttu-id="de1e2-106">A diferencia de otras advertencias de obsolescencia, el error no se puede suprimir.</span><span class="sxs-lookup"><span data-stu-id="de1e2-106">Unlike other obsoletion warnings, you can't suppress the error.</span></span>

## <a name="workarounds"></a><span data-ttu-id="de1e2-107">Soluciones alternativas</span><span class="sxs-lookup"><span data-stu-id="de1e2-107">Workarounds</span></span>

- <span data-ttu-id="de1e2-108">Si va a aplicar el atributo a un método de acción de MVC de ASP.NET:</span><span class="sxs-lookup"><span data-stu-id="de1e2-108">If you're applying the attribute to an ASP.NET MVC action method:</span></span>

  <span data-ttu-id="de1e2-109">Considere la posibilidad de usar la infraestructura de autorización integrada de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="de1e2-109">Consider using ASP.NET's built-in authorization infrastructure.</span></span> <span data-ttu-id="de1e2-110">En el código siguiente se muestra cómo anotar un controlador con un atributo <xref:System.Web.Mvc.AuthorizeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="de1e2-110">The following code demonstrates how to annotate a controller with an <xref:System.Web.Mvc.AuthorizeAttribute> attribute.</span></span> <span data-ttu-id="de1e2-111">El entorno de ejecución de ASP.NET autoriza al usuario antes de realizar la acción.</span><span class="sxs-lookup"><span data-stu-id="de1e2-111">The ASP.NET runtime will authorize the user before performing the action.</span></span>

  ```csharp
  using Microsoft.AspNetCore.Authorization;

  namespace MySampleApp
  {
      [Authorize(Roles = "Administrator")]
      public class AdministrationController : Controller
      {
          public ActionResult MyAction()
          {
              // This code won't run unless the current user
              // is in the 'Administrator' role.
          }
      }
  }
  ```

  <span data-ttu-id="de1e2-112">Para obtener más información, vea [Autorización basada en roles en ASP.NET Core](/aspnet/core/security/authorization/roles) e [Introducción a la autorización en ASP.NET Core](/aspnet/core/security/authorization/introduction).</span><span class="sxs-lookup"><span data-stu-id="de1e2-112">For more information, see [Role-based authorization in ASP.NET Core](/aspnet/core/security/authorization/roles) and [Introduction to authorization in ASP.NET Core](/aspnet/core/security/authorization/introduction).</span></span>

- <span data-ttu-id="de1e2-113">Si va a aplicar el atributo a código de biblioteca fuera del contexto de una aplicación web:</span><span class="sxs-lookup"><span data-stu-id="de1e2-113">If you're applying the attribute to library code outside the context of a web app:</span></span>

  <span data-ttu-id="de1e2-114">Realice las comprobaciones manualmente al principio del método mediante una llamada al método <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="de1e2-114">Perform the checks manually at the beginning of your method by calling the <xref:System.Security.Principal.IPrincipal.IsInRole(System.String)?displayProperty=nameWithType> method.</span></span>

  ```csharp
  using System.Threading;

  void DoSomething()
  {
      if (Thread.CurrentPrincipal == null
          || !Thread.CurrentPrincipal.IsInRole("Administrators"))
      {
          throw new Exception("User is anonymous or isn't an admin.");
      }

      // Code that should run only when user is an administrator.
  }
  ```

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a><span data-ttu-id="de1e2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="de1e2-115">See also</span></span>

- [<span data-ttu-id="de1e2-116">PrincipalPermissionAttribute está obsoleto como error</span><span class="sxs-lookup"><span data-stu-id="de1e2-116">PrincipalPermissionAttribute is obsolete as error</span></span>](core-libraries/5.0/principalpermissionattribute-obsolete.md)
